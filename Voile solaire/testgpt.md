## 1) Bilan vectoriel radial

Soit $\vec r(t)$ le vecteur position du dispositif depuis le Soleil. On ne s’intéresse qu’à la **composante radiale** du mouvement, c’est-à-dire la projection sur $\hat r$.

### a. Force gravitationnelle  
$$
\vec F_g
= -\frac{G\,M\,m}{r^2}\,\hat r
\;\Longrightarrow\;
\text{accélération grav. radiale} 
= -\frac{G\,M}{r^2}.
$$

### b. Force de pression de radiation  
- Intensité solaire à la distance $r$ :  
  $$
  I = \frac{L_\odot}{4\pi\,r^2}.
  $$
- Pression de radiation :  
  $$
  P_r = \frac{I}{c} = \frac{L_\odot}{4\pi\,r^2\,c}.
  $$
- Force sur la voile de surface $A$ :  
  $$
  \vec F_p
  = P_r\,A\,\hat r
  = \frac{L_\odot\,A}{4\pi\,r^2\,c}\,\hat r.
  $$
- Accélération radiale due à la radiation :  
  $$
  +\frac{L_\odot\,A}{4\pi\,m\,c\,r^2}.
  $$

### c. Résultante radiale  
$$
m\,\ddot r
= F_{p,\rm rad} + F_{g,\rm rad}
\quad\Longrightarrow\quad
\ddot r
= \underbrace{\frac{L_\odot\,A}{4\pi\,m\,c} - G\,M}_{C}\,\frac{1}{r^2}.
$$

On pose  
$$
C = \frac{L_\odot\,A}{4\pi\,m\,c} - G\,M,
\quad
\ddot r = \frac{C}{r^2}.
$$

---

## 2) Passage à la vitesse radiale

Définissons la **vitesse radiale**  
$$
v_r = \dot r.
$$  
Par la règle de la chaîne,  
$$
\ddot r
= \frac{d}{dt}(\dot r)
= \frac{dv_r}{dt}
= \frac{dv_r}{dr}\,\frac{dr}{dt}
= v_r\,\frac{dv_r}{dr}.
$$  
L’équation $\ddot r = C/r^2$ devient  
$$
v_r\,\frac{dv_r}{dr}
= \frac{C}{r^2}.
$$

---

## 3) Intégration pour obtenir $v_r(r)$

Séparons et intégrons par rapport à $r$ :

$$
\int v_r\,dv_r
= \int \frac{C}{r^2}\,dr
\;\Longrightarrow\;
\frac12\,v_r^2 = -\frac{C}{r} + K.
$$

**Condition initiale** : à $t=0$, $r(0)=r_0$ et $v_r(0)=0$.  
Donc  
$$
0 = -\frac{C}{r_0} + K
\;\Longrightarrow\;
K = \frac{C}{r_0}.
$$  

On obtient, pour l’éloignement ($v_r\ge0$) :

$$
\boxed{
v_r(r)
= \sqrt{\,2\,C\Bigl(\frac1{r_0}-\frac1r\Bigr)\,}
}
\quad\text{avec}\quad
C = \frac{L_\odot\,A}{4\pi\,m\,c} - G\,M.
$$

---

## 4) Passage à $v_r(t)$ (quadrature)

On sait que  
$$
\frac{dr}{dt} = v_r(r)
\quad\Longrightarrow\quad
dt = \frac{dr}{\sqrt{2\,C\bigl(\tfrac1{r_0}-\tfrac1r\bigr)}}.
$$  
En intégrant de $r_0$ (à $t=0$) à $r(t)$ :

$$
\boxed{
t
= \int_{r_0}^{r(t)}
  \frac{du}
       {\sqrt{\,2\,C\bigl(\tfrac1{r_0}-\tfrac1u\bigr)\,}}
}
$$  

Cette relation donne **implicitement** $r(t)$.  
Enfin,

$$
\boxed{
v_r(t)
= \sqrt{\,2\,C\Bigl(\frac1{r_0}-\frac1{r(t)}\Bigr)\,}.
}
$$
