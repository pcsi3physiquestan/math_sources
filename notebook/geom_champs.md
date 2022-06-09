---
jupytext:
  encoding: '# -*- coding: utf-8 -*-'
  formats: ipynb,md:myst
  split_at_heading: true
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.10.3
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---
# Champs scalaires et champs vectoriels
Nous allons être très souvent confrontés à des grandeurs définies en tout l'espace (ou portion). On parlera de __champ__. On peut citer l'énergie potentielle qui peut se définir en tout point de l'espace.

Nous sommes alors confrontés à des fonctions de plusieurs variables (les 3 variables d'espaces différentes suivant le systèmes de coordonnées).

Mais comme dans le cas d'une fonction à plusieurs variables, on peut être amené à s'interroger sur la monotonie d'une telle fonction. Il apparaît évident que les concepts mathématiques doivent être modifiés (en effet, en un même point, on peut compredre que le taux de variation va dépendre de la direction dans laquelle on se déplace - suivant x ? suivant y ? suivant x ET z ? ... ).

C'est dans cette optique que nous allons introduire la notion de __gradient__.

## Champ vectoriel et champ scalaire
__Champ vectoriel et champ scalaire__  
Soit une fonction f qui associe à tout point de l'espace un réel (un scalaire). On dit que f est un champ scalaire.

Soit une fonction f qui associe à tout point de l'espace un vecteur. On dit que f est un champ vectoriel. Par convention, on note les champs vectoriels avec une flèche comme des vecteurs.

__Expression des champs__  
Un champ scalaire peut être vu comme une fonction de trois variables: les trois coordonnées de l'espace. Il pourra avoir différentes expressions suivant le système de coordonnée choisi.

Un champ vectoriel peut être vu comme un vecteur dont les coordonnées dépendent du point M (trois fonctions scalaires). Cette vision suffit lorsqu'on est en coordonnées cartésiennes où la base est globale. Si l'on exprime le champ vectoriel dans des coordonnées cylindriques ou sphériques, il ne faut pas oublier que les vecteurs de la base vont aussi varier avecle point M.


````{admonition} Exemple
:class: hint
Considérons l'énergie potentielle associée à une force (par exemple la pesanteur). On peut associer à tout point de l'espace $M(x,y,z)$ une énergie potentielle $E_p(x,y,z)$. Par exemple $E_p(x,y,z) = mgz$ (dans ce cas, le champ ne dépend pas de x et y).

Un dispositif magnétique (aimant par exemple) crée un champ magnétique en tout point de l'espace. Il s'agit d'un champ vectoriel $\overrightarrow{B}(M)$.
````

## Dérivation et différentielle

### Dérivées partielles
__Dérivées partielles__  
Soit un champ scalaire $f(x,y,z)$, on définit la dérivée partielle ${(\frac{\partial f}{\partial x})}_{y,z}(x_0,y_0,z_0)$ comme la dérivée en $x=x_0$ de la fonction $g$ qui à $x$ associe $g(x) = f(x,y_0,z_0)$.

Cela revient à traiter $f$ comme une fonction d'une variable où y et z sont des constantes. On parle de dérivée partielle de f par rapport à x à y et z constants.


````{dropdown} Remarque
__Variables constantes__  
Les variables en indice définissent les variables qui restent constantes. En mécanique, on les omet souvent car elles sont évidentes. Elles deviendront extrêmement importante en thermodynamique car elles peuvent changer.
````

__Interprétation__  
On rappelle qu'une dérivée est un taux de variation qui donne une information sur la pente de la courbe. Ici, il s'agit d'une fonction de plusieurs variables, sa représentation n'est plus une courbe (cette représentation n'est d'ailleurs possible que pour une fonction de deux variables: c'est une surface). Mais on peut s'intéresser au taux de variation dans une direction particulière: celle où une seule des variables varie (x pour une dérivée partielle par rapport à x).

Les dérivées partielles donnent donc des informations sur les variations d'un champ scalaire dans certaines directions de l'espace. Mais nous allons voir qu'avec ces informations, on peut obtenir la variation du champ scalaire en un point M dans n'importe quelle direction de l'espace.

### Calcul de dérivées partielles

````{admonition} Exercice 
:class: attention
On considère les fonctions:

\begin{align*}
	f(x,y) &= xy^2\\
	g(r, \theta) &= r \sin \theta
\end{align*}

Calculer toutes les dérivées partielles.
````

````{dropdown} Correction
On trouve:

\begin{align*}
	\frac{\partial f}{\partial x} &= y^2\\
	\frac{\partial f}{\partial y} &= 2xy\\
	\frac{\partial f}{\partial r} &= \sin \theta \\
	\frac{\partial f}{\partial \theta} &= r \cos\theta
\end{align*}
````

### Déplacement infinitésimal
Un déplacement élémentaire $\overrightarrow{dOM}$ correspond à un déplacement infinitésimal (c'est-à-dire tendant vers O) à partir du point M vers un point M': $\overrightarrow{dOM} = \overrightarrow{MM'}_{M' \to M}$.

On ne précise pas ici comment M' tend vers M (en ligne droite, en ligne courbe, suivant l'axe Ox, suivant une direction dans le plan xOy... ). Suivant les cas cette précision a son importance. On distingue deux cas:

* on utilise un déplacement infinitésimal le plus général possible. On considère alors que chaque coordonnées du point M varie de manière infinitésimal et indépendante pour donner les coordonnées du point M'.

Par exemple, en coordonnées cartésiennes, on va passer d'un point $M(x,y,z)$ à un point $M'(x+dx,y+dy,z+dz)$ où dx, dy et dz représentent des variations infinitésimales des trois coordonnées.

* on utilise un déplacement infinitésimal dans une direction particulière. C'est en général le cas quand on suit une courbe (une trajectoire par exemple). On peut alors utiliser l'expression du déplacement élémentaire général en préciser des expressions pour les variations élémentaires.


````{important} __Fondamental : Déplacement infinitésimal en coordonnées cartésiennes.__
On rappelle qu'on passe d'un point $M(x,y,z)$ à un point $M'(x+dx, y+dy, z+dz)$. Il vient que le déplacement élémentaire est:

\begin{equation}
\overrightarrow{dOM} = dx \overrightarrow{e_x} + dy \overrightarrow{e_y} + dz \overrightarrow{e_z}
\end{equation}

En effet, on observe sur le schéma suivant que l'on peut décomposer le vecteur en une somme de trois vecteurs dans chaque direction Ox, Oy et Oz de distance respectives dx, dy et dz.

```{figure} ./images/mecanique_depl_elem_cartesien.png
:name: fig_349
:align: center
```
````

Les expressions des déplacements élémentaires dans chaque système de coordonnées doivent être connus et on doit savoir redémontrer leur expression. Le cas des coordonnées cylindriques et sphériques sera traité en exercice par la suite.


### Expression du déplacement élémentaire.
On rappelle qu'il faut connaître par coeur ces expressions et savoir les démontrer.

````{admonition} Exercice 
:class: attention
Montrer que le déplacement élémentaire en coordonnées cylindriques s'écrit:

\begin{equation}
\overrightarrow{dOM} = dr \overrightarrow{e_r} + r d \theta \overrightarrow{e_{\theta}} + dz \overrightarrow{e_z}
\end{equation}
````

````{dropdown} Correction
On fait varier chaque coordonnées de manière élémentaire. On passe donc du point $M(r, \theta, z)$ au point M' $(r+ dr, \theta + d\theta, z + dz)$.

On va décomposer le déplacement élémentaire siuvant trois directions: suivant $\overrightarrow{e_{\theta}}, \overrightarrow{e_r}$ et $\overrightarrow{e_z}$. Il faut noter que le déplacement "courbe" se fait suivant sa tangente (donc suivant $e_{\theta}$ puisqu'il s'agit d'une variation infinitésimale, donc tendant vers 0.

Les successifs sont déplacements sont $r d\theta \overrightarrow{e_{\theta}}, dr \overrightarrow{e_r}$ et $dz \overrightarrow{e_z}$.

```{figure} ./images/mecanique_depl_elem_cylindrique.png
:name: fig_350
:align: center
```

Il vient un déplacement élémentaire:

\begin{equation}
\overrightarrow{dOM} = dr \overrightarrow{e_r} + r d \theta \overrightarrow{e_{\theta}} + dz \overrightarrow{e_z}
\end{equation}
````
````{admonition} Exercice
:class: attention
Montrer que le déplacement élémentaire en coordonnées sphériques s'écrit:
\begin{equation}
\overrightarrow{dOM} = dr \overrightarrow{e_r} + r d \theta \overrightarrow{e_{\theta}} + r \sin \theta d\varphi \overrightarrow{e_{\varphi}}
\end{equation}\end{exercice}
````

````{dropdown} Correction
On fait varier chaque coordonnées de manière élémentaire. On passe donc du point $M(r, \theta, \varphi)$ au point M' $(r+ dr, \theta + d\theta, \varphi + d\varphi)$.

On va décomposer le déplacement élémentaire siuvant trois directions: suivant $\overrightarrow{e_{\theta}}, \overrightarrow{e_{\varphi}}$ et $\overrightarrow{e_r}$. Il faut noter que les déplacements "courbe" se fait suivant les tangentes au méridien (quand $\theta$ varie) soit suivant $\overrightarrow{e_{\theta}}$ et au parallèle (quand $\varphi$ varie) soit suivant $\overrightarrow{e_{\varphi}}$.

Les successifs sont déplacements sont $r d\theta \overrightarrow{e_{\theta}}, r \sin \theta d\varphi \overrightarrow{e_{\varphi}}$ et $dr \overrightarrow{e_r}$.

```{figure} ./images/mecanique_depl_elem_spherique.png
:name: fig_351
:align: center
```

Il vient un déplacement élémentaire:

\begin{equation}
\overrightarrow{dOM} = dr \overrightarrow{e_r} + r d \theta \overrightarrow{e_{\theta}} + r \sin \theta d\varphi \overrightarrow{e_{\varphi}}
\end{equation}
````

### Différentielle
Attention, il ne s'agit pas d'une définition mathématique mais d'une description physique permettant de raisonner.

__Différentielle__  
Considérons un point M de l'espace et un déplacement infinitésimal quelconque $\overrightarrow{dOM}$.

La différentielle df du champ scalaire f autour du point M est la variation infinitésimale de f du point M vers un point M' tel que $\overrightarrow{MM'} = \overrightarrow{dOM}$.

__Expression générale de la différentielle. (Admis)__  
La différentielle du champ f en un point M de coordonnées $(\xi,\zeta,\eta)$ est:

\begin{equation}
df = \frac{\partial f}{\partial \xi} d\xi + \frac{\partial f}{\partial \zeta} d\zeta + \frac{\partial f}{\partial \eta} d\eta
\end{equation}
où $(\xi,\zeta,\eta)$ représentent les 3 coordonnées du point M dans un système de coordonnées.

````{dropdown} Remarque
On peut comprendre qu'on commence à s'approcher d'une notion permettant de généraliser la dérivée. Mais cette dernière n'est pas une variation mais un taux de variation (donc divisé par la variation de l'abscisse). Ici une telle division n'a pas de sens. Nous pouvons néanmoins voir que la donnée des trois dérivées partielles en fonction de chaque coordonnées permet de prévoir la variation du champ scalaire dans toutes les directions. C'est ce qui va motiver l'introduction du gradient par la suite.

Il faut noter que l'expression donnée ici de la différentielle peut se généraliser à des fonctions de plusieurs variables qui ne sont pas des coordonnées d'espace.

Exemple: pour un gaz la pression P(T,V) où T et V sont la température et le volume.
````

## Gradient

### Gradient

__Observation__  
On désire généraliser le concept de dérivée. Si l'on se base sur la notion du taux de variation, on peut dire que lorsqu'on se déplace de $dx $, la dérivée $f'(x)$ permet de connaître la variation df de la fonction f: $df = f'(x) dx$ (on rappelle que c'est une égalité car le passage à la limite est implicite avec la notation différentielle).

Ici on veut connaître la différentielle df de la fonction f en un point M pour un déplacement élémentaire $\overrightarrow{dOM}$.


````{important} __Définition : Gradient__

On définit le gradient de la fonction f en en un point M comme le vecteur noté $\overrightarrow{grad}f$ tel que:

\begin{equation}
df = \overrightarrow{grad}f \cdot \overrightarrow{dOM}
\end{equation}

où df est la variation infinitésimale de f à partir du point M en suivant le déplacement élémentaire $\overrightarrow{dOM}$.
````

Comme nous allons le voir, il existe des expressions du gradient en fonctions des dérivées partielles suivant le type de coordonnées choisi.


### Propriétés du gradient
Avant d'établir les expressions du gradient dans chaque système de coordonnées, on va déjà établir certaines propriétés intéressantes du gradient.

__Intégration du gradient__
A l'image de la dérivée, on peut "intégrer" le gradient pour trouver une variation de la fonction f:

\begin{equation}
\Delta f = f(B) -f(A) = \int_{\Gamma(A \to B)} \overrightarrow{grad}f \cdot \overrightarrow{dl}
\end{equation}

L'intégrale proposée ici est appelée "intégrale de chemin" car on va intégrer le produit scalaire $\overrightarrow{grad}f \cdot \overrightarrow{dl}$ sur un chemin allant de A vers B. Dans ce cas, le déplacement élémentaire doit être tangent au chemin, ce qui conditionne a priori son expression (les déplacements élémentaires sont dépendants les uns des autres). Le calcul d'une intégrale de chemin sera explicitée en cours de physique (pour des calculs de travail d'une force).

__Ici__ le chemin pour l'intégrale n'a pas d'importance: l'intégrale d'un gradient __ne dépend pas du chemin parcouru__. Elle se résume toujours à la différence des valeurs de la fonction f aux points A et B. C'est une caractéristique fondamentale qu'on réutilisera lorsqu'on parlera des forces dérivant d'une énergie potentielle.

__Analogie topographique__  
Il est conseillé pour mieux visualiser les caractéristiques suivantes d'imaginer un champ scalaire z(x,y) qui donnerait l'altitude z en un point de coordonnées (x,y) sur une carte topographique.

__Orientation et sens du gradient__  
Le gradient est toujours orienté dans la direction où le champ f varie le plus fortement et dans le sens croissant de f (suivant la droite de plus grande pente).

_Démonstration: la variation df est maximale quand $\overrightarrow{grad}f \cdot \overrightarrow{dOM}$ est maximal soit quand le gradient est colinéaire (et dans le même sens) au déplacement élémentaire._

__Courbe iso-f__
Le gradient est toujours perpendiculaire aux courbes/surfaces où la fonction f est uniforme (f(x,y,z) = cste - les courbes iso-altitude sur une carte topographique).

_Démonstration: Pour un déplacement élémentaire le long de la courbe iso-f (ou contenu dans la surface iso-f), la différentielle df est nulle. Il vient que le gradient est perpendicualaire à ce déplacement élémentaire donc à la courbe/surface._

__Nullité du gradient__  
Un gradient nul implique que chaque dérivée partielles est nulle, c'est-à-dire que la fonction f atteint un extremum suivant chaque coordonnées. On distingue alors plusieurs cas:
* c'est un minimum local pour chaque coordonnées: c'est un minimum local du champ.
* c'est un maximum local pour chaque coordonnées: c'est un maximum local du champ.
* c'est un minimum pour une coordonnées et un maximum pour l'autre: c'est un point "col" (comme un col de montagne).

Pour visualiser ces situations, on a représenté une surface topographique z(x,y) pour chaque cas (minimum, maximum, point col).

```{figure} ./images/math_gradient_min.jpg
:name: fig_352
:align: center
```

```{figure} ./images/math_gradient_max.jpg
:name: fig_353
:align: center
```

```{figure} ./images/math_gradient_col.jpg
:name: fig_354
:align: center
```


### Expressions du gradient
On rappelle que la différentielle s'écrit suivant le système de coordonnées choisi (précisons qu'a priori, l'expression de f dépend des coordonneés choisies):

\begin{align*}
	df(x,y,z) = \frac{\partial f}{\partial x} dx + \frac{\partial f}{\partial y} dy + \frac{\partial f}{\partial z} dz \\
	df(r,\theta,z) = \frac{\partial f}{\partial r} dr + \frac{\partial f}{\partial \theta} d\theta + \frac{\partial f}{\partial z} dz \\
	df(r,\theta,\varphi) = \frac{\partial f}{\partial r} dr + \frac{\partial f}{\partial \theta} d\theta + \frac{\partial f}{\partial \varphi} d\varphi
\end{align*}

On veut pouvoir déterminer l'expression du gradient qui sera le vecteur $\overrightarrow{grad}f$ tel que $df = \overrightarrow{grad}f \cdot \overrightarrow{dOM}$. On va donc utiliser les expressions du déplacement élémentaire dans les différents systèmes de coordonneés: $\overrightarrow{dOM} = dx \overrightarrow{e_x} + dy \overrightarrow{e_y} + dz \overrightarrow{e_z}$, $\overrightarrow{dOM} = dr \overrightarrow{e_r} + r d \theta \overrightarrow{e_{\theta}} + dz \overrightarrow{e_z}$ et $\overrightarrow{dOM} = dr \overrightarrow{e_r} + r d \theta \overrightarrow{e_{\theta}} + r \sin \theta d\varphi \overrightarrow{e_{\varphi}}$.

__Expression du gradient dans les systèmes de coordonnées__  
En identifiant chaque terme du produit scalaire, il vient directement que:

\begin{align*}
	\overrightarrow{grad} f (x,y,z) = \frac{\partial f}{\partial x} \overrightarrow{e_x} + \frac{\partial f}{\partial y} \overrightarrow{e_y} + \frac{\partial f}{\partial z} \overrightarrow{e_z}\\
	\overrightarrow{grad} f (r,\theta,z) = \frac{\partial f}{\partial r} \overrightarrow{e_r} + \frac{1}{r}\frac{\partial f}{\partial \theta} \overrightarrow{e_\theta} + \frac{\partial f}{\partial z} \overrightarrow{e_z}\\
	\overrightarrow{grad} f (r,\theta,\varphi) = \frac{\partial f}{\partial r} \overrightarrow{e_r} + \frac{1}{r}\frac{\partial f}{\partial \theta} \overrightarrow{e_\theta} +\frac{1}{r \sin \theta} \frac{\partial f}{\partial \varphi} \overrightarrow{e_\varphi}
\end{align*}

````{dropdown} Remarque
Ces formules peuvent être directement utilisées.
````
