+++
author = "Elie Gavoty"
title = 'Hacking, sécurité informatique et construction d’une figure déviante'
weight = 93
subtitle =   'Les hackers face à l’abstraction informatique et une omniprésente disparition du technique.'
date = "2020-07-05"
description = "Les hackers face à l’abstraction informatique et une omniprésente disparition du technique. Mémoire de recherche en histoire et philosophie des science."
tags = [
	"mémoire",
]
+++


Depuis les années 90, les activités de
pénétration dans les systèmes informatiques, généralement à travers
Internet, attirent l’attention médiatique et sont devenues la face la
plus connue et spectaculaire du hacking[^62], éclipsant les autres types
de pratiques[^63]. Nous commencerons par nous intéresser techniquement à
ces pratiques de pénétration.

De plus à l’époque, ces activités inédites sont rapidement considérées
comme illégales et lourdement punies[^64]. On les associe à des figures
de hackers délinquants dont certains sont devenus célèbres, provoquant
souvent une certaine fascination. L’une des personnalités marquantes de
cette période et l’une des plus intéressantes politiquement est Kevin
Mitnick. Enfermé pour ses délits informatiques pendant une durée
exemplaire, il revendique son identité de hacker et a participé à
rassembler politiquement la communauté du « computer underground ».
Pourtant au sein d’autres groupes de la culture hacker, cette identité
lui est déniée, notamment en invoquant des raisons éthiques.

Il s’agira alors d’aborder ce conflit, traduit dans l’opposition
*hacker* légitime et *cracker* comme un processus de construction de
déviance, dont la signification politique dépasse le cadre de la culture
hacker. Le champ de la sécurité informatique peut alors apparaître sous
un jour plus complexe et politique, ce qui permet en particulier de
mieux comprendre la teneur de congrès *hackers* tels que l’historique
*Chaos Communication Congress*[^65].

### <span id="anchor-30"></span>Pénétration informatique<span id="anchor-31"></span>

<span id="anchor-32"></span>Que recouvrent techniquement les pratiques
de pénétration informatique (computer break in) souvent associées au
hacking ? On présente* *généralement ces problématiques en introduisant
une métaphore de la faille de sécurité, une sorte d’interstice dans les
murs électroniques du réseau, qui serait habilement exploitée par les
hackers (Jordan 2008, chap. 2). Cette métaphore, bien que pertinente à
certains égards reste assez mystérieuse. Avec cette image, il est
notamment difficile de comprendre pourquoi des possibilités de
détournement/pénétration existent dans les systèmes, sont fréquentes,
invisibles, et ne peuvent être facilement comblées a priori. Une façon
plus précise d’aborder cette idée de faille est d’imaginer qu’il s’agit
de faire sortir un système informatique du champ de son fonctionnement
habituel en le soumettant à des cas d’interactions extrêmes et
soigneusement choisies[^66]. Généralement, ces cas non gérés se
traduisent par un bogue ou arrêt brutal du système (crash). Trouver une
faille consiste dès lors à identifier l’un de ces cas extrêmes qui, à
cause d’un manquement dans le travail de programmation ou simplement à
cause de la structure incomplète d’un système, permettent un
détournement de son fonctionnement, tel que ce dernier a été défini par
ses concepteurs, administrateurs et/ou propriétaires. Il existe une
grande diversité[^67] de failles et plus largement de vecteurs de
détournements/attaques[^68] possibles. Pour introduire plus concrètement
une technique d’exploitation de faille de sécurité à travers Internet,
prenons un exemple élémentaire utilisant une technique classique,
l’injection SQL dans un site web.

Plus que des pages statiques écrites une fois pour toutes, les sites web
actuels sont souvent en réalité des applications web c’est-à-dire des
programmes complexes qui génèrent les pages web en fonction (1) des
requêtes de l’utilisateur et (2) des données accumulées lors de
précédentes interactions. Ces données sont stockées dans une base de
données, c’est-à-dire un logiciel qui les organise de façon complexe et
structurée. Pour récupérer des données dans une base, il s’agit d’écrire
une requête, à la syntaxe précisément formalisée, qui définit quel
sous-ensemble de toutes les données du site web il s’agit de récupérer.
Ces requêtes sont généralement formulées selon le langage standard SQL.
Par exemple, la requête « *SELECT \* FROM users WHERE name = 'bob' ;* »
récupère l’ensemble des informations (traduit par le symbole « \* »)
concernant l’utilisateur « *bob »* contenues dans le tableau « *users* »
de la base de données. Lorsqu’on charge une page web, on interroge un
serveur qui se charge d’écrire la page web avant de la renvoyer. Durant
le processus, il s’agit notamment de chercher automatiquement (avec une
requête SQL) les informations dans une base de données et de les
afficher correctement sur la page.

Imaginons maintenant que cette page soit construite en fonction d’une
requête personnalisée par l’utilisateur : on lui demande par exemple
d’entrer son nom dans un champ et c’est la valeur de cette entrée qui
sera utilisée pour récupérer les informations adéquates et les afficher
sur la page. Si l’utilisateur fournit le nom « bob » et son mot de
passe, les informations correspondantes seront récupérées. Mais
imaginons qu’il entre à la place de son nom la phrase suivante « ' OR
'1'='1' -- ». Si aucune mesure de sécurité particulière n’a été
prise[^69], le programme chargé de construire la page remplacera le nom
bob dans l’exemple de requête précédente par ce morceau écrit en langage
SQL. Il en résultera la requête suivante : « *SELECT \* FROM users WHERE
name = '' OR '1'='1' -- ;* » qui a une signification en pratique bien
différente : cette requête exécutée automatiquement renvoie non pas les
informations de l’utilisateur Bob, mais l’ensemble des informations de
tous les utilisateurs du site web. Dans un tel contexte, il est donc
possible avec une simple manipulation informée, de récupérer des
informations auxquelles il n’aurait pas été possible d’accéder de façon
légitime en utilisant le comportement habituel du site web.

Plusieurs points sont dès lors intéressants à souligner. D’abord,
l’ampleur et les conséquences d’une fuite de données peuvent être
extrêmement variables. Il peut s’agir de récupérer les noms
d’utilisateurs d’un site particulier pour pouvoir ensuite les cibler
avec de la publicité (Jordan 2008, chap. 2), ou de voler des
informations critiques (mots de passe et des numéros de carte bancaire).
L’ampleur croissante des services fonctionnant grâce à des systèmes
informatiques et donc de notre dépendance aux données numériques qui
supporte ces services, implique qu’une fuite de données a de plus en
plus de chance d’avoir un impact conséquent dans la vie réelle des
personnes.

L’injection SQL est une des techniques d’exploitation les plus utilisées
de la dernière décennie[^70]. Sa force réside dans sa simplicité de mise
en œuvre et les possibilités d’automatisation qu’elle implique : pour
l’utiliser, il suffit de tester quelques entrées SQL dans les
formulaires ou L’URL des pages d’un site web. De plus, il est possible
de développer simplement des outils pour parcourir l’ensemble des pages
d’un site web et tester automatiquement si des injections de code SQL
sont envisageables voire d’automatiser la recherche de sites vulnérables
avec un moteur de recherche comme Google.

D’autre part dans le cas de l’injection SQL comme pour la plupart des
techniques basées sur l’injection[^71], la défaillance qui permet de
lancer l’exploitation à un manque de contrôle sur les entrées
utilisateurs. L’injection SQL, si elle est facile à mettre en œuvre[^72]
est également aisée à prévenir, soit en utilisant des requêtes préparées
qui suppriment le lien direct entre l’entrée-utilisateur et la base de
données soit en filtrant simplement ces entrées-utilisateur pour
identifier et supprimer les morceaux de code SQL. Ces procédures sont
désormais incluses dans tous les cadriciels permettant de développer des
sites web. Pourtant ce type de vulnérabilité continue de poser des
problèmes aujourd’hui. Pour Mustafa Al-Bassam, hacker du groupe LulzSec
et chercheur en sécurité informatique, la persistance de ces failles est
due au manque de formation de nombreux développeurs, en particulier
concernant les problématiques de sécurité ainsi qu’à la pression mise
sur ces développeurs dans leur contexte de travail qui les poussent à
privilégier la quantité de fonctionnalités sur la sécurité[^73].

Plus largement en sécurité informatique, étant donné la complexité des
systèmes informatiques et les conditions imprévisibles dans lesquels ils
sont déployés, les cas extrêmes non anticipés, qui peuvent constituer
des vulnérabilités, sont très difficiles à anticiper et à tester. En
fait, comme le rappelle par exemple Paul Taylor, les systèmes
informatiques actuels apparaissent comme intrinsèquement non
sécurisés[^74] dès lors qu’il s’agit de composer avec l’ingéniosité
d’agents, qu’on qualifie habituellement d’*attaquants*. Étant donnée la
diversité des environnements informatiques c’est-à-dire l’ampleur des
configurations et interactions possibles entre les composants, il semble
en effet difficile d’imaginer les anticiper a priori de façon
exhaustive. Pour garantir, un fonctionnement sans imprévu, il s’agit
donc de traquer et de supprimer les possibilités de
détournement/pénétration au plus près des configurations concrètes une
fois les systèmes déployés.

Le hacker représente ainsi une telle figure capable techniquement et de
par son état d’esprit, de rassembler l’ingéniosité nécessaire pour
trouver et exploiter des failles. Le mot « hacker » demeure souvent le
terme générique pour désigner l’ennemi dans la littérature de sécurité
informatique. Pourtant, les hackers ne sont en réalité que rarement
délinquants et intéressés financièrement(Taylor 1999, 20). Leurs
motivations sont avant tout le défi technique ainsi que la provocation
des institutions et ce que Taylor identifie comme le « kick » : une
forme d’excitation face aux difficultés et le sentiment de contrôle et
de puissance induit par un hack réussi.

De plus, ce qui constitue un hack n’est pas la pénétration ou la fraude
numérique en tant que telle, mais bien l’étude et le déploiement de
connaissances techniques, de maîtrise pratique et d’ingéniosité par
lesquels il est possible de défier les systèmes techniques établis et
les organisations qui les contrôlent. À ce titre, on peut distinguer
quatre types de façons d’aborder ces activités de
pénétration/détournement : les attaques de type *script kidding*, les
attaques *zero-day*, les attaques *zero-plus-one-day* et les techniques
dites d’ingénierie sociale.

Le *script kidding* désigne le fait de cibler un système grâce à des
outils déjà conçus par d’autres hackers, détectant et exploitant des
failles bien connues plus ou moins automatiquement. Par exemple,
l’injection SQL si elle a pu être au départ un peu complexe à mettre en
œuvre, a vite été un bon exemple de technique automatisable induisant
dégâts et fraudes sur de nombreux sites Internet, notamment les plus
petits et les moins sécurisés et créant un climat d’insécurité sur
Internet. Les *script kiddies *utilisant ces méthodes automatiques sont
généralement appréhendés avec un certain mépris dans la culture hacker
en ce qu’ils confondent justement l’acte de pénétration/détournement,
souvent irresponsable, avec le hack en tant qu’acte original et complexe
manifestant la maîtrise technique. Ils sont de fait présentés par les
hackers comme responsables de leur mauvaise réputation.

À l’opposé, une attaque *zero-day* désigne le fait d’une part de
découvrir une vulnérabilité originale, c’est-à-dire identifier une
situation non prévue et potentiellement utilisable dans un nouveau
composant logiciel et/ou utilisant une technique/forme originale,
d’autre part réaliser une preuve pratique de cette vulnérabilité en
rassemblant et ou développant les outils logiciels pour produire la
situation adéquate et l’utiliser. Un exemple célèbre d’attaque
*zero-day* est l’attaque par *IP-spoofing* ou usurpation d’adresse IP,
probablement initiée par Kevin Mitnick à l’encontre d’un expert en
sécurité, Tsuotumo Shimomura, participant à sa traque.

Après avoir scanné le réseau de Shimomura, l’attaquant (supposé être
Mitnick) détecta deux ordinateurs faisant parti d’un réseau de
confiance, c’est-à-dire que les requêtes provenant de l’un sont
exécutées dès lors qu’elles proviennent de l’autre. L’attaque consista à
se faire passer pour l’un des ordinateurs, de façon à pouvoir commander
à l’autre, ce qui fut possible d’une part en noyant le premier sous des
requêtes de telle manière qu’il ne puisse plus communiquer et d’autre
part en usurpant son adresse IP[^75] pour tromper le second. Le résultat
se traduisit par une prise de contrôle temporaire de cette seconde
machine qui permit de la reconfigurer pour une connexion sans mot de
passe[^76]. Cette technique se base sur un usage astucieux des
mécanismes du protocole IP et de la confiance qu’il implique[^77] et sur
le déploiement d’un réseau de machines et d’outils permettant de
produire cette situation particulière mettant en échec les mécanismes de
sécurités en place.

Ainsi l’usage d’une technique d’exploitation connue nécessite, en
l’absence d’outil pour l’automatiser ou dans les cas défavorables, la
mise en place d’un dispositif relativement complexe et l’utilisation
d’astuces pour s’adapter à une configuration particulière[^78] du
système à exploiter. On parle alors d’attaque *zero-plus-one-day*,
c’est-à-dire utilisant une vulnérabilité connue, mais requérant une mise
en place spécifique manifestant le savoir-faire et l’ingéniosité de son
auteur.

Enfin, l’*ingénierie sociale *consiste à prendre acte que les humains
font partie intégrante des systèmes d’information et à chercher à les
manipuler eux pour récupérer des informations sensibles comme des mots
de passe ou des précisions techniques. Il s’agit par exemple d’appeler
un employé d’une compagnie en se faisant passer pour un technicien afin
de pouvoir obtenir un mot de passe ou un numéro d’identification
permettant ensuite d’avancer dans la pénétration du système plus
proprement informatique.

### <span id="anchor-33"></span>L’opposition hacker/cracker : constitution d’une figure déviante en informatique et dans la culture hacker.

Kevin Mitnick est une figure très connue de la culture hacker, elle est
intéressante, car elle fait ressortir à la fois une certaine cohésion
politique du *computer underground* et un clivage repris par de nombreux
hackers entre une figure légitime du hacker et une figure délinquante du
cracker.

<span id="anchor-34"></span>Mitnick affirme être devenu hacker parce
qu’il adorait la magie[^79]. Adolescent, il cultive de nombreuses
compétences, en phreaking, en informatique ainsi qu’un talent pour
l’ingénierie sociale qu’il a beaucoup contribué à développer[^80]. Dans
les années 80, il est condamné cinq fois pour des délits informatiques.
Il écope d’abord d’une année de prison assortie d’un engagement à ne
plus utiliser d’ordinateur. Il rompt cet engagement en 1992 et
disparaît. Durant plus de deux ans il sera sur la liste des criminels
les plus recherchés aux États-Unis et pendant cette période, il réalise
des hacks significatifs impliquant comme nous l’avons évoqué des
techniques informatiques inédites. Arrêté en 1995, il fut traité de
façon exemplaire et avec une certaine paranoïa : il passa 2 ans en
détention provisoire (dont huit mois en cellule de confinement pour
éviter qu’il ne déclenche une attaque nucléaire en sifflant dans un
combiné téléphonique) avant d’être condamné à cinq ans de prison pour
des charges vraisemblablement surévaluées[^81].

Entre 1995 et sa libération en janvier 2002, l’emprisonnement de Mitnick
suscite une vaste mobilisation, la campagne Free Kevin, à travers
laquelle la communauté informelle du *computer underground* se rassemble
physiquement et élargit son répertoire d’action. Les hackers organisent
des manifestations, produisent documentaires et éditoriaux, lancent un
congrès qui est aujourd’hui l’un des plus populaires du monde hacker.
HOPE, Hackers On Planet Earth, est le plus important événement hacker en
sécurité informatique aux États-Unis. En 2004, lors d’une édition de
HOPE et 2 ans après sa libération, Mitnick prononça un discours dans
lequel il revient sur sa vie et revendique clairement cette identité
frondeuse de hacker qui lui a valu son emprisonnement[^82].

Pourtant comme le relate notamment Coleman, certains hackers refusent
l’association du hacking avec les pratiques de Kevin Mitnick qu’ils
préfèrent nommer cracking dès lors qu’il s’agit de s’introduire dans les
ordinateurs d’autrui[^83]. Cette distinction entre *hacker* et
*cracker*, *hacking* et *cracking* se retrouvent également dans le
Jargon File, ce dictionnaire d’argot hacker que nous avons déjà évoqué
dans la partie I.1. Le *cracker* y est présenté de façon relativement
méprisante :

« Ethical considerations aside, hackers figure that anyone who can't
imagine a more interesting way to play with their computers than
breaking into someone else's has to be pretty
[*losing*](http://www.catb.org/jargon/html/L/losing.html). »[^84]

Pour Paul Taylor ce type d’opposition à l’intérieur de la culture hacker
apparaît lié historiquement à une rupture générationnelle(Taylor 1999,
chap. 2) et à la démocratisation des ordinateurs personnels. Il
identifie, après la génération hacker du MIT et les générations ayant
contribué au développement du PC, une « quatrième » génération hacker :
les jeunes hackers qui en grandissant avec les premiers PC domestiques
et une connexion à des réseaux numériques n’auraient pas, selon certains
hackers des générations précédentes, développé la même approche éthique
de l’informatique que leurs aînés ayant lutté pour avoir accès aux
ordinateurs et notamment le respect des informations d’autrui[^85].

L’exclusion dans la culture hacker se base également souvent sur le
critère la compétence technique, dès lors qu’il s’agit de distinguer les
hackers légitimes, motivés avant tout par leur passion technique, et des
aspirants incompétents en quête de reconnaissance. Ainsi, selon un récit
largement répandu, ce ne sont pas les hackers qui génèrent des dégâts
aux systèmes informatiques, mais des *script kiddies* inconscients qui
utilisent des outils automatiques (*rootkits*) pour pénétrer les
systèmes ou écrivent des virus par esprit puéril de rébellion. Dans le
même ordre d’idée, alors que des hackers experts en sécurité, sont
aujourd’hui bien intégrés au travail d’amélioration de la sécurité
informatique aussi bien à travers une professionnalisation qu’en tant
qu’indépendants[^86], une forme de distinction morale a priori entre les
hackers « chapeau blanc » respectant la loi et les hackers « chapeau
noir » délinquants est maintenue et largement reprise dans les
discussions sur le sujet et au sein même de milieux hackers. En fait,
comme l’analyse notamment Johan Söderberg, il apparaît que de nombreux
hackers se défendent contre les images négatives que construisent à leur
endroit l’industrie informatique et les médias en produisant leur propre
distinction[^87] entre pratiques technologiques légitimes et
illégitimes.

Ainsi, sans remettre en cause que le fait que des pratiques de vols ou
de fraudes numériques posent des problèmes éthiques dans notre société
de l’information, il s’agit ici de mettre en avant une illusion,
elle-même supportée indirectement par certains hackers et
chercheurs[^88], qui associe plus ou moins directement la figure du
cracker et une catégorie de pratiques de hacking en partie
fantasmée[^89] à une présomption de délinquance et d’immoralité. Dans
certains cas, cette présomption permet d’éviter d’interroger une
possible rationalité ou même légitimité[^90] dans les pratiques dites de
« cracking », c’est-à-dire empêche en particulier de les considérer
comme des actions dotées en elles-mêmes d’une valeur politique[^91]. Les
représentations déviantes, qui appuient toujours le récit habituel en
dépit de leur manque de réalisme, masquent en particulier la complexité,
aussi bien technique que sociologique, de la sécurité informatique et
les enjeux de pouvoir qu’elle supporte.

Pour rentrer plus concrètement dans des exemples qui manifestent ces
enjeux et oppositions, il s’agit d’élargir notre approche de la sécurité
informatique. Jusqu’ici, nous avons surtout parlé de cas simples de
pénétration dans un système informatique. En effet, en limitant la
compréhension de la sécurité informatique à cette insistance sur des
actes de « pénétration » supposée, on masque le sens des activités
hackers, pourquoi elles revêtent une place centrale dans ce champ et
manifestent une dimension intrinsèquement politique de l’informatique.

### <span id="anchor-35"></span>L’ambiguïté des questions de sécurité en informatique et leurs dimensions politiques.

Notre expérience de l’univers hacker s’est initialement forgée par des
visites au Chaos Communication Congress, un événement hacker
allemand[^92] de grande ampleur et vieux de plus de 30 ans. Cet
événement est soutenu par la principale organisation hacker allemande,
le Chaos Computer Club qui défend depuis son origine une approche
*hacktiviste*[^93] et politisée de l’informatique. Les débuts de cette
organisation sont intéressants, car ils illustrent la façon dont le
hacking en tant que pratique d’exploration et d’appropriation technique
devient de fait transgressif (voire délinquant) dans un contexte de
développement technologique propriétaire. Des enjeux pratiques présentés
sous le jour de la sécurité informatique apparaissent alors comme
traduisant un rapport de force entre des organisations déployant de
façon unilatérale une technologie et des usagers refusant de se
conformer au scénario ainsi défini.

En fondant le Chaos Computer Club (CCC) en 1984 et son magazine phare le
Datenschleuder, Wau Holland anarchiste et technophile essaye d’articuler
ce qui apparaît pour beaucoup dans son milieu politique comme une
contradiction : comment aimer les ordinateurs et promouvoir
l’informatique alors que ces machines semblent radicalement orientées
vers le contrôle technocratique ? Le CCC encourage dès lors
l’appropriation populaire et « Chaotique » des ordinateurs et des
réseaux, par exemple en fournissant des explications techniques
permettant de construire son propre modem. Ainsi, cette organisation se
revendique de l’éthique hacker tout en entretenant une approche
politique assez spécifique par rapport aux hackers américains.

Le club se fait connaître cette même année 84 par un fameux hack, rendu
public afin de dénoncer le fonctionnement opaque et centralisé du réseau
Bildschirmtext (Btx). Cet équivalent allemand du Minitel (on parle de
réseau *télétexte*) est distribué en exclusivité par l’organisation
postale ouest-allemande la Deutsche Bundespost (DBP). Wau Holland et son
comparse Steffen Wernéry, en explorant le fonctionnement des terminaux
et du réseau supportant le Bildschirmtext, découvrent une vulnérabilité
qui permet d’amener un serveur du réseau à révéler aléatoirement le
contenu de sa mémoire[^94]. Ils parviennent ainsi à récupérer les
identifiants d’une banque hambourgeoise ce qui permet de se faire passer
pour elle sur le réseau[^95].

Ces derniers organisent alors une forme spectaculaire de démonstration
publique en utilisant le système de paiement du Btx pour transférer en
une nuit 135 000 DM sur le compte du CCC sous forme de micropaiement. Le
lendemain ils restituèrent l’argent et convoquèrent une conférence de
presse. Ils rendirent compte de cette possibilité de détournement du
système de paiement et de la technique qu’ils utilisèrent, en expliquant
qu’elle pourrait facilement être utilisée pour voler de l’argent aux
usagers du Btx. Ils furent alors relativement célébrés dans les médias,
comme source d’une expertise et parce que l’affaire fit écho à un climat
général de méfiance à l’égard de déploiement de réseaux informatiques
centralisés[^96].

Or durant les années suivantes, cette image *d’hacktivistes* défendant
les droits des usagers fut éclipsée en Allemagne par un mouvement de
criminalisation des hackers qui furent rapidement assimilés à des
amateurs[^97] dont les pratiques à tendance déviante devaient être
strictement encadrées par la loi. Ainsi les hackers perdirent à l’époque
rapidement leur qualité d’experts et d’activistes pour être relégués à
la sphère des activités personnelles. Concrètement, le hacking devint
dans la plupart des cas illégal dès lors que toute manipulation du flux
d’exécution d’un programme informatique ou des données traitées fut
légalement considérée comme une fraude, mais seulement dans les cas où
rentre en jeu des pertes financières suffisantes. Ainsi, selon l’analyse
de Kai Denker, ces lois portées dès l’origine par les réflexions
d’experts au sein d’entreprises allemandes pour pénaliser tout
détournement de leurs infrastructures, ne furent pas prévues pour
encadrer l’accès abusif à des données personnelles d’usagers
particuliers.

La définition traditionnelle de la sécurité informatique met en jeu
trois dimensions : la garantie de confidentialité des données (il est
impossible d’accéder à des données privées), la garantie de l’intégrité
des données et du système (empêcher les modifications indues des données
ou des programmes) ainsi que celle de leur disponibilité (le système ne
doit pas pouvoir être mis hors service). Ces garanties sont adossées
notamment à des réflexions d’éthique appliquée à propos de ce qui
constitue un usage loyal de l’informatique et de la traduction dans les
contextes spécifiquement informatiques de certains impératifs
éthiques[^98]. Cependant en pratique, l’interprétation et l’application
de ces principes sont souvent inégales et reflètent des rapports de
pouvoir.

Ainsi, une illustration frappante du rôle de l’interprétation pour
définir le champ de la sécurité (ici la confidentialité) nous a été
proposée lors d’une discussion au Chaos Communication Congress. Alors
qu’un programme collectant automatiquement des données, par exemple à
des fins publicitaires, sans le consentement de l’usager d’un ordinateur
est en général considéré comme un virus informatique et ciblé par des
mesures de sécurité, le même comportement provenant des programmes
fournis par Google ou Microsoft dans le cadre de leurs services sans en
informer clairement l’utilisateur ne rentrera pas dans le cadre de la
sécurité informatique[^99]. Comme le résument les auteurs d’un manuel
classique sur la sécurité dans les systèmes Unix, la sécurité
informatique consiste simplement en pratique à garantir que « tout se
passe comme prévu »[^100]. Il s’agit dès lors de savoir *qui* définit le
scénario[^101].

En fait dans le cas du Bildschirmtext, il est clair que, pour la
Deutsche Bundespost, le système est conçu comme un terminal de
consommation défini par un cadre d’usage finalement très limité pour un
ordinateur[^102]. Or l’usage qu’en font les hackers du CCC excède
largement cet usage normal défini par les concepteurs[^103]. L’approche
du Btx développée au CCC qui vise la réappropriation technique de la
machine et des données rentre dès lors en conflit avec celle de la DBP
qui n’accorde qu’un rôle passif aux usagers. C’est de plus cette
approche expérimentale de l’artefact qui mène à la mise en évidence de
failles, voir se confond avec l’exploitation des failles. La définition
juridique de la fraude informatique apparaît dès lors comme une façon de
trancher cette opposition en faveur des concepteurs du système.

On peut proposer deux façons critiques d’interpréter l’intérêt de la
criminalisation des hackers pour une organisation comme la DBP. D’une
part, elle consiste en quelque sorte à traiter le symptôme plutôt que la
cause : éviter que des failles soient découvertes plutôt que de faire le
pari de les découvrir pour les éliminer[^104]. De ce point de vue,
limiter les comportements exploratoires et impliquant des usages non
standard du système permet de diminuer la probabilité que les
éventuelles failles existantes soient découvertes et exploitées. Ainsi,
même après cette révélation, la DBP a nié que le CCC ait pu récupérer
les codes de la banque en utilisant la vulnérabilité(Denker 2014, 177),
préférant minimiser le risque et faisant probablement le pari qu’en
pratique de tels usages du système ne seraient pas réalisables.

D’autre part, cette criminalisation peut apparaître comme une façon de
conforter le contrôle centralisé sur son usage : comme pour la plupart
des systèmes Videotex européens la version allemande du Bildschirmtext
est déployée par un organisme d’État suivant un objectif de
modernisation des services d’information et dans une approche de
planification technologique. Un aspect intéressant dans le cas d’un tel
réseau de communication numérique est que cette façon de restreindre le
système à un usage centralisé et orienté vers la consommation
d’information par les usagers semble corrélée à une faible adoption par
les utilisateurs. Comme le relève notamment Andrew Feenberg, le Minitel,
système Videotex français, fait figure d’exception avec ses millions
d’usagers réguliers. En cherchant les raisons de ce succès, il met en
avant la façon dont le Minitel a été finalement réorienté par quelques
hackers vers un usage en tant qu’outil de communication plutôt que
d’information. L’engouement pour l’envoi de message grâce au Minitel fit
qu’après une courte période de résistance et de transition, de plus en
plus d’opérateurs utilisant le Videotex commencèrent à fournir des
services de communication, notamment autour de messageries érotiques et
de services de rencontre. Pour Feenberg, cet épisode du Minitel
français, illustre un « conflit de codes techniques », une controverse
opposant deux lectures pratiques du système, et à l’issue de laquelle
celle poussée initialement par quelques hackers s’est imposée[^105].

[^62]: (Jordan 2008 chap.2)

[^63]: Ce constat est dans une certaine mesure toujours vrai
    aujourd’hui, et dans notre expérience il reste généralement
    nécessaire de clarifier la diversité du hacking lorsqu’on s’adresse
    à un public qui ne connaît pas cette culture.

[^64]: On évoque généralement, le *hacker crackdown* du début des années
    90, étudié par Bruce Sterling (Sterling 1992) qui entame une ère de
    répression et de criminalisation du hacking aux États-Unis.

[^65]: Rendez-vous annuel de la scène
    [*hacker*](https://fr.wikipedia.org/wiki/Hacker_%28sécurité_informatique%29)
    internationale, organisé en Allemagne par le [*Chaos Computer Club*](https://fr.wikipedia.org/wiki/Chaos_Computer_Club). Le
    congrès s’organise autour d’une série de conférences et d’ateliers
    sur des thématiques techniques, politiques, voir artistiques.
    Cependant l’ampleur du festival excède les événements officiels
    puisque de nombreuses rencontres et marathons de hacking
    (hackathons) ont organisé de façon informelle par les participants.
    Le congrès a eu lieu depuis quelques années du 27 au 30 décembre au
    [*Congress Center de Hambourg*](https://de.wikipedia.org/wiki/Congress_Center_Hamburg)*.

[^66]: On retrouve cette idée exprimée par exemple par Kane, un hacker
    interviewé par Paul Taylor : « To me hacking is just changing the
    conditions over and over again until there’s a different response. »
    Kane cité dans (Taylor 1999, 16). Nous aurons l’occasion de nous
    intéresser à cette logique plus an détail dans une analyse de la
    méthode du débordement de tampon dans la partie II.4.

[^67]: Voir par exemple (Chirillo 2001) ou (Gollmann 2010).

[^68]: Certaines attaques ne nécessitent pas à proprement parler de
    faille pour être exécutées, la fameuse attaque (D)DoS est un bon
    contre-exemple, car il consiste simplement à submerger les serveurs
    hébergeant un site web.

[^69]: Il existe de nombreuses précautions plus ou moins complexes à
    mettre en œuvre pour éviter ce type d’injection, par exemple
    vérifier que le nom ne contient pas de marqueur SQL, par exemple les
    – qui dans notre exemple signifie un début de commentaire
    c’est-à-dire désactive la fin de la requête. Les failles SQL
    élémentaires sont aujourd’hui largement comblées par différents
    mécanismes de sécurité.

[^70]: Les premières discussions à propos de cette vulnérabilité datent
    de 1998 dans le magazine hacker Phrack ([Sean Michael
    Kerner](http://www.esecurityplanet.com/author/4440/Sean-Michael-Kerner)
     2013 - How Was SQL Injection Discovered?
    <http://www.esecurityplanet.com/network-security/how-was-sql-injection-discovered.html>
    consulté le 1-7-2016).

    (Joseph Cox, The History of SQL Injection, the Hack That Will Never
    Go Away,
    <http://motherboard.vice.com/read/the-history-of-sql-injection-the-hack-that-will-never-go-away>
    consulté le 1-7-2016)

[^71]: L’injection est une méthode d’exploitation très générale :
    injecter un morceau de code est possible dans de nombreux contextes
    informatiques pour détourner l’exécution normale d’un programme.
    Nous reviendrons sur un autre exemple utilisant une injection
    mémoire dans la partie II.4 et discuterons plus généralement de ses
    implications dans un cadre de philosophie de l’informatique.

[^72]: À ce titre, elle est une vulnérabilité souvent associée aux
    *script kiddies*, sur lesquels nous reviendrons un peu plus loin,
    c’est-à-dire des débutants (supposés jeunes) qui attaquent des
    systèmes pour le fun sans posséder de réelles compétences permettant
    d’inventer ou d’adapter des des techniques de pénétration.

[^73]:  Joseph Cox op cit.

[^74]:  (Taylor 1999, 73)

[^75]: Dans le cadre du protocole IP à la base d’Internet, la
    communication s’effectue en envoyant des paquets de petites
    « aiguillés » à travers le réseau en fonction d’une adresse de
    destination, l’adresse IP. Cette adresse traditionnellement composée
    de quatre nombres identifie donc un ordinateur du point de vue de sa
    position virtuelle sur le réseau. Cependant, il est aisé d’envoyer
    des paquets IP en changeant l’adresse de l’expéditeur de façon soit
    à masquer son identité soit à se faire passer pour un autre
    ordinateur. Ainsi, l’une des machines utilisées par Mitnick a pu
    réussir à se faire passer pour un ordinateur de confiance dès lors
    que le protocole utilisé se basait sur l’adresse IP pour
    l’identification.

[^76]: (Jordan 2008, chap. 2) Il est également possible de dissimuler
    une telle attaque, ce qui permet de garder un ordinateur captif
    pendant de longue période à l’insu de son propriétaire et de pouvoir
    l’utiliser ponctuellement et anonymement.

[^77]: Le protocole IP implique la coopération des machines du réseau
    pour distribuer les paquets et fonctionne de façon transparente en
    laissant lisibles et modifiables les diverses informations
    techniques utiles pour son fonctionnement. Il est ainsi possible de
    manipuler le bon déroulement d’un échange IP en l’absence de
    mécanismes de sécurité supplémentaires, comme l’usage d’un protocole
    chiffré pour la communication (par exemple SSH ou HTTPS).

[^78]: Nous développerons l’exemple de l’usage d’un *tampon NOP* comme
    une astuce permettant de faciliter une exploitation mémoire par
    débordement de tampon sur la pile dans la deuxième partie (II.4).

[^79]:  (E. G. Coleman 2013, 16)

[^80]:  (Mitnick et Simon 2005)

[^81]:  (G. Coleman et Golub 2008, 266) Mitnick soutient notamment qu’il
    n’a jamais cherché à profiter financièrement de ses actes.

[^82]:  (G. Coleman et Golub 2008, 277)

[^83]:  (E. G. Coleman 2013, 16)

[^84]:  « Les considérations éthiques mises à part, les hackers
    considèrent que quiconque est incapable d’imaginer façon plus
    intéressante de jouer avec un ordinateur que pénétrer celui de
    quelqu’un d’autre doit être plutôt désespéré » traduction de
    l’auteur. Jargon File entrée *cracker*
    (<http://www.catb.org/jargon/html/C/cracker.html> consulté le
    3-7-2016 ).

[^85]:  Plus qu’une simple question générationnelle, certains auteurs
    comme Kirkpatrick identifient dans ce conflit une opposition de
    classe (Söderberg 2010, 168).

[^86]:  La *penetration testing* et la *sécurité offensive* apparaissent
    de plus en plus comme des outils indispensables pour améliorer la
    sécurité réelle des systèmes et sont de plus en plus utilisées par
    l’industrie (voir par exemple
    <https://www.facebook.com/notes/facebook-ctf/facebook-ctf-is-now-open-source/525464774322241/>
    consulté le 20 juillet 2016). Selon les derniers programmes, il est
    possible à n’importe qui de chercher des failles sur le mode de la
    compétition. Plus largement, la sécurité informatique a aujourd’hui
    largement intégré que la recherche de failles est un défi
    passionnant et ludique.

[^87]:  (Söderberg 2010, 168)

[^88]:  (Söderberg 2011, 26)

[^89]:  Taylor souligne (Taylor 1999, 152) que les métaphores du vol et
    de la pénétration tels qu’il ont été consacrés notamment par les
    législations sont contestées par les hackers. Ceci nous semble
    rejoindre le diagnostic de Pieters (Pieters 2011b) quant à la
    faiblesse du paradigme actuel qu’il qualifie de paradigme du
    « containment » en sécurité informatique. De plus, cette insistance
    sur le motif simple du « computer break in » n’est pas
    satisfaisante, car elle risque de masquer d’autres pratiques de
    hacking touchant à la sécurité informatique (hacking de console,
    déplombage logiciel ) reflétant cette complexité et des schémas plus
    clairement politiques.

[^90]:  Taylor analyse ce processus comme la constitution d’une figure
    déviante dans le champ de l’informatique en faisant référence au
    travail classique de Howard Becker sur la sociologie de la déviance.
    La déviance empêchant justement de rendre compte du point de vue
    déviant depuis une position mainstream, car les deux sont en quelque
    sorte incommensurables (Taylor 1999, 13).

[^91]:  Pourtant, comme le rappelle par exemple Gabriella Coleman
    (‘Phreaks, Hackers, and Trolls: The Politics of Transgression and
    Spectacle’, The Social Media Reader, 2012, 99–119), la dimension
    transgressive du hacking est liée à une critique politique qui se
    fit jour dans le mouvement des yippies et qu’on retrouve encore
    aujourd’hui au cœur de la culture hacker.

[^92]:  Si la culture hacker est initialement américaine, elle s’est
    rapidement développée à l’échelle locale dans d’autres pays avec ses
    spécificités, souvent éclipsées par des études centrées sur les
    États-Unis (Alberts et Oldenziel 2014). Les hackers du Chaos
    Computer Club sont, à cet égard, particulièrement politisés et
    agissent comme un groupe de pression depuis des années en
    revendiquant une position politique de gauche.

[^93]:  L’hacktivisme, contraction de activisme et hack recouvre le fait
    d’utiliser un mode d’action hacker au service d’actions
    explicitement politiques. Comme l’explique Kai Denker, l’activisme
    du Chaos Computer Club est dès le départ dans une vision de gauche
    et progressiste de l’hacktivisme. (Denker 2014)

[^94]:  On découvre ici un cas typique qui invalide la métaphore de la
    « pénétration » informatique : un réseau basé sur une architecture
    client-serveur implique que le client demande au serveur certaines
    informations et que celui-ci choisisse en fonction d’un protocole
    d’identification de fournir ou non ces informations. La technique
    utilisée par Holland et Wernéry consiste à interroger le serveur
    d’une façon atypique qui le pousse à renvoyer une partie de sa
    mémoire de travail (on parle en anglais de *memory dump*). À aucun
    moment, il ne s’est agi d’être à l’« intérieur » du réseau de la
    banque, mais seulement d’utiliser un comportement anormal en tant
    que client.

[^95]:  La problématique de l’identité et de l’authentification est
    complexe et centrale en sécurité informatique (Singer et Friedman
    2014, 31)

[^96]:  (Denker 2014, 178)

[^97]:  Kai Denker utilise le mot hobbyist (Denker 2014, 184) tout en
    insistant sur l’importance de cette image d’amateurisme qui permet
    de dénier une qualité d’expert et une valeur politique aux activités
    des hackers. Il nous semble ainsi intéressant d’être conscient au
    niveau sémantique que la dénomination d’amateur souvent associée aux
    hackers et libristes peut amener à trivialiser et dépolitiser leurs
    pratiques.

[^98]:  (Brey et Søraker 2009)

[^99]:  La surveillance généralisée organisée par certains acteurs
    dominants de l’informatique en partenariat avec les services de
    renseignement américain et ses possibles conséquences collectives
    est une problématique centrale au sein d’un événement comme le Chaos
    Communication Congress, en particulier à la suite des révélations de
    Edward Snowden.

[^100]:  (Garfinkel, Spafford, et Schwartz 2003)

[^101]:  On peut mettre en parallèle ces réflexions avec une critique
    intéressante adressée par Philip Brey à l’encontre des cadres
    traditionnels de l’éthique appliquée à l’informatique (Brey 2000).
    Il met en avant certains biais de cette discipline. Elle est
    notamment partiale dans son traitement puisqu’elle se centre sur les
    infractions et néglige les enjeux de conception des systèmes. Voir
    également (Taylor 1999, chap. 6).

[^102]:  L’ordinateur est une machine versatile à travers la possibilité
    qu’elle manifeste d’être programmée. Or dans le système du
    Bildshirmtext, les postes clients ne permettaient que de consulter
    les pages et seuls des postes spéciaux fournis aux entreprises
    permettaient de les éditer.

[^103]:  (Denker 2014, 179)

[^104]:  Le débat sur les conditions de la divulgation des failles est
    depuis devenu classique dans les discussions sur la sécurité
    informatique (Full disclosure / non disclosure).

[^105]:  (Feenberg 1995, chap. 7). Il s’agit pour Feenberg d’un exemple
    de « rationalisation démocratique ». Le processus de développement
    technique s’est opéré de telle façon que des usagers extérieurs à la
    démarche de conception initiale ont été à même de redéfinir la
    fonction/identité d’un système technique. La rationalisation
    démocratique constitue notamment une alternative à un développement
    hégémonique de la technique. Nous reviendrons sur ces concepts et
    sur la philosophie d’Andrew Feenberg dans la partie II.

### [Sommaire](../01-sommaire)
