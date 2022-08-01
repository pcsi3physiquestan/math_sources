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
# Méthodes de résolution
_Les corrections sont en ligne._

````{important} Méthode de résolution
Pour résoudre une équation différentielle, il faut suivre __scrupuleusement l'ordre de résolution__ suivant:
1. Mettre en équation le problème et mettre l'équation sous forme canonique en reconnaissant l'ordre de l'équation.
2. Déterminer la solution générale (notée ici $f_1(t)$) de l'équation homogène (ESSM) soit directement (ordre 1), soit par analyse du discriminant de l'équation différentielle. __Ne pas chercher à déterminer les constantes d'intégration.__
3. Déterminer une solution particulière  (notée ici $f_2(t)$) de l'équation avec second membre si il est non nul. Le seul cas où la méthode est à connaître est le cas d'un second membre constant. On cherche alors une solution particulière constante. __On ne fait pas de méthode de la variation de la constante en physique__. On verra aussi le cas d'un second membre sinusoïdal mais la méthode à connaître sera présentée dans un chapitre entier d'électrocinétique.
4. L'ensemble des solutions est alors de la forme $f(t) = f_1(t) + f_2(t)$
5. Déterminer les constantes d'intégration grâce aux conditions initiales.
````

## Résolution d'une équation d'ordre 1s

````{admonition} Exercice 
:class: attention
Résoudre l'équation différentielle suivante:

$$
\frac{\rm{d}f}{\rm{dt}}(t) + \frac{1}{\tau} f(t) = E
$$

avec f(0) = 0
````

````{topic} Correction
>L'équation est déjà sous forme canonique, la solution ESSM est $f_1(t) = A e^{-\frac{t}{\tau}}$
>
>Le second membre étant constant, on cherche une solution constante sous la forme $f_2(t) = K$. L'équation devient $0 + K/\tau = E$ soit $K = \tau E$.
>
>La solution générale de l'équation avec second membre :
>
>\begin{equation}
f(t) = A e^{-\frac{t}{\tau}} + \tau E
\end{equation}
>
>On cherche maintenant la constante d'intégration grâce à la condition initiale $f(0) = 0$. Il vient $A + \tau E = 0 \Longrightarrow A = - \tau E$. La solution est donc:
>
>\begin{equation}
f(t) = \tau E \left(1 -  e^{-\frac{t}{\tau}}\right)
\end{equation}
````

## Equation d'ordre 2

````{admonition} Exercice 
:class: attention

On considère l'équation suivante avec R et C positifs:

$$
R^{2}C^{2} \frac{\rm{d^2}u}{\rm{dt^2}} + 3RC \frac{\rm{d}u}{\rm{dt}} + u = E
$$

avec u(0) = 0 et $\frac{\rm{d}u}{\rm{dt}}(0) = 0$
````

````{topic} Correction
>En cours de physique, on introduira les grandeurs $\omega_0$ et Q. Ici, on va résoudre directement l'équation sans ces grandeurs. L'équation caractéristique est donc: ${(RC)}^2 r^2 + 3RC r + 1 = 0$ dont le discriminant est: $\Delta = 5 {(RC)}^2> 0$. Les solutions sont réelles et valent: 
>
>\begin{equation}
r_{1,2} = \frac{1}{2RC} \left(3 \pm \sqrt{5}\right)
\end{equation}
>
>La solution générale ESSM est donc de la forme:
>
>\begin{equation}
u_1(t) = A e^{r_1 t} + B e^{r_2 t}
\end{equation}
>
>On cherche une solution particulière sous une forme constante $u_2(t) = K$ ce qui donne l'équation $0 + 0 + K = E$ soit une solution générale EASM:
>
>\begin{equation}
u(t) = A e^{r_1 t} + B e^{r_2 t} + E
\end{equation}
>
>On détermine maintenant les constantes d'intégration à partir des conditions initiales. On obtient le système:
>
>\begin{equation}
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
