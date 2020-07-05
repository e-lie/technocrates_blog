+++
author = "Elie Gavoty"
title = 'L’abstraction informatique comme généralisation de la logique de la boîte noire.'
weight = 89
subtitle =   'Les hackers face à l’abstraction informatique et une omniprésente disparition du technique.'
date = "2020-07-05"
description = "Les hackers face à l’abstraction informatique et une omniprésente disparition du technique. Mémoire de recherche en histoire et philosophie des science."
tags = [
	"mémoire",
]
+++

Il existe de nombreuses façons de concevoir la nature de l’informatique
et ses objets en philosophie[^134]. Les programmes informatiques sont
notamment souvent abordés comme des objets mathématiques dans le cadre
des théories de la calculabilité ou de la logique en suivant, la
correspondance de Curry-Howard[^135]. Ce n’est cependant pas la piste
que nous suivrons ici, car il semble que ces approches sont, en tout cas
au départ, peu adaptées pour rendre compte de la façon dont
l’informatique pénètre notre société et est devenue un domaine
technologique, c’est-à-dire opère une gamme de médiations techniques de
plus en plus significatives. Pour analyser les pratiques de hacking, il
s’agit en particulier de pouvoir donner une place primordiale à
l’interaction avec l’humain, c’est-à-dire aux dimensions pratiques et
politiques des appareils informatiques en tant qu’outils et en tant
qu’objets socialement construits et disputés.

Sans aborder ici cette dimension sociale des outils informatiques, nous
allons poursuivre notre logique de la boîte noire avec une proposition
de Raymond Turner qui suggère, en s’inspirant notamment des analyses de
Kroes, de regarder les programmes comme des artefacts techniques
articulant un domaine de propriétés structurelles et un domaine de
propriétés fonctionnelles[^136]. Il s’agit notamment de considérer les
artefacts informatiques comme des objets définis à travers une
spécification, résultat d’une étape de conception qui est ensuite
implémentée, c’est-à-dire écrite dans un langage de programmation : cela
correspond en quelque sorte à la production de l’artefact.

Cependant le modèle de la boîte noire et la caractérisation de la
conception technique précédente, est comme l’indique Kroes, avant tout
adapté à description d’artefacts simples par exemple un coupe-ongle ou
une machine à laver, prototype de l’artefact technique moderne proposé
par Hans Radder. Justement, dire que la machine à laver est conçue comme
une boîte noire c’est constater qu’elle est susceptible d’être
considérée comme un ensemble simple. Elle se présente alors comme un
unique objet physique, local, c’est-à-dire clairement délimité dans
l’espace, et qui semble dans une certaine mesure autonome. Cependant,
comme le relève classiquement Radder[^137], cette représentation de la
machine autonome néglige notamment les différents réseaux sans lesquels
elle est inutilisable : réseaux d’eau, d’électricité, et de pièces de
rechange. La pertinence de la métaphore de la boîte noire semble liée à
la possibilité de construire une vue de l’esprit qui simplifie et
autonomise l’artefact technique. Cette approche est loin d’être
possibles pour toutes les catégories de systèmes techniques.

Typiquement en informatique, les systèmes logiciels sont
irréductiblement complexes : ils dépendent de librairies et des
ressources du système d’exploitation, de communications avec d’autre
programmes et sont constamment susceptibles d’être perturbés par les
programmes s’exécutant en parallèle. En outre, leur nature virtuelle
semble rendre plus problématique la question de leur délimitation. Les
logiciels peuvent généralement être non localisés physiquement, en
particulier à l’heure d’une informatique *ubiquitaire[^138]* où de
multiples appareils connectés en réseaux produisent des calculs et des
données distribués entre eux. Cette possibilité est permise justement
par la nature virtuelle et abstraite des programmes et objets
informatiques : bien qu’il nécessite toujours un ou plusieurs
processeurs pour les calculer ils peuvent être rendus indépendants d’une
machine physique particulière et donc d’une localité particulière.
Pourtant, comme pour les autres artefacts il est possible de masquer
toutes ces dépendances pour tenter de les faire apparaître comme des
boîtes noires simples. C’est même une tendance historique notable de
l’évolution des logiciels. Depuis les années 1960 et les ensembles
logiciels conçus avec l’ordinateur et dédiés à une machine spécifique,
jusqu’aux *applications *actuelles,* *simples, affublées d’une petite
icône et vendues en « magasin » virtuel, la perception du logiciel a
nettement changé. La commodification progressive des logiciels paraît
ainsi inséparable de leur transformation en boîtes noires bien
délimitées[^139].

Cependant, pour décrire de façon plus générale et réaliste les artefacts
informatiques, une description en terme de boîte noire unifié et
délimitable apparaît inadaptée. Quand est-il dès lors de notre projet de
décrire le masquage du fonctionnement et de l’incorporation d’une
distinction entre concepteur et usager dans les artefacts en
informatique ? En fait, ce passage à l’informatique nous semble offrir
justement la possibilité d’opérer une forme de généralisation de ce
modèle de la boîte noire. Une telle généralisation implique en
particulier de distinguer le fait que ce modèle délimite un système et
la façon dont il décrit un processus de masquage de la réalité interne.
Dès lors qu’on s’intéresse à la fonction de masquage de la boîte noire
et la façon dont elle sépare un domaine structurel et un domaine
fonctionnel, l’abstraction informatique processus structurant pour les
systèmes logiciels se présente en effet comme un candidat adéquat.

Pour comprendre la spécificité des processus d’abstraction informatique,
il est utile de noter une difficulté théorique en philosophie de
l’informatique : quelle nature accorder à un programme informatique,
objet virtuel et qui pourtant peut être considéré comme un arrangement
physique ? Il apparaît qu’une forme de dualité des programmes s’impose
dès lors qu’un programme informatique, objet logique descriptible
textuellement n’a d’existence qu’en tant qu’il est réalisé
électroniquement par l’intermédiaire d’une (ou plusieurs) machine(s)
physique(s). Pour rendre compte de cette dualité de l’informatique,
Timothy Colburn, qualifie les programmes d’abstractions
concrètes[^140] : il s’agit par cette expression d’exprimer le fait
général que bien qu’un programme puisse être décrit comme une entité
abstraite toute entité informatique se réalise *in fine* à travers
l’exécution d’un calcul, lui-même matérialisé par des impulsions
électriques au niveau d’un dispositif électronique appelé processeur.

Ainsi, l’abstraction informatique est différente de ce qu’on qualifie
d’abstraction en mathématique ou en philosophie. Dans ces deux cas,
l’abstraction consiste essentiellement à « supprimer de la spécificité
de telle façon qu’une description incomplète de l’entité concrète
initiale devienne une description complète de l’abstraction »[^141].
Ainsi, un groupe en mathématique est un objet abstrait en ce qu’il
extrait des propriétés caractéristiques à partir d’objets plus concrets.
Leurs caractéristiques considérées comme non significatives sont donc
supprimées de l’objet abstrait. Au contraire en informatique il est
impossible de supprimer définitivement la spécificité dès lors que les
objets informatiques abstraits n’existent qu’en tant qu’ils sont
effectivement concrétisés dans des processus de calcul[^142].
L’abstraction informatique est un masque, une façon de composer de
nombreuses opérations de calcul pour former des opérations plus
complexes qui peuvent être utilisées sans faire référence ou même
connaître l’ensemble d’opérations (plus) concrètes sous-jacentes.

Prenons comme exemple la liste en informatique : il s’agit de ce qu’on
nomme une structure de donnée fondamentale qui permet d’organiser des
données en mémoire. Une liste l de 12 nombres consiste en un
enchaînement de 12 cases contenant chacune un nombre. Une opération sur
cette liste consiste par exemple à ajouter un nouveau nombre à la fin de
la liste. Mais cette opération d’ajout correspond concrètement à allouer
une nouvelle case dans la mémoire et à relier cette nouvelle case à la
fin de la liste. Le fait que la liste soit structurée comme un
enchaînement implique certaines contraintes : ajouter un élément au
milieu de la liste sera nettement plus long (demandera plus
d’opérations) qu’ajouter un nombre à la fin. Ainsi la liste est une
abstraction qui permet à un développeur d’ignorer la structure des cases
mémoire enchaînées et les multiples opérations que leur manipulation
implique. Pourtant, s’il est possible de les ignorer partiellement, en
pratique, il est impossible de les négliger totalement puisqu’elles
imposent des contraintes irréductibles.

L’abstraction est structurante en informatique. Tout système
informatique s’organise schématiquement en couches empilées et
agencées[^143]. Les impulsions électriques dans divers composants de la
machine sont rassemblées pour former des opérations de contrôle de
chaque composant. Ces opérations sont organisées au niveau micrologiciel
des composants pour fournir notamment des instructions utilisables pour
les calculs (additions, soustractions, opérations mémoire, vectorielles,
voire dédiées à certains usages comme le rendu graphique). Mais ces
instructions sont elles-mêmes trop élémentaires pour écrire efficacement
des programmes. Elles sont donc abstraites grâce à des langages de
programmation dits de haut niveau qui fournissent des opérations plus
avancées, par exemple pour reprendre l’exemple précédent la manipulation
de listes. Ce niveau d’abstraction correspond au code source des
programmes. Les programmes et les objets que ces derniers manipulent,
constituent la couche encore supérieure. Les éléments graphiques qui
constituent l’interface graphique forment enfin les abstractions
visibles pour l’usager. Lorsqu’à force d’abstraction, sont construits
des objets virtuels qui paraissent manipulables et indépendants de leur
réalisation en terme de calcul, on parle en informatique de simulation.
Comme l’analyse Philip Brey, l’extension de possibilité de simulation
liée notamment à l’augmentation de la puissance de calcul transforme
l’usage fondamental des ordinateurs : ils remplissent désormais une
« fonction ontique »[^144] en supportant des univers virtuels sur
lesquels reposent une part croissante de nos activités.

Parallèlement, un autre type d’empilement abstraction est utilisé pour
la gestion des réseaux informatiques[^145] : on appelle ces couches des
protocoles réseaux. Ainsi pour charger une page web (niveau
d’abstraction le plus élevé), il est nécessaire que les informations
soient traduites depuis le protocole HTTP du web dans les protocoles TCP
puis IP formant la base d’Internet et jusqu’aux impulsions électriques
ou lumineuses dans les câbles de transmission.

Ainsi chaque couche constitue une sorte de milieu d’opérations qui
remplissent des fonctions informatiques et à partir desquelles peut être
programmée une couche supérieure. À chaque niveau il est possible de
manipuler, dans une certaine mesure, les opérations en ignorant la façon
dont elles se réalisent au niveau inférieur. Comme pour un artefact
simple, les opérations de la couche inférieure constituent une sorte de
domaine structurel qui est masqué pour laisser la place à une interface
fonctionnelle. Si l’on avance une analogie avec le modèle de la boîte
noire et la façon dont elle permet de décrire les artefacts techniques,
il semble que l’abstraction informatique fonctionne comme une logique de
la boîte noire généralisée et répétée à plusieurs niveaux.

[^134]:  (Turner 2014)

[^135]:  La correspondance de Curry-Howard désigne un résultat
    mathématique fondamental qui affirme que tout algorithme de calcul
    peut-être mit en équivalence avec une preuve logique. Ainsi les
    problèmes et objets de l’informatique peuvent être traduits en
    logique mathématique.

[^136]:  (Turner 2014, partie 1)

[^137]:  (Radder 2008, 55)

[^138]:  *L’*informatique ubiquitaire* désigne une sorte de changement
    d’ère dans laquelle l’informatique n’est plus attachée simplement à
    des ordinateurs personnels classiques, mais à de nombreux autres
    objets-ordinateurs comme les smartphones. L’existence de ces
    multiples ordinateurs entraîne que l’informatique nous suit
    désormais où que nous allions.*

[^139]:  Voir notamment (Campbell-Kelly 2004, 96‑103) sur l’apparition
    des produits logiciels et (Auray 2000) Introduction à la partie II.
    Nicolas Auray analyse en particulier le fait que le logiciel en tant
    que produit qui rend le comportement de la machine prévisible
    constitue justement un objet central de la critique hacker. Nous y
    reviendrons.

[^140]:  (T. R. Colburn 2000).

[^141]:  (Lewis 1986, 322:84‑85) cité dans (T. Colburn et Shute 2007)

[^142]:  (T. Colburn et Shute 2007)

[^143]:  (Tanenbaum et Austin 2013)

[^144]:  (Brey 2005, 393‑96)

[^145]:  (Tanenbaum 2003)

### [Sommaire](../01-sommaire)
