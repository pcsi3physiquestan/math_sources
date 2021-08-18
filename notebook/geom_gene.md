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

# Géométrie vectorielle: Généralités
Les définitions données ici ne sont pas à apprendre pour la physique. Elles sont là pour cadrer correctement le cours de physique. On utilisera leur version "opératoire" basée sur la vision des vecteurs introduits au lycée.

## Espace vectoriel: Définition


````{dropdown} Définition: Espace vetoriel (pas à apprendre)
Soit un corps K commutatif. Un K-espace vectoriel est un ensemble E muni d'une loi interne (+, on l'appellera somme vectorielle) et d'une loi externe (*, on l'appellera multiplication par un scalaire) tel que:
* la somme vectorielle est commutative, associative, possède un élément neutre (vecteur nul) et tel que tout élément v possède un "opposé" (noté -v) tel que $\overrightarrow{v} + \overrightarrow{-v} = \overrightarrow{0}$.
* la loi externe est distributive sur la somme vectorielle (c'est-à-dire quie $(\lambda + \mu)*(\overrightarrow{v} + \overrightarrow{u}) = \lambda \overrightarrow{v} + \mu \overrightarrow{v} + \lambda \overrightarrow{u} + \mu\overrightarrow{u}$), associative mixte (c'est-à-dire $(\lambda \times \mu) * \overrightarrow{u} = \lambda * (\mu * \overrightarrow{u})$ et possède un élément neutre noté 1 (c'est-à-dire que $1 * \overrightarrow{u} = \overrightarrow{u}$).
````


````{dropdown} Cas utilisé en physique
Cette définition très générale peut s'appliquer à de nombreux cas (comme des ensembles de fonctions) avec des conséquences très intéressantes. Dans le cadre du programme en physique, on considèrera des R-espaces vectoriels, c'est-à-dire que le corps de "scalaires" sur lequel s'appuie sera le corps des réels.

Les espaces vectoriels que nous utiliserons principalement sont les ensembles $\mathbb{R}^2$ et $\mathbb{R}^3$. La somme vectorielle représente la somme vectorielle usuelle (qu'on peut associer à la somme graphique de deux vecteurs) et la multiplication par un scalaire aussi. A noter que cette dernière est en général notée de manière implicite.

On peut associer aux vecteurs des espaces nommés précédemment une direction, un sens et une longueur (cf.suite). Ces caractéristiques, utiles pour visualiser les problèmes physiques ont leur limite lorsqu'on manipule les grandeurs vectorielles (notamment les sommes). C'est pourquoi, nous allons introduire des caractéristiques générales des espaces vectoriels pour préparer à la manipulation mathématiques des objets comme les forces, vecteur vitesse, vecteur position... )

Au contraire des mathématiques, __on conservera la notation fléchée__ pour désigner les vecteurs (élément de l'espace vectoriel) de manière à bien les différencier des grandeurs scalaires (réels).
````


````{admonition} Combinaison linéaire
:class: important
Une combinaison linéaire est une somme vectorielle qui peut s'écrire $\overrightarrow{v} = \sum\limits_{i} \lambda_i \overrightarrow{u_i}$.
````

## Famille et base
````{dropdown} Famille libre
Une famille libre (ou linéairement indépendants) de vecteurs est une ensemble de vecteurs dont aucun ne peut être écrit comme une combinaison linéaire des autres. Cela revient à imposé la condition:

\begin{equation}
 \forall (a_1, a_2, ..., a_n) \in \mathbb{R}^n \left(\sum\limits_{k = 1}^{n} a_k \overrightarrow{v_k} = 0 \Longrightarrow \left(\forall k \in [\![1;n]\!] a_k = 0\right)\right)
\end{equation}

c'est-à-dire que toute combinaison linéaire nulle des vecteurs d'une famille libre implique que tous les coefficients sont nuls.
````

````{dropdown} Famille génératrice
Une famille génératrice est une famille de vecteurs tels que tout vecteur de l'espace vectoriel E peut s'écrire comme une combinaison linéaire des vecteurs de la famille.
````

````{dropdown} Base
Une famille de vecteur est une base s'il s'agit d'une famille linéairement indépendante et génératrice.

Tous les vecteurs d'une base sont donc indépendants et tout vecteur de E peuvent s'écrire comme une combinaison linéaire des vecteurs d'une base.
````

````{dropdown} Dimension d'un espace vectoriel (Admis)
Toutes les bases d'un même espaces vectoriel ont la même cardinalité (le même nombre d'élements). Ce cardinal définit la dimension de l'espace vectoriel.

Ainsi $\mathbb{R}^2$ est de dimension 2 et $\mathbb{R}^3$ est de dimension 3. Remarque: il peut exister des espaces vectoriels de dimension infinie mais nous n'en rencontrerons pas en physique.
````


````{dropdown} Nombre de base
Si la dimension d'un espace vectoriel sera en général fini en physique, le nombre de base possibles est infini.
````

## Produit scalaire
Un produit scalaire (noté $\cdot$) de E est une forme bilinéaire définie positive symétrique. C'est-à-dire:

* Un forme bilinéaire est une application de $E^2$ dans $\mathbb{R}$ (En toute rigueur, elle a ses images dans le corps $\mathbb{K}$ associé à l'espace vectoriel. Pour nous, c'est toujours $\mathbb{R}$.) linéaire à gauche est à droite:
    * linéaire à gauche: $(\lambda \overrightarrow{u_1} + \overrightarrow{u_2}) \cdot \overrightarrow{v} = \lambda (\overrightarrow{u_1} \cdot \overrightarrow{v})+ \overrightarrow{u_2} \cdot \overrightarrow{v}$
    * linéaire à droit: $\overrightarrow{u} \cdot (\lambda \overrightarrow{v_1} + \overrightarrow{v_2}) = \lambda (\overrightarrow{u} \cdot \overrightarrow{v_1})+ \overrightarrow{u} \cdot \overrightarrow{v_2}$
* Elle est symétrique si $\overrightarrow{u}\cdot \overrightarrow{v} = \overrightarrow{v} \cdot \overrightarrow{u}$
* Elle est positive si $\overrightarrow{u} \cdot \overrightarrow{u} > 0$ quelque soit $\overrightarrow{u}$
* Elle est définie si (Si $\overrightarrow{u} \cdot \overrightarrow{u} = 0$ alors $\overrightarrow{u} = \overrightarrow{0}$)


````{admonition} Attention : 
:class: note
Le produit scalaire est à valeur dans K (pour nous dans $\mathbb{R}$), c'est-à-dire qu'__il renvoie un scalaire et non un vecteur__.
````

````{dropdown} Remarque
Plus qu'une définition, il s'agit en physique de propriétés opératoires pour manipuler et calculer les produits scalaires (cf. exemple ci-après).
````


````{dropdown} Vecteurs orthogonaux
Deux vecteurs sont sont dits orthogonaux si et seulement si leur produit scalaire est nul.

Dans le cas plan ou de l'espace en physique, celà correspond à la notion d'angle droit usuel.
````

## Norme euclidienne
````{dropdown} Norme euclidienne
Soit un vecteur $\overrightarrow{u}$, on définit la norme euclidienne de $\overrightarrow{u}$ par:

\begin{equation}
\left \| \overrightarrow{u}	\right \| = \sqrt{\overrightarrow{u} \cdot \overrightarrow{u}}
\end{equation}
````


````{dropdown} Notation
En physique, on notera souvent $u$ la norme du vecteur $\overrightarrow{u}$. C'est possible en physique car on rappelle que tous les vecteurs doivent être notés avec des flèches.
````

````{dropdown} Vecteur normé
Un vecteur de norme 1 est appelé vecteur normé ou vecteur unitaire.
````

## Base orthonormée
````{dropdown} Base orthonormée
Une base orthonormée est une base dont tous les vecteurs sont normés et orthogonaux deux à deux.

En physique, on travaillera __toujours__ avec des base orthonormées.
````


## Projection orthogonale
````{dropdown} Projection orthogonale sur une droite vectorielle
Soit un vecteur non nul $\overrightarrow{v}$. Le projeté orthogonal (en physique) d'un vecteur $\overrightarrow{u}$ sur la droite vectorielle portée par $\overrightarrow{v}$ est le vecteur $\frac{\overrightarrow{u} \cdot \overrightarrow{v}}{\left \| v\right \|} \overrightarrow{v}$.

Si $\overrightarrow{v}$ est un vecteur unitaire (noté $\overrightarrow{e_m}$, alors le projecté orthogonal de $\overrightarrow{u}$ se réécrit: $(\overrightarrow{u} \cdot \overrightarrow{e_m}) \overrightarrow{e_m}$

Cette écriture du projeté orthogonal sur un vecteur normé est très utile en physique pour donner un sens à une composante d'un vecteur.
````

````{dropdown} Remarque
En mathématiques, la projection est un scalaire mais pour des raisons pratiques, on considérera en physique qu'il s'agit du vecteur associé et on parlera de composante (cf. suite)
````

````{dropdown} Projection dans une base orthonormée
Soit une base orthonormée $(\overrightarrow{e_k})\ k\in [\![1;n]\!]$ et un vecteur $\overrightarrow{u}$ dont la décomposition dans la base est $\overrightarrow{u} = \sum\limits_{k=1}^{n} u_k \overrightarrow{e_k}$. On appelle cette décomposition la projection de $\overrightarrow{u}$ dans la base et chaque __composante __ $u_k \overrightarrow{e_k}$ correspond à la projection du vecteur $\overrightarrow{u}$ sur la droite vectorielle portée par $\overrightarrow{u_k}$.
````

## Méthode: Calcul d'un produit scalaire
Comme nous allons le voir à travers un exemple, on utilise rarement les angles pour calculer les produits scalaires mais plutôt la décomposition des vecteurs dans une base orthonormée.


````{admonition} Exercice 
:class: attention
Soit E un R-espace vectoriel muni du produit scalaire $\cdot$ et une base base orthonormée de E $(\overrightarrow{e_1}, \overrightarrow{e_2}, \overrightarrow{e_3})$. On considère deux vecteurs dont les décompositions dont la base orthonormée sont:

\begin{align*}
	\overrightarrow{v} = v_1 \overrightarrow{e_1} + v_2 \overrightarrow{e_2}\\
	\overrightarrow{u} = u_1 \overrightarrow{e_1} + u_2 \overrightarrow{e_2} + u_3 \overrightarrow{e_3}
\end{align*}

Déterminer le produit scalaire $\overrightarrow{u} \cdot \overrightarrow{v}$.
````

````{dropdown} Correction
On va utiliser successivement la bilinéarité du produit scalaire et le caratère orthonormé de la base

\begin{align*}
	\overrightarrow{u} \cdot \overrightarrow{v} =& \left(v_1 \overrightarrow{e_1} + v_2 \overrightarrow{e_2}\right) \\
	&\cdot \left(u_1 \overrightarrow{e_1} + u_2 \overrightarrow{e_2} + u_3 \overrightarrow{e_3}\right)\\
	=& v_1 u_1 \underbrace{\overrightarrow{e_1} \cdot \overrightarrow{e_1}}_{=1} + v_1 u_2 \underbrace{\overrightarrow{e_1} \cdot \overrightarrow{e_2}}_{=0} \\
	&+ v_1 u_3 \underbrace{\overrightarrow{e_1} \cdot \overrightarrow{e_3}}_{=0} + v_2 u_1 \underbrace{\overrightarrow{e_1} \cdot \overrightarrow{e_2}}_{=0} \\
	&+ v_2 u_2 \underbrace{\overrightarrow{e_2} \cdot \overrightarrow{e_2}}_{=1} + v_2 u_3 \underbrace{\overrightarrow{e_2} \cdot \overrightarrow{e_3}}_{=0}\\
	=& v_1 u_1 + v_2 u_2
\end{align*}
````

