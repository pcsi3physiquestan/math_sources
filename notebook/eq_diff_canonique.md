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
# Equations différentielles: forme canonique et solution

## Equation d'ordre 1

````{important} __Forme canonique d'une équation d'ordre 1.__
Une équation d'ordre 1 peut se mettre sous la forme:

\begin{align}
	\frac{\rm{d}y}{\rm{dt}} + \frac{1}{\tau} y(t) &= f(t) \textrm{ équation avec second membre}\\
	\frac{\rm{d}y}{\rm{dt}} + \frac{1}{\tau} y(t) &= 0 \textrm{ équation sans second membre}
\end{align}
````

```{margin} __Traitement du second membre__
Attention, s'il y a un second membre il faut aussi le traiter. Nous verrons la méthode générale par la suite.
```
````{important} __Solution de l'équation sans second membre__
Toutes les solutions de l'équation __homogène__, c'est-à-dire sans second membre sont de la forme:

\begin{equation}
y(t) = A e^{-\frac{t}{\tau}}
\end{equation}
````


## Equation d'ordre 2

````{important} __Forme canonique d'une équation d'ordre 2.__
Une équation d'ordre 2 peut se mettre sous la forme:

\begin{align}
	a \frac{\rm{d^2}y}{\rm{dt^2}} + b \frac{\rm{d}y}{\rm{dt}} + c y(t) &= f(t) \textrm{ équation avec second membre}\\
	a \frac{\rm{d^2}y}{\rm{dt^2}} + b \frac{\rm{d}y}{\rm{dt}} + c y(t) &= 0 \textrm{ équation sans second membre}
\end{align}

On mettra en général l'équation sous la forme canonique:

\begin{align}
	\frac{\rm{d^2}y}{\rm{dt^2}} + \frac{\omega_0}{Q} \frac{\rm{d}y}{\rm{dt}} + \omega_0^2 y(t) = g(t)\\
	\frac{\rm{d^2}y}{\rm{dt^2}} + 2 \xi \omega_0 \frac{\rm{d}y}{\rm{dt}} + \omega_0^2 y(t) = g(t)
\end{align}

On donnera des interprétations aux grandeurs $\omega_0, \xi$ et Q dans le cours d'électrocinétique.
````

````{important} __Equation caractéristique__
La détermination de la solution générale passe par la résolution de l'équation caractéristique:

\begin{equation}
a r^2 + b r + c = 0
\end{equation}

dont les solutions sont:

\begin{equation}
r_{1,2} = \frac{-b \pm \sqrt{\Delta}}{2a} \textrm{ avec } \Delta = b^2 - 4ac
\end{equation}
````

```{margin} __Traitement du second membre__

Attention, s'il y a un second membre il faut aussi le traiter. Nous verrons la méthode générale par la suite.
```
````{important} __Solution de l'équation sans second membre__
Les solutions de l'équation __homogène__, c'est-à-dire sans second membre ont une forme différente suivant la nature des solutions de l'équation caractéristique.

* Cas 1: $\Delta > 0$, les racines $r_{1,2}$ sont réelles. La solution générale de l'équation homogène s'écrit:

\begin{equation}
f_1(t) = A e^{r_1 t} + B e^{r_2 t}
\end{equation}

* Cas 2: $\Delta = 0$, il y a une racine double notée $r_0 = \frac{-b}{2a}$ et réelle. La solution générale de l'équation homogène s'écrit:

\begin{equation}
f_1(t) = (A + Bt) e^{r_0 t}
\end{equation}

* Cas 3: $\Delta < 0$, les racines $r_{1,2}$ sont complexes et conjuguées, on peut les écrire sous la forme $r_{1,2} = \lambda \pm j \Omega$. La solution générale de l'équation homogène est à valeur réelle et il est important d'en donner une expression qui fait apparaître ce caractère et qui permet de l'analyser physiquement. On l'écrit donc sous les formes:

\begin{equation}
f_1(t) = (A \cos \Omega t + B \sin \Omega t) e^{\lambda t} =C \cos(\Omega t + \phi) e^{\lambda t}
\end{equation}

_$\Omega$ est appelée pseudo-pulsation.
````
