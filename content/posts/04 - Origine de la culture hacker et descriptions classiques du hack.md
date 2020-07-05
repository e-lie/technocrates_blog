+++
author = "Elie Gavoty"
title = 'Origine de la culture hacker et descriptions classiques du hack'
weight = 96
subtitle =   'Les hackers face à l’abstraction informatique et une omniprésente disparition du technique.'
date = "2020-07-05"
description = "Les hackers face à l’abstraction informatique et une omniprésente disparition du technique. Mémoire de recherche en histoire et philosophie des science."
tags = [
	"mémoire",
]
+++

## 

Le hacking est une notion délicate à manipuler : elle fascine, car elle
charrie à la fois une part de mystère en tant que forme d’engagement
technique non conventionnel et parallèlement une part de transgression
parfois valorisée, parfois minimisée par ceux qui se revendiquent
hackers. Au-delà d’une image médiatique construite depuis les années
1980[^2] qui assigne souvent le hacker au rôle du magicien informatique
délinquant, la culture hacker manifeste une certaine diversité et une
énergie techno-politique frappante[^3]. Ainsi, il existe de multiples
caractérisations conflictuelles du hacking comme activité et des
qualités qui font le "véritable" hacker, aussi bien chez les acteurs qui
se revendiquent de cette identité[^4] que dans la littérature. En effet,
la culture hacker est ancienne et s'est largement diversifiée. Elle est
traversée par des conflits générationnels[^5] et des divergences
pratiques aussi bien que de culture politique. Enfin, elle est très
stimulante et fait l'objet de nombreuses déclarations d'intention[^6].
Ces tendances participent à un certain flou quant à l'emploi des termes
hacker et hacking.

Nous nous proposons d'aborder dans un premier temps quelques approches
classiques et de présenter rapidement une double origine historique de
la culture hacker. Par la suite, pour donner une image plus actuelle des
pratiques de hacking, nous évoquerons deux « genres »[^7] du hacking qui
polarisent en quelque sorte la culture hacker aujourd'hui : il s'agit du
« cracking » et du logiciel libre. Nous désignerons le plus souvent le
« cracking » comme hacking transgressif ou détournement pour des raisons
que nous développerons dans la partie I.2.3. Le logiciel libre met quant
à lui en avant le hacking comme une pratique de programmation
collaborative.

Ces précisions étant apportées, il semble utile, pour commencer, de
s'intéresser à quelques définitions. Le qualificatif de *hacker* désigne
souvent de façon assez générale un informaticien curieux et
débrouillard[^8] ou plus précisément selon le *Jargon File*, un
dictionnaire classique d'argot hacker :

> A person who enjoys exploring the details of programmable systems and
> how to stretch their capabilities, as opposed to most users, who
> prefer to learn only the minimum necessary[^9].

Cependant, correspondre plus ou moins à cette définition ne suffit pas
pour être considéré comme un hacker. En effet, cette culture est
traversée par un certain élitisme et dans de nombreux cas une forme
particulière de reconnaissance par les pairs est nécessaire pour faire
de quelqu'un un hacker (Jordan 2008, chap. 2). Cette reconnaissance
s'opère sur la base d'un type d'acte particulier, le *hack* qui
manifeste l'ingéniosité, la maîtrise technique voire l'humour de son
auteur. Le hack n’est pas aisé à cerner. En tant que « Graal »(Taylor
1999, 16) recherché par les hackers, il est réputé revêtir un sens
subtil et profond qui défie l'explication[^10]. De façon très générale,
le hack est parfois caractérisé comme une « application adéquate de
l'ingéniosité ». Il traduit la capacité d'agir de façon non orthodoxe et
inventive dans des contextes technologiques et particulièrement
informatiques.

Pour prendre un exemple élégant et humoristique de hack informatique,
présenté par Gabriella Coleman, considérons un court programme écrit
dans le langage de programmation Perl (E. G. Coleman 2013, 93) :

```
#count the number of stars in the sky

$cnt = $sky =~ tr/*/*/;
```

L'objet de cette courte expression est comme l'indique le commentaire
initial de « compter les étoiles dans le ciel ». En pratique, elle
compte littéralement le nombre de caractères astérisque (*) d'un texte
enregistré dans la variable « ciel » ($sky)[^11].

En plus du jeu de mots qui lui donne une connotation humoristique et
poétique, cette expression célèbre la centralité de l'astérisque dans
les systèmes UNIX[^12], et la puissance du langage Perl. En effet, elle
démontre qu'il est possible d'effectuer, grâce à ce langage, un
traitement informatique non élémentaire[^13] en seulement une ligne
grâce à la syntaxe originale du langage qui laisse le programmeur
condenser plusieurs opérations avec un minimum de symboles. Un programme
explicite effectuant la même tâche utiliserait pour ce faire un code
sensiblement plus long[^14]. Le jeu qui consiste à condenser ainsi des
expressions est très répandu dans la communauté des programmeurs Perl et
demande une ingéniosité combinatoire certaine. Par cette simple
expression, l'auteur manifeste une maîtrise importante des détails
techniques du langage de programmation et de l'environnement
informatique. Il élève en quelque sorte, par un acte qui n'est pas
uniquement utilitaire, la programmation au rang de discipline poétique.
Le hack et son rapport intime aux méandres de la programmation
proviennent des pratiques développées par certains informaticiens du
*Massachussets Institute of Technology (MIT)*. Revenons sur cette
origine de la culture hacker.

### <span id="anchor-7"></span>Naissance de la culture hacker au MIT et son éthique

Le sens original du terme *hack* se rapporte en anglais au fait de
couper ou tailler grossièrement (Taylor 1999, 14). Il a été détourné,
dans un premier temps, par quelques étudiants-ingénieurs appartenant au
*Tech Model Railroad Club (TRMC)* (Levy 2013, chap. 1). Au sein de ce
club, organisé autour d'une énorme maquette ferroviaire, les étudiants
chargés de l'ingénierie électrique se prénommaient hacker avec une
certaine fierté. Réparer et étendre cet immense système électrique en
ajoutant de nouvelles routes, des dispositifs de contrôle, en testant et
bricolant les systèmes à partir de matériel récupéré passionnait ces
jeunes, souvent acclimatés à l'électronique depuis l'enfance. L'ensemble
de ces pratiques impliquant beaucoup d'astuces et de capacité à résoudre
des problèmes techniques avec peu de moyens constitue donc en quelque
sorte un ancêtre du hacking en informatique. Les hackers donnaient une
dimension héroïque et esthétique à cette activité technicienne. Steven
Levy relate l'existence de poèmes vantant les exploits des hackers.

Les étudiants "hackers" du TRMC se tournèrent vers les ordinateurs en
1959, à l'occasion de l'ouverture d'un cours d'informatique débutant,
proposé par John McCarthy, pionnier de l'intelligence artificielle. On
peut relever une continuité frappante entre l'électronique et
l'informatique de l'époque. Programmer une machine était un travail très
fastidieux dans un contexte où la mémoire était très limitée et les
opérations utilisées extrêmement élémentaires. Les machines tombaient
également en panne et il fallait souvent intervenir directement au
niveau électronique.

Les hackers développèrent progressivement, au sein du laboratoire
d'intelligence artificielle (*AI lab*), une approche interactive de la
programmation très originale à l'époque. Ils rejetaient le principe du
traitement par lot, symbolisant une vision étriquée de l'ordinateur
comme simple machine à calculs : dans cette approche, les tâches sont
soumises les unes après les autres pour obtenir un résultat, concluant
ou non. Le programmeur ne se confronte alors jamais directement à la
machine. Au contraire, les hackers développèrent des programmes
précurseurs, pour suivre l'exécution des calculs en temps réel et
« déboguer » le programme au fur et à mesure. Ils conçurent également un
des premiers systèmes d'exploitation à temps partagé qui permet à
plusieurs usagers d'utiliser simultanément un ordinateur. Dans ce
contexte, Levy relate divers types de hacks, ayant trait à
l'optimisation des programmes ou encore à des usages innovants de
l'ordinateur pour faire de la musique ou jouer (Levy 2013, chap. 2 et
3).

L’activité des hackers du AI lab répondait à un code informel. Il est
formulé par Steven Levy, à partir d'entretiens avec les protagonistes,
autour de six principes[^15]. D'abord, l'accès aux machines et aux
systèmes doit être libre, car l'exploration par le démontage et
l'analyse est ce qui permet de vraiment comprendre les systèmes (nous
appellerons cet impératif le *principe d'accès direct aux machines)*.
Deuxièmement, l'accès à l'information doit aussi être libre, notamment
l'information technique qui facilite les hacks ultérieurs* *(*principe
de divulgation* *de l'information*). Le troisième principe est la
défiance de toute autorité et la valorisation de la décentralisation de
l'accès à l'ordinateur* *(*principe anti-bureaucratique*). Le quatrième
principe concerne le refus qu'un hacker soit jugé sur autre chose que
les compétences qu'il démontre en pratique et en particulier sur ses
diplômes, son statut ou son âge* *(*principe du mérite par le hack*). Le
cinquième principe souligne la valeur esthétique du hack informatique*
*(*principe esthétique*). Enfin, le sixième principe affirme que
l'informatique peut améliorer la vie ce qui n'a rien d'évident à
l'époque* *(*principe d'utilité générale*).

<span id="anchor-8"></span>Ces principes font implicitement référence
aux activités des hackers et dessinent en négatif les conditions
matérielles et les obstacles, auxquels ils étaient confrontés dans leur
pratique. En effet, comme nous l'avons évoqué, les hackers du MIT ont dû
lutter pour avoir accès à des ordinateurs, rares et surveillés. Le
*principe direct d'accès aux machines* traduit cette difficulté
originelle à pratiquer l'informatique. Mais il ne s'agissait pas pour
eux de se contenter d'une utilisation superficielle et indirecte de
l'ordinateur, d'accéder en somme à du temps de calcul, mais bien de se
confronter directement aux machines à leur interface matérielle (la
console du TX-0) et leur fonctionnement interne. La culture hacker remet
donc en cause, dès le départ, la constitution de l'ordinateur en une
« boîte noire » masquant son fonctionnement pour exhiber un ensemble de
fonctions « magiques ». Ce motif de la boîte noire, de l'abstraction
masquant les détails techniques, est récurrent en informatique, mais
également dans l'architecture de la plupart des techniques. Nous verrons
dans la partie II qu'il traduit un aspect épistémologique central et
ambigu de notre rapport à la technique. Les pratiques hackers sont, de
ce point de vue, à contre-courant d’une attitude dominante face à
l'environnement technologique, car elles valorisent l'attention au
fonctionnement interne des systèmes.

<span id="anchor-9"></span>Accéder aux entrailles d'un système n'est
souvent pas suffisant pour le comprendre, le réparer, l'améliorer. Le
principe que nous désignerons comme *principe de divulgation* affirme
que l'information doit être libre, d'une part, pour faciliter voir
simplement rendre possible l'étude des ordinateurs et des
programmes[^16], mais surtout pour permettre l'utilisation du système.
En effet, dès lors que les programmes informatiques, codés sous forme de
suites de nombres, sont assimilés à de l'information, l'usage même de
l'ordinateur implique de pouvoir accéder à ces outils informationnels.
De plus, au-delà de ces considérations pratiques, les hackers du MIT ont
perçu très tôt, une certaine universalité de l'ordinateur traitant
l'information numérique et perçoivent le monde à travers ce prisme
informatique. De ce point de vue, un libre flux d'information est ce qui
permet d'améliorer le fonctionnement d'un ordinateur et donc également
du monde, perçu comme informationnel[^17]. Ce principe doit, dès lors,
être formulé de façon générale et appliqué le plus largement possible.
Il en résulte des parallèles amusants :

> « To a hacker, a closed door is an insult, and a locked door is an
> outrage. Just as information should be clearly and elegantly
> transported within a computer, and just as software should be freely
> disseminated, hackers believed people should be allowed access to
> files or tools which might promote the hacker quest to find out and
> improve the way the world works. » [^18]

<span id="anchor-11"></span>Le troisième principe est lié à une critique
de la bureaucratie (*principe* *anti-bureaucratique*). Les hackers
abhorrent les systèmes centralisés et hiérarchisés, parce qu'ils forment
des obstacles à l'accès aux ressources et à la circulation des
informations. Ils instituent des règlementations arbitraires entravant
la curiosité hacker. Ils sont plus fondamentalement incapables de
tolérer les pratiques exploratoires qui forment le coeur du hacking. En
effet, ces dernières cherchent toujours à aller au-delà des règles : les
hackers du MIT recherchent une liberté radicale dans la programmation
qui s'accommode mal des limitations légales. De ce point de vue, IBM,
entreprise très largement dominante et hiérarchisée, produisant des
ordinateurs énormes et chers constitue la figure repoussoir contre
laquelle se définissent les hackers dans leur activité[^19].

<span id="anchor-12"></span>Le principe suivant se présente comme une
forme de méritocratie particulière, dans laquelle la source légitime
d'autorité est l'investissement dans le hacking et la capacité à
produire des hacks remarquables. Les hackers valorisent ainsi les
exploits gratuits et un savoir-faire plutôt que les statuts sociaux.
Pour ces passionnés, peu sociables, l'idée de devoir justifier leur
pratique par des diplômes ou une origine sociale pour pouvoir pratiquer
l'informatique est profondément absurde. Ils ont par exemple accueilli
un passionné adolescent, dans ce milieu universitaire, qui a été reconnu
pour son investissement personnel et ses capacités en programmation. Ce
principe central parmi les hackers du MIT semble trouver une
continuation au sein des générations suivantes, en particulier dans
l'idée de « do-ocracy »[^20] structurant aujourd'hui le développement
communautaire de logiciels libres. Nous aurons l'occasion d’y revenir.

<span id="anchor-13"></span>On pourrait considérer le hack musical de
Peter Samson comme un bon exemple d'une démarche artistique associée à
l'ordinateur : il utilisa un petit son de diagnostic, de hauteur
variable, pour jouer un morceau de musique en écrivant un programme
informatique. Mais il serait pourtant erroné d'associer le *principe
esthétique* hacker aux créations artistiques produites grâce à un
ordinateur, selon des critères culturellement indépendants de
l'informatique (la beauté des morceaux de musique numérique dans le
paysage global de la création musicale par exemple). La valeur
esthétique dont il est question ici concerne bien plus profondément les
activités de la programmation et du hacking sur leur versant d'abord
informatique et technologique[^21]. Ainsi pour les hackers, le code d'un
programme possède une qualité esthétique propre, liée en particulier aux
astuces sur lesquelles il s'appuie, à sa taille réduite au minimum, à la
maîtrise algorithmique et la connaissance de la machine qu'il manifeste.
Dans le contexte technique dans lequel opère les premiers hackers,
c'est-à-dire avec un ordinateur comme le TX-0, peu performant et
disposant de très peu de mémoire pour stocker les programmes, le fait de
pouvoir écrire un programme avec le moins possible d'instructions est
très intéressant : disposer d'un programme court permet de charger plus
de programmes en même temps et une exécution plus rapide. *Hacker
*consistait alors par exemple à mettre toute son astuce au service de
l'économie d'instructions du programme.

<span id="anchor-14"></span>Ce critère n'est plus valable de la même
façon aujourd'hui, alors que la mémoire disponible sur les ordinateurs
est très importante, largement suffisante pour charger tout code
nécessaire. On peut cependant retrouver des critères de valorisation de
la concision du code, notamment dans le conflit entre les hackers
amateurs du langage *Python* et ceux préférant le langage *Perl*. Alors
que le premier est volontairement très explicite et formaté pour
favoriser la lisibilité, le second permet des raccourcis et
comportements implicites qui rendent possible de puissantes expressions
extrêmement concises. Cependant, il est alors difficile de comprendre le
déroulement algorithmique, ce qui rend le code en *Perl* moins adapté à
un environnement collaboratif. On peut dire que le langage *Perl* est
plus adapté à l'exploit individuel du programmeur et aux
expérimentations esthétiques sur le code alors que le langage *Python* a
été créé pour favoriser le partage et la transparence. Plus
généralement, cette valorisation collective d'une esthétique du hack et
en particulier du code informatique, manifeste une mise en culture
d'activités techniques traditionnellement très professionnalisées et
utilitaires. La valorisation esthétique s'hybride alors avec des
considérations, notamment fonctionnelles, que l'on fait habituellement
appartenir à un tout autre ordre de valeur.

<span id="anchor-15"></span>Enfin, le dernier principe affirme que
l'ordinateur peut améliorer la vie humaine. L'informatique est
aujourd'hui ubiquitaire, au point que nous ne sommes plus que très
partiellement conscients au quotidien du rôle des ordinateurs et des
diverses fonctions qu'ils remplissent pour nous faciliter la vie. Dans
les années 60, au contraire, les ordinateurs étaient présents
principalement aux États-Unis et considérés comme des machines très
spécialisées, utiles dans quelques branches professionnelles, pour le
calcul scientifique en particulier. Sans imposer aux autres comme une
évidence cette intuition d'une utilité très large de l'ordinateur, à une
époque où les ordinateurs étaient de fait inaccessibles pour l'immense
majorité des gens, les hackers ont vu leurs vies effectivement
transformées par les premiers ordinateurs. Cette confiance dans
l'intérêt de ces machines et dans l'utilité générale des solutions
informatiques a amené les hackers de la génération suivante à défendre
la démocratisation de l'ordinateur.

### <span id="anchor-16"></span>Hack et Phreaking

Le hacking ne concerne pas nécessairement l'informatique. Il peut
s'appliquer à de nombreux systèmes technologiques, voir par analogies à
de nombreuses situations pratiques(Taylor 1999, 17). En outre, il
manifeste souvent une dimension transgressive, voire illégale, centrale
dans la culture hacker. Sherry Turkle, dans une tentative classique pour
illustrer les caractéristiques s'intéresse à un autre type de pratique,
le *phreaking*. Il s'agit d'une forme de piratage téléphonique, qui
consiste pour ses pratiquants à débloquer certaines fonctions de
contrôle du réseau, par divers procédés, en particulier grâce à
l'utilisation des « phreaking boxes »[^22] . Le hack étudié par Turkle,
initié par un phreaker célèbre nommé *Captain Crunch,* consistait à
l'aide d'une paire de téléphones et d'une « blue box » à déclencher une
série d'appels internationaux en piratant le réseau. Ensuite lorsqu’il
parlait dans l'un des combinés, on entendait sa voix dans le second avec
un délai important indiquant que l'appel venait d'effectuer le tour du
monde.

«  Appreciating what made the call around the world a great hack is an
exercise in hacker aesthetics. It has the quality of \[a\] magician’s
gesture: a truly surprising result produced with ridiculously simple
means. Equally important: Crunch had not simply stumbled on a curiosity.
The trick worked because Crunch had acquired an impressive amount of
expertise about the telephone system. That is what made the trick a
great hack, otherwise it would have been a very minor one. Mastery is of
the essence everywhere within hacker culture. Third, the expertise was
acquired unofficially and at the expense of a big system. The hacker is
a person outside the system who is never excluded by its rules. »[^23]

Ainsi selon Turkle, le hack est un acte de détournement qui combine la
simplicité, une maîtrise manifeste d'un système technique complexe, et
une dimension de transgression des règles imposées par « le système ».
Plus largement, comme le présente Gabriella Coleman, la communauté
*phreaker* et sa proximité avec le mouvement politique des *Yippies*
dans les années 70 constitue l'une des origines des positions politiques
de critique radicale du système, caractéristiques du c*omputer
underground* hacker jusqu'à aujourd'hui (G. Coleman 2012).

Les travaux désormais classiques de Steven Levy et Sherry Turkle datent
de 1984 et l'informatique a beaucoup évolué depuis avec notamment
l'apparition de l'ordinateur personnel et d'Internet. Les hackers ont
d'ailleurs joué un rôle important dans ces innovations[^24]. Il s’agit
dès lors de s’intéresser aux formes plus contemporaines de cette
culture. Pour cela, Tim Jordan propose de comprendre la dynamique du
hacking au niveau pratique en mettant en regard les pratiques de
développement collaboratif portées par le mouvement logiciel libre et
les pratiques transgressives du computer underground. Bien que cette
catégorisation classique soit contestable(G. Coleman et Golub 2008
Introduction), elle nous semble correspondre à une perception répandue
de l’héritage hacker. Nous la reprendrons donc dans le but notamment de
la questionner.



[^2]: (Thomas 2002, xiv‑xv)

[^3]: Plusieurs séjours au *Chaos Communication Congress*, convention
    hacker allemande parmi les plus populaires du monde ont achevé de
    nous en convaincre.

[^4]:  Coleman relève que les hackers sont constamment en train de
    débattre du sens des termes hacker et hacking. (E. G. Coleman 2013
    Introduction)

[^5]:  (Taylor 1999, 25)

[^6]: Par exemple, Mc Kenzie Wark (Wark 2009) fait des hackers une
    nouvelle classe virtuelle révolutionnaire.

[^7]:  (G. Coleman et Golub 2008)

[^8]: La culture hacker est traditionnellement une culture très
    masculine, ce qui est relevé par plusieurs sociologues, notamment
    (Taylor 1999, 34). Notre choix d'utiliser le masculin neutre, bien
    que très habituel, invisibilise les femmes hacker. Il nous semble
    important de préciser qu'il existe aujourd'hui des groupes hacker
    féminins et féministes et queer politiques qui luttent en
    particulier contre le sexisme au sein de cette culture. Illes
    cherchent à se réapproprier ses codes et rendre les groupes et
    espaces hackers moins excluants pour les femmes et personnes
    transgenres.

[^9]: « Une personne qui aime explorer les détails de systèmes
    programmables et les façons d'étendre leurs capacités, contrairement
    à la plupart des utilisateurs qui préfèrent eux, apprendre le
    minimum nécessaire. » Traduction de l'auteur. Entrée du Jargon File,
    citée dans (Söderberg 2011, 22).

[^10]: (Taylor 1999, 14)

[^11]: C'est-à-dire un emplacement de mémoire, qui permet de stocker une
    information durant l'exécution du programme et auquel le programmeur
    donne un nom.

[^12]: L'astérisque, omniprésente dans les commandes UNIX, est utilisé
    pour désigner une chaîne de caractère quelconque dans une
    expression.

[^13]:  Tâche qui habituellement nécessiterait au moins un télescope et
    un temps conséquent...

[^14]: (E. G. Coleman 2013, 93‑94). Le programme explicite équivalent
    pour être exprimé en 9 lignes comme suit :
    ```
    $cnt = 0;
    $i = 0;
    $skylen = length($sky)
    while ($i < $skylen) {
        $sky = substr($sky,0, $i) . ‘*’ . substr($sky, $i+1,
        length($skylen));
        $i++;
    }
    $cnt = length($sky);
    ```

[^15]:  (Thomas 2002, 10), (Levy 2013, chap. 2).

[^16]:  Pour quiconque ayant déjà eu affaire à un programme en langage
    d'assemblage (voir II.4 pour un exemple), il est clair que le code
    seul n'est pas du tout explicite quant à sa fonction et même son
    organisation. Généralement, la pratique de programmation nécessite
    énormément de commentaires (informations destinées à l'humain
    présentes dans le code) et de coopération de la part des différentes
    personnes impliquées, d'autant plus dans un langage comme
    l'assembleur qui est très verbeux et très peu explicite. Dans ce
    contexte, on imagine aisément qu'une l'ouverture informationnelle
    est vitale.

[^17]: <span id="anchor-10"></span> (Levy 2013, chap. 2)

[^18]:  « Pour un hacker, une porte fermée est une insulte, une porte
    verrouillée est un affront. De la même façon que l’information
    devrait être clairement et élégamment transportée à l’intérieur d’un
    ordinateur, et que le logiciel devrait être librement disséminé, les
    hackers croyaient que chacun devrait être autorisé à accéder aux
    fichiers ou aux outils qui pourraient faciliter la quête hacker pour
    améliorer la façon fonctionne le monde. » (traduction de l’auteur)

    (Levy1984 chap. 5) édition originale de (Levy 2013).

[^19]:  (Levy 2013, chap. 2)

[^20]:  La *do-ocracy* désigne une forme d'organisation, d'orientation
    libertaire, dans laquelle toute personne tire la légitimité
    d'entreprendre collectivement dans l'action même de l'entreprise et
    dans son investissement personnel qui bénéficie à la communauté.
    Voir par exemple [https://communitywiki.org/wiki/DoOcracy](https://communitywiki.org/wiki/DoOcracy).

[^21]:  (Levy 2013, chap. 2)

[^22]: Voir notamment la liste des différentes boîtes :
    [http://www.elfqrin.com/docs/hakref/phrkbox/phreakboxes.php](http://www.elfqrin.com/docs/hakref/phrkbox/phreakboxes.php)
    (consulté le 9 août 2016).

[^23]: « Apprécier ce qui a fait de cet appel autour de la terre un
    superbe hack est un exercice d'esthétique hacker. Il a la qualité du
    geste de magicien : un résultat vraiment surprenant produit par des
    moyens ridiculement simples. Et chose tout aussi importante, Crunch
    n'a pas simplement exploité une curiosité. L'astuce fonctionne, car
    Crunch avait acquis une expertise importante du système
    téléphonique. C'est ce qui fait de cet acte un hack significatif.
    Sans cette expertise, il n'aurait été qu'un hack mineur. La maîtrise
    est l'essence omniprésente de la culture hacker. Troisièmement,
    cette expertise a été acquise aux dépens d'un système dominant. Le
    hacker est une personne hors du système qui n'est jamais exclue par
    ses règles. » (Turkle 1984, 232) cité dans (Taylor 1999, 16).

[^24]: <span id="anchor-17"></span><span id="anchor-18"></span>C'est
    l'un des propos central de (Levy 2013).


### [Sommaire](../01-sommaire)
