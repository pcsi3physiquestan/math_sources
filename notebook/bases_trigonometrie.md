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
````{topic} Théorèmes utiles
On rappelle ici le nom des théorèmes utiles:
* le théorème de Pythagore
* le théorème de Thales: on peut aussi le voir comme un rapport de grandeur lors d'une homothétie. Cette vision, développée en optique sera alors très utile.
* le théorème d'Al-Kashi: en fait non, il est préférable de calculer la norme d'une somme de vecteur pour aboutir à une telle formule.
````

````{important} __Fonctions trigonométriques et triangle rectangle__
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

````{important} __Cercle trigonométrique__
Le cercle trigonométrique est un cercle de rayon 1. L'axe Ox représente l'origine des angles parcourus sur le cercle. Ce cercle est orienté, c'est-à-dire que les angles orientés dans le sens dit trigonométrique (sens inverse du sens horaire) sont comptés positifs.

Soit un angle $\alpha$ orienté, la longueur de l'arc associé à l'angle $\alpha$ (arc AM) sur le cercle trigonométrique est égale à l'angle $\alpha$ multiplié par la longueur unité. Sur un cercle de rayon R, la longueur de l'arc associé à $\alpha$ est égale à $R \alpha$.

```{figure} ./images/mathematique_cercle_trigo.jpg
:name: cercle_trigo
:align: center
```

Soit M un point du cercle trigonométrique et $\alpha$ l'angle orienté entre OM et l'axe Ox. On note N le projeté de M sur l'axe Ox et P le projeté de M sur l'axe Oy. Les distances __algébriques__ $\overline{ON}$ et $\overline{OP}$ sont respectivement égales à $\cos(\alpha)$ et $\sin(\alpha)$.

On peut tracer les deux tangentes au cercle perpendiculaires à l'axe Ox orienté (vers le haut du côté des x positifs et vers le bas du côté des x négatifs). Soit T l'intersection de OM et de la tangente la plus proche. La distance de T à l'axe Ox est égale à$ \tan(\alpha)$ (distance __algébrique__ AT).

```{figure} ./images/mathematique_cercle_trigo_sincos.jpg
:name: fig_330
:align: center
```
````
