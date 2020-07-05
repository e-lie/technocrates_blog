+++
author = "Elie Gavoty"
title = 'L’interface graphique comme boîte noire au sens constructiviste et sa critique en terme d’hégémonie technique.'
weight = 85
subtitle =   'Les hackers face à l’abstraction informatique et une omniprésente disparition du technique.'
date = "2020-07-05"
description = "Les hackers face à l’abstraction informatique et une omniprésente disparition du technique. Mémoire de recherche en histoire et philosophie des science."
tags = [
	"reprogrammer-des-boites-noires",
  "hacking",
  "STS/philotech",
]
+++


### Interface graphique et interface texte

La notion d’interface graphique désigne de façon générale, les
interfaces permettant d’interagir avec un ordinateur à travers des
éléments visuels (boutons, fenêtres, icônes). Ce type d’interface
s’utilise avec un dispositif d’entrée « spatial », traditionnellement
une souris ou plus récemment une interface tactile, c’est-à-dire qui
permet de se rapporter très interactivement à un espace virtuel (en 2 ou
3 dimensions). De plus, l’interface graphique permet traditionnellement
d’introduire des métaphores ayant pour but de rapprocher les traitements
informatiques d’un modèle conceptuel compréhensible par un utilisateur
non informaticien[^178]. Pour prendre un exemple commun et
paradigmatique, le système d’exploitation Windows s’est développé autour
de la métaphore d’un bureau : l’utilisateur manipule des documents
rangés dans des dossiers et visualise les programmes comme des icônes
évocatrices disposées dans des fenêtres. Les fonctions rassemblées dans
un programme correspondent à un ensemble de fonctionnalités délimitant
un type d’activité se rapportant plus ou moins à un corps de
métier[^179]. Enfin, la disposition spatiale des fonctions permet une
exploration plus spontanée des différentes possibilités fonctionnelles.
On dit que l’interface graphique favorise la *découvrabilité* d’un
environnement informatique.

L’interface graphique s’oppose en particulier aux interfaces textes, ou
interfaces en ligne de commande, qui proposent d’interagir avec la
machine grâce à un langage de commandes. Les systèmes d’exploitation
compatibles UNIX fonctionnent ainsi traditionnellement grâce à une telle
interface. Elles ne sont susceptibles d’afficher que les caractères d’un
alphabet prédéfini plutôt que des éléments graphiques quelconques. On ne
peut donc pas, avec une interface en ligne de commande, représenter très
efficacement des éléments visuels et donc proposer des objets réalistes
et des métaphores auxquels se rapporter en utilisant des intuitions non
informaticiennes.

Ces interfaces en ligne de commande sont plus anciennes et apparaissent
à beaucoup désuètes, ou tout du moins austères et élitistes. On
considère généralement qu’elles ne permettent pas une découvrabilité des
fonctionnalités et une interaction aussi spontanée. En effet, elles ne
permettent pas d’explorer à la souris ou au doigt des listes de
fonctionnalités et d’interagir avec des objets en les manipulant d’une
façon intuitive, car basée sur notre rapport au monde physique. L’usage
de la ligne de commande nécessite de connaître des conventions
(notamment des raccourcis clavier) et de faire preuve d’une démarche
active en mémorisant au moins partiellement les noms des opérations,
malgré leur caractère souvent arbitraire et mystérieux. Il s’agit
également d’anticiper plus précisément ce qu’une commande est
susceptible de réaliser pour éviter d’effectuer des opérations non
désirées. Il est donc nécessaire de connaître certains éléments
fondamentaux du fonctionnement d’un ordinateur. Ces prérequis les
rendent difficiles à aborder pour un usager qui n’est pas familier avec
le mode « linguistique » de l’informatique.

Cependant, ces interfaces présentent d’un point de vue pratique un
avantage notable. Les opérations obéissent à une logique plus
informaticienne[^180] ne s’encombrant pas de métaphores surdéfinissant
cette logique. Elles sont moins abstraites et impliquent une
compréhension plus fondamentale des traitements effectués ce qui amène
plus de contrôle et de flexibilité de la part de l’usager. En effet,
elles sont basées sur une syntaxe qui permet la combinaison logique
d’opérations et l’expression d’algorithmes, c’est-à-dire qu’elles
fonctionnent grâce à des langages de programmation. Ainsi, les langages
de commandes d’une interface texte, par exemple le bash ou csh sous UNIX
ou Powershell sous Windows, permettent d’utiliser la machine en la
programmant.

Cette opposition entre interface graphique et interface en ligne de
commande alimente de nombreux débats dans les collectifs libristes et en
particulier pour ce qui concerne les différentes versions (ou
distributions) du système d’exploitation GNU/Linux : faut-il privilégier
des outils en ligne de commande, simples et programmables[^181] ou créer
des interfaces graphiques pour chaque fonctionnalité c’est-à-dire des
logiciels plus vastes et complexes, mais plus accessibles et
découvrables ? Une grande partie des distributions GNU/Linux ont depuis
le début des années 2000 intégré des interfaces graphiques pour tous les
outils et emportent des suites logicielles finalement assez semblables
en apparence aux logiciels du monde propriétaire, de façon à toucher
également un large public profane. Mais certaines continuent
volontairement à proposer une approche en ligne de commande par défaut,
notamment pour des raisons pédagogiques[^182] ou pour éviter d’imposer
une complexité et une configuration standard qui serait superflue dans
certains cas[^183]. Ainsi de l’avis de certains, le fait qu’il subsiste
certaines tâches réalisables uniquement en ligne de commande constitue
un défaut potentiel pour une distribution GNU/Linux, car cela rehausse
la courbe d’apprentissage pour de potentiels nouveaux utilisateurs.
Pourtant ce prétendu manque reflète généralement le fait que les
développeurs et les utilisateurs compétents qui font ces systèmes
travaillent effectivement, et encore aujourd’hui, en ligne de commande,
car elle favorise le contrôle et la flexibilité.

Bien que ces disputes puissent apparaître anecdotiques, locales à un
monde du logiciel libre minoritaire et divisé, il s’agit en fait d’un
enjeu important. L’ordinateur personnel doit-il dans son usage habituel
être cette machine programmable dans laquelle l’utilisateur est
conscient des traitements effectués et dispose de possibilités infinies
de définir ou d’altérer les conditions de son usage ou doit-il être un
outil plus immédiatement accessible, mais appréhendable à travers des
fonctions et objets préconçus et inaltérables ? Il semble qu’il y ait là
une divergence profonde quant à la façon d’aborder l’informatique. Cette
divergence gagne dès lors à être vue comme une controverse dans le cadre
de laquelle une approche dominante s’est en grande partie imposée et a
défini les termes « objectifs » du débat.

Ainsi comme le relève Kirkpatrick, les théories dominantes de
l’interaction homme-machine, en valorisant avant tout le caractère
« user friendly » (ou dans des termes plus français et récents la
qualité intuitive de l’*expérience utilisateur*), manifestent un
présupposé quant à ce qui constitue le critère pertinent pour le
développement d’une informatique grand public[^184]. En effet, cette
conception de l’accessibilité des ordinateurs s’est développée largement
au détriment de la programmabilité qui constitue pourtant, une des
caractéristiques les plus centrales de l’ordinateur et d’où il tire
notamment sa puissance et sa généricité. Elle constitue, ainsi une
victoire de l’approche non-technicienne et visuelle, qui se fait par
exemple au détriment des mal voyants comme le souligne Kirkpatrick, sur
une approche programmable et linguistique de l’informatique. En cela, ce
paradigme actuel des interfaces graphiques peut être analysé comme
incorporant techniquement une lutte entre divers groupes sociaux dans
leur rapport à l’informatique.

Pourtant, pourrait-on objecter, des études sont menées pour évaluer les
différents choix de conception des interfaces, et s’adapter aux
comportements et attentes des usagers. Dans un article classique
consacré aux tests d’usage (usability trials) organisés par une grande
entreprise logicielle[^185], Steve Woolgar montre comment ces tests, dès
lors qu’ils ne laissent pas les usagers interagir de façon très ouverte
avec le système et cherchent avant tout à dégager un comportement moyen,
entérinent plus qu’ils n’interrogent la pertinence des choix de
conception. Les arguments retenus pour défendre les choix de conception
de l’interface apparaissent alors au moins autant comme une rationalité
partiale produite pour appuyer des orientations dominantes que comme une
démarche pour déterminer une solution adaptée.

Ainsi, pour pouvoir déceler le caractère contingent et paradigmatique de
la tendance actuelle des interfaces graphiques, il s’agit de voir cette
ultime couche d’abstraction comme le résultat d’une construction
sociale, et considérer la façon dont, avec elle, s’impose une
rationalité justificatrice qui l’appuie comme la solution la meilleure
ou la plus naturelle. En d’autres termes, il s’agit analyser l’interface
graphique comme une boîte noire dans le sens proposé par Bruno Latour.

### La boîte noire au sens de Bruno Latour : un processus de réification dans la construction sociale des techniques.

Empruntant la métaphore de boîte noire à la cybernétique, Latour
l’emploie comme une notion centrale dans son livre, désormais classique
*La science en action[^186]*. Elle doit alors être comprise dans le
cadre de la *sociologie de la traduction* (ou *théorie de
l’acteur-réseau*) qui cherche à opérer une sorte de révolution dans
l’étude de la science et de l’innovation technique. Nous ferons dès lors
un détour pour présenter cette approche. Celle-ci opère en effet une
inversion méthodologique importante par rapport à d’autres cadres
théoriques qui, en donnant un statut spécial aux productions
technoscientifiques, leur permettent d’échapper à une compréhension
sociale. Une fois cette révolution opérée, ce ne sont pas les qualités
rationnelles d’une machine ou d’un énoncé technoscientifique qui
permettent d’expliquer son succès et sa diffusion, mais plutôt ces mêmes
qualités qui doivent justement être expliquées comme une dynamique
sociale. Cette démarche répond à une exigence de méthode que l’on peut
rapprocher notamment de la démarche ethnométhodologique : pour rendre
compte d’un processus « le langage de la description scientifique ne
doit pas emprunter ses ressources au phénomène étudié »[^187], ici la
technoscience.

Ainsi, il s’agit de ne pas aborder simplement l’innovation technique
comme la diffusion d’un type d’artefact dans un milieu social du fait de
ses qualités, notamment instrumentales. L’artefact technique n’est pas
simplement un objet produit dans un contexte purement technique puis
confronté à la société. Cela signifie en particulier qu’on ne peut pas
expliquer la genèse de sa forme par des arguments
utilitaristes/fonctionnels dès lors que sa réalité instrumentale se
construit justement durant l’émergence de l’artefact en tant
qu’innovation technique. Par exemple, si l’ordinateur *Eclipse MV/8000,*
étudié par Latour, a pu être perçu à son époque comme une machine
performante et que son choix d’abandonner la compatibilité du jeu
d’instruction[^188] avec les machines précédentes peut être présenté
comme un choix pertinent[^189], en réalité durant sa conception, la
machine n’apparaît pas encore comme un ensemble viable et les choix
faits par l’équipe, extrêmement précaires, auraient aussi bien pu
échouer. Comprendre la logique qui a guidé la conception ce n’est pas
reprendre les arguments finaux qui donnent du sens à l’assemblage, mais
suivre l’évolution mouvante et incertaine de l’ensemble au fur et à
mesure de son élaboration.

En fait dans le cadre de la sociologie de la traduction, le processus
d’innovation technique (tout comme la recherche scientifique) est
analysé comme la construction progressive d’un réseau composé d’actants
hétérogènes, c’est-à-dire à la fois des humains et des non-humains. Ces
éléments s’organisent comme des alliés de circonstances reliés au fur et
à mesure par des opérations de traduction (Latour parle également de
médiations). Pour faire exister l’ordinateur, l’équipe qui le conçoit
doit interpréter les intérêts des patrons, s’arranger avec les
fournisseurs de composants, faire en sorte d’organiser spatialement les
éléments pour qu’ils participent ensemble à la réalisation d’opérations
logiques, faire en sorte que les électrons se comportent correctement à
des échelles microscopiques, et enfin que l’équipe du logiciel puisse
réaliser les opérations virtuelles nécessaires. Les différents éléments
sont enrôlés, ils sont sommés de travailler ensemble, leurs intérêts et
leur identité sont traduits, transformés pour constituer un ensemble
cohérent. Les machines consistent, de ce point de vue, en des
machinations[^190] dans lesquelles chacun des actants se tient. Ainsi,
les usagers veulent communiquer en réseau, les électrons circulent selon
une différence de potentiel, les investisseurs récupérer de la
plus-value, etc.  : le réseau peut tenir solidement.

Les artefacts techniques doivent être compris comme intrinsèquement
sociaux en ce qu’il n’y a rien de plus social que ces réseaux,
assemblages d’actants divers, qui les font exister en tant que réalités
techniques. Ils sont des constructions sociales. Mais, pourrait-on
objecter, il semble toujours possible de distinguer un artefact, objet
physique, comme une entité indépendante de tout milieu social. C’est ici
qu’intervient la notion de boîte noire : elle désigne notamment pour
Latour, cette façon dont les productions de la technique peuvent
apparaître, à l’issue d’un processus de renforcement et de clôture du
réseau comme des objets indépendants et non problématiques.

Lorsqu’un réseau socio-technique est encore incertain, illisible, il
apparaît comme un composé instable. Son identité cohérente, notamment
fonctionnelle, menace à tout moment de disparaître face à des problèmes
de fonctionnement : ainsi l’ordinateur Eclipse, ou tout ordinateur,
avant de pouvoir être simplement allumé et utilisé, a du passer par un
stade où il manifestait tellement de bogues qu’il apparaissait avant
tout comme un ensemble de problèmes à résoudre et non comme un outil. Il
devient une boîte noire dès lors que « l’ensemble des alliés désordonnés
et non fiables que l’on discipline les uns par les autres se transforme
\[…\] lentement en quelque chose qui ressemble à un tout organisé »
(Latour 1989, 321). Les liens qui le font tenir ensemble sont
suffisamment solides, contrôlables pour qu’il apparaisse comme un objet
: l’artefact, comme le dit Andrew Feenberg peut alors devenir un « lieu
systématique » (Feenberg 1999, 201) hors de son cadre d’usage, sans la
médiation qu’il opère, sans les réseaux de dépendances qui lui
permettent de fonctionner, un artefact n’est rien de technique. Il est
technique justement en ce qu’il n’est pas un simple objet, mais un
ensemble de conditions servant de support à un motif instrumental, voire
une connotation et une valeur symbolique particulière (Feenberg 1999,
chap. 3).

Ainsi, la boîte noire désigne chez Latour les systèmes techniques (les
faits scientifiques) en tant qu’ils sont devenus des produits
incontestables, qui peuvent être perçus indépendamment de leur processus
d’élaboration et du réseau qui leur confère justement cette dimension
technique. Le processus de stabilisation est nécessaire pour que l’objet
puisse se diffuser en tant que motif fonctionnel reconnaissable (le
téléphone permet de passer des appels), mais c’est justement le fait de
cette diffusion qui le constitue comme une catégorie technique évidente.
En fait, c’est selon lui la docilité des usagers qui transforme les
machines en objets indiscutables, du fait qu’ils sont repris sans
contestation (Latour 1989, 325).

La notion de boîte noire nous a servi jusqu’ici pour caractériser un
masquage des opérations servant de support au fonctionnement et à la
constitution d’une séparation entre une dimension fonctionnelle et une
dimension structurelle de l’artefact. Dans le contexte de
l’informatique, nous avons pu suggérer que cette notion permettait de
décrire un aspect central du processus d’abstraction et de la façon dont
se construisent les assemblages logiciels. La notion *latourienne* de
boîte noire fonctionne au départ de la même façon. Il s’agit de masquer
une dimension centrale qui fait d’un artefact technique ce qu’il est.
Cependant ce qui est masqué ici c’est le caractère intrinsèquement et
largement médiateur de l’artefact qui loin d’être une mécanique neutre
et isolée manifeste une mise en relations de multiples éléments, humains
et non-humain.

Cette approche de la technique en terme de boîtes noires
socio-techniques semble également très adaptée pour décrire les
écosystèmes informatiques. Les fonctions d’une librairie de
programmation, pour prendre un exemple d’abstraction, opèrent une forme
de traduction des opérations élémentaires en des formes instrumentales
nouvelles. Elle opère ainsi une médiation entre les intérêts du
programme et la logique informatique sous-jacente. En outre, les
abstractions informatiques les plus répandues à différents niveaux (la
compilation d’un langage comme le C, les protocoles réseau, les réseaux
sociaux) sont des boîtes noires également au sens ou les médiations
qu’elles opèrent la façon dont elles s’opèrent n’a plus besoin d’être
interrogée. Bien sûr, de nombreux informaticiens critiquent et peuvent
proposer de nouvelles abstractions, langages, logiciels, mais cette
démarche reste une démarche exceptionnelle. Elles sont le plus souvent
reprises par les développeurs et les usagers comme les formes naturelles
que revêt l’informatique. Si l’on suit ce raisonnement constructiviste,
il s’agit dès lors de considérer que la façon dont ces abstractions
fonctionnent n’est pas la plus viable ou rationnelle, mais au contraire
que c’est en tant que réseaux solides que ces abstractions traduisent de
façon consistante les intérêts des acteurs, produisant une rationalité
associée.

Enfin, l’approche de la sociologie de la traduction, en ce qu’elle évite
de séparer a priori actants humains et non humains est très intéressante
pour analyser les systèmes informatiques. L’existence de nombreux
traitements automatiques, voire manifestant une intelligence
artificielle, font que, en informatique tout particulièrement, une
action non-humaine est souvent équivalente à une action humaine : il est
facile d’écrire un robot envoyant des spams comme le ferait un usager,
explorant (on parle de « crawler » qui servent généralement pour indexer
les pages web) le web, ou essayant automatiquement des mots de passe.
Envisager un système informatique comme un ensemble d’actants en
interaction et intégrant aussi bien les humains que les non humains, est
notamment la piste suivie par (Pieters 2011a) pour proposer une
compréhension des systèmes informatiques mieux à même de décrire les
enjeux de sécurité informatique.

### L’interface graphique hégémonique et l’ambiguïté de la logique de la boîte noire.

Restituer ce caractère construit et social des objets informatiques
permet de mettre en valeur une « flexibilité interprétative »[^191] lors
de leur conception, et ainsi de *dénaturaliser* les lignées techniques
actuelles pour envisager des alternatives. Cette analyse incite dans
notre exemple à critiquer le présupposé que la création d’interfaces
graphiques accessibles et la mise en valeur de la logique informatique
et de la programmabilité des ordinateurs personnels s’excluent
nécessairement.

Dans une approche critique, Graeme Kirkpatrick, suggère que l’interface
graphique s’est développée, depuis les années 90, dans une direction
qu’il qualifie d’hégémonique et indissociable désormais de la forme des
ordinateurs personnels. Cette « nouvelle » approche de l’informatique
s’est construite sur la valorisation d’objet-métaphores, très éloignés
de toute réalité informatique, comme éléments de base du rapport profane
à l’ordinateur[^192]. On peut prendre l’exemple de la métaphore du
bureau précédemment évoquée, mais il semble qu’on pourrait caractériser
ainsi la plupart des environnements informatiques actuels. Il met
notamment en valeur comment ces choix ont été présentés comme une
nécessaire émancipation des contraintes de l’informatique et une lutte
contre son élitisme historique. Pourtant ces interfaces métaphoriques,
et la suppression de la programmabilité qui les accompagne permettent de
créer des environnements conditionnant fortement les usages possibles
d’une machine, sans que l’utilisateur dispose des éléments pour le
déceler et le contester. En effet, les éléments qui la composent, quand
bien même ils ne sont aucunement réalistes en terme informatique, sont
des boîtes noires complètement closes et apparaissent de fait comme la
réalité première de l’informatique. En d’autres termes, l’interface
graphique nous semble constituer une abstraction qui introduit une
coupure pratique plus importante encore que les autres : elle rend
l’informatique des usagers relativement incommensurable avec les
logiques, en particulier algorithmiques et informationnelles, qui
régissent plus fondamentalement les systèmes de traitement de
l’information.

L’idée du PC portée initialement par les hackers « hobbyistes »,
pionniers de l’ordinateur personnel rassemblés notamment au sein du
Homebrew Computer Club[^193], était différente. Ceux de ce groupe[^194]
qui développaient une vision politique de la démocratisation de
l’ordinateur l’envisageaient comme un vecteur d’émancipation dans la
mesure justement où il est une machine programmable et permet ainsi à
l’usager de s’impliquer dans la formation et le contrôle de son
comportement. Cette démocratisation et l’apparition d’Internet, bien
qu’on puisse dans une large mesure la considérer comme émancipatrice, se
sont traduite au contraire en une commodification des logiciels et la
construction d’une forte dépendance des usagers à l’égard de l’industrie
informatique. L’interface graphique est dès lors hégémonique dans la
mesure justement où elle structure cette dépendance en séparant le monde
informatique des usagers fait d’ontologies non programmables et le monde
de l’informatique des développeurs ouvert à la création et la
reconfiguration. Les logiciels libres et leur code accessible ainsi que
les travaux d’ingénierie inverse et de déverrouillages d’appareils
informatiques comme les smartphones ou les consoles, qui sont au centre
des activités hacker aujourd’hui se comprennent en rapport avec ce
besoin de ramener les ordinateurs à leur condition de machines
programmables.

Cependant, les logiciels libres se sont démocratisés justement dans une
certaine mesure, car ils ont pu intégrer des interfaces graphiques les
rendant immédiatement utilisables par les usagers habitués aux systèmes
propriétaires. Le logiciel libre ne se serait probablement pas autant
développé s’il ne s’était pas accordé à certains des paradigmes de
l’informatique commerciale. D’un point de vue libriste, ne vaut-il pas
mieux, effectivement toucher un large public et lui permettre d’utiliser
des logiciels libres formant un écosystème bienveillant, dépourvu de
publicité, de mécanismes de collectes de données et d’intentions de
contrôle des usagers ? Ceci nous amène à réintroduire une nécessité
paradoxale de cette logique de la boîte noire : masquer le
fonctionnement sous-jacent et proposer des catégories informatiques
préconstruites, univoques[^195] et donc aisément identifiables n’est-il
pas dans une certaine mesure inévitable pour permettre la constitution
d’un monde technique ? Concrètement, l’abstraction informatique en tant
que telle, semble constituer aujourd’hui une forme d’organisation
relativement indépassable en informatique.

Ce constat paradoxal d’une certaine nécessité de la logique de la boîte
noire rejoint l’approche d’Andrew Feenberg qui identifie une forme
d’« ambiguïté de la technologie »[^196] : d’une part, dans la lignée de
divers penseurs critiques, en particulier Heiddeger, Marcuse et
Foucault, il s’interroge sur la profonde association entre technologie,
rationalité et domination qu’on associe notamment au développement de la
technocratie. De ce point de vue, le développement technologique
apparaît fondamentalement lié à la définition de *codes techniques* qui
conditionnent les comportements et jusqu’aux catégories à travers
lesquelles se manifeste le monde. Cependant, Feenberg refuse de se
cantonner à une approche exclusivement pessimiste et impuissante de la
technique. Si elle peut apparaître comme une condition radicalement
limitante, elle est également pour lui toujours susceptible de servir
les intérêts de tous les humains. Dès lors que l’hégémonie technique se
met en place dans la façon dont les industries et diverses instances de
pouvoir définissent les *codes techniques* pour imposer les modes
dominants de réception des techniques, il est envisageable de limiter et
inverser ce processus. Pour cela, il propose notamment d’exploiter la
façon dont les artefacts et leurs *codes techniques* peuvent être
redéfinis durant leur appropriation par l’usager et leur mise en société
– c’est-à-dire en exploitant ce qu’il décrit comme leur
*instrumentalisation secondaire – *pour développer une forme de*
rationalisation démocratique[^197].*

Le monde de l’informatique, lorsqu’on le considère comme
fondamentalement (re)programmable ainsi que la façon dont les hackers
dans leur diversité s’en saisissent, laisse entrevoir justement la
possibilité dans ce domaine d’une forme de *rationalisation
démocratique*. La flexibilité de l’informatique facilitée par son
caractère logico-linguistique au niveau logiciel, rend possible une
forme d’« usage-programmation », dont le hacking informatique nous
semble une illustration, qui limite la portée de l’activité de
conception en tant qu’incorporation et institution d’une domination.
C’est notamment, semble-t-il, en cela que le mouvement du logiciel
libre, lorsqu’il institutionnalise une forme de *hackabilité* et cherche
à la mettre à la portée du plus grand nombre, constitue, comme le
suggère Christopher Kelty, une véritable « réorganisation du savoir et
du pouvoir ». Cependant, il nous semble qu’il est de ce point de vue
toujours nécessaire d’être vigilant et de ne pas tenir l’ouverture du
code des logiciels libres pour un aboutissement. Dès lors que des formes
d’expertise indépassables et qu’une séparation entre position d’usager
et position de concepteur demeurent très prégnantes même dans le
contexte du logiciel libre, les progrès vis-à-vis de l’orientation
hégémonique de l’informatique restent précaires.


[^178]:  (Kirkpatrick 2004, 53)

[^179]:  Par exemple, le logiciel Adobe Photoshop, dédié à la retouche
    photographique et traitement d’images numériques proposes de
    nombreuses métaphores (les calques, les filtres) définissant un
    espace d’usage adapté au métier de photographe ou de graphiste.
    Cette critique est développée notamment par l’artiste John Maeda
    (Maeda 2004).

[^180]:  Gestion des processus, combinaison des traitements avec flux de
    textes et autres structures de données fondamentales comme des
    arborescences, gestion organisée des messages d’erreurs, les entités
    rencontrées lors de l’usage de la ligne de commande UNIX sont moins
    abstraites et décrivent directement les traitements informatiques
    sous-jacents.

[^181]:  On fait généralement référence à ce principe sous le nom de
    philosophie UNIX.

[^182]:  Par exemple, Linux from stratch, qui est une distribution à
    compiler et configurer soit même étape par étape.

[^183]:  Par exemple la distribution Archlinux, qui est distribuée dans
    une version minimale dans le but de rester simple et flexible.

[^184]:  (Kirkpatrick 2004, 49)

[^185]:  (Woolgar 1990)

[^186]:  (Latour 1989, 26)

[^187]:  (Quéré 1989, 99)

[^188]:  Les opérations machine évoquées dans la partie II.1.4.

[^189]:  (Latour 1989, 41)

[^190]: (Latour 1989, 23)

[^191]:  Concept développé notamment par (Orlikowski 2000).

[^192]:  (Kirkpatrick 2004, chap. 2 et 3).

[^193]:  Voir (Levy 2013) et (Kirkpatrick 2004, chap. 2).

[^194]:  On peut évoquer en particulier les ambitions de Lee
    Felkenstein, animateur du Homebrew Computer Club.

[^195]:  Par exemple des marques, des noms de logiciels clairement
    identifiables et des métaphores standard.

[^196]:  Notamment (Feenberg 2002, chap. 3) et (Feenberg 1999) ou encore
    (Kirkpatrick 2004, chap. 1).

[^197]: (Feenberg 1999)


### [Sommaire](../01-sommaire)
