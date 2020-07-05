+++
author = "Elie Gavoty"
title = 'La boîte noire, modèle issu de la cybernétique'
weight = 90
subtitle =   'Les hackers face à l’abstraction informatique et une omniprésente disparition du technique.'
date = "2020-07-05"
description = "Les hackers face à l’abstraction informatique et une omniprésente disparition du technique. Mémoire de recherche en histoire et philosophie des science."
tags = [
	"reprogrammer-des-boites-noires",
  "hacking",
  "STS/philotech",
]
+++

Dans un sens historique, la notion de boîte noire fait référence à un
modèle élémentaire qui se traduit en pratique par un type de méthode de
découpage fonctionnel utile dans différents domaines d’ingénierie (en
génie électrique et en informatique notamment). Mais en tant que concept
important de la cybernétique, ce modèle de la boîte noire a été
généralisé à tout type de système et notamment appliqué à la
compréhension du cerveau, du comportement d’acteurs ou d’autres systèmes
complexes de natures diverses.

En effet, les premières occurrences de ce terme en anglais datent de la
Seconde Guerre mondiale, dans le champ du génie électrique. La méthode
d’analyse de la boîte noire consiste à considérer un sous-ensemble d’un
système électrique sans considérer ses composants, mais uniquement du
point de vue de la transformation qu’il opère sur des signaux d’entrée
pour donner des signaux de sortie. Ce terme fait notamment partie de la
culture du Radiation Laboratory (Radlab) du MIT et faisait référence
dans ce contexte aux équipements électriques des radars militaires
(récepteurs, amplificateurs et filtres divers) qui se présentaient comme
des boîtes de couleur noire au contenu inconnu[^124]. Peter Galison
suggère que cette culture du Radlab influença en particulier le
mathématicien Norbert Wiener, souvent considéré comme l’initiateur de la
cybernétique. Ce dernier travaillait durant la seconde guerre mondiale
sur un système de défense antiaérienne expérimental et tentait pour cela
de modéliser les réactions d’un pilote ennemi, sans rien postuler sur sa
psychologie, mais plutôt comme un système échangeant de l’information
avec son milieu. Ce travail de modélisation mettant sur le même plan les
mécanismes de commande d’un système de tir et les réactions d’un pilote
apparaît pour Galison, ce qui amena Wiener à l’une des idées directrices
de la cybernétique, la possibilité d’une science universelle permettant
d’étudier tout type d’entité complexe comme un système qui,
indépendamment de sa nature, est régulé à travers des échanges
d’informations. La boîte noire cybernétique issue de la guerre apparaît
dès lors comme une forme d’ »ontologie de l’ennemi » étranger ou
inaccessible qui finit par inspirer notamment une méthode générale
d’étude du comportement humain.

Hérité de la cybernétique, la boîte noire en tant que modèle en théorie
des systèmes est simple et très général : il s’agit d’abstraire un
système comme un tout indivisible et non local réagissant à des stimuli
selon un ou plusieurs canaux[^125], c’est-à-dire reliant plusieurs
entrées à autant de sorties. On peut modéliser ces couples
stimuli/réponse selon la théorie mathématique de l’information. Ainsi ce
modèle exprime une notion informationnelle de fonction comme
transformation d’un signal d’entrée en un signal de sortie. Elle est
notamment directement pertinente pour décrire d’un point de vue externe
la fonction d’un programme informatique vu comme un artefact de
traitement de l’information (idée que nous développerons plus loin dans
cette partie). Le modèle apparaît cependant vite réducteur lorsqu’il
s’agit de décrire plutôt que des signaux, des interactions matérielles,
voire pratiques, qui ne sont qu’imparfaitement traduisibles
formellement. Plus largement, Mario Bunge et Martin Mahner, comparant
différentes notions de fonctions et attitudes fonctionnalistes, font de
la boîte noire le type d’un fonctionnalisme, radicalement réducteur à
l’activité externe, indifférent au contenu et à la substance[^126] :
dans ce cas deux systèmes sont vus comme équivalents et interchangeables
s’ils manifestent la même fonction.

De plus dans ce modèle les boîtes noires peuvent être composées pour
former une boîte englobante[^127]. L’interchangeabilité et la
*composabilité* font de la boîte noire un modèle adapté à la
décomposition fonctionnelle d’un système en sous-systèmes ainsi qu’au
test des sous-systèmes. En informatique en particulier, la méthode de
test la boîte noire désigne une méthode qui consiste à tester
systématiquement la réponse d’un programme ou d’un sous-ensemble de ce
programme à différentes entrées caractéristiques pour voir s’il se
comporte comme prévu[^128]. Ce type de méthode correspond à ce qu’on
nomme désormais plus communément les tests unitaires.


[^124]:  (Galison 1994)

[^125]:  (Bunge 1963)

[^126]:  (Mahner et Bunge 2001, 82) Ils opposent notamment la fonction
    comme activité externe de la boîte noire à la fonction comme *telos*
    et à la fonction comme adaptation. Une interrogation plus générale
    concernant la notion de fonction technique serait également
    intéressante pour enrichir cette approche en terme de boîte noire.

[^127]:  (Bunge 1963, 357)

[^128]:  (Beizer 1995)


### [Sommaire](../01-sommaire)
