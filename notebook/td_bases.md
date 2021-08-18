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

# TD Bases

## TD Equations

### Equation du second degré: Equations numériques

Résoudre les équations ou inéquations suivantes (l'inconnue est toujours $x$):

````{admonition} Exercice
:class: attention
1. $x^2+3x-1=0$
2. $(x-3)(x-4)=1$
3. $(x-3)(x-4)=0$
4. $x^2+x=-1$
5. $x^2+2x-3 < 0$
6. $(x-3)(x-4)>1$
````

### Equations diverses: Equations numériques

Résoudre les équations (ou systèmes d'équations suivants):

````{admonition} Exercice 
:class: attention
1. $e^{x^2}=k$ avec comme inconnue $x$
2. Chercher $a$ et $b$ tels que $ab = 3\textrm{~et~}a+b=5$
3. Déterminer $x$ tel que $\frac{x+3}{x-2}=x$
````

### Systèmes d'équations
Résoudre les systèmes d'équations suivants (les inconnues sont x,y,z):
````{admonition} Exercice 
:class: attention

\begin{align}
	&\begin{cases}
		3x - 2y + z &= 1\\
		2x - 3y + 5z &= 0\\
		6x - y - 4z &= 4
	\end{cases}\\
	&\begin{cases}
		x - 2y &= 3\\
		2x - y &= 0\\
	\end{cases}\\
	&\begin{cases}
		5x &= 3 - 4y\\
		3y &= 5x - 2\\
	\end{cases}\\
\end{align}
````

## TD Etude de fonctions

### Limites de fonctions
Déterminer, en le justifiant, les limites suivantes:

````{admonition} Exercice 
:class: attention
1. $\lim\limits_{x \to +\infty} -3x^3 + 4x^2 - 2$
2. $\lim\limits_{x \to 0} -3\frac{1}{x^3} + 4\frac{1}{x^2} - 2$
3. $\lim\limits_{x \to +\infty} \frac{-4x^2-2x-1}{-3x^3+2x^2-x-5}$
4. $\lim\limits_{x \to -\infty} \frac{-4x^3-2x-1}{-2x^2-x-5}$
5. $\lim\limits_{x \to +\infty} \frac{-4x^3-2x-1}{-2x^3-x-5}$
6. $\lim\limits_{x \to -\infty} \frac{-4x^2-2x-1}{-2x^2-x-5}$
7. $\lim\limits_{x \to 0} \frac{\sin(x)}{x}$
8. $\lim\limits_{x \to 0} x-\ln (x)$
9. $\lim\limits_{x \to +\infty} x^2-\ln (x)$
10. $\lim\limits_{x \to -\infty} x^2-e^{-x}$
11. $\lim\limits_{x \to +\infty} \frac{e^{x}}{x}$
12. $\lim\limits_{x \to -\infty} xe^{x}$
````

### Représentation graphique
Etudier complètement les fonctions suivantes puis réaliser un tracé graphique complet (points et caractéristiques importantes à faire apparaître sur le graphique).


````{admonition} Exercice 
:class: attention
1. $f(x) = x^2 - 3x + 1$ sur $\mathbb{R}$
2. $f(\zeta) = \zeta^3 - 2 \zeta^2 - \zeta + 2$ sur $\mathbb{R}$
3. $f(x) = \frac{x-1}{x-2}$ sur $\mathbb{R}/{2}$
4. $f(z) = \frac{x^2+2x-1}{x}$ sur $\mathbb{R}^{*}$
5. $f(x) = \frac{3x^2-2x-1}{x+1}$ sur $\mathbb{R}^{+}$
6. $f(\gamma) = \cos(\gamma)$ sur $[0;2\pi]$
7. $f(x) = x+2 - \frac{4e^2}{e^x+3}$ sur $\mathbb{R}$
8. $f(x) = e^2 - x + 1$ sur $\mathbb{R}^{+}$
9. $f(x) = x^2\ln(x)$ sur $\mathbb{R}^{+*}$. On montrera que la fonction peut être prolongée en $x=0$ et on déterminera la tangente en $x=0$.
10. $f(x) = \ln \frac{e^x-1}{e^{2x}+1}$. Déterminer le domaine de définition le plus large de la fonction puis l'étudier sur cet intervale.
11. $f(x) = \sqrt{x^2 - 4}$ Déterminer le domaine de définition le plus large de la fonction puis l'étudier sur cet intervale.
12. $f(x) = \ln(x) - x$  sur $\mathbb{R}^{+}$
````

## TD Nombres complexes
### Complexes: Représentation graphique
Représenter graphiquement les complexes suivant dans le plan complexe puis déterminer leur norme et leur argument.

````{admonition} Exercice 
:class: attention
1. $z = 3 + 4j$
1. $z = 4 - 5j$
1. Les conjugués des deux complexes précédents
1. Leur somme, leur différence puis leur produit
1. $z = 4 e^{j \frac{\pi}{6}}$
1. $z = 2 e^{j \frac{\pi}{3}}$
1. Les conjugués des deux complexes précédents
1. Leur somme, leur différence puis leur produit
````

