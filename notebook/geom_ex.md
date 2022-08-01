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
# Applcations : Géométrie vectorielle

## Théorème d'Al Kashi

````{admonition} Exercice 
:class: attention
Démontrer le théorème d'Al Kashi à l'aide de la géométrie vectorielle.
````

## Géométrie vectorielle

````{admonition} Exercice 
:class: attention
On considère la figure suivante. On note $\overrightarrow{\Omega} = \Omega \overrightarrow{z}$ et $\alpha$ est un angle fixe.

```{figure} ./images/mathematiques_td_pates.jpg
:name: fig_355
:align: center
```

1. Déterminer les expressions des vecteurs $\overrightarrow{G_1 A}$ et $\overrightarrow{G_2 A}$
2. Déterminer les expressions des vecteurs $\overrightarrow{v_A} = \overrightarrow{\Omega} \wedge \overrightarrow{G_1 A}$ et $\overrightarrow{v_2} = \overrightarrow{\Omega} \wedge \overrightarrow{G_1 G_2}$.
3. Représenter graphiquement $\overrightarrow{v_1}$ et $\overrightarrow{v_2}$ (on fera surtout attention à la direction et au sens du vecteur).
````

## Angles d'Euler

````{admonition} Exercice 
:class: attention
On considère un repère cartésien $\mathfrak{R_1}$ $(O, \overrightarrow{e_{x1}}, \overrightarrow{e_{y_1}}, \overrightarrow{e_{z_1}})$. On définit trois autres repères cartésiens:

* le repère $\mathfrak{R_2}$ $(O, \overrightarrow{e_{x2}}, \overrightarrow{e_{y_2}}, \overrightarrow{e_{z_1}})$ obtenu par rotation de $\mathfrak{R_1}$ d'un angle $\theta$ autour de $\overrightarrow{z_1}$
* le repère $\mathfrak{R_3}$ $(O, \overrightarrow{e_{x3}}, \overrightarrow{e_{y_2}}, \overrightarrow{e_{z_3}})$ obtenu par rotation de $\mathfrak{R_2}$ d'un angle $\phi$ autour de $\overrightarrow{y_2}$
* le repère $\mathfrak{R_4}$ $(O, \overrightarrow{e_{x3}}, \overrightarrow{e_{y_4}}, \overrightarrow{e_{z_4}})$ obtenu par rotation de $\mathfrak{R_3}$ d'un angle $\psi$ autour de $\overrightarrow{x_3}$

1. Représenter sur un schéma les quatres repères. Commenter la difficulté de raisonner sur un tel schéma.
2. Représenter des plans de coupe d'axe perpendiculaire $\overrightarrow{z_1}$, puis $\overrightarrow{y_2}$ puis $\overrightarrow{x_3}$. Représenter pour chaque coupe les vecteurs des repères contenus dans ces plans et les angles $\phi, \theta, \psi$ lorsqu'ils apparaissent.
3. Soit un point A de coordonnées $(x_4,y_4,z_4)$ dans $\mathfrak{R_4}$, exprimer le vecteur $\overrightarrow{OA}$ dans le repère $\mathfrak{R_1}$ en fonction de $x_4,y_4,z_4,\phi,\theta$ et $\psi$.
````
