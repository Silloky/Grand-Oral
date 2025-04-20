#### 1. Equation du plan $T$

On a $A(x_{A};0;0)$, $B(0;y_{B};0)$ et $C(0;0;z_{C})$

Donc : $\overrightarrow{AB}\begin{pmatrix}0-x_{A}\\y_{B}-0\\0-0\end{pmatrix}\overrightarrow{AB}\begin{pmatrix}-x_{A}\\y_{B}\\z_{C}\end{pmatrix}$ et $\overrightarrow{AC}\begin{pmatrix}0-x_{A}\\0-0\\z_{C}-0\end{pmatrix}\overrightarrow{AC}\begin{pmatrix}-x_{A}\\0\\z_{C}\end{pmatrix}$

On a posé que $\vec{n}\begin{pmatrix}a\\b\\c\end{pmatrix}\perp T$ et $\overrightarrow{AB}$ et $\overrightarrow{AC}$ ne sont pas colinéaires puisqu'une des coordonnées est nulle.
Donc :

$$
\begin{align}
\vec{n}\begin{pmatrix}a\\b\\c\end{pmatrix}\perp T &\implies 
\begin{cases}
\vec{n}\perp \overrightarrow{AB} \\ \\
\vec{n}\perp \overrightarrow{AC}
\end{cases}  \implies \begin{cases}
\vec{n}\cdot \overrightarrow{AB}=0 \\ \\
\vec{n}\cdot \overrightarrow{AC}=0
\end{cases} \\
 \\
&\implies \begin{cases}
-ax_{A}+by_{B}+0\times0=0 \\
-ax_{A}+0\times0+cz_{C}=0
\end{cases} \implies \begin{cases}
ax_{A}=by_{B} \\
ax_{A}=cz_{C}
\end{cases} \\
 \\
\vec{n}\begin{pmatrix}a\\b\\c\end{pmatrix}\perp T &\implies \begin{cases}
b=a\frac{x_{A}}{y_{B}} \\
c=a\frac{x_{A}}{z_{C}}
\end{cases}
\end{align}
$$

Donc en posant $a=1$ on obtient : $\vec{n}\begin{pmatrix}1\\ \frac{x_{A}}{y_{B}} \\ \frac{x_{A}}{z_{C}} \end{pmatrix}$

Ainsi, $T:x+ \frac{x_{A}}{y_{B}}y+\frac{x_{A}}{z_{C}}z+d=0$
Or $A(x_{A};0;0) \in T$ donc ses coordonnées vérifient $T$ :
$$x_{A}+\frac{x_{A}}{y_{B}}\times0+\frac{x_{A}}{z_{C}}\times0+d=0\implies d=-x_{A}$$

Donc finalement : $$T:x+\frac{x_{A}}{y_{B}}y+\frac{x_{A}}{z_{C}}z-x_{A}=0$$
#### 2. Equations paramétriques de la droite $d$

On a posé que la droite $d$ possède un vecteur directeur $\vec{u}\begin{pmatrix}\lambda_{A} \\\lambda_{B}\\\lambda_{C}\end{pmatrix}$
Donc ses équations paramétriques sont :

$$d:\begin{cases}
x=\lambda_{A}\cdot t \\
y=\lambda_{B}\cdot t \\
z=\lambda_{C}\cdot t
\end{cases}, \quad t\in \mathbb{R}$$
#### 3. Intersection de $T$ et $d$

Les coordonnées du point $I$ vérifient l'équation du plan $T$ *et* les équations paramétriques de $d$ :

$$\begin{cases}
x=\lambda_{A}\cdot t \\
y=\lambda_{B}\cdot t \\
z=\lambda_{C}\cdot t \\
x+\frac{x_{A}}{y_{B}}y+\frac{x_{A}}{z_{C}}z-x_{A}=0
\end{cases}$$
On remplace les équations paramétriques dans celle du plan, et on résout pour $t$ :

$$
\lambda_{A}t+\frac{x_{A}}{y_{B}}\lambda_{B}t+\frac{x_{A}}{z_{C}}\lambda_{C}t-x_{A}=0 \implies t\left( \lambda_{A}+\frac{x_{A}}{y_{B}}\lambda_{B}+\frac{x_{A}}{z_{C}}\lambda_{C} \right)=x_{A}
$$
Donc : $$t=\frac{x_{A}}{\lambda_{A}+\frac{x_{A}}{y_{B}}\lambda_{B}+\frac{x_{A}}{z_{C}}\lambda_{C}}$$
Il suffit ensuite de remplacer dans les les équations paramétriques, et on trouve :

$$x_{I}=\frac{x_{A}}{\lambda_{A}+\frac{x_{A}}{y_{B}}\lambda_{B}+\frac{x_{A}}{z_{C}}\lambda_{C}}\cdot\lambda_{A} \quad\text{et}\quad y_{I}=\frac{x_{A}}{\lambda_{A}+\frac{x_{A}}{y_{B}}\lambda_{B}+\frac{x_{A}}{z_{C}}\lambda_{C}}\cdot\lambda_{B} \quad\text{et}\quad z_{I}=\frac{x_{A}}{\lambda_{A}+\frac{x_{A}}{y_{B}}\lambda_{B}+\frac{x_{A}}{z_{C}}\lambda_{C}}\cdot\lambda_{C}$$

#### 4. Distance $f=OI$

On utilise une simple distance euclidienne :

$$\begin{align}
f&=\sqrt{ x_{I}^2+y_{I}^2+z_{I}^2 } \\
&=\sqrt{ (\lambda_{A}t)^2+(\lambda_{B}t)^2+(\lambda_{C}t)^2 } \\
&=\sqrt{ t^2(\lambda_{A}^2+\lambda_{B}^2+\lambda_{C}^2) } \\
f&=t\cdot \sqrt{ \lambda_{A}^2+\lambda_{B}^2+\lambda_{C}^2 }
\end{align}$$

Ainsi, finalement, à partir de 6 paramètres d'entrée ($x_{A}$, $y_{B}$, $z_{C}$, $\lambda_{A}$, $\lambda_{B}$ et $\lambda_{C}$), on obtient un score final, où tous les paramètres sont pris en compte :

$$f=\frac{x_{A}\cdot\sqrt{ \lambda_{A}^2+\lambda_{B}^2+\lambda_{C}^2}}{\lambda_{A}+\frac{x_{A}}{y_{B}}\lambda_{B}+\frac{x_{A}}{z_{C}}\lambda_{C}}$$
