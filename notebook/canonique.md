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

````{admonition} Définition : Forme canonique d'une équation d'ordre 1.
:class: tip
Une équation d'ordre 1 peut se mettre sous la forme:

\begin{align}
	\frac{\rm{d}y}{\rm{dt}} + \frac{1}{\tau} y(t) &= f(t) \textrm{ équation avec second membre}\\
	\frac{\rm{d}y}{\rm{dt}} + \frac{1}{\tau} y(t) &= 0 \textrm{ équation sans second membre}
\end{align}
````

````{admonition} Fondamental : Solution de l'équation sans second membre
:class: important
Toutes les solutions de l'équation __homogène__, c'est-à-dire sans second membre sont de la forme:

\begin{equation}
y(t) = A e^{-\frac{t}{\tau}}
\end{equation}
````

````{admonition} Attention : Traitement du second membre
:class: note
Attention, s'il y a un second membre il faut aussi le traiter. Nous verrons la méthode générale par la suite.
````

## Equation d'ordre 2

````{admonition} Définition : Forme canonique d'une équation d'ordre 2.
:class: tip
Une équation d'ordre 2 peut se mettre sous la forme:

\begin{align}
	a \frac{\rm{d^2}y}{\rm{dt^2}} + b \frac{\rm{d}y}{\rm{dt}} + c y(t) &= f(t) \textrm{ équation avec second membre}\\
	a \frac{\rm{d^2}y}{\rm{dt^2}} + b \frac{\rm{d}y}{\rm{dt}} + c y(t) &= 0 \textrm{ équation sans second membre}
\end{align}

On mettra en général l'équation sous la forme canonique:

\begin{align}
	\frac{\rm{d^2}y}{\rm{dt^2}} + \frac{\omega_0}{Q} \frac{\rm{d}y}{\rm{dt}} + \omega_0^2 y(t) = f(t)\\
	\frac{\rm{d^2}y}{\rm{dt^2}} + 2 \xi \omega_0 \frac{\rm{d}y}{\rm{dt}} + \omega_0^2 y(t) = f(t)
\end{align}

On donnera des interprétations aux grandeurs $\omega_0, \xi$ et Q dans le cours d'électrocinétique.
````

````{admonition} Fondamental : Equation caractéristique
:class: important
La détermination de la solution générale passe par la résolution de l'équation caractéristique:

\begin{equation}
a r^2 + b r + c = 0
\end{equation}

dont les solutions sont:

\begin{equation}
r_{1,2} = \frac{-b \pm \sqrt{\Delta}}{2a} \textrm{ avec } \Delta = b^2 - 4ac
\end{equation}
````

````{admonition} Fondamental : Solution de l'équation sans second membre
:class: important
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
````

````{admonition} Attention : Traitement du second membre
:class: note
Attention, s'il y a un second membre il faut aussi le traiter. Nous verrons la méthode générale par la suite.
````

# Equations différentielles: méthodes de résolution

## Méthode de résolution

````{admonition} Méthode de résolution
:class: important
Pour résoudre une équation différentielle, il faut suivre __scrupuleusement l'ordre de résolution__ suivant:
* Mettre en équation le problème et mettre l'équation sous forme canonique en reconnaissant l'ordre de l'équation.
* Déterminer la solution générale (notée ici $f_1(t)$) de l'équation homogène (ESSM) soit directement (ordre 1), soit par analyse du discriminant de l'équation différentielle. __Ne pas chercher à déterminer les constantes d'intégration.__
* Déterminer une solution particulière  (notée ici $f_2(t)$) de l'équation avec second membre si il est non nul. Le seul cas où la méthode est à connaître est le cas d'un second membre constant. On cherche alors une solution particulière constante. __On ne fait pas de méthode de la variation de la constante en physique__. On verra aussi le cas d'un second membre sinusoïdal mais la méthode à connaître sera présentée dans un chapitre entier d'électrocinétique.
* L'ensemble des solutions est alors de la forme $f(t) = f_1(t) + f_2(t)$
* Déterminer les constantes d'intégration grâce aux conditions initiales.
````

## Méthode: Résolution d'une équation d'ordre 1s

````{admonition} Exercice 
:class: attention
Résoudre l'équation différentielle suivante:

\begin{equation}
\frac{\rm{d}f}{\rm{dt}}(t) + \frac{1}{\tau} f(t) = E
\end{equation}

avec f(0) = 0
````

````{dropdown} Correction
L'équation est déjà sous forme canonique, la solution ESSM est $f_1(t) = A e^{-\frac{t}{\tau}}$

Le second membre étant constant, on cherche une solution constante sous la forme $f_2(t) = K$. L'équation devient $0 + K/\tau = E$ soit $K = \tau E$.

La solution générale de l'équation avec second membre :

\begin{equation}
f(t) = A e^{-\frac{t}{\tau}} + \tau E
\end{equation}

On cherche maintenant la constante d'intégration grâce à la condition initiale $f(0) = 0$. Il vient $A + \tau E = 0 \Longrightarrow A = - \tau E$. La solution est donc:

\begin{equation}
f(t) = \tau E \left(1 -  e^{-\frac{t}{\tau}}\right)
\end{equation}
````

## Méthode: Equation d'ordre 2

````{admonition} Exercice 
:class: attention

On considère l'équation suivante avec R et C positifs:

\begin{equation}
R^{2}C^{2} \frac{\rm{d^2}u}{\rm{dt^2}} + 3RC \frac{\rm{d}u}{\rm{dt}} + u = E
\end{equation}

avec u(0) = 0 et $\frac{\rm{d}u}{\rm{dt}}(0) = 0$
````

````{dropdown} Correction
En cours de physique, on introduira les grandeurs $\omega_0$ et Q. Ici, on va résoudre directement l'équation sans ces grandeurs. L'équation caractéristique est donc: ${(RC)}^2 r^2 + 3RC r + 1 = 0$ dont le discriminant est: $\Delta = 5 {(RC)}^2> 0$. Les solutions sont réelles et valent: 

\begin{equation}
r_{1,2} = \frac{1}{2RC} \left(3 \pm \sqrt{5}\right)
\end{equation}

La solution générale ESSM est donc de la forme:

\begin{equation}
u_1(t) = A e^{r_1 t} + B e^{r_2 t}
\end{equation}

On cherche une solution particulière sous une forme constante $u_2(t) = K$ ce qui donne l'équation $0 + 0 + K = E$ soit une solution générale EASM:

\begin{equation}
u(t) = A e^{r_1 t} + B e^{r_2 t} + E
\end{equation}

On détermine maintenant les constantes d'intégration à partir des conditions initiales. On obtient le système:

\begin{equation}
\begin{cases}
	A + B + E &= 0\\
	r_1 A + r_2 B &= 0
\end{cases}
\Longrightarrow
\begin{cases}
	A &= \frac{r_2 E}{r_1 - r_2}\\
	B &= \frac{r_1 E}{r_2 - r_1}
\end{cases}	
\end{equation}
````
