+++
author = "Elie Gavoty"
title = 'La posture du hacker en informatique comme rétablissement d’un lien pratique avec la réalité opératoire d’un programme par delà l’abstraction.'
weight = 86
subtitle =   'Les hackers face à l’abstraction informatique et une omniprésente disparition du technique.'
date = "2020-07-05"
description = "Les hackers face à l’abstraction informatique et une omniprésente disparition du technique. Mémoire de recherche en histoire et philosophie des science."
tags = [
	"reprogrammer-des-boites-noires",
  "hacking",
  "STS/philotech",
]
+++

Le rôle d’un développeur est de faire usage des abstractions que sont
les opérations du système d’exploitation (gestion de la mémoire par
exemple), le langage de programmation (permettant de décrire un
algorithme de traitement des données de façon commode) et éventuellement
des librairies de fonctions prédéfinies pour en produire une nouvelle,
le programme proposant des fonctionnalités spécifiques. Dans le même
sens, le rôle d’un administrateur système est de rassembler, configurer
et maintenir un ensemble de programmes pour fournir un système adéquat à
un usage spécifique. Ainsi avec ce découpage structurant
(informatiquement et sociologiquement) des systèmes informatiques qu’est
l’abstraction, il s’agit habituellement toujours d’aller des niveaux les
plus bas vers les niveaux supérieurs. L’activité de l’informaticien se
doit en quelque sorte, d’un point de vue utilitariste, d’être
constructif : si un artefact informatique (que ce soit une application,
une librairie, un programme utilitaire) existe déjà pour remplir une
fonction requise, il s’agit de l’utiliser et, s’il ne convient pas tout
à fait, d’en produire un autre plus adéquat. Ainsi, une fois qu’une
couche d’abstraction est établie et testée, elle n’a plus de raison
d’être réinterrogée quant à sa réalisation. Dans ce schéma, on est donc
toujours producteur ou usager d’une boîte noire, ou simultanément usager
de boîtes noires et concepteur pour en produire une de niveau supérieur,
utilisant les précédentes comme fondation. Les notions d’usager et de
concepteur dépassent ainsi ici, dans un cadre informatique découpé en de
multiples couches d’abstraction, ce que l’on désigne habituellement
comme usager et concepteur essentiellement séparé par une division
professionnelle. De façon plus générale, être usager implique le fait de
se rapporter à une couche d’abstraction « par le dessus » comme à un
ensemble fonctionnel, même si l’on est un professionnel de
l’informatique en train de construire ou configurer une nouvelle
interface. Le concepteur est caractérisé par le fait de définir une
nouvelle abstraction, c’est-à-dire un nouvel artefact destiné à
d’autres.

Notre exemple d’injection mémoire illustre dans un cas typique, le fait
qu’un hacker lorsqu’il cherche à exploiter un système manifeste un
rapport différent à l’abstraction informatique. Le mouvement depuis
l’identification d’un vecteur jusqu’au développement de la méthode
d’exploitation s’opère au départ en sens inverse, depuis les
abstractions auxquelles est confronté l’usager vers les opérations de la
couche inférieure. On peut considérer qu’il s’agit d’un mouvement de
contournement, car l’objectif final est malgré tout généralement
d’altérer la réalité aux niveaux supérieurs : par exemple obtenir un
accès à un système sans passer par un mécanisme d’authentification ou
encore modifier un micrologiciel pour pouvoir éviter les verrouillages
introduits par le constructeur d’un appareil.

Ainsi la posture transgressive du hacker implique dans un sens général
une subversion de cette division entre la position de réception de
l’usager et celle du concepteur qui articule pour d’autres une nouvelle
interface structure/fonction, et donc un nouvel ensemble de
fonctionnalités. En effet, même si l’on considère, comme Madeleine
Akrich[^166] que l’usager est actif dans sa réception en tant qu’il
interprète le script d’un artefact de façon potentiellement différente
de ce qu’avait prévu le concepteur, qu’il dispose en ce sens d’une
liberté tactique[^167], il est rarement à même de transformer
radicalement les conditions pratiques qu’impose cet artefact, comme le
manifeste souvent les détournements informatiques. De l’autre côté le
concepteur est caractérisé par l’activité stratégique de définir une
interface pérenne, qui devra pour exister s’imposer comme une innovation
et qui conditionnera ainsi les possibilités d’action de ses potentiels
usagers. Au-delà de cette logique le hack est un acte temporaire qui ne
vise souvent la production d’aucun script fonctionnel et ne nous semble
pas en cela supporter une démarche innovante au sens strict (créatrice
certes, mais sans processus d’institutionnalisation)[^168].

En outre, cette approche éclaire à nouveau la continuité du hacking
lorsqu’il fait référence à des pratiques de détournement et de
déverrouillage de systèmes et lorsqu’il désigne une activité de
développement informatique, par exemple dans le mouvement du logiciel
libre. Pour caractériser le rapport hacker à la programmation[^169],
Gisle Hannemyr introduit une distinction significative entre attitude
holiste et fragmentée/réductionniste :

> « While the industrial ideal is to **treat such components** as ‘**black boxes**’, of which nothing needs to be known except how to **interface to** it—hackers generally like to have a **complete understanding** of the systems they work on, including the **components contributed by others**…the difference between the hackers’ approach and those of the industrial programmer is one of outlook: between having an **integrated** and **holistic attitude** towards the creation of artifacts, and having a **fragmented** and **reductionist** one. » [^170]

Il semble que ce soit le même rapport holiste à l’informatique qui est à
l’origine de la possibilité de trouver des failles dans un système et de
les exploiter. Ainsi, après avoir fait un détour par l’abstraction
informatique et la logique de la boîte noire, il nous est possible de
proposer une façon plus précise de comprendre cette opposition
qu’exprime Hannemyr entre une attitude fragmentée et réductionniste et
une attitude holiste.

Le découpage de l’informatique en abstraction dessine dans chaque cas
une limite, qui varie selon la position de chacun, entre les logiques
opératoires à connaître et celles qu’il est inutile de considérer
puisqu’elles ont déjà été encapsulées et traduites en termes
fonctionnels. Un utilisateur final d’un ordinateur sera ainsi confronté
à un écosystème logiciel proposant un ensemble d’interfaces graphiques
et d’objets métaphores lui permettant d’effectuer tel ou tel traitement
qui lui sont suggérés[^171]. Il aura à saisir un ensemble d’opérations
déterminant certaines possibilités, mais uniquement dans un cadre
délimité plus ou moins solidement[^172] par les développeurs. Mais de
plus, chaque développeur agit également dans un cadre d’opérations
clairement délimitées correspondant à son corps de métier : s’il est
chargé du développement d’une partie d’un logiciel, il n’aura qu’à se
préoccuper de la logique de cette partie à un niveau d’abstraction
particulier. Bien sûr, les bons professionnels sont souvent ceux qui
sont capables de s’appuyer sur une compréhension plus fondamentale de la
réalisation de leurs logiciels. Cependant, considérer les abstractions
non seulement à travers leurs interfaces, mais d’abord à travers les
opérations qui les concrétisent demeure une démarche exceptionnelle dans
un contexte où l’objectif d’une construction informatique réussie
consiste à la production d’une boîte noire qui incite (dans le cas d’un
logiciel à sources ouvertes) ou force (dans le cas d’un logiciel fermé)
à oublier cette réalisation.

On comprend au contraire qu’une attitude holiste consiste d’abord à ne
pas se contenter de la promesse fonctionnelle que nous fait l’artefact,
mais de s’autoriser à rétablir un rapport avec les opérations qu’il
encapsule. Dans la culture hacker, cette attitude se traduit par un
intérêt particulier[^173] pour les détails techniques du fonctionnement
d’un ordinateur, qui sont considérés comme des informations
inintéressantes par la plupart des utilisateurs voir des informaticiens.
Mais il s’agit également de considérer que les connaissances
véritablement valorisées dans le cadre de la culture hacker sont celles
qui ne se trouvent pas dans les manuels et documentations techniques,
mais résultent de l’exploration, de la confrontation avec le système
dans des contextes limites[^174]. Entre le comportement annoncé et les
comportements réels d’un système, il y a souvent un écart que même les
concepteurs ne sont pas toujours à même de mesurer. Ainsi, dépasser,
dans une attitude holiste, le découpage fonctionnel en terme
d’abstraction des systèmes informatiques correspond au rétablissement
d’un rapport à des domaines d’expérience habituellement négligés. Par
exemple, s’intéresser aux comportements résultants d’un débordement de
tampon implique d’aller explorer un domaine d’exécution qui est
habituellement considéré comme relevant du bogue informatique,
c’est-à-dire par définition au-delà de ce qui est appréhendable en terme
de fonctionnalité. Les hacks de systèmes informatiques révèlent et
exploitent ainsi une réalité opératoire qui semble en excès par rapport
son identité fonctionnelle.

De ce point de vue, la subversion d’une logique fonctionnaliste de la
boîte noire telle qu’elle est mise en valeur par diverses pratiques de
hacking nous semble pouvoir être saisie en lien avec une appréhension
*pragmatiste* de la technique. Elle correspond en quelque sorte au
rétablissement d’une forme de rapport pratique (caractérisé par
l’expérience et l’enquête) aux systèmes informatiques en lieu et place
d’un rapport pragmatique (caractérisé par la recherche fonctionnelle de
l’utilité). Pour aborder cette distinction, nous empruntons à Roberto
Frega une partie de sa clarification épistémologique de l’approche
*deweyienne* [^175]. La pensée pragmatique appréhende ses objets et leur
signification à travers les effets recherchés : dans notre cas c’est la
fonction déterminée par le comportement externe de la boîte noire qui
définit l’identité d’un logiciel, d’un objet virtuel et d’une
abstraction. Au contraire, la pensée pratique (pragmatiste) détermine
ses objets et leur signification en suivant les conséquences d’une
action, c’est-à-dire à travers une confrontation avec ce qui est
produit : dans notre contexte informatique, il s’agit d’un point de vue pratique
de considérer la réalisation des abstractions informatiques en terme
d’opérations, à différents niveaux, afin de les saisir pour ce qu’elles
sont fondamentalement.

Finalement, l’impuissance face aux déterminations imposées par notre
environnement technique relevée par Tim Jordan et par opposition à
laquelle se construit selon lui un tempérament hacker[^176] apparaît
ainsi comme la conséquence d’une tendance pragmatique à accepter les
objets techniques tels qu’ils sont codifiés fonctionnellement. La
dimension subversive de la culture hacker peut dès lors apparaître comme
directement liée aux tentatives (la valorisation d’un motif tel que le
hack notamment) de maintenir un rapport radicalement pratique[^177] à un
outil aussi riche que l’ordinateur.

Mais notre approche des artefacts informatiques en particulier en
reprenant les termes de l’informatique elle-même montre ses limites
lorsqu’il s’agit d’interroger la dimension sociale et politique du
hacking. Il est notamment difficile d’envisager en ces termes,
c’est-à-dire en suivant une rationalité technologique spécifique, la
dimension radicalement contingente de certains choix techniques, les
rapports de forces et de pouvoir qui traversent la genèse des réalités
informatiques particulières auxquelles nous avons affaire. Autrement
dit, afin de prolonger la notion de boîte noire jusqu’à présent
convoquée sur un plan plutôt techniciste, il nous paraît important de
l’aborder sur son versant constructiviste (la boîte noire *latourienne*)
et critique (la boîte noire participant d’une logique hégémonique chez
Andrew Feenberg).

[^166]:  (Akrich, s. d.)

[^167]:  Au sens proposé par Michel de Certeau.

[^168]:  Ce point mériterait d’être amplement développé : il s’agit ici
    d’une référence au cadre d’analyse de la sociologie de la traduction
    dans le but d’en manifester une limite : elle est difficilement
    susceptible d’accorder une positivité à la démarche du hack en tant
    qu’elle décrit avant tout les processus de création technique comme
    innovation c’est-à-dire d’une forme institutionnalisation (au sens
    de Merleau-Ponty ) de la médiation technique (Guchet2005).

[^169]:  Comme nous l’avons rapidement évoqué dans la partie I.2,
    Hannemyr analyse notamment la transformation de l’organisation du
    développement avec l’introduction d’une approche d’ingénierie.

[^170]:  (Hannemyr 1999)

[^171]:  Pour une présentation critique de la logique de l’interface
    graphique : voir partie II.6.

[^172]:  Certains systèmes sont plus ou moins faciles à hacker et
    détourner. Pour donner un cadre d’usage particulièrement renforcé,
    on peut s’intéresser aux consoles récentes de jeux vidéo : il est
    assez impressionnant de constater la quantité de verrouillages et de
    chiffrements ajoutés par le constructeur pour empêcher toute
    ingénierie inverse et déverrouillage (voir par exemple
    [la conférence "console hacking 2013"](https://media.ccc.de/v/30C3\_-\_5290\_-\_en\_-\_saal\_2\_-\_201312272030\_-\_console\_hacking\_2013\_-\_sven\_-\_marcan\_-\_nicholas\_allegra\_comex)).
    Si autant d’efforts sont consentis, c’est que l’enjeu économique est
    de taille : empêcher la distribution parallèle de copies des jeux
    vidéo. Dès lors que la console est un ordinateur, il est en quelque
    sorte possible par défaut de l’utiliser pour exécuter un code
    arbitraire et l’ajout de nombreux mécanismes de signature des codes
    exécutables permet de garantir que la machine n’exécutera que des
    programmes officiels. Cependant cette difficulté du hack de console
    attire des équipes de hackers passionnés par cette compétition avec
    les fabricants. Ainsi, au Chaos Communication Congress des
    conférences intitulées console hacking se déroule presque chaque
    année. Plus largement, la confrontation entre les hackers et les
    consoles de jeux vidéo est au cœur de l’histoire de cette culture et
    notamment des scènes démo dans différents pays. Voir notamment
    (Alberts et Oldenziel 2014).

[^173]:  (E. G. Coleman 2013, chap. 1)

[^174]:  (Auray 2002), montre notamment en quoi l’overclocking
    (c’est-à-dire déblocage de la fréquence nominale de fonctionnement)
    de processeurs pratiqué par certains hackers qu’il a rencontré,
    consiste pour eux en une confrontation aux comportements extrêmes du
    processeur au-delà des limites explorées par le constructeur.

[^175]:  (Frega 2006, 63)

[^176]:  (Jordan 2008, chap. 1 et Conclusion)

[^177]:  L’approche de Sennett (Sennett 2008), qui qualifie les hackers
    d’artisans et développe cette notion d’artisan de façon très
    générale s’inscrit dans une approche pragmatiste. Une telle approche
    pragmatiste du hacking nous paraît assez riche et mériterait un
    développement.

### [Sommaire](../01-sommaire)
