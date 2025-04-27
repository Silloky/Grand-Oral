## 1. Etude de la pression de radiation et de la force qui en résulte

On part de la température $T$ en kelvin du soleil.
On utilise la loi de Stefan-Boltzmann pour obtenir le flux lumineux $\varphi_{S}$ :
$$\phi_{S}=\sigma \cdot T^4\quad[\pu{ W.m-2}]$$
C'est le flux quittant la surface du Soleil ; pour avoir la luminosité $L_{\odot}$, on multiplie par la surface du Soleil, $4\pi R_{S}^2$, si $R_{S}$ est le rayon solaire.
Donc :
$$L_{\odot}=\phi_{S}\times{4\pi R_{S}^2}=\sigma \cdot T^4 \times 4\pi R_{S}^2 \quad [\pu{ W}]$$
On veut connaître l'intensité lumineuse à une distance $r$ du centre du Soleil (il s'agit du rayon de l'orbite circulaire, donc la distance voile-centre du Soleil) :
$$I(r)=\frac{L_{\odot}}{4\pi r^2}=\frac{\sigma \cdot T^4\cdot4\pi R_{S}^2}{4\pi r^2}=\frac{\sigma \cdot T^4\cdot R_{S}^2}{r^2} \quad [\pu{ W.m-2}]$$
Posons $k=\sigma T^4\cdot R_{S}^2$ en $W$ afin de simplifier l'expression précédente : $I(r)=\frac{1}{r^2}\cdot k$

On introduit un paramètre $\gamma$ qui correspond à la proportion de lumière réfléchie par la voile.
Des démonstrations trop compliquées à réaliser ici (elles abordent des notions de relativité, de quantité de mouvement, etc...), permettent de passer à la pression de radiation, que l'on note $P(r)$.
Ainsi : $P=\frac{(1+\gamma)I}{c}\cdot \cos^2(\alpha)$ où $\alpha$ est l'angle d'incidence des rayons par rapport à la normale (on prend son $\cos$ car seule la composante normale agit sur la voile) et $c$ la célérité.
Et donc dans notre cas : 
$$P(r)=\frac{1}{r^2}\cdot \frac{(1+\gamma)k}{c}\cdot \cos^2(\alpha) \quad [\pu{ N.m^-2}]$$

On passe de la pression à l'intensité de la force de la radiation avec la relation $P=\frac{F}{A} \implies F=P\cdot A$ : 
$$F_{R}(r)=\frac{1}{r^2}\cdot \frac{(1+\gamma)Ak}{c} \cdot \cos^2(\alpha) \quad [\pu{ N}] \quad \text{avec} \quad k=\sigma T^4\cdot R_{S}^2\quad [\pu{ W}]$$
On peut tout de suite tenter avec des valeurs.
Si l'on prend une voile qui réfléchit totalement la lumière ($\gamma=100\%=1$), perpendiculaire aux rayons ($\alpha=0^o$), située à $r=\pu{ 1AU }=\pu{ 1.496*10^11 m }$ du Soleil, qui possède une température de $T=\pu{ 5772K }$ et un rayon de $R_{S}=\pu{ 6.96*10^8m }$, et que l'on prend $\sigma=\pu{ 5.670*10^−8 W.m−2.K−4 }$ et $c=\pu{ 3*10^8m.s-1 }$ on obtient une pression de :

$$
\begin{align}
\text{AN :}\quad P&=\frac{1}{(\pu{ 1.496*10^11})^2}\cdot\frac{(1+1)\cdot(\pu{ 5.670*10^-8}\cdot(5772)^4\cdot(\pu{ 6.96*10^8})^2)}{\pu{ 3*10^8 }}\cdot \cos^2(0) \\
&=\pu{ 9.08*10^-6N.m-2 } \\
P&=\pu{ 9.08µPa }
\end{align}
$$
Ce qui correspond parfaitement au tableau renseigné sur la page [Wikipedia](https://en.wikipedia.org/wiki/Radiation_pressure#Radiation_pressure_perturbations) .

## 2. Etat du système initialement et conjecture de trajectoire

### 2.1. Etat initial et bilan des forces

On suppose qu'à l'instant $t=\pu{ 0s}$, le dispositif de masse $m$ est en mouvement circulaire uniforme, et se déplace selon une orbite considérée donc circulaire autour du Soleil.
Le rayon de cet orbite est donné par $r$.
On modélise le dispositif par un point matériel $M$ et le Soleil par le point matériel $S$, et on munit le plan d'un repère de Frenet $(M,\vec{u}_{r}, \vec{u}_{t})$ où $\vec{u}_{r}$ correspond au vecteur unitaire normal à la trajectoire, donc radial, et orienté à l'opposé de $S$, et $\vec{u}_{t}$ le vecteur unitaire tangentiel.

Les forces qui s'appliquent au système sont donc :
* l'intéraction gravitationnelle $\vec{F}_{G}=-G\frac{m_{S}\cdot m}{r^2}\cdot \vec{u}_{r}$ où $m_{S}$ est la masse du Soleil, qui attire le dispositif vers le Soleil
* la pression de radiation, répulsive : $\vec{F}_{R}=||\vec{F}_{R}||\cdot \vec{u}_{r}=F_{R}\cdot \vec{u}_{r}$

$\vec{F}_{g}$ et $\vec{F}_{R}$ sont donc colinéaires et de sens opposés ; au vu de la valeur trouvée à la partie précédente pour $F_{R}$, il semble logique $F_{G}$ sera toujours plus grande, et donc que $\vec{F}_{g}$ aura toujours plus d'impact.
Nous y reviendrons plus tard.

D'après la deuxième loi de Newton, $m\vec{a}=\Sigma \vec{F}$ donc ici :$$ \vec{a}(r)=\frac{\vec{F}_{G}+\vec{F}_{R}}{m}=\frac{1}{r^2}\cdot\frac{(1+\gamma)Ak}{cm}\cdot \vec{u}_{r}-G\frac{m_{S}\cancel{ m }}{r^2\cancel{ m }}\cdot \vec{u}_{r}=\frac{1}{r^2}\cdot\left( \frac{(1+\gamma)Ak\cdot \cos^2(\alpha)}{cm} -Gm_{S}\right) \cdot \vec{u}_{r}$$
On remarque que l'accélération demeure uniquement radiale : le vecteur accélération ne possède pas de composante tangentielle exprimée en fonction de $\vec{u}_{t}$

### 2.2. Trajectoire

On connaît donc à présent la direction et le sens de $\vec{a}$ et on étudie maintenant à l'infini le comportement de l'intensité de l'accélération, que l'on notera à présent $a_{r}$

En effet, puisque $\frac{(1+\gamma)Ak\cdot \cos^2(\alpha)}{cm} -Gm_{S}<0$ car $m_{S}\gg \frac{x}{c}$, le vecteur $\vec{a}$ est colinéaire et de sens opposé à $\vec{u}_{r}$
Ainsi, le système n'accélère pas vers l'extérieur, mais accélère moins vers l'intérieur que s'il ne subissait pas la force de pression de radiation ; par conséquent, il s'éloigne du centre de son orbite : $r$ augmente.
Il conserve cependant sa vitesse tangentielle, puisqu'il n'y a aucune accélération tangentielle qui la modifie.

Donc, la voile solaire suit une trajectoire en spirale divergente : à chaque instant $t$, elle s'éloigne un petit peu du Soleil.
En fait, à chaque instant, on peut modéliser ceci par le fait qu'à tous les instants, la voile se trouve sur une orbite circulaire dont le rayon est une fonction du temps.
Car en effet, on introduit dès lors la fonction $r(t)$


## 3. Etude cinématique de la voile

Pour alléger les calculs suivants, notons $J=\left( \frac{(1+\gamma)Ak\cdot \cos^2(\alpha)}{cm} -Gm_{S}\right)$ qui est une constante

On a donc à présent : $a_{r}(r(t))=\frac{1}{r(t)^2}J$
On sait que l'accélération est la dérivée seconde de la position ; étant donné qu'ici l'accélération est uniquement radiale, on peut écrire :
$$\ddot{r}=a_{r}(r(t))=\frac{1}{r(t)^2}J$$
On se retrouve avec l'équation différentielle $\frac{d^2r}{dt^2}=\frac{1}{r^2}J$


https://youtu.be/Oxcw8SdmAhI





 













### 2.2. Signe et limite de l'accélération

On a : $a_{r}=\frac{1}{r^2}\cdot\left( \frac{(1+\gamma)Ak\cdot \cos^2(\alpha)}{cm} -Gm_{S}\right)$
Or $\lim_{ r \to +\infty }(r^2)=+\infty$ et $\lim_{ y \to +\infty }\left( \frac{1}{y} \right)=0^+$ et $\frac{(1+\gamma)Ak\cdot \cos^2(\alpha)}{cm} -Gm_{S}>0$ car $m_{S}\gg \frac{x}{c}$ donc :
$$\lim_{ r \to +\infty } (a)=0^+$$
Autrement dit, lorsque $r$ tend vers l'infini, l'intensité de l'accélération radiale tend vers $0$, et donc que le vecteur vitesse tend vers un équilibre, puisque $\frac{d}{dr}\vec{v}=\vec{a}\implies \frac{d}{dr}v_{r}=a_{r}$. 
Le dispositif tend alors vers un mouvement rectiligne uniforme dans la direction tangentielle (j'y reviendrai plus tard).

Mais avant d'y arriver... $a_{r}$ commence loin de $0$, puisque $F_{G}(0)\gg F_{R}(0)$, pour tendre vers $0^+$.
L'accélération a donc été décroissante, mais toujours positive ; la vitesse radiale est donc elle toujours croissante.
Ainsi, le dispositif s'éloigne 




En tout cas, jusqu'à ce point, c'est $\vec{F}_{G}$ qui est majoritaire, donc $\vec{F}_{G}<\Sigma \vec{F}<\vec{0}$ 
On peut alors conjecturer la trajectoire du dispositif.

En effet, si l'accélération

La loi des périodes de Kepler nous indique que (dans le cas spécifique d'une orbite circulaire),




















à partir de quelle distance $r_{inv}$ cela s'inverse, et le dispositif passe en mouvement rectiligne, et 

