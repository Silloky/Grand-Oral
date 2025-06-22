# Agrégation de classements grâce à la géométrie dans l'espace

Bonjour Madame, bonjour Monsieur.

Ce soir à 23h59, tous les lycéens de Terminale ayant des vœux en attente sur Parcoursup doivent les avoir classés. Et si Parcoursup a laissé 5 jours pour effectuer ce classement, ce n'est pas pour rien : c'est une étape qui est difficile et qui nécessite pas mal de réflexion.

Quand j'ai appris il y a quelques mois le caractère obligatoire de cette phase par rapport à l'année dernière, je me suis demandé quelle était la meilleure stratégie pour construire ce classement.
En bon analyste, j'ai voulu attribuer à chacun des vœux un score qui dépendrait de plusieurs critères plus ou moins importants : un score de niveau, un score de motivation pour l'établissement et la formation, et un autre sur l'hébergement (le temps de transport entre l'hébergement probable et l'établissement).
Ainsi, il semble évident que ces différents critères de classement n'ont pas tous la même importance ; mais au-delà de cela, comment peut-on les combiner, les compiler un seul classement final.

Après un bon petit moment de recherches sur Internet, de réflexion, et de trifouillage dans Geogebra, je crois avoir trouvé une méthode, avec la géométrie dans l'espace.
Alors voilà, en quoi la géométrie dans l'espace ouvre-t-elle la voie à une nouvelle méthode d'agrégation de classements ?
L'agrégation de classements étant le terme "juste" utilisé pour signifier ce que j'ai vulgairement appelé jusqu'ici la combinaison de classements.

L'objectif de cette méthode est de donner non seulement une visualisation, mais surtout une relation qui permet, à partir de 3 classements et de pondération respectives, d'obtenir une métrique aboutissant à un classement final.


## Figure, notations et démarche

Intéressons-nous tout d'abord aux scores que j'attribue à chaque formation et pour chaque critère.
En général, l'agrégation de classements utilise les rangs des éléments classés ; la valeur associée à un certain élément dans un certain critère est donc simplement sa position dans le classement.
Cependant, on peut extrapoler d'une certaine manière, et considérer des valeurs non-entières, et ça fonctionne tout aussi bien.

Avoir des valeurs décimales permet d'utiliser des scores qu'on peut normaliser entre $0$ et $20$, et analogues à des rangs, donc où $0$ et le meilleur et $20$ est le pire.
En outre, cela permet de ne pas effacer des écarts significatifs entre 2 éléments consécutifs, ce que ferait une simple considération des rangs dans un classement ; je vais donner un exemple dans peu de temps, mais pour le moment ne prêtez pas attention au tableau de valeurs.

Par exemple, si l'on prend 3 prépas $P_1$, $P_2$ et $P_3$, dont les pourcentages d'intégration dans le top-5 des écoles d'ingénieur sont respectivement $55\%$, $50\%$ et $20\%$, alors que les rangs seraient respectivement $1$, $2$ et $3$, les scores normalisés sont $0$, $2.9$ et $20$. On remarque bien la conservation de l'écart entre les $50$ et $55$ initiaux et les $0$ et $2.9$ normalisés.

Cette normalisation a lieu pour chaque critère, et on se retrouve alors avec un tableau de données comme celui que vous trouverez en bas de la page. On a alors bien 5 formations notées $P_i$ pour $i\in\{1\dots5\}$ qui ont un score pour chaque critère.
Ma méthode ne permet ici que 3 critères, que l'on notera par la suite $A$, $B$ et $C$.

Considérons alors la figure que vous trouverez en haut de ma feuille support.
La figure utilisée est une pyramide à base triangulaire de sommet $O(0;0;0)$, où chaque axe correspond à un classement : on attribue au classement $A$ l'axe des abscisses, à $B$ l'axe des ordonnées et à $C$ l'axe des cotes.
La base de la pyramide, en bleu sur la figure, correspond aux "pires" éléments ; puisqu'on a normalisé entre $0$ et $20$, les coordonnées des sommets de ce triangle sont toujours à $20$ de $O$, qui est donc le meilleur élément théorique (score $0$ dans les 3 critères).

Considérons maintenant un seul élément, par exemple la formation $P_2$, qui a pour scores, dans l'ordre des classements, $12$, $16.4$, $12.9$.
On le modélise sur la figure par 3 points de coordonnées $(12;0;0)$, $(0;16.4;0)$ et $(0;0;12.9)$ qui appartiennent donc aux axes du repère ; ce sont les points rouges sur la figure.

On appelle $T_i$ le plan qui passe par les points modélisant $P_i$. Il y a donc autant de plans $T$ qu'il n'y a de formations.

Et enfin, on ajoute une droite qu'on appelle $d$ et qui est constante pour toutes les formations.
Sa direction, son orientation, dépend de 3 choses : $\lambda_A$, $\lambda_B$ et $\lambda_C$, qui sont les pondérations respectives des critères $A$, $B$ et $C$.
Ce sont eux qui vont juger l'importance d'un critère par rapport à un autre, et c'est totalement subjectif dans le cas de mon exemple de Parcoursup.
Quelques règles à respecter pour ces pondérations : elles doivent être entre $0$ et $1$ et leur somme doit toujours être égale à $1$.

Mais considérons l'intersection entre un plan $T_i$ et la droite $d$ ; c'est un point, que l'on note $F_i$ ("f" pour "final"), et soit $f_i$ minuscule la distance $OF_i$.
Et notre métrique de classement final, c'est $f_i$ ; il suffit alors de classer les $P_i$ par $f_i$ croissant.

Ce qu'on remarque ici, c'est que si un des points modélisant $P$ est confondu avec $O$, autrement dit si cet élément a un score de $0$ dans un des critères, il va obligatoirement être premier, car le point $F$ correspondant sera lui aussi confondu avec $O$.
On va donc rajouter un paramètre $\delta$ dans notre formule de normalisation, qui devient alors ce que vous trouvez écrit au-dessus du tableau de valeurs.
Ce nouveau paramètre a pour effet de décaler toutes les valeurs normalisées de $0$ ; il mesure le poids d'être très bon dans un ou plus de critères.
En fait, ça quantifie ce qu'on dit couramment : "il est excellent en ça et ça, presque peu importe qu'il soit pas incroyable dans le troisième critère".

Il faut dès lors trouver une expression de $f_i$ qui dépend de $a$, $b$, $c$, $\lambda_A$, $\lambda_B$ et $\lambda_C$.

## Expression de la distance $f_i$

On va considérer ici un seul élément, donc inutile de mettre les $i$ en indice, ce qui alourdirait l'écriture.

Les scores de cet élément dans les classements $A$, $B$ et $C$ sont respectivement $a$, $b$ et $c$.
L'élément est donc modélisé par les points $A(a;0;0)$, $B(0;b;0)$ et $C(0;0;c)$

On peut en déduire les coordonnées des vecteurs $\vec{AB}$ et $\vec{AC}$ qui forment une base du plan $T$, dont on note le vecteur normal $\vec{n}$.
On peut alors déterminer les coordonnées du vecteur $\vec{n}$, et en déduire une équation du plan $T$, à une constante près.
Or puisque le point $A$ appartient à $T$, on peut conclure sur l'expression du plan, que vous pouvez trouver à la fin de la première ligne.

Ensuite, on détermine à l'aide des coordonnées du vecteur directeur $\vec{u}$ les équations paramétriques de $d$, à la ligne 2.

L'objectif est ensuite de trouver les coordonnées du point d'intersection $F$, dont les coordonnées vérifient le système au début de la troisième ligne.
En le résolvant, on trouve la relation donnant le paramètre $t$ ; on injecte dans les équations paramétriques de $d$, et on trouve alors $x_F$, $y_F$ et $z_F$, les coordonnées du point $F$.

Il suffit alors d'utiliser la distance algébrique pour trouver l'expression de la distance $OF=f$, notre métrique, ou score final.


## Etude stochastique

Ce qu'on peut faire ensuite, c'est poser les pondérations comme des variables, et on va fixer les scores pour chaque critère.
Ainsi, on étudie l'influence des pondérations et de leurs variations sur les classements qui en résultent.

L'algorithme pour réaliser cette étude est en fait assez simple.

Le première étape est de générer des ensembles de $(\lambda_A,\lambda_B,\lambda_C)$. Sur mon ordinateur, j'en ai créé $250000$.

Nous avons vu que la droite $d$ est spécifiquement donnée par les $\lambda$, et donc, si on les fait varier, on se retrouve avec un ensemble de droites qui intersectent le plan des "pires".
Il faut voir cette droite comme un faisceau qui balaie l'entièreté de la base de la pyramide selon les pondérations.

La suite de l'algorithme a lieu pour chacun de ces ensembles créés.

On calcule alors les métriques $f$ de chacun des éléments, et on en déduit un classement.
La prochaine étape, c'est de colorer le point d'intersection de la base de la pyramide, le plan des "pires", et de la droite $d$, d'une couleur qui dépend du classement qu'on vient d'obtenir.

Et ces calculs, ils ont été effectués $250000$ fois par mon ordinateur, toujours avec les données du tableau, pour aboutir au triangle coloré que pouvez voir en bas de la page.

Une des premières choses qu'on remarque, c'est qu'il y a pas mal de zones ; mais combien y en a-t-il exactement ?
Dans le cas de nos données du tableau, il y en a $19$.

Raisonnons de manière théorique. Quel est le nombre maximum de zones ?
Sachant que chaque zone colorée correspond à un classement unique, il s'agit donc du nombre de permutations des éléments à classer, soit $n!$ zones possibles, où $n$ est le nombre d'éléments à classer.

Mais revenons à notre exemple, et tentons de comprendre le triangle.

J'ai écrit en légende les classements correspondant aux cinq zones les plus grosses, et vous trouverez à sa droite un graphique en barres qui représente la proportion d'aire totale occupée par chacune des plus grosses zones.
Mais comment calculer l'aire, étant donné que nous n'avons que des points, discrets par nature ? Je me suis souvenu d'une activité faite en cours de maths l'année dernière à propos de la méthode de Monte-Carlo.
Étant donné que les points sont placés de manière équitable partout sur le triangle, il suffit de faire le rapport de points d'une certaine couleur sur le nombre total de points pour accéder à l'aire.
Comme prévu, la somme des valeurs du diagramme en barres total est bien égale à $1$.

Mais maintenant, comment peut-on interpréter ce triangle ?

Premièrement, ce il met en avant la solidité de certains classements, dans le sens où même si les pondérations varient, ils restent souvent optimaux.
Même le nombre de zones est interprétable ; il correspond à la capacité d'aboutir à un consensus sur le classement final à adopter si l'on considère un grand nombre de votants. En effet, plus il y a de zones, plus il y a désaccords.

Dans certains contextes, il peut être aussi intéressant de prévoir vers quel classement une personne risque de changer d'avis.
Dans notre figure ici, hors du contexte des prépas où ça n'a pas de sens, la probabilité qu'une personne passe du classement 13524 (le plus gros en jaune) au 14325 est très faible, et par des calculs, cette probabilité relative peut être quantifiée avec les distances entre les zones.

Une dernière chose à remarquer, ce sont les lignes de séparation entre les zones, qui concrètement signifient que les 2 classements de part et d'autre conviennent de manière égale aux pondérations données par la personne.

En outre, ça offre une représentation des choix possibles pour une personne donnée ; dans le cadre d'un traitement contre le cancer, certains patients seraient peut-être rassurés en voyant l'effet qu'ont leurs choix, à travers les pondérations, sur les traitements qu'ils devront prendre.


## Approche matricielle

Une dernière chose dont j'aimerais parler, c'est pourquoi ne pas faire une simple moyenne pondérée des scores normalisés ?

Déjà, en quoi ça consiste, mathématiquement, de faire la moyenne ?
On pose chaque colonne du tableau comme un vecteur, donc une matrice colonne, qu'on appelle $C_i$ et $\lambda_i$ la pondération de ce critère.
Et faisant ça, on peut résumer le fait d'appliquer une moyenne pondérée à une simple formule : la somme des produits $\lambda_iC_i$ pour $i$ entre $1$ et $3$.

Pour en revenir à la question, quels inconvénients cette méthode crée-t-elle, et quels avantages apporte la méthode avec la géométrie dans l'espace ?
La moyenne pondérée réduit un vecteur de scores à un simple scalaire, ce qui fait perdre toute la structure géométrique du problème, alors que la méthode avec le plan et la droite conserve cette structure, et permet notamment de visualiser correctement l'effet du changement d'un score, ce qui est extrêmement apparent lorsqu'on utilise une figure interactive dans Geogebra.
De plus, elle introduit aussi une non-linéarité : avec l'approche géométrique, l’effet d’un critère dépend des autres, ce qui permet de mieux représenter des compromis complexes, là où la moyenne reste toujours proportionnelle.

D'ailleurs, l'exemple que vous avez dans le tableau ne se classe pas dans le même ordre selon la méthode : il y a un échange entre $P_1$ et $P_3$.
Pour avoir appliqué cet algorithme à mes vrais vœux Parcoursup, je peux vous affirmer que les résultats trouvés sont plus cohérents que ceux obtenus avec la moyenne pondérée.


## Conclusion

Pour conclure, cette méthode m’a permis d’aller bien plus loin qu’un simple classement intuitif. Elle apporte une rigueur mathématique, une visualisation concrète des préférences, et une compréhension fine de la stabilité des décisions. 
Loin d’être un simple exercice de modélisation, elle m’a aidé à faire un choix personnel important. Et je pense même qu’elle pourrait, dans d’autres contextes, devenir un véritable outil d’aide à la décision.