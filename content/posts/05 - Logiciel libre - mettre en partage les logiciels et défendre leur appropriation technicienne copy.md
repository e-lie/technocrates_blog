+++
author = "Elie Gavoty"
title = 'Logiciel libre : mettre en partage les logiciels et défendre leur appropriation technicienne'
weight = 95
subtitle =   'Les hackers face à l’abstraction informatique et une omniprésente disparition du technique.'
date = "2020-07-05"
description = "Les hackers face à l’abstraction informatique et une omniprésente disparition du technique. Mémoire de recherche en histoire et philosophie des science."
tags = [
	"mémoire",
]
+++

Le *logiciel libre* (ou *Logiciel Libre et Open Source* souvent abrégé
F/OSS)[^25] fait avant tout référence à un ensemble de pratiques de
création collaborative de logiciels informatiques dont le code est rendu
librement accessible à travers Internet et modifiable à volonté.
Cependant, le logiciel libre se retrouve également au centre d'un vaste
public qui par ses pratiques et son rapport particulier aux
infrastructures informatiques participe de façon centrale à la
construction d'Internet et de l'informatique actuelle. Cette forme
spécifique de collectif, que Christopher Kelty(Kelty 2008) caractérise
en introduisant la notion de « public récursif » sera l'objet de la
partie 2.2. Enfin, nous nous interrogerons sur ce qui relie en pratique
le développement logiciel à la notion de *hack* précédemment évoquée et
notamment à sa dimension transgressive.

### <span id="anchor-20"></span><span id="anchor-21"></span>Définition et premières implications informatiques du logiciel libre

Tel qu'on le rencontre en tant qu'usager d'un ordinateur, un logiciel
libre est avant tout un logiciel[^26] librement téléchargeable et
utilisable, mais également dont le code source[^27] est publiquement
accessible. Ces logiciels sont souvent gérés de façon communautaire :
ils sont développés par des contributions de programmeurs d'horizons
différents et distribués sous diverses formes à l'usage de tout un
chacun. Mais le logiciel libre est également un mouvement d'un type
particulier organisé autour de ces pratiques de développement
informatique collaboratif pour défendre leur spécificité, c'est-à-dire
une façon d'envisager les programmes informatiques comme des biens
communs appropriables.

La notion de *logiciel libre* (*free software*) et le mouvement éponyme
remontent à 1983. Elle fut introduite par un hacker de l'*AI Lab* du
Massachusetts Institute of Technology, Richard Stallman. Elle découle
directement de l'éthique de travail collectif des hackers et des
pratiques universitaires de partage du code informatique. Cependant à
l'époque, une transformation rapide du monde du logiciel en un
écosystème commercial fermé et protégé par des brevets menaçait ce
rapport libre à l'informatique. Stallman décida alors de lancer un
projet, nommé GNU[^28], et introduisit pour le caractériser la notion de
*logiciel libre[^29],* afin d'une part de réaffirmer l'importance en
informatique d'accéder au code des logiciels et d'autre part de
rassembler les hackers encore susceptibles de défendre cet idéal. Il
s'agissait concrètement de développer un système d'exploitation dont le
code serait à jamais un objet collectif, librement disponible et
modifiable.

Selon cette approche de Stallman, devenue en quelque sorte canonique, un
logiciel est dit libre s’il respecte quatre libertés :

-   «  la liberté d’exécuter le programme comme vous voulez, pour
    n’importe quel usage (liberté 0);
-   la liberté d’étudier le fonctionnement du programme, et de le
    modifier pour qu’il effectue vos tâches informatiques comme vous le
    souhaitez (liberté 1) ; l’accès au code source est une condition
    nécessaire ;
-   la liberté de redistribuer des copies, donc d’aider votre voisin
    (liberté 2) ;
-   la liberté de distribuer aux autres des copies de vos versions
    modifiées (liberté 3) ; en faisant cela, vous donnez à toute la
    communauté une possibilité de profiter de vos changements ; l’accès
    au code source est une condition nécessaire. » [^30]

En 1985, au moment de la distribution du premier logiciel GNU, Stallman
écrivit une toute première version de la *General Public Licence* (GPL),
pour qualifier juridiquement les libertés associées au logiciel libre.
En effet, si le partage de code, librement disponible et modifiable,
était une pratique courante dans le milieu universitaire des années 60
et 70, le cadre juridique habituel du *domaine public*, n'était pas
satisfaisant. Stallman désirait protéger les logiciels libres d'une
réappropriation et d'une intégration de leur code dans des logiciels non
libres. Il introduisit pour ce faire une clause qui contraint tout
développeur utilisant le code d'un logiciel libre sous licence GPL à
distribuer son logiciel selon cette même licence, c'est-à-dire en
respectant les libertés associées. Ce *hack* *juridique[^31] *fonde ce
que l'on appelle le *copyleft*, c'est-à-dire un retournement du
*copyright* anglo-saxon de façon à protéger non pas une possession
exclusive du code, mais une possession collective de celui-ci. Cette
première *licence* *libre*, encore largement utilisée aujourd'hui dans
sa version mise à jour[^32]. De plus, le *copyleft* s'applique désormais
à d'autres objets, par exemple des livres, des images et des œuvres
d'art.

Pour clarifier, le cadre informatique qui donne son sens en pratique aux
libertés du logiciel libre, il est utile de comparer son code « ouvert »
avec son pendant au code « fermé » qu’on désigne habituellement du
qualificatif de *propriétaire. *Les logiciels sont initialement écrits
sous la forme d'un code qu'on qualifie de * source*. Un tel code est
formulé dans un langage potentiellement compréhensible par l'humain, car
composé de mots organisés selon une syntaxe régulière. Cependant, sous
cette forme le programme n'est pas lisible par le(s) processeur(s) de la
machine. Il doit être, à un moment ou un autre traduit en *langage*
*machine*. Le programme peut alors être compris par l'ordinateur,
c'est-à-dire lancé et utilisé, mais non par l'humain. En effet, *le code
machine* exécutable se présente sous la forme d'un imbroglio binaire
(codé sous forme de 0 et de 1). Les opérations sont alors difficilement
distinguables et si élémentaires que la logique du programme est
extrêmement fastidieuse, voire impossible à reconstituer[^33]. Le
processus de traduction d'un code source en un binaire exécutable,
appelé *compilation*, est fondamental en informatique.

Généralement, un *logiciel propriétaire *(ou encore* privatif)* est
techniquement <span id="anchor-22"></span>un programme pour lequel le
*code source* n'est pas distribué par ses créateurs. Seul un programme
sous forme compilé c'est-à-dire un *fichier exécutable* est disponible.
Le programme se présente alors en pratique comme une boîte noire[^34]
dont seuls les créateurs connaissent la logique de fonctionnement. Au
contraire, l'ouverture du code en tant que caractéristique technique a
de nombreuses conséquences pratiques et autour d'elle cristallise
également la dimension politique portée par le mouvement. En effet,
avoir accès au code source du programme correspond, dans les conditions
techniques particulières de l'informatique à disposer à la fois d'un
artefact technique[^35] en tant que tel[^36] et d'une description de sa
logique/structure qui constitue une connaissance technique souvent
suffisante pour comprendre cette dernière à peu près intégralement. Il
est possible, lorsque le code source est disponible de s'approprier,
dans la mesure de son temps et de ses compétences, un logiciel d'une
façon tout à fait différente d'un usager habituel : chacun peut se faire
en quelque sorte (re)concepteur du programme pour changer plus ou moins
profondément ses fonctions, améliorer sa conception, supprimer certaines
parties jugées inadéquates ou dangereuses[^37]. Pouvoir lire et
comprendre le code d'un programme est également la seule façon de
s'assurer que ce dernier fait bien ce qu'on pense qu'il fait. En effet,
au-delà de l'évidence de ce qui se déroule sur l'écran, les traitements
informatiques sont largement invisibles[^38] et il est très aisé de
cacher des dispositifs malveillants[^39]. Comprendre, contrôler et
s’approprier au niveau technique ce que fait le programme constitue pour
Stallman, et pour une grande partie des hackers dont il s'est fait le
porte-parole, une liberté fondamentale de tout usager d'un ordinateur.
Cette liberté d'appropriation ne s'impose d'ailleurs pas plus
aujourd'hui qu'à l'époque comme un droit des usagers dans nos sociétés
dites technologiquement avancées : des smartphones aux consoles de jeu
vidéo en passant par les multiples services qui fleurissent sur Internet
à l'heure du nuage, la majorité des industriels redoublent ces dernières
années d'efforts pour s'octroyer un contrôle en aval sur tous leurs
produits et services au détriment des possibilités d'appropriation par
les usagers[^40]. Pour Stallman, face à cette tendance, le logiciel
libre constitue un mouvement social œuvrant pour défendre la liberté des
utilisateurs, notamment à choisir ce qui constitue pour eux une
technologie utile et éthique.

Cependant, cette approche politique du logiciel libre comme un mouvement
social ne fait pas l'unanimité[^41] : face aux premiers succès
commerciaux du logiciel libre, apparaît en 1998 la notion d'*open
source* défendue notamment par le libertarien Eric Raymond. Cette
nouvelle qualification, outre qu'elle règle le problème de l’ambiguïté
du mot *free* en anglais[^42], fut portée stratégiquement à la fois pour
prendre le contre-pied de l'approche engagée de Stallman que Raymond et
de nombreux hackers considèrent comme idéologique (Broca 2013, 62‑63,
69‑70), mais également pour changer l'image et les conditions de
distribution du logiciel libre et ainsi le rendre plus compatible avec
l'industrie. Cette transformation des *logiciels libres* en un phénomène
relativement soluble dans l'industrie logicielle s'est effectivement
opérée et les logiciels libres et open source se sont diffusés largement
dans divers pans de l'informatique[^43].

Une certaine forme de rupture s'est confirmée par la suite entre les
deux approches, Stallman évitant par exemple de fréquenter les
événements étiquetés *open source. *Il les décrit comme deux factions
opposées au sein d'une même communauté, l'une assumant et exprimant la
dimension politique de son engagement et l'autre insistant sur la
dimension techniquement et économiquement avantageuse de l'ouverture.
Pourtant, il affirme également que cette opposition n'empêche pas une
certaine cohésion de la communauté, les divergences politiques
n'entravant pas la coopération pratique autour d'objectifs communs.

En fait selon Christopher Kelty, le phénomène du logiciel libre excède
ce qu'on appelle traditionnellement un mouvement(Kelty 2008, 98). Pour
lui, la dimension de mouvement n'est qu'une composante de ce qui fait du
logiciel libre et open source un phénomène original et la matrice d'une
tendance plus vaste[^44]. Cette composante de mouvement est liée avant
tout à la réflexivité de la communauté, aux disputes et clarifications
quant aux enjeux pratiques et politiques de l'ouverture et du partage
des logiciels. Ainsi plutôt que de se former d'abord autour d'une
cohésion symbolique et politique ce collectif fonctionne justement, car
autour des logiciels libres et d'Internet qui permettent un partage
d’artefact et de culture techniques se construit un contexte dans lequel
il est possible de travailler ensemble. Pour parler de cette forme
collective, dont il décèle une forme possible de généralisation,
Christopher Kelty introduit la notion de *public récursif*.

### <span id="anchor-23"></span>Le collectif du logiciel<span id="anchor-24"></span> libre : constitution d'un public récursif.

Pour saisir la forme particulière du *public* *récursif* du logiciel
libre, il s'agit selon Kelty de s'intéresser à une « concentration
particulière de pratiques »(Kelty, préface de Broca 20132013, p.10). Il
la décompose en cinq composantes qui se développent à différentes
époques et convergent pour donner au public du logiciel libre sa
dynamique particulière.

La première composante dans cette analyse est celle du logiciel libre et
open source en tant que mouvement, c'est-à-dire la prise de conscience
de l'existence d'une communauté large valorisant l'ouverture et le
partage du code ainsi que les discussions quant à son identité et ses
enjeux.

La deuxième composante qui constitue le cœur pratique du logiciel libre
est le partage du code source informatique ; comme nous l'avons évoqué,
ce partage implique que le code soit facilement disponible et modifiable
et permet d'envisager une forme de travail de conception technique à
plusieurs mains. Les pratiques de partage de code trouvent leurs racines
dès les années 70, avec la révolution constituée par le système
d'exploitation UNIX : il s'agit du premier système d'exploitation
véritablement indépendant du matériel, c'est-à-dire que le même code
était capable de fonctionner sur de nombreuses machines grâce au
processus de compilation. Entre autres qualités, cette possibilité
d'adapter UNIX à différents contextes informatiques et le fait que le
code était distribué avec le logiciel ont garanti sa popularité parmi
les informaticiens : distribués librement et améliorés par des
professionnels pour leur propre usage, les programmes compatibles et
versions du système se sont multipliés jusqu'à créer un écosystème
énorme devenu de facto un standard[^45]. L'histoire d'UNIX a en quelque
sorte rendu naturelle l'idée du « fork » centrale dans le logiciel
libre : dès lors que le code est partagé, il est possible de créer sa
propre version d'un logiciel existant en aménageant son code ou en le
réécrivant presque totalement, pour l'utiliser ou par exemple pour des
raisons d'apprentissage.

Mais le fait de disposer d'un accès au code ne fait pas nécessairement
des systèmes informatiques des écosystèmes ouverts et compatibles. Pour
pouvoir communiquer informatiquement, il est nécessaire notamment
d'élaborer un protocole qui sera respecté par les différents systèmes et
logiciels. Le troisième jalon mis en valeur par Kelty est le tournant
des réseaux informatiques dans les années 80. Il devint alors largement
évident que l'avenir de l'informatique se situait dans le partage
d'information plutôt que simplement dans le calcul. Pour cette raison,
l'industrie informatique commença à valoriser l'interopérabilité, en
particulier des systèmes Unix, autour du concept d'*Open System*. En
outre, les premiers protocoles réseau standard et génériques virent le
jour, en particulier la norme TCP/IP à la base d'Internet. Cependant
dans un contexte de concurrence où les différents industriels voulaient
imposer leur version et abusaient pour cela des brevets logiciels, cette
promotion de l'ouverture se solda en pratique par un échec. La
« guerre » des versions d'Unix se conclut sur la victoire d'écosystèmes
incompatibles et radicalement fermés : les systèmes *Msdos, *puis
*Windows,* vendus* *par* Microsoft.*

La quatrième composante apparaît dès lors comme une solution à cet échec
des *Open Systems*. Il s'agit, à travers la création de diverses
licences libres, de la formation de cadres juridiques permettant, comme
nous l'avons évoqué précédemment de défendre une forme de mise en commun
des logiciels et des protocoles. Ainsi, en plus de sa composante
technique, la composante juridique est centrale pour le logiciel libre
et l'établissement de cadres dans lesquels contester les modes
traditionnels de la propriété intellectuelle. En outre, une forme de
comparaison entre technique et juridique, présente en particulier dans
les travaux du juriste Lawrence Lessig[^46], nous semble relativement
influente dans la culture hacker : en tant qu'il fait exister le
*cyberespace* d'une façon particulière, le code informatique, définit et
contraint les comportements collectifs, d'une façon semblable aux lois,
si ce n'est que cette législation technique est plus fondamentale, car
elle précède et conditionne les processus législatifs traditionnels.

Enfin, la cinquième composante est la constitution de modes nouveaux
d'organisation et de gouvernement du travail collectif de développement,
tirant notamment parti d'Internet. Un exemple classique en la matière
est l'organisation du développement du noyau[^47] Linux, initié par
Linus Torvald et qui a dès l'origine impliqué des dizaines de
développeurs. Eric Raymond caractérise cette organisation, par la
métaphore du bazar : plutôt que de partir avec un objectif logiciel
ambitieux et précisément conçu, Linux Torvald travailla, partant d'un
projet minimal de noyau déjà existant et fonctionnel, à son amélioration
pour atteindre un objectif pragmatique : le faire fonctionner sur un
ordinateur personnel IBM PC. Lorsqu'il mit à disposition son code sur le
net, de nombreux développeurs, intéressés par l'existence d'un noyau
libre fonctionnel pour PC, aussi modeste soit-il, contribuèrent au
projet. Torvalds se laissa guider par les contributions et les besoins
de ses usagers en intégrant toutes les modifications intéressantes
apportées par d'autres au logiciel. Ce mode de développement, très
étonnant au regard des modes d'organisation de projets logiciels de
l'époque, s'avéra très fructueux puisque le noyau en vint en quelques
années à concurrencer les solutions commerciales. C'est en grande partie
l'exemple de Linux qui fut au centre des discussions sur l'open source
comme modèle de développement, au point qu'il fut discuté bien au-delà
des cercles libristes jusqu'à influencer la pensée managériale. Mais,
partant de ces innovations des années 1990, chaque projet libre présente
une forme d'organisation collaborative relativement spécifique, plus ou
moins *doocratique*, plus ou moins formelle, exploitant différents
outils pour aider à l'intégration du code et la gestion collective des
versions[^48].

À travers ces différents jalons, on comprend que le *logiciel libre* est
un phénomène à de nombreux égards paradigmatique. Concrètement, les
logiciels à sources ouvertes sont aujourd’hui au cœur de
l’informatique : on peut traditionnellement relever que le navigateur
Firefox, les systèmes d’exploitation de la famille GNU/Linux, très
utilisés notamment sur les serveurs à la base d’Internet, ou encore des
composants logiciels cruciaux comme le logiciel serveur HTTP Apache,
sont libres. Plus largement, cette orientation collaborative du
développement logiciel a débouché sur un modèle reconnu et largement mis
en valeur jusque chez les ténors de l’industrie du logiciel. On
pourrait, pour illustrer cette dimension paradigmatique du *libre*,
s’intéresser au phénomène récent qui se constitue autour de la
plateforme *Github *: ce réseau social basé sur le développement
contributif et le code source comme vecteur d’interaction sociale,
rencontre un franc succès chez nombre de développeurs professionnels ou
amateurs, au point de transformer les habitudes dans le champ de
l’informatique.

D’autre part, la spécificité de ce phénomène collectif est liée à sa
dimension récursive :

« Why recursive? I call such publics recursive for two reasons: first,
in order to signal that this kind of public includes the activities of
making, maintaining, and modifying software and networks, as well as the
more conventional discourse that is thereby enabled; and second, in
order to suggest the recursive « depth » of the public, the series of
technical and legal layers—from applications to protocols to the
physical infrastructures of waves and wires—that are the subject of this
making, maintaining, and modifying. The first of these characteristics
is evident in the fact that geeks use technology as a kind of argument,
for a specific kind of order: they argue about technology, but they also
argue through it. »[^49]

La récursivité, concept fondamental en informatique, décrit ici le
public des *geeks* en tant qu’il s’est constitué par et pour
l’informatique et Internet. Tels des *homo faber* numériques, ils
produisent un monde technique partagé, des infrastructures logicielles
et réseau qui sont à la fois l’objet et le milieu de leur mobilisation
collective. Cela implique une articulation permanente du technique et du
politique, du pratique et du symbolique.

Nous avons introduit le *logiciel libre* comme une composante centrale
de la culture hacker. Dans quelle mesure, ce public récursif des
*geeks*, mobilisés par le phénomène du *libre* et de l’*open source*
correspond-il plus généralement à celui des hackers dont nous
interrogeons les spécificités ?

Kelty désigne bien par le terme de *geek*, les héritiers de la culture
hacker dans un sens inclusif. Au sens strict, il s’avère qu’il y a des
hackers qui ne participent pas au développement du *libre* et des
libristes qui sont gênés par la figure du hacker, voire des partisans
des sources ouvertes au sein d’entreprises dont l’idéal est bien éloigné
de l’éthique hacker. Cette question d’identité est donc complexe et
instable (Söderberg 2011, 22). Kelty utilise justement la figure du
*geek* comme une identité plus générale et détachée des forts enjeux
d’appartenance et des disputes qui sont associées à la figure du hacker.
Ces enjeux sont marqués en particulier par l’élitisme revendiqué de
certains hackers et d’autre part par l’image de déviance associée à
cette figure[^50]. En outre, comme nous l’avons évoqué, il y a une forte
dispersion de la notion de hacking et donc également des identités
associées. Au contraire, Johan Söderberg critique le choix de ce terme
de geek (Söderberg 2011, 28) : l’identité de hacker lui semble en effet
d’une part généralement revendiquée par les acteurs et d’autre part plus
à même de faire référence à leur ambition de maîtrise technicienne,
héritée des premiers hackers américains.

Cependant, au-delà, de distinctions principalement terminologiques, la
notion de public récursif, en proposant d’aborder cette question au
niveau des pratiques, des infrastructures techniques et de l’autonomie
collective qu’elles produisent s’adapte bien à une compréhension des
collectifs hackers, qu’ils appartiennent ou non à ce que Coleman et
Golub appellent le « genre moral » du libre. Pour poursuivre cette
interrogation du rapport entre logiciel libre et la culture hacker il
nous semble dès lors pertinent de nous intéresser à la convergence
pratique entre le libre et les orientations plus transgressives de la
culture hacker. Ainsi on peut se demander en quoi les activités de
développement logiciel qui sont au centre du libre peuvent-elles se
rapporter au motif du hack que nous avons évoqué dans la première
partie. Ou dit autrement, en quoi l’approche de création de programmes
informatiques au sein du mouvement du logiciel libre est-elle voisine
d’autres pratiques de hacking, notamment celles qui consistent à
détourner ou pénétrer des systèmes informatiques ?

### <span id="anchor-25"></span><span id="anchor-26"></span>Le développement de logiciel libre comme activité de hacking.

L’activité de production logicielle prend typiquement dans le cadre des
projets de logiciel libre, une forme itérative : le programme se
développe par des contributions ponctuelles qui lui ajoutent de
nouvelles fonctionnalités ou corrigent des erreurs et bogues. Le
programme passe ainsi d’un état fonctionnel à un autre légèrement plus
étendu ou fiable. Dans cette approche, le développement n’est pas
nécessairement planifié. Elle s’oppose ainsi, comme le relève notamment
Gisle Hannemyr[^51], à une approche d’ingénierie logicielle[^52], dans
laquelle tous les développements doivent préalablement être décrits sous
forme de spécifications et où le développement est dirigé
hiérarchiquement.

Dans le cadre d’une approche industrielle du développement, il s’agit
ainsi de produire des composants logiciels partiels pour répondre à une
liste de spécifications préétablies et de scinder les tâches de
développement pour les répartir sur une équipe avec des spécialités.
Dans le cas du producteur de logiciel, de la même façon que dans le cas
d’un ouvrier qui produirait des pièces métalliques sans être
véritablement impliqué dans la création de la machine résultante, cela a
pour résultat que le producteur est peu concerné personnellement par les
qualités potentiellement complexes et non univoques de l’objet
résultant. Il ne réalise notamment pas le logiciel, car ce dernier fait
sens d’un point de pratique pour lui, mais seulement pour répondre à un
cahier des charges largement extrinsèque. Hannemyr qualifie en
comparaison l’approche hacker d’artisanale : il s’agit pour un hacker de
produire des programmes sur des bases volontaires et autonomes en
définissant, souvent pour son propre usage, ce qui constitue la forme et
les qualités adéquates de l’artefact informatique. Cette autonomie est
intéressante pour produire du travail de qualité, car plutôt que de
limiter le jugement au respect d’une spécification, elle permet une
véritable implication pratique.

Cependant avec cette opposition entre approche hacker *artisanale* et
approche industrielle *tayloriste*, Hannemyr nous semble, en tout cas
dans le contexte actuel de l’informatique, trancher un peu trop
nettement le développement logiciel. En effet, le développement du
logiciel libre n’implique pas nécessairement de se passer de
spécification ou de planification. Il s’agit également de pouvoir
répartir les tâches entre des développeurs. De plus, des méthodes de
développement incrémental et autres méthodes « agiles » d’organisation
du développement logiciel créées en réaction à des modèles extrêmement
planifiés issus de l’ingénierie logicielle se sont largement répandues
dans l’industrie logicielle. Cette nuance étant posée, il demeure que
l’opposition entre attitude industrielle et position hacker reste
pertinente historiquement et politiquement dans la mesure ou
l’ingénierie logicielle est une approche de l’informatique qui se
développe à la fin des années soixante dans un contexte où il s’agit de
rendre « manageables » des régiments de programmeurs pour répondre à une
demande croissante de produits logiciels (Tedre 2014, chap. 6). En fait
d’après Hannemyr, les hackers se constituent justement en tant que
groupe clairement identifié dans les années 70 par leur opposition à
cette approche de la programmation qui déqualifie et détruit le sens
pratique de leur travail. Söderberg et Dafermos (Söderberg et Dafermos,
George 2009) parlent à ce propos d’une forme de *lutte ouvrière* (labour
struggle) dans le champ de l’informatique.

Par ailleurs, un mode de développement contributif et itératif implique
également que le programmeur travaille dans le cadre d’un système
prédéfini (le logiciel avec ses bibliothèques de fonctions et ses
différents modules) voire d’un système qu’il n’a pas conçu et ne
maîtrise pas complètement s’il s’agit d’un contributeur ponctuel. En
fait, étendre un logiciel consiste à composer avec sa forme actuelle qui
impose de nombreuses contraintes : un langage de programmation
particulier, un choix de cadriciel et de bibliothèques de fonctions
prédéfinies, mais surtout une architecture qui définit les principales
masses du logiciel et des points de passages obligés lors de la
programmation. Par exemple, ajouter une nouvelle fonctionnalité à un
logiciel qui organise ses données d’une certaine façon et les stocke
dans une base de données spécifique va imposer au programmeur de
respecter cette organisation (on parle de modèle de données) et un
ensemble de façons d’accéder aux données. Ce type de contraintes peuvent
parfois rendre difficile, voire presque impossible, l’ajout de
fonctionnalités originales à un logiciel. Cette affirmation est d’autant
plus vraie lorsque celui-ci possède une forte intégration entre ses
composants et ne prévoit pas dans son architecture la possibilité d’être
étendu.

Dans un tel contexte de contrainte (plus ou moins forte), une dose
d’astuce et d’ingéniosité est souvent nécessaire pour toute création
technique : lorsque les choix de conception d’un composant ne sont pas
suffisamment versatiles (souvent pour de bonnes raisons, par exemple
pour optimiser la rapidité d’exécution du programme) et qu’il n’est pas
possible d’intégrer simplement ce composant d’une autre manière que
celle prévue par les concepteurs, le travail de développement s’éloigne
d’un simple travail de production : il est alors tout particulièrement
nécessaire de comprendre les conditions de fonctionnement des composants
(au niveau de leurs opérations élémentaires) et de construire par
exemple une nouvelle interface entre eux pour créer les conditions
nécessaires à l’extension du logiciel.

En fait, la tâche d’étendre un système, dès lors qu’il s’agit d’utiliser
un code existant, un ensemble de composants définis, pour faire plus que
ce que l’auteur original avait envisagé, constitue toujours d’une
certaine façon une forme de transgression à l’égard de ce qu’on pourrait
appeler à la suite de Madeleine Akrich le « script » du logiciel,
c’est-à-dire son scénario fonctionnel (et ici fonctionnant
également)[^53]. Comme le résume Gabriella Coleman, le travail
contributif de programmation rejoint alors directement la notion de
hacking, dans le sens classique d’une façon de retourner un système
contre lui-même[^54].

Cependant, cette approche de certains enjeux pratiques de la
programmation, en particulier itérative n’est pas ici spécifique. Il ne
s’agit pas d’affirmer qu’il existerait une façon « hacker » de
programmer qui se retrouverait uniquement dans certains milieux, mais
plutôt qu’une certaine dose d’attitude « hacker » fait partie intégrante
de toute activité de développement logiciel et que c’est cette attitude
pratique, que certains préfèreront nommer *bidouille*, qui est mise en
avant dans le mode contributif du logiciel libre. Comme l’affirme
poétiquement Julian Dibbel[^55], la nature de l’informatique consiste en
une « collusion répétée sans fin entre liberté et déterminisme ». Le
savoir-faire informatique valorisé par la culture hacker consiste en
cette capacité à transcender les contraintes de la programmation par des
astuces techniques afin de pouvoir jouir d’une liberté de création
informatique[^56].

Tous les systèmes logiciels sont loin d’être également contraignants et
modifiables. On désigne généralement la facilité de modification d’un
logiciel, par le terme anglais de « hackability »[^57]. Un logiciel
(propriétaire) sous forme compilée dont le code source n’est pas
publiquement accessible sera en pratique très difficilement
*hackable*[^58]. Mais même quand on dispose du code source d’un
logiciel, il est parfois très difficile d’intervenir sur lui, notamment
s’il est trop complexe, peu documenté et commenté, ou si comme nous
l’avons évoqué, son architecture impose trop de contraintes pour
développer des fonctionnalités originales. Ainsi la *hackabilité* dépend
souvent de la coopération des concepteurs à cette pratique en un sens
transgressive qu’est l’extension non sollicitée du logiciel. De nombreux
logiciels libres sont volontairement conservés très simples pour être
facilement maîtrisables techniquement[^59]. D’autres, plus complexes,
sont activement rendus extensibles grâce à des scripts aisément
programmables[^60].

Insister ainsi sur cette notion de hackabilité et celle de public
récursif pour décrire le phénomène du logiciel libre, montre notamment
qu’avoir accès au code source n’est qu’une condition nécessaire, mais
non suffisante, à la forme d’émancipation technicienne que ce mouvement
porte. Ainsi en un sens fondamental, l’ouverture d’un système ne
consiste pas seulement en la disponibilité du code, mais plus
profondément dans la possibilité d’avoir effectivement une action
transformatrice sur les logiciels et les médiations techniques qu’ils
opèrent. Inversement, si l’on aborde la *fermeture* d’un logiciel comme
l’impossibilité pratique d’influer sur les conditions de son usage et
ses impacts collectifs, on constate que les enjeux de cette dernière
dépassent l’impossibilité d’avoir accès au code.

Prenons, l’exemple, d’un groupe de hackers qui effectue l’ingénierie
inverse d’une console de jeu vidéo[^61]. Il sera à même d’influer
radicalement sur son usage alors que cette machine répondait pleinement
à la définition d’un système informatique *propriétaire*, voire
extrêmement fermé. En effet, les industriels ajoutent généralement de
nombreux mécanismes pour garantir que leurs machines ne seront pas
détournées par des hackers. Ainsi, même des systèmes propriétaires
peuvent être, dans une certaine mesure, l’objet d’une appropriation et
d’une redéfinition de leur fonctionnement.

D’autre part, un usager pourra malgré tout se sentir impuissant face à
un logiciel libre, notamment lorsqu’il n’a aucune compréhension du
traitement effectué par le logiciel. Dès lors qu’il n’instaure pas un
rapport pratique avec le code et le fonctionnement du logiciel, parce
qu’il ne dispose pas des connaissances, n’a pas conscience ou envie
d’exploiter cette possibilité, la disponibilité du code ne changera pas
sa position d’usager recevant les programmes informatiques comme des
objets préconçus. Ainsi, si l’usage de logiciels libres induit dans tous
les cas de nombreux avantages, il fait tout particulièrement sens en
lien avec une attitude particulière face aux environnements
informatiques et techniques de façon plus générale. Cette attitude, que
l’on pourrait qualifier d’attitude hacker, bien que cette expression
soit à ce stade encore relativement floue, implique une volonté
d’explorer et de transformer les conditions des infrastructures
informatiques ce qui ne va pas sans poser certains problèmes dans nos
sociétés.


[^25]: Nous évoquerons le fait que l’histoire du logiciel libre est
    traversée par une concurrence entre deux approches à propos de
    l’ouverture des logiciels qui impliquent deux appellations
    distinctes. L’acronyme FOSS (Free and Open Source Software) permet
    d'inclure les deux tendances.

[^26]: Habituellement, on utilise le terme logiciel pour désigner un
    paquet ou un produit logiciel, mais dans un sens plus large, un
    logiciel peut désigner aussi bien une application qu'un système
    d'exploitation ou encore un système de services distribués sur
    internet (le logiciel d'un réseau social), c'est-à-dire tout
    ensemble logique permettant de contrôler un ordinateur.

[^27]:  Succinctement, le code source est un texte qui décrit les
    opérations du programme et donc sa logique de fonctionnement et sur
    lequel travaillent les développeurs du logiciel. Nous préciserons
    cette notion plus loin.

[^28]: L'acronyme *GNU* vaut pour *GNU is Not Unix*. Il s'agit donc
    d'un acronyme récursif (qui se contient lui-même) typique de
    l'humour hacker (Broca2013 p.50).

[^29]: Les objectifs du projet GNU qui définissent en quelque sorte le
    logiciel libre furent clarifiés au sein du *GNU manifesto*, publié
    par Stallman en 1985.

[^30]: Http://www.gnu.org/philosophy/free-sw.fr.html, consulté le 13
    avril 2016.

[^31]: *(Broca 2013, 52‑57)* Par ailleurs, il s'agit de relever que ce
    hack de Stallman a fait école et que le hacking juridique fait
    aujourd'hui partie intégrante de la culture hacker. Voir par
    exemple (Jordan 2008, chap. 4).

[^32]: La première version générique de la GPL, coécrite par Stallman et
    le juriste Eben Moglen date de 1989 (Kelty 2008, 206). De multiples
    licences libres existent aujourd'hui, dont certaines utilisent le
    principe du copyleft et d'autres non. Pour une approche très
    complète des aspects juridiques de ces licences, voir (Jean 2011),
    un livre également sous licence libre.

[^33]: Lorsqu'on reconstitue la logique d'un programme à partir d'un
    code machine on parle en informatique d'*ingénierie inverse*.
    L'ingénierie inverse est une activité pratiquée par des hackers pour
    des raisons pratiques et politiques et par goût du défi.

[^34]: Nous reviendrons largement sur ce concept de boîte noire dans la
    partie II.

[^35]: Il existe en philosophie de l'informatique de nombreux débats sur
    la nature des programmes informatiques : certains auteurs les
    considèrent comme des objets mathématiques tandis que d'autres les
    font rentrer dans la catégorie des artefacts techniques, avec
    certaines spécificités. Nous penchons dans le cadre de ce mémoire
    plutôt pour la deuxième possibilité. Nous aborderons cette question
    dans la partie II.3.

[^36]: Concrètement, il est possible de compiler le programme,
    c'est-à-dire reproduire un fichier exécutable pour l'utiliser sur
    son ordinateur.

[^37]: Par exemple des dispositifs qui collecteraient des informations
    personnelles portant atteinte à la vie privée numérique d'un usager.

[^38]: Cette invisibilité du fonctionnement d'un ordinateur est due
    notamment au fonctionnement de l'abstraction informatique, mécanisme
    central qui implique de masquer les opérations informatiques
    élémentaires. Nous traiterons cette notion clé dans la partie partie
    II.3.

[^39]: À ce niveau, l'accès au code source converge avec d'autres
    problématiques qui sont au centre de la culture hacker : la défense
    de la vie privée et la sécurité informatique, notion dont la
    définition controversée et politique sera l'un des objets de la
    partie I.3. On pourrait résumer cette problématique par la question : peut-on
    considérer qu'il est malveillant, au même titre qu'un
    virus informatique, que les grands industriels du logiciel
    incorporent des dispositifs de collecte de données invisibles dans
    leurs produits ?

[^40]: Nous aurons l'occasion de revenir plus en détail sur ces
    problématiques, et notamment la notion d'hégémonie technique dans la
    partie II.

[^41]: Les sensibilités politiques des hackers varient notamment avec
    les pays.

[^42]: Pour clarifier la notion de « free », Stallman introduisit la
    distinction entre le terme « libre » correspondant à « liberté
    d'expression » (free speech) plutôt que « gratuit » comme pour une
    bière gratuite (free beer). La gratuité n'est qu'une conséquence
    contingente du mode de distribution des logiciels libres. C'est
    pourquoi on emploie également le terme français « libre » en anglais
    qui permet de supprimer cette ambiguïté comme dans l'acronyme FLOSS
    (Free Libre Open Source Software).

[^43]: Répertorier, l'ensemble des logiciels libres constituerait
    aujourd'hui une tâche colossale. On peut cependant relever en
    particulier que de nombreuses briques fondamentales d'Internet sont
    aujourd'hui des logiciels libres et open sources : allant des
    systèmes d'exploitation (GNU/Linux), aux programmes gérant les
    communications en réseau (Apache, Nginx, ou encore OpenSSL). De
    plus, la plupart des usages informatiques peuvent être remplis en
    utilisant des logiciels libres et open sources.

[^44]: Le logiciel libre sert notamment de modèle dans le mouvement de
    l'open science, et des Creatives Commons.

[^45]: Les systèmes respectant la norme UNIX sont encore dominants
    aujourd'hui, notamment dans les entreprises. GNU/Linux, fleuron du
    logiciel libre est également un système d'exploitation compatible
    UNIX.

[^46]: Voir notamment (Lessig 2009) et (Kelty 2008, chap. 9).

[^47]: Le *noyau, *ou *kernel* en anglais, désigne l'ensemble des
    fonctions de base d'un système d'exploitation, et en particulier le
    contrôle et la répartition des différentes ressources, temps de
    calcul, mémoire, périphériques de communication.

[^48]: Kelty analyse notamment le rôle central des logiciels
    gestionnaires de code source dans les pratiques concrètes des
    libristes et plus largement des approches collaboratives du
    développement. Il y aurait beaucoup à développer à ce sujet.

[^49]: « Pourquoi récursif ? Je nomme de tels publics récursifs pour
    deux raisons : d’abord, pour indiquer que ce type de public inclut
    les activités de produire, maintenir et modifier des logiciels et
    des réseaux, en plus des discours que ces activités permettent ; et
    en outre pour suggérer la “profondeur” récursive du public,
    c’est-à-dire les séries de couches techniques et légales – depuis
    les applications jusqu’aux protocoles et jusqu’aux infrastructures
    physiques faites d’ondes et de câbles – qui sont le sujet de ces
    activités de production, maintenance et modification. La première de
    ces caractéristiques est évidente dans le fait que ces geeks utilise
    la technique comme une sorte d’argument adapté à un ordre
    spécifique : ils argumentent à propos de la technique, mais
    également à travers elle. » (Kelty 2008, 29)

[^50]: Dont nous parlerons dans la partie I.3

[^51]: (Hannemyr 1999)

[^52]: (Tedre 2014, chap. 6)

[^53]: La notion de « script » désigne pour Madeleine Akrich le scénario
    fonctionnel et pratique d’un objet technique tel qu’il est reçu par
    un usager (Akrich, s. d.) Dans le cadre d’une activité de
    programmation, on pourrait alors objecter que le hacker se retrouve
    plutôt dans une position de concepteur. <span
    id="anchor-27"></span>Cependant, comme nous le développerons dans la
    partie II.3, il nous apparaît que la plupart des programmeurs en
    tant qu’ils font usage de fonctionnalités qui sont déjà composées et
    abstraites (au sens informatique), c’est-à-dire l’objet d’un travail
    de conception, sont en réalité également des usagers. Ils sont en
    permanence en train d’alterner entre une approche fonctionnelle de
    leurs outils et la dimension fonctionnante (les opérations
    informatiques) qui organise ce qu’ils sont en train de produire. À
    de nombreux égards, nous aurons à détailler comment la posture du
    hacker nous semble brouiller la limite entre conception et
    utilisation.

[^54]: (E. G. Coleman 2013, 98)

[^55]: Cité dans (E. G. Coleman 2013, 98)

[^56]: « Hacking is where craft (savoir-faire) and craftiness (astuce)
    converge ». (Coleman 2012 p98)

[^57]: Le terme est parfois traduit en français par « bidouillabilité »,
    mais nous le transposerons simplement ici par « hackabilité » et
    « hackable ».

[^58]: Bien qu’il soit en principe possible de décompiler le code et
    d’en faire l’ingénierie inverse pour reconstituer un code source
    manipulable. Ce type de pratique est important pour soutenir
    diverses formes de hacking, par exemple pour obtenir plus
    d’informations sur un logiciel ou par exemple dans le contexte du
    logiciel libre pour développer des pilotes et micrologiciels en
    l’absence de coopération du constructeur à fournir des informations
    techniques.

[^59]: Par exemple pour les programmes GNU qui respectent la philosophie
    UNIX : il s’agit une façon d’assigner à chaque fondamentale un
    programme simple et de permettre la combinaison universelle de ces
    programmes élémentaire pour effectuer des traitements plus
    complexes.

[^60]: On peut citer par exemple, le logiciel de modélisation 3D
    Blender, le lecteur de musique Rhythmbox ou encore le navigateur
    Firefox pour lequel il est possible d’écrire des extensions.

[^61]: Voir notamment les multiples conférences de « Console hacking »
    disponibles sur http://media.ccc.de.

### [Sommaire](../01-sommaire)
