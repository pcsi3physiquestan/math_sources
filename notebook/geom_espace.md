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

# Géométrie dans l'espace
_Tout ce qui a été dit en introduction reste vrai et nous allons voir que de nombreuses propriétés du plan restent vraies. On pourra ainsi redéfinir les coordonnées cartésiennes en rajoutant simplement la troisième coordonnée (z suivant un vecteur $\overrightarrow{e_z}$)._

## Angle orienté
_Lorsqu'on s'intéresse à l'orientation des angles, on ne peut plus définir de "sens trigonométrique" (tout dépend de quel coté on regarde le plan!)._

````{important} __Orientation d'un plan__  
Soit un plan $(\Pi)$ de l'espace, on oriente le plan par un vecteur normal au plan $\overrightarrow{n}$. Les angles sont alors orientés en cohérence avec le vecteur normal $\overrightarrow{n}$, c'est-à-dire:

* Règle du tire-bouchon: Un tire-bouchon se vissant dans le sens de $\overrightarrow{n}$ tourne dans le sens des angles de $(\Pi)$ comptés positivement.
* Règle de la main droite: Si l'on place le majeur __de la main droite__ dans le sens de $\overrightarrow{n}$, les angles allant du pouce vers l'index sont comptés positivement.

```{figure} ./images/mathematiques_orientation_angle.jpg
:name: fig_340
:align: center
```
````

## Base directe et produit vectoriel
### Base directe

````{margin} Permutation des vecteurs
Si l'on permute deux vecteurs d'une base directe, elle devient indirecte (c'est-à-dire non directe).

De la même manière, le symétrique d'une base directe par rapport à un plan est une base indirecte. On pourra faire le lien avec la notion de chiralité en chimie.
````
````{important} __Trièdre directe__  
Soit trois vecteurs de l'espace $(\overrightarrow{i}, \overrightarrow{j}, \overrightarrow{k})$ de sorte qu'aucun ne soit colinéaire à un autre vecteur du triplet, on dit qu'ils forme un trièdre directe si:

* règle de la main droite: l'on peut superposer simultanément $\overrightarrow{i}$ au pouce de la main droite, $\overrightarrow{j}$ à l'index de la main droite et $\overrightarrow{k}$ au majeur de la main droite.
* règle du tire-bouchon: un tire-bouchon vissant dans le sens de $\overrightarrow{i}$ amène $\overrightarrow{j}$ sur $\overrightarrow{k}$ en un quart de tour (et pas trois quart de tour)

```{figure} ./images/mathematiques_trois_doigts_triedre.jpg
:name: fig_341
:align: center
```

```{figure} ./images/mathematiques_tire_bouchon_triedre.jpg
:name: fig_342
:align: center
```
En physique, on travaillera toujours avec des __bases orthonormées directes.__
````

### Produit vectoriel
__Produit vectoriel__  
Soit deux vecteurs $\overrightarrow{u_1}$ et $\overrightarrow{u_2}$, on définit le produit vectoriel $\overrightarrow{u_1} \wedge \overrightarrow{u_2}$ comme le vecteur $\overrightarrow{w}$ tel que:
* $\left \| \overrightarrow{w} \right \|= \left \| u_1 \right \| \left \| u_2 \right \| \vert \sin (\overrightarrow{u_1} ; \overrightarrow{u_2}) \vert$
* Le vecteur $\overrightarrow{w}$ est perpendiculaire au plan $(\Pi)$ formé par les vecteurs $\overrightarrow{u_1}$ et $\overrightarrow{u_2}$.
* Le sens de $\overrightarrow{w}$ est tel que le trièdre $(\overrightarrow{u_1}; \overrightarrow{u_2}; \overrightarrow{w})$ est direct.

````{important} 
__Propriété d'un produit vectoriel__  
* Bilinéarité du produit vectoriel
* Antisymétrie: $\overrightarrow{u} \wedge \overrightarrow{v} = - \overrightarrow{v} \wedge \overrightarrow{u}$
* Si $\overrightarrow{u}$ et $\overrightarrow{v}$ sont deux vecteurs colinéaires, leur produit vectoriel est nul. En particulier, le produit vectoriel d'un vecteur par lui-même est nul.

Ces propriétés sont fondamentales pour le calcul d'un produit vectoriel.
````

````{important} Vecteur d'une base orthonormée direct
Considérons $(\overrightarrow{e_x}, \overrightarrow{e_y}, \overrightarrow{e_z})$ une base orthonormée directe. On a:

\begin{align}
    \overrightarrow{e_x} \wedge \overrightarrow{e_y} &= \overrightarrow{e_z}\\
    \overrightarrow{e_z} \wedge \overrightarrow{e_x} &= \overrightarrow{e_y}\\
    \overrightarrow{e_y} \wedge \overrightarrow{e_z} &= \overrightarrow{e_x}\\
    \overrightarrow{e_y} \wedge \overrightarrow{e_x} &= -\overrightarrow{e_z}\\
    \overrightarrow{e_x} \wedge \overrightarrow{e_z} &= -\overrightarrow{e_y}\\
    \overrightarrow{e_z} \wedge \overrightarrow{e_y} &= -\overrightarrow{e_x}
\end{align}
````

### Méthode: Calculer un produit vectoriel
Nous allons voir ici comment calculer un produit vectoriel.


````{admonition} Exercice 
:class: attention
Soit une base orthonormée direct $(O, \overrightarrow{e_x}, \overrightarrow{e_y}, \overrightarrow{e_z})$. On considère deux vecteurs $\overrightarrow{u} = u_x \overrightarrow{e_x} + u_y \overrightarrow{e_y}$ et $\overrightarrow{v} = v_x \overrightarrow{e_x} + v_z \overrightarrow{e_z}$. Calculer le produit vectoriel $\overrightarrow{u} \wedge \overrightarrow{v}$.
````

````{topic} Calcul
On va utiliser succissement la bilinéarité puis les expressions des produits vectoriels des vecteurs de la base.

\begin{align*}
	\overrightarrow{u} \wedge \underline{v} &= \left(u_x \overrightarrow{e_x} + u_y \overrightarrow{e_y}\right) \wedge \left(v_x \overrightarrow{e_x} + v_z \overrightarrow{e_z}\right)\\
	&= u_x v_x \underbrace{\overrightarrow{e_x} \wedge \overrightarrow{e_x}}_{= 0 \textrm{(colinéaires)}} + u_x v_z \underbrace{\overrightarrow{e_x} \wedge \overrightarrow{e_z}}_{= -1} \\
	+& u_y v_x \underbrace{\overrightarrow{e_y} \wedge \overrightarrow{e_x}}_{= -1} + u_y v_z \underbrace{\overrightarrow{e_y} \wedge \overrightarrow{e_z}}_{= 1}\\
	&= - u_x v_z - u_y v_x + u_y v_z
\end{align*}
````

## Coordonnées cartésiennes
On définit notament un repère cartésien comme un repère orthonormé direct: $(O, \overrightarrow{e_x}, \overrightarrow{e_y}, \overrightarrow{e_z})$ où $(\overrightarrow{e_x}, \overrightarrow{e_y}, \overrightarrow{e_z})$ forme un trièdre direct.

Il s'agit à nouveau d'un repère global.

```{figure} ./images/mathematiques_coord_cartesien.png
:name: fig_343
:align: center
```


## Coordonnées cylindriques
Le système de coordonnées cylindriques revient à repérer le point M sur les bords d'un cylindre. Il faut alors le rayon et la hauteur du cylindre et l'angle de rotation par rapport à une référence.

```{margin}
On remarquera que M est repéré sur un cylindre.
```
````{important} __Coordonnées cylindriques.__  
Soit un repère cartésien $(O, \overrightarrow{e_x}, \overrightarrow{e_y}, \overrightarrow{e_z})$, soit un point M quelconque de l'espace et H son projeté orthogonal dans le plan $(O , \overrightarrow{e_x} , \overrightarrow{e_y})$. On définit les coordonnées cylindriques (d'axe Oz) de M notées $(r , \theta, z)$ par:

* $r = OH$
* $\theta=(\overrightarrow{e_x} ,\overrightarrow{OH})$, le plan $(O, \overrightarrow{e_x}, \overrightarrow{e_z})$ étant orienté par $\overrightarrow{e_z}$
* $z$: coordonnées cartésiennes suivant$ \overrightarrow{e_z}$
\end{itemize}

```{figure} ./images/mathematiques_coord_cylindriques.png
:name: fig_344
:align: center
```
````

````{admonition} __Base cylindrique__  
On définit la base __locale__ cylindrique (cf. figure précédente) associée au point M par la famille $(\overrightarrow{e_r} ; \overrightarrow{e_{\theta}}, \overrightarrow{e_z})$ tel que:
* $\overrightarrow{e_z}$ est le vecteur de la base cartésienne.
* vecteur radiale: $\overrightarrow{e_r}$ est défini tel que $\overrightarrow{OH} = r \overrightarrow{e_r}$.
* vecteur orthoradiale: $\overrightarrow{e_{\theta}}$ tel que la base $( \overrightarrow{e_r}, \overrightarrow{e_{\theta}}, \overrightarrow{e_z})$ soit une base orthonormée directe soit: $\overrightarrow{e_{\theta}}= \overrightarrow{e_z} \wedge \overrightarrow{e_r}$
````

````{attention}
* $\overrightarrow{e_{\theta}}$ pointe toujours dans le sens des $\theta$ croissants.
* C'est une base locale, cela veut dire que les vecteurs dépendant du points M. Autrement dit, si l'on suit un point M mobile, les vecteurs de la base varieront au cours du temps.
````

````{topic} Rappel
Les relations entre $(r, \theta)$ et (x,y) ainsi qu'entre les vecteurs de la base cylindriques et les vecteurs de la base cartésiennes sont les mêmes que les relations entre la base polaire et la base cartésienne dans le plan. On pourra s'en convaincre avec la représentation du plan perpendiculaire à l'axe Oz et passant par le point M (attention, le centre du plan n'est pas nécessairement le point O):

```{figure} ./images/mathematiques_proj_cylindrique.png
:name: fig_345
:align: center
```
````

## Coordonnées sphériques
Les coordonnées sphériques reviennent à placer le point M sur une sphère et repérer ses coordonnées. Il faut ainsi le rayon de la sphère et deux coordonnées angulaires pour le placer sur la sphère. A l'image du repérage sur le globe terrestre, on utilisera un axe de référence (l'âxe des pôles) pour définir la __colatitude__ (on ne travaille pas avec la latitude pour des raisons mathématiques non développées ici) et un méridien de référence pour définir la longitude (ou azimuth).

### Définition
````{admonition} __Coordonnéees sphériques__  
Soit un repère cartésien $(O, \overrightarrow{e_x}, \overrightarrow{e_y}, \overrightarrow{e_z})$, soit un point M quelconque de l'espace et H son projeté orthogonal dans le plan $(O , \overrightarrow{e_x} , \overrightarrow{e_y})$. On définit les coordonnées sphériques (d'axe Oz) de M notées $(r , \theta, \phi)$ par:

* $r = OM$
* Colatitude: $\theta=(\overrightarrow{e_z} ,\overrightarrow{OM})$ avec $\theta \in [0; \pi]$
* Azimuth: $\phi = (\overrightarrow{e_x} ,\overrightarrow{OH})$ avec $\phi \in [0; 2 \pi]$. Le plan $(O, \overrightarrow{e_x}, \overrightarrow{e_z})$ étant orienté par $\overrightarrow{e_z}$

```{figure} ./images/mathematiques_coord_spheriques.png
:name: fig_346
:align: center
```
````

````{attention} __Définition des angles__
Il faut noter la différence de domaine de définition de $\theta$ et $\phi$. Elle est cruciale pour que chaque point possède un jeu de coordonnées uniques.
````

```{topic} __Parallèle et méridien__  
On définit le parallèle au point M comme le plan passant par M est parallèle au plan $(O , \overrightarrow{e_x} , \overrightarrow{e_y})$ (donc perpendiculaire à $Oz$).

On définit le méridien au point M comme le plan passant par M et contenant $Oz$. $\phi$ est l'angle entre le plan $xOz$ et le méridien.
```

````{margin}
C'est une base locale: les vecteurs dépendent donc du point M. Plus précisément, il dépendant des coordonnées angulaires.
````
````{important} __Base sphérique__  
On définit la base __locale__ sphérique (cf. figure précédente) associée au point M par la famille $(\overrightarrow{e_r} ; \overrightarrow{e_{\theta}}, \overrightarrow{e_{\phi}})$ tel que:

* vecteur radiale: $\overrightarrow{e_r}$ est défini tel que $\overrightarrow{OP} = r \overrightarrow{e_r}$.
* vecteur azimutal: $\overrightarrow{e_{\phi}} = \overrightarrow{e_z} \wedge \frac{\overrightarrow{OH}}{OH}$: il est dans le plan $(O , \overrightarrow{e_x} , \overrightarrow{e_y})$ perpendiculaire à (OH) dans le sens des $\phi$ croissants.
* $\overrightarrow{e_{\theta}} = \overrightarrow{e_{\phi}} \wedge \overrightarrow{e_r}$: il est dans le plan du méridien, orthogonal à $\overrightarrow{e_r}$ et dans le sens des $\theta$ croissants.
````


### Relation sphérique-cartésien
Il est extrêmement important de savoir passer des coordonnées sphériques aux coordonnées cartésiennes et réciproquement. 

````{admonition} Exercice 
:class: attention
Exprimer la coordonnées radiale r en fonction de x, y et z et les coordonées x,y et z en fonction des coordonnées sphériques.

Exprimer les vecteurs de la base sphérique dans la base cartésiennes en faisant intervenir les coordonnées angulaires du point M.
````

````{topic} Correction
La méthode la plus simple est de passer par le parallèle et le méridien pour réaliser les projections et les calculs trigonométriques. On utilise notamment le vecteur unitaire $\overrightarrow{u_{\Delta}}$  qui porte la droite PM (P est le centre du cercle parallèle) car il présente l'intérêt d'être présent dans les deux plans: celui du méridien (cf. schéma) et celui du parallèle.

__Coordonnées__  
Il vient (utiliser les schémas de coupe du parallèle et du méridien - __s'entraîner à le prouver__):

```{figure} ./images/mathematiques_parallele_spherique.jpg
:name: fig_347
:align: center
```

```{figure} ./images/mathematiques_meridien_spherique.jpg
:name: fig_348
:align: center
```

\begin{align*}
	r = \sqrt{x^2 + y^2 + z^2}\\
	x = r \sin \theta \cos \varphi \\
	y = r \sin \theta \sin \varphi \\
	z = r \cos \theta
\end{align*}
\begin{align*}
	\overrightarrow{e_r} = \sin \theta \cos \varphi \overrightarrow{e_x} + \sin \theta \sin \varphi \overrightarrow{e_y} + \cos\theta \overrightarrow{e_z}\\
	\overrightarrow{e_{\theta}} = \cos \theta \cos \varphi \overrightarrow{e_x} + \cos \theta \sin \varphi \overrightarrow{e_y} - \sin\theta \overrightarrow{e_z}\\
	\overrightarrow{e_{\varphi}} = - \sin \varphi \overrightarrow{e_x} + \cos \varphi \overrightarrow{e_y}
\end{align*}

````

