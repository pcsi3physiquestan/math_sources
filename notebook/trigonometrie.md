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

# Géométrie et trigonométrie

## Généralités
On rappelle ici le nom des théorèmes utiles:
* le théorème de Pythagore
* le théorème de Thales: on peut aussi le voir comme un rapport de grandeur lors d'une homothétie. Cette vision, développée en optique sera alors très utile.
* le théorème d'Al-Kashi: en réalité, ce théorème n'est pas utile à connaître. Il peut servir tant qu'on utilise pas de géométrie vectorielle mais il est préférable de calculer la norme d'une somme de vecteur pour aboutir à une telle formule.

````{admonition} Définition : Fonctions trigonométriques et triangle rectangle
:class: tip
On rappelle que dans un triangle __rectangle__:

\begin{align}
    \cos \alpha &= \frac{\textrm{Côté adjacent}}{\textrm{Hypothénuse}} &=& \frac{BA}{AC}& &\\
    \sin \alpha &= \frac{\textrm{Côté opposé}}{\textrm{Hypothénuse}} &=& \frac{BC}{AC}& &\\
    \tan \alpha &= \frac{\textrm{Côté opposé}}{\textrm{Côté adjacent}} &=& \frac{BC}{BA}& &
\end{align}

```{figure} ./images/mathematique_triangle_rectangle.jpg
:name: tr_rect
:align: center
```
````

## Cercle trigonométrique

### Cercle trigonométrique: Définition

````{admonition} Définition : Cercle trigonométrique
:class: tip
Le cercle trigonométrique est un cercle de rayon 1. L'axe Ox représente l'origine des angles parcourus sur le cercle. Ce cercle est orienté, c'est-à-dire que les angles orientés dans le sens dit trigonométrique (sens inverse du sens horaire) sont comptés positifs.

Soit un angle $\alpha$ orienté, la longueur de l'arc associé à l'angle $\alpha$ (arc AM) sur le cercle trigonométrique est égale à l'angle $\alpha$ multiplié par la longueur unité. Sur un cercle de rayon R, la longueur de l'arc associé à $\alpha$ est égale à $R \alpha$.

```{figure} ./images/mathematique_cercle_trigo.jpg
:name: cercle_trigo
:align: center
```
````

````{admonition} Fondamental : Fonctions trigonométriques et cercle
:class: important
Soit M un point du cercle trigonométrique et $\alpha$ l'angle orienté entre OM et l'axe Ox. On note N le projeté de M sur l'axe Ox et P le projeté de M sur l'axe Oy. Les distances __algébriques__ $\overline{ON}$ et $\overline{OP}$ sont respectivement égales à $\cos(\alpha)$ et $\sin(\alpha)$.

On peut tracer les deux tangentes au cercle perpendiculaires à l'axe Ox orienté (vers le haut du côté des x positifs et vers le bas du côté des x négatifs). Soit T l'intersection de OM et de la tangente la plus proche. La distance de T à l'axe Ox est égale à$ \tan(\alpha)$ (distance __algébrique__ AT).

```{figure} ./images/mathematique_cercle_trigo_sincos.jpg
:name: fig_330
:align: center
```
````

### Méthode: Résoudre une équation trigonométrique
Une équation du type $\sin(x) = k$ possède soit 0 solution (si k est plus grand que 1 en valeur absolue) soit une infinité de solution sur l'ensemble des réels. Néanmoins, on est souvent amené à chercher les solutions dans l'intervalle $]-\pi;\pi]$ (ou $[0;2\pi[$). Il y a alors 2 solutions.

Il arrive aussi qu'on soit amené à chercher un angle unique dans cet intervalle donné par deux équations au lieu d'une. On se propose d'étudier ici quelques exemples.

On rappelle que la fonction arccos est à valeur dans $[0;\pi]$, les fonctions arcsin et arctan sont à valeur dans $[-\pi/2;\pi/2]$. Mais il existe en général une deuxième solution dans le reste de l'intervalle et c'est elle qu'il faut savoir déterminer en plus.

Essayer de trouver la solution a ces équations avant de trouver la réponse.


````{admonition} Exercice 
:class: attention
Déterminer dans l'intervalle $]-\pi;\pi]$ les solutions des équations suivantes:

1. sin(x) = k
2. cos(x) = k
3. tan(x) = k
````

````{dropdown} Correction
>1. Soit une équation en du type $\sin(x) = k$ avec $x \in [-\pi; +\pi ]$. Elle possède des solutions uniquement si $-1 \leq k \leq 1$. Les solutions sont alors $x = \theta_1 = \arcsin(k)$ et $x = \theta_2 = \pi - \arcsin(k)$.
>2. Soit une équation en du type $\cos(x) = k$ avec $x \in [-\pi; +\pi ]$. Elle possède des solutions uniquement si $-1 \leq k \leq 1$. Les solutions sont alors $x = \theta_1 = \arccos(k)$ et $x = \theta_2 = - \arccos(k)$.
>3. Soit une équation en du type $\tan(x) = k$ avec $x \in [0; 2\pi ]$. Les solutions sont alors $x = \theta_1 = \arctan(k)$ et $x = \theta_2 = \pi + \arctan(k)$.
```{figure} ./images/mathematiques_eqn_trigo.jpg
:name: fig_331
:align: center
```
````

````{admonition} Exercice 
:class: attention
On considère un angle $\theta$ qui vérifie les équations suivantes: $\cos \theta < 0$ et $\tan \theta = k$ avec k > 0.

1. Déterminer le quadran dans lequel se trouve l'angle $\theta$
2. Déterminer une expression de l'angle $\theta$
````

````{dropdown} Correction
1. Les signes des fonctions trigonométriques permettent de déterminer le quadran dans lequel se trouve l'angle. Ici le cosinus et négatif donc $\theta \in ]-\pi;\pi/2[ \cup ]\pi/2;\pi[$. La tangente est négative donc $\theta \in ]-\pi/2;0[ \cup ]\pi/2;\pi[$. La conjonction des deux équations donne $]\pi/2;\pi[$.
2. Nous sommes dans une zone hors de l'intervalle image de arctan. La solution n'est donc pas arctan k mais $\boxed{\pi - \arctan k}$
````

