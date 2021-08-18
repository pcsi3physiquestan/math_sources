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
# Calcul différentiel

````{admonition} Objectifs
:class: hint
* Interpréter l'intégrale comme une somme de contributions infinitésimales, en lien avec la méthode des rectangles en mathématiques.
* Interpréter graphiquement la notion de dérivée.
* Séparer les variables d’une équation du premier ordre à variables séparables.
````

## Notation différentielle
````{dropdown} Remarque
Les "définitions" données ici ne sont pas les définitions complètes mathématiques. Il s'agit d'une interprétation physique de ces grandeurs permettant de leur donner du sens et de les utiliser ne physique.
````


````{admonition} Différentielle
:class: dropdown, info
La grandeur dx est appelée différentielle de x et représente une variation infinitésimale de x. Il est sous entendu que cette variation se fait autour d'une valeur $x_0$ appartenant à un ensemble plus ou moins contraint suivant le système étudié.

D'un point de vue strict, on dit que __infinitésimale__ signifie "qui tend vers 0" à la différence de __fini__ qui signifie que la variation reste à une valeur non nulle.
````

````{admonition} Utilisation de la différentielle
:class: dropdown, info
Nous verrons des exemples en cours mais l'intérêt de la notation différentielle est de permettre de faire des raisonnements géométriques sur des grandeurs finies qu'on fera implicitement tendre vers 0 pour faire apparaître des dérivées ou des intégrales.
````

## Interprétation géométrique de la dérivée et de l'intégration

### Interprétation de la dérivée

````{admonition} Interprétation de la dérivée: tangente
:class: dropdown, info

Si y est une fonction de x, alors le rapport $\frac{\Delta y}{\Delta x}$ représente le taux de variation de la fonction y pour une variation de x égale à $\Delta x$ (autour d'un point $x_0$). En faisant tendre vers 0 cette variation, ce taux de variation tend vers la pente de la tangente de la fonction en $x_0$. La notation $dy/dx$ inclut déjà le fait qu'on prend la limite vers 0.

```{figure} ./images/mathematiques_derivee_tangente.jpg
:name: fig_336
:align: center
```
````

### Interprétation de l'intégrale
On rappelle que l'intégration de y(x) entre a et b peut être aussi vu comme une limite, celle d'une somme de Riemann. On somme une série de N "bâtons" de hauteur y(x) et de largeur $\frac{b-a}{N}$. On augmente alors le nombre d'intervalle dans la somme en augmentant le nombre N. La limite quand N tend vers l'infini est l'intégrale de y(x) entre a et b.

On peut aussi avoir une approche différentielle en considérant des bâtons de largeur dx. L'aire d'un bâton est alors f(x)dx. Il suffit de sommer chaque bâton pour obtenir l'aire sous la courbe (puisque la notation différentielle implique que l'on fait tendre leur largeur vers 0). Sauf que la notation $\sum$ n'est valable que pour une somme discrète. On la remplace donc par la notation $\int$.


````{dropdown} Généralisation
L'intérêt d'une telle vision est qu'elle peut se généraliser à des cas plus complexes où l'on ne somme pas des fonctions de x comme le cas de la transformée de Fourier (non présentée ici).

On peut aussi procéder par analogie comme nous le verrons en cours de mécanique entre une situation discrète et une situation continue.
````

## Séparation des variables

### Séparation des variables: Généralités
On suppose qu'on doit résoudre une équation du type: $\frac{\rm{d}y}{\rm{dx}} = f(x,y)$ où f est une fonction à variables séparables, c'est-à-dire qu'on peut la mettre sous la forme $f_1(x) \times f_2(x)$

\begin{equation}
\frac{\rm{d}y}{\rm{dx}} = f_1(x) \times f_2(y)
\end{equation}

En assimilant les différentielles à des variations infinitésimales, on peut réécrire l'équation précédente en séparation la partie en x de la partie en y puis intégrer l'ensemble.

\begin{equation}
\frac{\rm{d}y}{f_2(y)} = \rm{d}x f_1(x) \Longrightarrow \int_{y(x_1)}^{y(x_2)}\frac{\rm{d}y}{f_2(y)} = \int_{x_1}^{x_2} f_1(x) \rm{d}x
\end{equation}


### Méthode: Séparation des variables
Nous allons voir ici comment utiliser la séparation des variables pour résoudre une équation.

````{admonition} Exercice 
:class: attention
Résoudre l'équation $\frac{dy}{dx} = a y x^2$ avec $a \in \mathbb{R}^{+*}$ et $y(x=0) = y_0$.
````

````{dropdown} Correction
Séparons les variables en mettant toutes les fonction en x d'un côté et toutes les fonctions en y de l'autre:

\begin{equation}
\frac{dy}{y} = ax^2dx
\end{equation}

On intègre en faisant __attention à ce que les bornes des deux intégrales soient cohérentes__. Ici, on a choisit les bornes de l'intégrale en x (0 et $x_0$), les bornes de l'intégrale en y doivent correspondre ($y(x=0)$ et $y(x=x_0)$)

\begin{equation}
\int_{y(x=0)}^{y(x=x_0)} \frac{dy}{y} = \int_{x=0}^{x=x_0}ax^2dx \Longrightarrow \ln\left(\frac{y(x_0)}{y_0}\right) = \frac{a}{3}x_0^3
\end{equation}

Il reste à isoler y(x) (on a remplacé $x_0$ par x car l'expression est vraie pour tout $x_0$):

\begin{equation}
y(x) = y_0 \exp^{\frac{a}{3}x^3}
\end{equation}
````

````{dropdown} Remarque
On peut aussi procéder par changement de variables. On commence par isoler les fonctions de y avec la dérivée y'(x) puis on intègre (suivant x):

\begin{equation}
\frac{1}{y}\frac{\rm{d}y}{\rm{dx}} = ax^2 \Longrightarrow \int_{x=0}^{x=x_0}\frac{1}{y(x)}\frac{\rm{d}y}{\rm{dx}} dx = \int_{x=0}^{x_{0}} ax^2 dx
\end{equation}

On réalise alors un changement de variables x vers u = y(x) dans la première intégrale. Les bornes deviennent $y(x=0)$ et $y(x=x_0)$ et $du = y'(x)dx= \frac{\rm{d}y}{\rm{dx}} dx$. L'intégrale devient donc:

\begin{equation}
\int_{y(x=0)}^{y(x=x_0)}\frac{1}{u}du = \int_{x=0}^{x_{0}} ax^2 dx
\end{equation}

La suite du calcul est identique au cas précédent.
````