+++
author = "Elie Gavoty"
title = 'Une méthode de hack : débordement de tampon sur la pile et injection d’un shellcode'
weight = 87
subtitle =   'Les hackers face à l’abstraction informatique et une omniprésente disparition du technique.'
date = "2020-07-05"
description = "Les hackers face à l’abstraction informatique et une omniprésente disparition du technique. Mémoire de recherche en histoire et philosophie des science."
tags = [
	"reprogrammer-des-boites-noires",
  "hacking",
  "STS/philotech",
]
+++

Nous allons maintenant présenter de façon assez détaillée une technique
classique de hack en informatique : le débordement de tampon sur la
pile. Cette technique combine un détournement du flux d’exécution d’un
programme ciblé avec l’injection d’un shellcode en assembleur : il
s’agit d’une méthode permettant en quelque sorte de reprogrammer
localement le système, qui consiste dans notre cas en un ordinateur
personnel utilisant un système d’exploitation GNU/Linux[^146].
L’objectif dans notre cas sera de façon assez classique de « rooter » la
machine c’est-à-dire d’obtenir un accès en tant qu’utilisateur *root*
qui permet d’effectuer toutes les actions possibles sur le système sans
restriction.

Pour désigner ce type de technique, on parle généralement en anglais
d’*exploit*. L’acteur d’une telle pratique est habituellement décrit
soit comme un hacker soit comme un cracker, comme un attaquant ou comme
un pirate. Toutes ces appellations sont fortement connotées. Cracker
semble généralement participer comme l’avons évoqué dans la partie I.3,
d’une stratégie de discrédit moral à l’encontre de diverses figures de
« mésusagers » (misuser). Pirate implique une illégalité du
détournement, attaquant implique une forme d’agressivité : or le fait
d’utiliser une méthode d’injection mémoire n’implique en soit ni
illégalité ni agressivité : imaginons par exemple qu’une telle méthode
soit utilisée par le propriétaire d’un appareil informatique verrouillé
par le constructeur (ce qui est très courant) pour pouvoir supprimer ce
verrouillage. Dans ce cas, l’action apparaît comme un acte légitime et
éthique. Par ailleurs, être hacker implique traditionnellement une forme
d’astuce et de maîtrise technique : l’usage d’une méthode originale ou
l’adaptation d’une technique existante à un contexte nouveau. Nous avons
vu que quelqu’un qui exploiterait une faille dans un système en
utilisant un logiciel automatique, par exemple déverrouillant son
téléphone grâce à un « rootkit » quelconque, ne peut généralement pas
prétendre à la qualité de hacker. Nous utiliserons dès lors
volontairement le terme neutre bien qu’inhabituel d’« exploitant » pour
désigner l’acteur d’un tel « exploit ».

Comme nous le verrons, cette technique illustre un jeu particulier avec
l’abstraction informatique. Les principaux mécanismes d’abstraction
impliqués dans notre exemple du débordement de tampon avec injection en
mémoire d’un shellcode sont d’une part la compilation qui implique un
rapport entre un programme écrit en langage C et sa traduction en terme
d’opérations en langage machine, ainsi que d’autre part le rapport entre
le programme exécuté (OS) et la façon dont le système d’exploitation
organise la mémoire virtuelle. Il s’agira dès lors de faire un détour
par une mise en contexte informatique pour détailler comment fonctionne
l’abstraction liée à la compilation d’un programme et notamment en quoi
elle consiste en un masquage du flux d’exécution du programme au niveau
du processeur. Ces précisions seront utiles pour analyser dans un second
temps notre méthode d’exploitation.

### <span id="anchor-45"></span>Compilation et flux d’exécution au niveau du processeur

Comme nous l’avons évoqué, la **compilation** consiste en une opération
de traduction automatique d’un programme écrit dans un langage de
départ, un **code source**, en un programme équivalent écrit dans un
langage cible.

Prenons l’exemple d’un programme volontairement simpliste en langage C
et le résultat de sa compilation (présenté page suivante) [^147].

#### Programme en langage C

```c
#include <stdio.h>

int main() {
    int i;
    for(i=0; i < 10; i++) {
        puts("Hello, world!\\n");
    }
    return 0;
}
```

Lorsqu’on exécute ce programme d’exemple, il affiche dix fois « Hello,
World! ». Décrivons rapidement sa logique :

1.  L’instruction `int main() {` déclare l’entrée dans le programme :
    en langage C, le code est découpé en blocs imbriqués qui sont
    délimités par des accolades, ici `main` désigne le programme
    principal dont le bloc se termine ici à la dernière ligne de code.
2.  `int i` déclare un nombre entier (integer) destiné à compter
    le nombre d’affichages de `Hello World!`.
3.  L’instruction `for (i=0; i < 10; i++) {` déclare l’ouverture
    d’une **boucle** c’est-à-dire d’un un ensemble d’instructions qui
    sera répété plusieurs fois. Le contrôle du nombre d’exécution est
    contrôlé grâce à un test effectué à chaque tour de boucle sur la
    valeur de i : le bloc est exécuté tant que le compteur i, augmenté
    de 1 à chaque tour, est inférieur à la valeur 10.
4.  l’instruction d’affichage `puts`, envoie littéralement une
    suite de caractères `(H,e,l,l,o, ,W,o,r,l,d,!)` vers la `sortie
    standard`, c’est-à-dire l’affiche dans un terminal.

Le langage C peut sembler peu intuitif à une personne non familière avec
la pratique de la programmation. En effet, bien qu’il soit dans notre
exemple le langage source, c’est-à-dire le plus abstrait, il est en
réalité un langage qui s’éloigne peu[^148] du fonctionnement
élémentaire, matériel et logique de l’ordinateur. Ceci explique
notamment pourquoi l’action de répéter dix fois une instruction est
décrite par une boucle utilisant un compteur *i* explicitement déclaré
`for(i=0; i < 10; i++) {`, littéralement « commencer avec
le compteur à 0 ; répéter le bloc suivant si le compteur est inférieur à
dix ; augmenter le compteur à la fin ». On entrevoit ici le
principe du flux d’exécution : le processeur de l’ordinateur est
incapable de rassembler en une seule opération l’exécution de dix
instructions d’affichage. Il les exécute l’une après l’autre,
vérifiant au fur et à mesure que le compteur n’ait pas dépassé la
valeur 10, ce qui constitue un flux d’opération.

Intéressons-nous maintenant au programme compilé,
c’est-à-dire à la traduction de ce programme C en instructions
machine qui rend directement « visible » ce fonctionnement
séquentiel de l’exécution. Situé, un niveau d’abstraction en deçà du
langage C, il est codé comme une suite de nombres correspondant
directement à des opérations disponibles au niveau du processeur.


#### Le résultat[^189] de la compilation du programme C :
```
8048374:   55                        push ebp
8048375:   89 e5                     mov ebp,esp
8048377:   83 ec 08                  sub esp,0x8
804837a:   83 e4 f0                  and esp,0xfffffff0
804837d:   b8 00 00 00 00            mov eax,0x0
8048382:   29 c4                     sub esp,eax
8048384:   c7 45 fc 00 00 00 00      mov DWORD PTR [ebp-4],0x0
804838b:   83 7d fc 09               cmp DWORD PTR [ebp-4],0x9
804838f:   7e 02                     jle 8048393 <main+0x1f>
8048391:   eb 13                     jmp 80483a6 <main+0x32>
8048393:   c7 04 24 84 84 04 08      mov DWORD PTR [esp],0x8048484
804839a:   e8 01 ff ff ff            call 80482a0 <printf@plt>
804839f:   8d 45 fc                  lea eax,[ebp-4]
80483a2:   ff 00                     inc DWORD PTR [eax]
80483a4:   eb e5                     jmp 804838b <main+0x17>
80483a6:   c9                        leave
80483a7:   c3                        ret
80483a8:   90                        nop
80483a9:   90                        nop
80483aa:   90                        nop
```


[^189]: Ce texte est exprimé à gauche en langage machine (nombres en base 16) et à droite en langage d’assemblage. Les nombres de gauche ne
font pas partie du code : ce sont en quelque sorte des numéros de ligne
qui précisent l’emplacement où est enregistré le programme dans la
mémoire (on parle d’adresse mémoire d’une instruction).

</br>

Ce deuxième listing de code contient en réalité deux fois le code du
programme. Sur la partie gauche, on découvre le véritable programme
compilé sous forme d’instructions en langage machine, codées sous la
forme de nombres[^149]. Au niveau du processeur, ces nombres sont ceux
qui sont chargés dans des zones mémoires appelées registres[^150] et qui
déclenchent l’une ou l’autre opération élémentaire de calcul. Chaque
ligne correspond à une instruction exécutée en un battement d’horloge du
processeur c’est-à-dire, pour les ordinateurs actuels, plusieurs
millions de fois par seconde. Le nombre de gauche désigne généralement
le type d’instruction machine, alors que les nombres de droite sont les
paramètres de cette instruction, par exemple les données concernées par
le calcul.

Sur la partie droite, les mêmes instructions sont écrites en **langage d’assemblage** ou **assembleur.**
Ce langage d’assemblage est un codage
direct (bijectif) des instructions machines (les nombres de la partie gauche) qui vise à améliorer la
lisibilité du code pour l’humain. Ainsi, il n’introduit pas de
modification irréversible de la structure logique du code[^151]
c’est-à-dire notamment qu’il conserve la forme du flux d’exécution.
L’équivalence directe est apparente dans la mise en parallèle des deux
codes.

Maintenant, pour visualiser comment se déroule l’exécution d’un tel code
machine il s’agit d’imaginer que chaque instruction (ligne) est chargée
dans une case de la mémore. Le processeur *pointe* sur chacune de ces
cases mémoires pour les exécuter successivement (ici de haut en bas), à
moins de rencontrer une instruction de saut[^152] qui le fait *pointer*
vers une autre case arbitraire de la mémoire. C’est la succession de ces
déplacements qu’on désigne par l’expression de flux d’exécution.

Au contraire de l’assembleur, le langage C s’éloigne quelque peu de ce
flux d’exécution en introduisant plusieurs abstractions, notamment les
concepts de **boucle**, de **variable** et de **fonction**.
Intéressons-nous à la façon dont la boucle `for(i=0; i < 10; i++) {`
est traduite au niveau des **instructions du programme compilé**[^255] :

1. (a) `804838b : cmp DWORD PTR [ebp-4],0x9`
2. (b) `804838f : jle 8048393`
3. (c) `8048391 : jmp 80483a6`
4. (d) Les instructions `8048393` à `80483a2` correspondent au contenu de la boucle.
5. (e) `80483a4 : jmp 804838`

[^255]: **Schéma du flux d'exécution**
    {{<figure
    src="../../images/fluxExec.jpg"
    caption="Sur ce schéma correspondant à la suite d’instruction, nous avons matérialisé le flux d’exécution par des flèches. En bleu le branchement conditionnel qui opère la sortie de la boucle si le compteur est supérieur ou égal à dix, en rouge la portion de code circulaire qui permet la répétition du traitement, en jaune la sortie de la boucle."
    width=280
    height=449
    >}}


La logique de ces instructions peut être rendue comme suit :

1. (a) comparer (CoMPare) la valeur du compteur avec 9 (0x9) (**en bleu sur le schéma**)
2. (b) si elle est inférieure ou égale (Jump Less or Equal), dans le cas ou
    la boucle n’a pas encore été exécutée 10 fois, sauter à
    l’instruction 8048393, ce qui correspond à exécuter les instructions
    de l’intérieur de la boucle et augmenter la valeur du compteur de un
    (4 ou d. **petites flèches en rouge sur le schéma**).
3. (c) Sinon, sauter (JuMP) à l’instruction 80483a6, ce qui correspond à
    exécuter la suite du programme (**en jaune sur le schéma**).
4. (e) Sauter au niveau de l’instruction 1., c’est-à-dire exécuter une
    nouvelle fois cette portion de code. Pour plus de détails sur les
    principes de l’assembleur (x86), voir notamment (Erickson
    2008, 19‑37) (**longue flèche en rouge remontant sur le schéma**)

En suivant étape par étape cette séquence,
on comprend que la machine exécute le programme instruction par
instruction, **sautant au cas par cas d’un endroit du programme à l’autre**.
La portion de code circulaire (en rouge) correspond à la
boucle. Cette dernière est donc le résultat d’un enchaînement
automatique d’instruction élémentaire. C’est en cela que la boucle est
une abstraction : elle permet de faciliter l’écriture et la
compréhension de l’opération « répéter une action **n** fois » pour
donner plus de flexibilité au programmeur.

Dire que l’exécution est au niveau de son flux un processus élémentaire
et automatique, c’est préciser que la machine physique qui exécute ces
instructions est incapable d’appréhender de façon globale un bloc entier
d’instructions, une boucle, ou d’autres objets du langage. Pire, à ce
niveau, la machine traite de la même façon les données du programme (par
exemple les lettres de « hello world ») et les adresses qui contrôlent
le flux d’exécution. En effet, lorsqu’on dit que le processeur
**pointe** vers une instruction, il ne s’agit bien sûr pas de déplacer
un élément mécanique. La sélection d’une instruction pour l’exécution se
fait à travers la mémorisation d’un nombre, stocké dans une zone mémoire
spécifique appelée *instruction pointer.* Ce nombre est une donnée comme
une autre manipulée par le processeur bien qu’elle désigne une donnée
critique c’est-à-dire l’emplacement de la mémoire[^153] où est stockée
l’instruction à exécuter[^154].

Ce détour par un exemple de compilation et de flux d’exécution permet
ainsi de mettre en valeur deux caractéristiques centrales qui
interviennent dans la méthode du débordement de tampon. D’une part le
fait que le programmeur code dans un langage de « haut niveau » (ici le
C) qui introduit des abstractions c’est-à-dire un écart avec la réalité
de l’exécution au niveau du processeur. Cet écart est à double tranchant
puisqu’il permet à la fois de faciliter le développement, mais est
susceptible également de dissimuler certaines erreurs dans la logique du
programme qui peuvent constituer éventuellement des vecteurs de son
détournement. D’autre part, l’équivalence aux bas niveaux d’abstraction
entre données du programme et contrôle du flux, ainsi que plus largement
entre code du programme et données traitées est, ce qui rend possible,
comme nous allons l’illustrer, de détourner le flux par débordement
mémoire et l’injection d’un code arbitraire pour *reprogrammer*
localement le système.

### Injecter un shellcode en mémoire, déborder d’un tampon pour prendre le contrôle d’une machine.

En suivant les éléments que nous venons d’introduire, le système peut
être vu comme déterminé par un ensemble de règles, c’est-à-dire un
ensemble de flux d’exécution possibles. L’**exploitation** de programme
est une façon de s’écarter de l’usage normal du système, d’utiliser un
bogue ou un cas non géré pour en prendre le contrôle localement ou
complètement[^155]. Le **débordement de tampon** (**buffer overflow**)
est une méthode classique d’**exploitation** qui se base sur un
détournement du flux d’exécution. Ce détournement peut ensuite permettre
à l’**« exploitant »** d’injecter un code personnalisé et d’entériner la
prise de contrôle, dans notre cas par l’ouverture d’un interpréteur de
commande (**shell**), c’est-à-dire une interface permettant d’exécuter
des commandes d’administration sur le système.

Les programmes en langage C sont découpés en
blocs de code étiquetés, les **fonctions**, destinées à être appelées
par la suite dans le code pour mettre en œuvre un traitement spécifique.
Elles permettent donc d’organiser le code en le subdivisant en éléments
fonctionnels cohérents. À un niveau d’abstraction inférieur, elles
correspondent à des séquences d’instructions machine enregistrées dans
un segment de la mémoire RAM[^156]. En effet, lors du lancement d’un
programme, un certain espace mémoire contiguë lui est alloué pour
stocker les instructions du programme et les diverses données
nécessaires à son exécution. Ces différents éléments sont répartis de
façon conventionnelle en cinq segments nommés **text, data, bss, heap (tas) et stack (pile)** [^157].
Les instructions du programme compilé
sont stockées dans le segment **text**: cela comprend le programme avec
ses différentes fonctions locales. Lors d’un appel de fonction, le flux
d’exécution « saute » du code principal à la séquence d’instructions
correspondant à la fonction. Pour pouvoir revenir à l’exécution du code
principal à la fin de la fonction, une donnée supplémentaire est
enregistrée. Il s’agit de l’**adresse de retour**, un nombre qui fait
référence à l’instruction en cours au moment de l’appel de la fonction.
Les données sur lesquelles opère la fonction ainsi que l’adresse de
retour sont enregistrées **sur la pile** (dans le segment **stack**,
voir schéma).

La caractéristique spécifique sur laquelle
se base la technique du **débordement de tampon sur la pile** est la
proximité en mémoire des données traitées par la fonction et de
l’adresse de retour. L’astuce consiste dès lors à faire déborder les
données de la fonction pour écraser l’adresse de retour. En effectuant
cette opération de façon contrôlée, il est alors possible de modifier
sciemment cette adresse pour agir sur le flux d’exécution. Cette
technique permet à *l’exploitant* d’effectuer un saut vers un endroit
quelconque de la mémoire. Il peut par exemple exécuter un code
arbitraire qu’il aura préalablement chargé dans un autre segment de la
mémoire.

Concrètement, il s’agit d’abord pour
l’exploitant de repérer dans le programme à exploiter un tampon
permettant le débordement. Le **tampon** (**buffer**) désigne un espace
mémoire contigu destiné à accueillir un ensemble de données
élémentaires, par exemple un court texte sous la forme d’une chaîne de
caractères, chaque caractère étant codé comme un nombre. Le tampon
possède une taille maximale (de l’ordre de quelques centaines d’octets
dans notre cas). En langage C, l’opération de vérifier si la taille des
données écrites dans le tampon ne dépasse pas la taille maximale est
laissée à la charge du développeur du programme. Si le programme C écrit
au-delà de limite, aucun contrôle ne viendra l’empêcher au niveau
d’abstraction inférieur et les cases mémoire suivant le tampon seront
effectivement remplies par des données qui lui sont normalement
destinées. Donc si un tel tampon non borné est utilisé pour enregistrer
des données fournies par l’utilisateur du programme, il est possible
pour celui-ci, s’il est conscient de cette faille, de fournir une entrée
spécifiquement prévue pour volontairement déborder du *buffer* et écrire
des valeurs choisies dans les cases mémoire sur la pile au-delà du
tampon.

Cependant, modifier l’adresse de retour de façon contrôlée est déjà une
opération complexe qui dépend du contexte spécifique d’exécution du
programme. Il faut être capable d’évaluer précisément la distance entre
le tampon et la case mémoire contenant cette adresse. Il s’agit pour
cela d’étudier le code source C et/ou la configuration brute de la
mémoire durant l’exécution du programme. Pour cela, il s’agit
généralement pour l’« exploitant » d’étudier au préalable le programme
sur son ordinateur en se procurant son code source et en utilisant des
outils spécifiques, en particulier un **debugger** qui permet d’étudier
le déroulement de l’exécution d’un programme[^158]

Cette première étape implique deux remarques
importantes. D’une part, la possibilité du débordement de tampon dépend
d’une négligence du développeur, qui n’implémente pas de mécanisme de
vérification. C’est une erreur du point de vue de la sécurité, mais elle
peut sembler peu importante lorsqu’il s’agit surtout de produire un
programme fonctionnel. En effet, un tel oubli n’est problématique que
dans certains cas limites, où l’utilisateur du programme entre,
volontairement ou non, des données anormalement longues et ne constitue
donc pas nécessairement un problème d’un point de vue fonctionnel. Une
telle faille n’est pas évidente à remarquer. Si le code n’est testé que
vis-à-vis de son fonctionnement dans des cas d’usage habituels, elle
peut passer au travers du processus de vérification du programme.
D’ailleurs, même un éventuel débordement ne sera visible à l’exécution
que s’il provoque une erreur critique : par exemple si le débordement
est suffisamment important pour atteindre un autre segment de la mémoire
du programme, une erreur critique sera déclenchée à l’exécution et le
programme s’arrêtera.

D’autre part, l’existence de telles failles
est liée à un environnement informatique caractéristique : dans notre
cas, le déficit de contrôle automatique des débordements de tampon est
assez spécifique au langage C et la possibilité de l’écrasement est liée
à la configuration de la mémoire des programmes UNIX/Linux. La viabilité
généralisée de cette méthode[^159] repose donc notamment sur la
popularité du langage C, qui est, depuis des décennies, l’un des
langages les plus populaires dans l’industrie informatique, utilisé pour
le développement de la plupart des programmes de gestion du réseau sur
les systèmes UNIX/Linux, et cette famille de systèmes est très utilisée
pour l’administration des serveurs. Il semble dès lors raisonnable de
chercher ce type de faille pour compromettre un serveur à travers
Internet.

Mais revenons à notre exploitation. Une fois
que la valeur de retour peut être modifiée, il est possible pour
l’*exploitant* de faire sauter l’exécution à une adresse arbitraire.
Cela permet d’exécuter une courte séquence d’instructions choisies. Ce
code, nommé de façon conventionnelle un **shellcode,** n’est pas un
programme du système à proprement parler. En effet, l’exploitant n’a pas
les droits nécessaires sur le système cible pour démarrer un programme
en passant par la procédure habituelle. La viabilité de la technique du
**shellcode** repose justement sur le fait qu’au niveau d’abstraction
des instructions machines, le système n’est pas à même de distinguer les
instructions du programme « officiellement » lancé d’autres instructions
qui auraient été chargées dynamiquement au cours de l’exécution. Le
shellcode est donc un tel ensemble d’instructions machine, **injectées**
dans la mémoire pendant l’exécution pour contourner les mécanismes de
sécurités habituels du système. Le shellcode, comme son nom le suggère
est traditionnellement destiné à demander au système de démarrer un
**shell**, interface dédiée à l’administration du système. Il est
composé de quelques dizaines d’octets consécutifs contenant des
opérations élémentaires. Un exemple de tel code proposé par Erickson et
spécifique aux processeurs x86 des ordinateurs personnels est le
suivant[^160] : `31 c0 50 68 2f 2f 73 68 68 2f 62 69 6e 89 e3 50 10 89 e2 53 89 e1 b0 0b cd 80`.

Une autre difficulté technique se pose
concrètement à l’exploitant : à quel emplacement de la mémoire peut-il
charger cette séquence d’instructions pour pouvoir deviner sa position
au moment de l’exploitation et ainsi modifier la valeur de retour en
conséquence ? Une méthode pratique consiste ici par exemple à utiliser
des variables d’environnement, qui sont des emplacements mémoire
indépendants du code du programme, mais qui sont destinés à rendre
accessibles des données venant de l’environnement d’exécution. Ils sont
situés au début du segment de pile du programme. Il est donc possible de
charger le **shellcode** dans un tel emplacement pour y accéder pendant
l’exécution. Mais il s’agit alors de deviner sa position (son adresse)
en mémoire. La configuration de la mémoire est susceptible de changer à
chaque exécution du programme ce qui fait varier légèrement la position
relative des variables d’environnement sur la pile. Le shellcode doit
être exécuté depuis le début, ce qui signifie qu’en l’état il s’agit de
trouver l’adresse de retour, c’est-à-dire cette position relative, à
l’octet près ce qui est souvent presque irréalisable.[^161]

Ici intervient une autre astuce classique : l’ajout d’un « NOP sled »
précédant le shellcode. L’instruction machine NOP (« no operation »),
est utilisée habituellement pour faire attendre le processeur pendant le
temps d’une opération. Lorsque le processeur la rencontre, il se
contente de passer à l’instruction suivante. En ajoutant une généreuse
quantité de « NOP » avant le shellcode, son exécution peut débuter à
n’importe quel endroit de cette séquence neutre débouchant
automatiquement sur la partie utile. La position relative de la variable
d’environnement ne doit plus alors être évaluée qu’à quelques centaines
d’octets près, ce qui augmente énormément la probabilité de réussir
l’exploitation. L’usage habituel de l’opération NOP est ainsi détourné
pour constituer des séquences neutres permettant de remplir la mémoire
d’exécution.

Récapitulons, en trois étapes, le déroulement de l’exploitation par
débordement de tampon et injection d’un shellcode.

D’abord[^256](schéma 1), au lancement du programme une zone mémoire lui est allouée. Des données de
calculs sont progressivement ajoutées dans le segment de pile. En
particulier dès le départ les variables d’environnement sont copiées sur
la pile. Le shellcode est ainsi ajouté à sa base avec une séquence
(« sled ») de quelques centaines d’instructions NOP. Au cours de
l’exécution, lorsque la fonction contenant la faille ciblée est appelée
par le programme, des emplacements pour ses données sont empilés
au-dessus de la pile courante, ainsi que l’adresse de retour. Cette
allocation comprend notamment le tampon pour accueillir des données
fournies par l’utilisateur du programme. Il est situé quelques dizaines
d’octets en dessous de l’adresse de retour.

[^256]: État initial de la pile
    {{<figure
    src="../../images/pileInitiale.jpg"
    caption="La configuration de la pile au lancement du programme avec une variable d’environnement contenant le shellcode."
    width=280
    height=360
    >}}

</br>
</br>
</br>

Par la suite[^257](schéma 2), l’*exploitant* fournit au programme des données excédant la taille
maximale du tampon. Comme le programme n’effectue aucune vérification de
cette taille (c’est l’objet de la faille), le programme continue à
enregistrer les octets supplémentaires qui viennent écraser les
emplacements mémoires suivants, jusqu’à remplacer l’adresse de retour.
Si l’*exploitant* a bien évalué la distance, il est capable de remplacer
cette valeur par une autre désignant n’importe quelle partie de la
mémoire du programme. Il y écrit donc l’adresse évaluée durant ses
explorations précédentes en espérant atteindre une position dans la
séquence de `NOP`.


[^257]: Débordement des données hors du tampon (de bas en haut)
    {{<figure
    src="../../images/debordement.jpg"
    caption="Le tampon déborde jusqu’à écraser l’adresse de retour."
    width=280
    height=300
    >}}

</br>
</br>
</br>

Troisièmement[^258](schéma 3), lors de l’exécution du retour de fonction, le shellcode
situé sur la **pile** est exécuté à la place du code du programme (la
fonction principale normalement désignée par l’adresse de retour) situé
dans le segment **text**. L’exécution au niveau des instructions
machines est aveugle à cette modification dynamique : à la suite des
instructions de la fonction, la machine exécute les instructions
arbitrairement définies par l’exploitant. En l’occurrence un appel
système pour le démarrage d’un shell.

[^258]: Saut pour l'exécution du shellcode
    {{<figure
    src="../../images/sautShellcode.jpg"
    caption="(a) la portion de mémoire désignée par l’adresse de retour est chargée (b) en tant que séquence d’instructions à la place du code du programme principal normalement exécuté à ce stade (c). Lors de la poursuite de l’exécution, les instructions NOP sont ignorées puis viennent celles du shellcode qui permettent d’effectuer des actions  arbitraires définies par l’exploitant. Dans notre cas ces instructions du shellcode demandent l’ouverture d’un shell, `/bin/sh`"
    width=280
    height=280
    >}}

</br>
</br>
</br>
</br>
</br>
</br>

Le shell est une interface qui permet de demander à la machine
d’effectuer des commandes. L’« exploitant » peut désormais effectuer des
opérations d’administration sur le système cible. Ainsi, la commande
whoami (Illustration 5) permet à l’utilisateur de connaître son identité
au sein du système. Dans un cas favorable, c’est-à-dire lorsque le
programme utilisé pour le lancement du shellcode est un programme lancé
par l’administrateur du système (**root**) avec les privilèges maximum,
le shell est ouvert en tant qu’utilisateur **root**. La commande whoami
permet de le vérifier.


</br>
</br>
</br>
</br>
</br>





### Un jeu déconstructif de l’abstraction.

Cette méthode classique, qui constitue en quelque sorte un modèle
canonique[^162], illustre clairement un jeu avec l’abstraction. La
faille (ou vecteur) d’exploitation permet une première intervention sur
la mémoire. Lorsque la gamme des interactions possibles avec
l’utilisateur n’a pas été délimitée correctement[^163] – par exemple
dans notre cas un tampon non borné ou dans d’autres situations d’entrées
utilisateur atypiques telles que l’injection SQL– il est possible
d’interférer avec la logique interne de l’abstraction. Il s’agit ensuite
d’essayer en connaissance de cause de profiter de ces interférences pour
provoquer un comportement spécifique qui permette à l’exploitant de
récupérer des informations ou un contrôle sur le système qui ne lui
était pas accordé de prime abord.

Mener cette intervention nécessite de connaître la logique sous-jacente
de l’organisation mémoire (qui varie selon les systèmes d’exploitation
par exemple) ainsi que des opérations machines constituant le flux
d’exécution. Cette connaissance n’est pas d’abord théorique, mais
pratique. Plutôt que de simplement aborder les abstractions comme des
objets définis, il s’agit de les considérer à travers leur réalisation
concrète[^164], bien que masquée, et ainsi percevoir la possibilité
toujours ouverte d’interférer avec cette réalité. La façon dont les
abstractions imposent à un certain niveau une gamme d’actions possibles
peut ainsi être contestée en percevant la façon dont elles se
décomposent en opérations et dont cette réalisation à un niveau
inférieur d’abstraction ne peut jamais être totalement négligée au plan
pratique. En d’autres termes, la boîte noire ne peut jamais être
considérée a priori comme parfaitement close et opaque, d’autant plus
que les systèmes informatiques mettent en jeu de nombreux composants en
interaction, des configurations presque aussi nombreuses que les
systèmes et se retrouvent au centre d’interactions complexes avec les
humains.

Il s’agirait de discuter généralement de la représentativité de cette
méthode (ou modèle de méthodes) particulière par rapport aux pratiques
d’exploitation et de hacking de façon plus générale. Bien que nous ne
soyons pas à même ici de considérer de façon exhaustive la diversité des
nombreuses pratiques et techniques dont certaines sont beaucoup plus
complexes, il nous semble que la logique de rapport à l’abstraction qui
prévaut dans ce cas est généralisable à de nombreuses méthodes. Ainsi si
l’on reprend l’exemple a priori bien différent de l’usurpation d’adresse
IP, on peut constater qu’il implique une décomposition des abstractions
que sont les protocoles réseau (couche IP et supérieure) à la base
d’Internet ainsi que des méthodes d’authentifications. De même, les
méthodes de hacking de console que nous avons eu l’occasion de
considérer[^165] bien qu’elles mettent en jeu des niveaux d’abstraction
encore inférieurs (notamment ceux des micrologiciels contrôlant les
composants de l’ordinateur, voire des impulsions électriques dans les
bus de communication entre les composants), manifestent la même logique
qui consiste à décomposer les objets à contester, pour pouvoir en
changer partiellement les conditions voire les reprogrammer plus
largement pour maîtriser de façon approfondie leur comportement.

On comprend dès lors plus clairement en quoi le hacking d’un système
informatique se base sur une forme de *déréification* et de
déconstruction des abstractions. Si ce que nous avons désigné comme la
logique de la boîte noire peut être identifié comme une réalisation au
niveau technique de la distinction entre une posture du concepteur et
une posture de l’usager, il semble que le hacking d’un système
informatique pour le détourner manifeste une posture différente qu’il
s’agit maintenant de caractériser.


[^146]:  Le même type de technique peut s’appliquer dans la plupart des
    contextes informatiques, sur d’autres machines et d’autres systèmes
    d’exploitation, John Erickson (Erickson 2008) la décrit comme une
    technique d’exploitation généralisée.

[^147]:  <span id="anchor-46"></span>Cet exemple est tiré de l’ouvrage
    de (Erickson 2008)**, **sur les techniques de hacking

[^148]:  Le langage C est en quelque sorte l’un des langages les moins
    abstraits parmi les langages de programmation utilisés aujourd’hui.
    Bien que de nombreux langages plus abstraits, expressifs et
    sécurisés aient été développés depuis lors, le langage C est encore
    largement utilisé, notamment en programmation embarquée, car en
    restant relativement proche des instructions machines, il permet un
    contrôle assez fin de la gestion mémoire.

[^149]:  Les nombres sont sous forme hexadécimale c’est-à-dire en base
    16 (les chiffres vont de 0 à 9 puis de *a *à* f *avec f qui vaut
    donc 15 sous forme décimale ). C’est une base très utilisée en
    informatique, car elle est en équivalence simple avec la base 2
    (binaire) caractéristique des circuits informatiques : un chiffre
    hexadécimal correspond à quatre chiffres binaires. Par exemple, 8d =
    1000 1101. Ainsi les opérations sont codées par deux chiffres **qui
    expriment huit bits** c’est-à-dire un **octet** qui est
    traditionnellement l’unité de base pour mesurer une quantité de
    mémoire.

[^150]:  Les **registres** sont les zones mémoires directement intégrées
    dans le processeur, qui servent à stocker les données actives, sur
    lesquelles sont effectuées les opérations. (Erickson 2008, 34)

[^151]:  Comme nous l’avons évoqué dans la partie I, la compilation est
    peu ou pas réversible. Concrètement, au cours de la transformation
    des opérations irréversibles sont introduites qui empêchent de
    mettre facilement les deux codes en équivalence. Cette
    irréversibilité est à l’origine de l’impossibilité de comprendre le
    fonctionnement de logiciels propriétaires distribués sous forme
    compilée.

[^152]:  Les instructions de saut sont notamment, *jmp *et* jle *dans
    notre code.

[^153]:  On parle d’adresse mémoire.

[^154]:  Cette indistinction au plus faible niveau d’abstraction entre
    données et contrôle du flux d’exécution est ce qui donne sa
    flexibilité aux ordinateurs : l’architecture de Von Neumann,
    principe central qui sous-tend l’informatique moderne, implique en
    effet que les programmes sont des données comme les autres et
    peuvent eux-mêmes être manipulés au cours de l’exécution.

[^155]:  (Erickson 2008, 115)

[^156]:  La RAM (Random Access Memory) est un espace mémoire
    relativement vaste et linéaire, découpé en segments. Il est utilisé
    comme réserve de mémoire active par les programmes du système. On
    peut opposer cet espace mémoire aux registres qui sont des cases
    mémoires indépendantes situées dans le processeur et destinées
    directement aux opérations de calcul.

[^157]: (Erickson 2008, 69)

[^158]:  L’analogie avec un travail de laboratoire, environnement
    contrôlé qui permet une étude d’un phénomène spécifique, semble
    ainsi à première vue assez pertinente. Nous l’évaluerons plus
    sérieusement à la fin de cette partie.

[^159]:  Erickson la qualifie de « méthode d’exploitation généralisée ».

[^160]:  (Erickson 2008, 298‑99) : Ces opérations permettent simplement
    d’effectuer l’appel système d’un programme externe, dans ce cas le
    programme **/bin/sh, qui **est le shell de base d’un système Linux.

[^161]:  (Erickson 2008, 139)

[^162]:  L’injection mémoire est un des leviers les plus répandus pour
    récupérer un certain contrôle sur une machine, localement ou à
    travers le réseau. En effet, la reprogrammation locale qu’elle ouvre
    permet une grande flexibilité dans le détournement (Erickson chap.
    Shellcode). Cette variante utilisant comme vecteur un débordement
    mémoire sur le segment de pile est également l’une des plus
    flexibles et des plus faciles à mettre en œuvre. C’est pourquoi elle
    constitue la technique centrale du livre d’Erickson.

[^163]:  Ce problème d’éliminer les vecteurs d’exploitation est en
    pratique impossible à traiter de façon exhaustive. Cependant,
    l’usage de langages et méthodes pour rendre la gestion mémoire plus
    consistante a permis dans de nombreux cas aujourd’hui de diminuer
    drastiquement les possibilités d’exploiter des failles mémoires dans
    les programmes.

[^164]:  Comme nous l’avons évoqué, cette réalisation concerne tous les
    programmes et objets informatiques en tant qu’ils sont des
    abstractions concrètes.

[^165]:  (Mantle et Huang 2003).

### [Sommaire](../01-sommaire)
