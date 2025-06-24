# Voile solaire

Bonjour Madame, bonjour Monsieur.

Une astéroïde se dirige tout droit vers la Terre et une équipe de scientifiques essaient de trouver une solution. C'est l'intrigue de la série télévisée Salvation, que j'ai regardée l'été dernier, et qui m'a donné l'idée pour cet oral.

Et une des solutions qu'ils mettent en place, c'est une voile solaire ! Mais alors, qu'est-ce qu'une voile solaire ? 
C'est un dispositif équipé d'une grande voile qui réfléchit la lumière du Soleil, et quand il y a peu de frottements, la seule pression de la lumière permet de le faire bouger.

Dès lors, comment peut-on modéliser et optimiser le mouvement d'une voile céleste propulsée uniquement par le rayonnement solaire ?

D'abord, je vais vous expliquer la modélisation, dont je vous donne le schéma. Ensuite, nous allons tenter de trouver une expression de la force de pression de radiation qui agit sur la voile, afin de voir dans une troisième partie une une modélisation de l'évolution du rayon d'orbite de la voile.
Et enfin, la quatrième partie sera consacrée à une analyse de cette fonction pour en déduire des optimisations possibles sur la dispositif, y compris au niveau des matériaux utilisés.

## Explication du modèle utilisé

On assimile le dispositif (donc la voile et la charge qu'elle porte) à un point matériel $M$ situé à une distance $r(t)$ du Soleil, à tout instant $t$.

On suppose que le dispositif a été préalablement éloigné de la Terre, dont il ne subit donc aucune interaction gravitationnelle.
On imagine qu'à l'instant $t=0s$, on déploie la voile, qui était initialement pliée. A cet instant, le système se trouve sur une orbite de rayon $r_0$, et devient alors soumis à une nouvelle force, celle de la pression de radiation ; on va noter cette force $\vec{R}$.

De plus, on suppose que la force soit suffisamment petite devant l'interaction gravitationnelle avec le Soleil et donc que ce changement d'orbite soit suffisamment lent pour considérer qu'à tout instant, l'orbite suivie par le système est circulaire ; on ne va pas étudier ici des orbites de transfert d'Hohmann.
Cependant, de manière globale, l'orbite est en spirale, puisque son rayon augmente (ou diminue) progressivement ; nous verrons plus tard dans quelles conditions la trajectoire est divergente ou convergente.

Dans tous les cas, on choisit que le sens de rotation du système autour du Soleil est le sens trigonométrique.

Et enfin, pour étudier ce déplacement, on se sert d'un repère mobile proche de celui de Frenet ; la seule différence est le sens du vecteur unitaire normal, que j'appelle vecteur radial et que je note $\vec{u}_r$. En effet, il pointe vers l'extérieur, comme vous pouvez le voir sur la figure.

## Force de pression de radiation

Maintenant qu'on a posé les fondations de ce modèle, on va essayer d'obtenir une expression de la force de pression de radiation.

Voici la démonstration, que je vais expliciter à l'oral, et voici les différentes notations que je vais utiliser, ainsi que quelques constantes que je vais poser pour alléger l'écriture.

Intuitivement, on peut se douter qu'elle dépend de la lumière qui atteint la voile.

Partons déjà de la température $T$ du Soleil ; la loi de Stefan-Boltzmann, en thermodynamique, nous indique l'expression du du flux lumineux, c'est-à-dire la puissance lumineuse dégagée par un $m^2$ du Soleil. C'est la toute première expression de la feuille.

Pour avoir toute l'énergie dégagée par le Soleil, il faut donc multiplier par la surface du Soleil, qu'on peut assimiler à une boule.
On arrive à la première relation de la deuxième ligne, où $R_S$ est le rayon du Soleil.

Toute cette énergie, une fois qu'elle a quitté le Soleil, se répartit sur une sphère imaginaire, dont le rayon est celui de l'orbite de la voile.

Donc, en posant $K_S$, et en divisant par la surface de cette sphère, on obtient l'irradiance à un rayon $r$ du Soleil : $I(r)=\frac{K_S}{r^2}$. C'est la puissance lumineuse fournie à un $m^2$ de surface à une distance $r$ du Soleil.

On peut maintenant trouver une expression de la force de pression de radiation, en utilisant la quantité de mouvement.
Car en effet la deuxième loi de Newton nous indique que la force est la dérivée temporelle de la quantité de mouvement, et la relation de de Broglie $p=\frac{h}{\lambda}$ nous permet d'obtenir une expression de la force qui dépend du nombre de photons et de leur longueur d'onde.
La souci avec cette approche, c'est qu'on ne sait pas combien de photons frappent la voile par seconde, seulement l'irradiance, et le Soleil n'est pas un laser, les photons ne sont pas de la même longueur d'onde.

Donc on utilise le fait que l'énergie d'un photon vaille $E=\frac{hc}{\lambda}$ pour obtenir l'expression de la ligne 4 où vous pouvez remarquer le coefficient $1+\gamma$, où $\gamma$ est la proportion de lumière réfléchie, donc la proportion de collisions dites élastiques.
En dérivant, on obtient une expression de la force en fonction de la puissance ; c'est la ligne 5.

L'expression de cette puissance est juste en-dessous, et remarquons qu'il s'agit de l'intégration d'un produit scalaire par la surface de la voile $A$.
Le vecteur $\vec{S}$ est d'ailleurs appelé vecteur de Poynting, et il a pour expression $I(r)\cdot \vec{u}_r$.
Et donc on aboutit à l'expression de l'intensité de la force $\vec{R}$.

On pose maintenant $I$ (qui n'est pas l'irradiance de plus tôt, dont on ne se resservira pas), et on peut décomposer la force selon les vecteurs unitaires pour obtenir ce que vous avez sur la ligne 7.


## Etude énergétique du système

Maintenant qu'on a l'expression de cette force, on va réaliser une étude énergétique du système, en notant la masse du Soleil $M_S$ et la masse du dispositif $m$.
On détermine d'abord l'expression de l'énergie mécanique, à la ligne 8.

De plus, la puissance mécanique est égale au produit scalaire de $\vec{R}$ et de la vitesse, qu'on peut décomposer selon les vecteurs unitaires.
De plus, puisque la trajectoire est quasi-circulaire, la vitesse radiale est par définition négligeable.
Et enfin, puisque la puissance mécanique est égale à la dérivée temporelle de l'énergie mécanique, on obtient ce qu'il y  a écrit à la ligne 9.

## Vers une expression pour $r$

Même si on ne le dirait pas encore, on se rapproche d'une expression pour $r(t)$.

En effet, puisqu'on a donné l'expression de l'énergie mécanique, on peut elle aussi la dériver, et on obtient une deuxième expression de $\frac{dE_m}{dt}$.
En identifiant les 2 expressions, en réarrangeant les termes, et avec un peu de calcul différentiel, on aboutit à ce qu'il y a écrit à la ligne n°11.

Et c'est là que la magie des maths opère ; on va passer de $r^{1/2}\frac{dr}{dt}$ à un simple $r$, grâce à l'intégration.
En effet, en primitivant par rapport à $r$ à gauche et par rapport à $t$ à droite, on obtient ce qu'il y a écrit à ligne 13, où on remarque la présence de la constante d'intégration $C$.

Pour la déterminer, on utilise les conditions initiales : on a vu plus tôt qu'à l'instant $t=0s$ le rayon vaut $r_0$.

Finalement, on isole $r$ et on peut remplacer le $I$ et le $K_S$ qu'on avait posé plus tôt à la ligne 2.
Et voici, à la dernière ligne, l'expression de la fonction $r(t)$.

## Optimisations possibles

Essayons de débroussailler cette expression qui a l'air assez barbare.
Quel paramètres peut-on faire varier nous-mêmes ? 
Seuls la réflectivité, la surface de la voile, sa masse et l'angle d'incidence de la lumière.
Ainsi, on remarque que plus on augmente la surface de la voile et/ou sa réflectivité, plus on peut s'éloigner du Soleil en une même durée ; à l'inverse plus on augmente la masse du dispositif, par exemple en rajoutant de la charge, moins on peut s'éloigner du Soleil en une même durée.

On remarque aussi que $r(t)$ est maximal lorsque $\cos\alpha \sin\alpha$ est maximal.
En dérivant cette nouvelle fonction, dont vous pouvez trouver la courbe au verso, et en résolvant une équation sur l'intervalle sur $]-90;90[$, on trouve que $\cos\alpha \sin\alpha$, et donc $r(t)$ aussi, admettent des extrémums en $45°$ et $-45°$.

## Convergence ou divergence

D'autre part, plus tôt dans la démonstration, à la ligne 11, on avait l'expression de la dérivée temporelle de $r$.
Ce qu'on y remarque maintenant, c'est que le signe de $\frac{dr}{dt}$ est le signe de $\sin\alpha$ car tout le reste est positif.
Par étude de la fonction $\sin$, on peut en déduire que lorsque $\alpha$ est compris entre $-90^o$ et $0^o$, $r$ est décroissante, et donc le dispositif se rapproche du Soleil, et la trajectoire est une spirale convergente, alors que lorsque $\alpha$ est compris entre $0^o$ et $90^o$, $r$ est croissante et la trajectoire est une spirale divergente.
Je rappelle que cet angle est mesuré dans le sens trigonométrique du point de vue de la voile.

Avec les informations d'optimisation qu'on a trouvées plus tôt, on peut donc dire que la dispositif se rapproche le plus rapidement du Soleil lorsque l'angle vaut $-45°$ et s'en éloigne le plus rapidement lorsque l'angle vaut $45°$.

## Les matériaux à utiliser

L'objectif est de maximiser la surface de la voile et sa réflectivité tout en minimisant sa masse.
De plus, le matériau à utiliser doit être difficilement déchirable, pour éviter des dégradations lors d'une potentielle collision avec des débris spatiaux.
De plus, il faut éviter tout effet photoélectrique, car dans ce cas, pour un photon, la collision est inélastique, et $\gamma=0$.

Le projet de voile solaire le plus réussi est *IKAROS* de la JAXA, l'agence spatiale japonaise ; le dispositif s'est éloigné de la Terre de 110 millions de kilomètres, et le projet a pris officiellement fin il y a seulement 1 mois.
Ils ont utilisé une membrane de $7.5µm$ d'épaisseur, fait de polyimide, un polymère dont le gap optique vaut $E_g=7.1eV$ et dont le potentiel d'ionisation vaut $IP=8.4eV$ d'après une publication scientifique datant de 1990.

En utilisant la relation qu'on a vue plus tôt, $E=\frac{hc}{\lambda}$ on peut déterminer la longueur d'onde minimale pour qu'un photon ne soit pas absorbé, du moins par l'effet photoélectrique.
On trouve $\lambda_{min}=174nm$ ; or le Soleil n'est pas assez chaud pour émettre des photons d'une telle longueur d'onde.
Ainsi, une voile en polyimide ne subit aucun effet photoélectrique, et encore moins d'ionisation.

## Conclusion

En conclusion, la voile solaire représente une avancée remarquable dans la propulsion spatiale, exploitant uniquement la pression de radiation émise par le Soleil. À travers cette étude, nous avons démontré comment son mouvement peut être modélisé, en tenant compte de plusieurs paramètres influençant l'évolution de son orbite. L'optimisation des matériaux et des dimensions de la voile permet d'améliorer ses performances, que ce soit pour s'éloigner ou se rapprocher du Soleil. Ce concept, encore en développement, ouvre des perspectives fascinantes pour l'exploration spatiale et les missions interstellaires.