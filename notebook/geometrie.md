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
# Géométrie vectorielle

````{admonition} Objectifs
:class: hint
* Exprimer les coordonnées d'un vecteur dans une base orthonormée d'un espace de dimension inférieure ou égale à 3.
* Interpréter géométriquement le produit scalaire et connaître son expression en fonction des coordonnées dans une base orthonormée.
* Utiliser la bilinéarité et le caractère symétrique du produit scalaire.
* Interpréter géométriquement le produit vectoriel et connaître son expression en fonction des coordonnées dans une base orthonormée directe.
* Utiliser la bilinéarité et le caractère antisymétrique du produit vectoriel.
* Faire le lien avec l'orientation des trièdres.
* Définir une convention d'orientation des angles d'un plan (euclidien) et lire des angles orientés.
* Relier l'orientation d'un axe de rotation à l'orientation positive des angles d'un plan perpendiculaire à cet axe.
* Connaître le lien entre le gradient et la différentielle.
* Connaître l'expression du gradient en coordonnées cartésiennes; utiliser un formulaire fourni en coordonnées cylindriques ou sphériques.
* Utiliser le fait que le gradient d'une fonction f est perpendiculaire aux surfaces iso-f et orienté dans le sens des valeurs de f croissantes.
````

Le but de ce cours est avant tout d'avoir une maîtrise du calcul vectoriel et une comprehension physique de la géométrie dans l'espace.

Il ne s'agit pas ici de faire un cours d'algèbre linéaire générale. Nous allons ici étudier des notions relativement générales uniquement à travers l'exemple de la géométrie dans l'espace. Plusieurs définitions seront ainsi introduites "à la main" et certaines propriétés seront admises.

