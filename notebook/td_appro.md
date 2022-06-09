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

# Entrainement : Nouveautés

## Equations

````{admonition} Résolution graphique 
:class: attention
1. Déterminer graphiquement les conditions sur $k$ pour qu'il existe une solution à l'équation $4x = k(e^x - 1)$ telle que $x>0$.
````

## Etude de fonctions


````{admonition} Fonctions hyperboliques
:class: attention
Les fonctions hyperboliques $\cosh ,\ \sinh,\ \tanh$ sont définies sur $\mathbb{R}$ par:

\begin{align*}
	\cosh (x) &= \frac{e^x + e^{-x}}{2}\\
	\sinh (x) &= \frac{e^x - e^{-x}}{2}\\
	\tanh (x) &= \frac{\sinh (x)}{\cosh (x)}
\end{align*}
1. Etudier chacune des trois fonctions (valeurs limites, monotonie... ) et en déduire le tracé des trois fonctions.
1. Montrer que $\cosh ^2 - \sinh ^2 = 1$.
1. Déterminer les domaines de définition des trois fonctions réciproques et l'allure graphique de leur tracé. On limitera les calculs pour cette questions.
1. Résoudre l'équation $\cosh (x) = 3$.
````

### Transformations graphiques
En partant du tracé (connus) des fonctions usuelles, déterminer le tracé le plus complet possibles des fonctions suivantes (points et caractéristiques importantes à faire apparaître sur le graphique). One ne fera AUCUNE étude de fonction, on utilisera uniquement les transformations usuelles des fonctions pour réaliser ces tracés. On pourra réaliser des tracés intermédiaires si nécessaires.


````{admonition} Exercice 
:class: attention
1. $f(x) = \ln(\frac{1}{x})$ sur $\mathbb{R}^{+*}$ connaissant le tracé de la fonction $\ln(x)$
1. $f(x) = 4\ln(1-x)$ sur $]-\infty;1[$ connaissant le tracé de la fonction $\ln(x)$
1. $f(x) = \sin(\frac{x}{2}-\frac{ \pi}{3})$ connaissant le tracé de la fonction $\sin(x)$ Préciser la période de la fonction et représenter un tracé graphique sur 3 périodes.
1. $f(x) = 4 \cos(\frac{x}{3}+\frac{ \pi}{6})$ connaissant le tracé de la fonction $\cos(x)$ Préciser la période de la fonction et représenter un tracé graphique sur 3 périodes.
1. $f(x) = \cos(x) + \sin(x)$ sur $[-\pi;\pi]$ (retrouver une expression similaire aux expressions précédentes).
1. $f(t) = 4 e^{-3t}$  sur $\mathbb{R}^{+}$ connaissant le tracé de la fonction $e^z$. On précisera bien la tangente en $t=0$ et l'intersection de celle-ci avec l'axe des abscisses.
1. $f(x) = 5 (1-e^{-x/3})$ sur $\mathbb{R}^{+}$ connaissant le tracé de la fonction $e^z$. On précisera bien la tangente en $t=0$ et l'intersection de celle-ci avec l'asymptote de la fonction en $+\infty$.
````

## Nombres complexes

````{admonition} Fractions de nombres complexes
:class: attention
Déterminer le module et l'argument des complexes suivant en fonction de x (réel strictement positif) et j le complexe dont le carré est égal à -1.
1. $z=\frac{1}{1+jx}$
1. $z=\frac{1}{1-x^2+3jx}$
1. $z=\frac{j x}{1-x^2+3jx}$
1. $z=\frac{-Kx^2}{1- LCx^2 + jRCx}$ avec $K,R,L,C$ positifs
````