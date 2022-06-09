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
# Géométrie dans le plan
_Le plan peut être assimilé à l'espace vectoriel $\mathbb{R}^2$ et les caractéristiques énoncées précédemment restent vraies. A noter qu'il s'agit donc d'un espace de dimension 2. Précisons qu'on sera en physique amené à parler de points dans l'espace en parlant de __repère__ et certains vecteurs auront un "point d'application". On travaille alors dans un espace affine et non vectoriel. Celà étant les propriétés et méthodes vues précédemment ainsi que le vocabulaire restera en physique identique et cette subtile distinction a peu d'importance pour nous._

## Produit scalaire usuel du plan

````{dropdown} Angle orienté du plan
Soit deux vecteurs $\overrightarrow{u}$ et $\overrightarrow{v}$ du plan. On définit l'angle orienté $\theta = (\overrightarrow{u}; \overrightarrow{v})$ comme l'angle orienté allant de $\overrightarrow{u}$ vers $\overrightarrow{v}$.
````

On rappelle que:
* la valeur de l'angle en radian est égale, en valeur absolue, à la longueur de l'arc de cercle de rayon 1 et de centre O délimité par $\overrightarrow{u}$ et $\overrightarrow{v}$
* le signe de $\theta$ est défini par convention, __dans le plan__, comme positif dans le sens trigonométrique et négatif dans l'autre sens.


````{dropdown} Produit scalaire usuel du plan
Dans le plan, on utilise le produit scalaire usuel tel que: $\overrightarrow{u}\cdot\overrightarrow{v} = u v\cos (\overrightarrow{u}; \overrightarrow{v})$ avec u et v les longueurs des vecteurs. Cette notion visuelle des longueurs reste cohérente avec la norme euclidienne définie précédemment.
````

_Il faut noter qu'on utilisera au maximum la bilinéarité et la projection dans une base orthonormée plutôt que de passer par cette formule. Elle devient néanmoins très utile et indispensable lorsque les deux vecteurs ne sont pas exprimer dans la même base (cf. suite)._


## Coordonnées cartésiennes
__Coordonnées cartésiennes__  
Dans le plan, on peut définir une base orthonormée $(\overrightarrow{e_x}; \overrightarrow{e_y})$ et lui associer un point origine O. Le triplet $(O, \overrightarrow{e_x}, \overrightarrow{e_y})$ défini un __repère__ orthonormée. On lui associe un système de coordonnée cartésien.

Les coordonnées (x,y) d'un point M du plan dans le repère correspond aux composantes (scalaires) du vecteur $\overrightarrow{OM} = x \overrightarrow{e_x} + y \overrightarrow{e_y}$.

Le repère ainsi défini est dit $global$ car les vectaurs de la base associée ne dépendent pas du point M considéré dont on veut exprimer les coordonnées.


````{attention}, dropdown
Par convention, le second vecteur ($\overrightarrow{e_y}$) est toujours orienté de telle sorte que l'angle $(\overrightarrow{e_x}, \overrightarrow{e_y})$ soit égale à $+ \frac{\pi}{2}$.
````

## Coordonnées polaires

### Coordonnées polaires: Définition
__Système de coordonnées polaires.__  
Soit un point M du plan et un repère cartésien $(O, \overrightarrow{e_x}, \overrightarrow{e_y})$. On définit les coordonnées polaires du M dans un système de centre O et d'origine des angles $\overrightarrow{e_x}$ comme les coordonnées $(r,\theta)$ où:

* $r$ est la norme du vecteur $\overrightarrow{OM}$
* $\theta$ est l'angle orienté $\theta = (\overrightarrow{e_x}; \overrightarrow{OM})$ (avec $\theta \in \left [0; 2\pi \right [$)

```{figure} ./images/mathematiques_coord_polaire.jpg
:name: fig_338
:align: center
```

__Base polaire__  
Soit un point M de coordonnées polaires $(r,\theta)$ dans un système de coordonnées polaires de centre O et d'axe $\overrightarrow{e_x}$, on lui associe une base locale orthonormée $(\overrightarrow{e_r}, \overrightarrow{e_{\theta}})$ telle que:

* $\overrightarrow{e_r}$ est le vecteur unitaire suivant $\overrightarrow{OM}$: $\overrightarrow{e_r} = \frac{\overrightarrow{OM}}{\left \| \overrightarrow{OM} \right \|}$
* $\overrightarrow{e_{\theta}}$ est le vecteur tel que $(\overrightarrow{e_r}, \overrightarrow{e_{\theta}})$ soit orthonormée et $(\overrightarrow{e_{r}};\overrightarrow{e_{\theta}}) = + \pi /2$. Le vecteur $\overrightarrow{e_{\theta}}$ est alors tangent au cercle de centre O et de rayon $r$ dans le sens des $\theta$ croissants.

On parle de base __locale__ car les vecteurs de la base dépendent du point M.

```{figure} ./images/mathematiques_base_polaire.jpg
:name: fig_339
:align: center
```

### Correspondance cartésien polaire
Les expressions que nous allons prouver sont __fondamentales__. Il faut autant les connaître par coeur que savoir les reprouver.

````{admonition} Exercice 
:class: attention
Exprimer la coordonnées r en fonction de x et y les coordonnées du même point M dans un repère cartésien puis exprimer x et y en fonction de r et $\theta$.

Exprimer ensuite les vecteurs de la base polaire dans la base cartésienne en fonction de $\theta$.
````

````{dropdown} Correction
Il vient directement:

\begin{align*}
	r = \sqrt{x^2 + y^2}\\
	x = r \cos \theta \\
	y = r \sin \theta
\end{align*}

Par projection, il vient:

\begin{align*}
	\overrightarrow{e_r} = \cos \theta \overrightarrow{e_x} + \sin \theta \overrightarrow{e_y}\\
	\overrightarrow{e_{\theta}} = \sin \theta \overrightarrow{e_x} - \cos \theta \overrightarrow{e_y}
\end{align*}
````

### Produit scalaire
Nous allons voir ici comment calculer un produit scalaire quand les deux vecteurs ne sont pas exprimer dans la même base (par exemple ici une base cartésienne et une base polaire mais ce principe peut se généraliser). On va à nouveau utiliser la bilinéarité et le caractère orthonormé des bases mais on va ajouter le calcul du produit scalaire faisant intervenir l"angle entre les vecteurs.


````{admonition} Exercice 
:class: attention
Calculer le produit scalaire des vecteurs $\overrightarrow{u} = u_x \overrightarrow{e_x} + u_y \overrightarrow{e_y}$ et du vecteur $\overrightarrow{v} = v_r \overrightarrow{e_r}$.
````

````{dropdown} Correction
On va à nouveau utiliser la bilinéarité et le caractère orthonormé des bases mais on va ajouter le calcul du produit scalaire faisant intervenir l'angle entre les vecteurs (qui sont de norme 1).

\begin{align*}
	\overrightarrow{u} \cdot \overrightarrow{v} =& \left(u_x \overrightarrow{e_x} + u_y \overrightarrow{e_y}\right) \cdot \left(v_r \overrightarrow{e_r}\right)\\
	&= u_x v_r \underbrace{\overrightarrow{e_x} \cdot \overrightarrow{e_r}}_{=\cos\theta} + u_y v_r \underbrace{\overrightarrow{e_y} \cdot \overrightarrow{e_r}}_{=\sin\theta}\\
	&= u_x v_r \cos\theta + u_y v_r \sin \theta
\end{align*}
````
