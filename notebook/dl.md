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
# Développements limités

## Développements limités: principe général

````{topic} __Approximations polynomiales__  
Le principe d'un développement limité consiste à remplacer le comportement d'une fonction $f(x)$ autour d'un point $x_0$ par un polynôme de degré $n$ dont les coefficients vont dépendre de la fonction $f$ et du point $x_0$. Cela suppose certaines régularités sur la fonction et l'écart entre le polynôme et la fonction est alors d'autant plus faible que:

* on calcule la fonction en $x$ près de $x_0$
* le degré $n$ du polynôme est plus élevé

Vous verrez les conditions d'applications en cours de mathématiques plus tard. En physique, on les supposera toujours vérifiées. On admettra ces formules en physique.
````

```{margin} Ordre 0 et ordre 1
A l'ordre 0, on a simplement: $f(x) \approx f(x_0)$, cela revient à calculer la limite en $x_0$.

A l'ordre 1, on a: $f(x) \approx f(x_0) + f'(x_0) (x-x_0)$ on confond alors la fonction f avec sa tangente en $x_0$. On parle de __linéarisation__.
```
````{important} __Développements limités__
Soit une fonction $f$ définie et $n$ fois dérivable au voisinage d'un point $x_0$. Soit un point $x$ situé dans ce voisinage, alors on a:

\begin{equation}
f(x) = \sum\limits_{k=0}^{n} \frac{f^{(k)}(x_0)}{k !}{(x-x_0)}^k + \epsilon(x) {(x-x_0)}^n
\end{equation}

où $f^{(k)}$ désigne la k-ième dérivée de la fonction f et $\epsilon(x)$ est une fonction tendant vers 0 quand x tend vers $x_0$.
````
```{topic} Traitement du terme négligeable
* On dit que le terme $\epsilon(x)$ est négligeable devant ${(x-x_0)^n}$ et a fortiori devant les autres termes (qui sont des puissances inférieures) quand x tend vers $x_0$. En mathématiques, on remplace le terme $\epsilon(x) {(x-x_0)}^n$ par $o({(x-x_0)}^n)$ ce qui signifie la même chose. On parle de développement limité (DL) à l'ordre n.
* En physique, on va remplacer $f(x)$ par la somme polynomiale sans tenir compte du terme en $\epsilon(x) {(x-x_0)}^n$.  En physique, on préfèrera parler d'approximation polynomiales à l'ordre n. Néanmoins, les techniques vues en mathématiques restent utilisables en physique et le terme employé importe peu.
```

````{topic} Exemple : Développements limités de la fonction sinus
* Ordre 1: $\sin(x) = x + o(x)$ 
* Ordre 3: $\sin(x) = x - \frac{x^3}{3} + o(x^3)$
* Ordre 5: $\sin(x) = x - \frac{x^3}{3} + \frac{x^5}{120} + o(x^5)$
* Ordre 7: $\sin(x) = x - \frac{x^3}{3} + \frac{x^5}{120} - \frac{x^7}{5040} + o(x^7)$

```{figure} ./images/math_dl_sinus.png
:name: fig_337
:align: center
:width: 50%
```
````

## Fonctions usuelles


```{margin}
Les développements limités précédents sont TOUS données autour de x=0. Si on a la même fonction mais que le développements limités est autour d'une autre valeur de x, il faut recalculer les coefficients du polynômes avec la formules précédentes (ou se débrouiller avec les méthodes proposées par la suite).
```
```{margin}
_En physique la connaissance jusqu'à l'ordre 2 suffit._
```
````{important} __Développements limités usuels__
Si la fonction est inconnue, on doit utiliser la formule ci-dessus. On utilise néanmoins souvent les mêmes formules en physique, il est donc bon de connaître leur développement (qu'on peut utiliser directement). Ils s'agit de fonctions usuelles prises autour du point $x_0 = 0$.

\begin{align}
	{(1+x)}^{a} &=_{0} 1 +  ax + \frac{a(a+1)}{2}x^2 + \cdots &= &1+ \sum\limits_{k=1}^{n} \frac{1}{k !}(\prod\limits_{j=0}^{j=k-1}(a-j))x^k + o(x^n)\\
	\frac{1}{1+x} &=_{0} 1 -  x + x^2 - x^3 + \cdots &=& \sum\limits_{k=0}^{n} {(-x)}^k + o(x^n)\\
	\ln(1+x) &= x -  \frac{x^2}{2} + \frac{x^3}{3} + \cdots &=& \sum\limits_{k=1}^{n} \frac{{(-1)}^(k-1)}{k} x^k + o(x^n)\\
	e^x &=_{0} 1 + x + \frac{x^2}{2} + \frac{x^3}{6} + \cdots &=& \sum\limits_{k=0}^{n} \frac{{(x)}^k}{k!} + o(x^n)\\
	\cos(x) &=_{0} 1 -  \frac{x^2}{2} &=& \sum\limits_{k=0}^{n} \frac{{(-1)}^k}{(2k)!} x^{2k}+ o(x^{2n})\\
	\sin(x) &=_{0} x -  \frac{x^3}{6} &=& \sum\limits_{k=0}^{n} \frac{{(-1)}^k}{(2k+1)!} x^{2k+1}+ o(x^{2n+1})\\
\end{align}
````

## Manipulation des développements limités
_En physique, on utilise souvent les formules courantes données ci-dessus. Associées à la "composition" des fonctions, on peut en général s'en sortir. On peut en effet utiliser les opérations usuelles pour les développements limités. Mais certaines règles sont à respecter._


````{important} Opérations sur les développements limités
Règle générale: si l'on fait un développements limités à l'ordre N, alors on ne doit garder __QUE__ les termes de degré inférieurs où égal dans les DL et __TOUS__ les termes de degré inférieurs où égal dans les DL.

__Addition et soustraction:__ Il faut faire attention à une règle: si aucun ordre n'est précisé, cela signifie qu'on attend un résultat non nul. Donc si on obtient un résultat nul à l'ordre n, il faut reprendre le calcul à l'ordre n+1.

__Multiplication:__ on peut multiplier des DL mais il faut faire très attention car si on fait un DL à l'ordre n, il faut garder TOUT les termes d'ordres inférieur ou égal à n et UNIQUEMENT ces termes: les termes d'ordre supérieur doivent être enlevés.

__Composition de fonctions:__ on peut appliquer un DL usuels à une fonction simple, on peut aussi composer 2 DL en respectant la même règle que pour la multiplication et en vérifiant bien qu'on peut le faire: si on fait le DL de __$g(f(x))$__ en __$x=0$__, on utilise la formule du DL de f en __$x=0$__ et la formule du DL de g en __$y=f(0)$__.

__Division:__ il est possible de diviser des DL mais le principe est moins directe que la multiplication (cours de math). On utilise souvent le DL de $\frac{1}{1+x}$.
````

````{topic} Exemple : Compositions simples
:class: note

\begin{align*}
	\sqrt{1-x} &= {(1-x)}^{1/2} = 1+ \frac{1}{2} (-x) - \frac{1}{8} {(-x)}^2 + o(x^2) = 1 - \frac{1}{2} x - \frac{1}{8} x^2 + o(x^2)\\
	\frac{1}{1-x} &= 1 - (-x) + {(-x)}^2 - {(-x)}^3 + o(x^3) = 1 + x + x^2 + x^3 + o(x^3)\\
	\textrm{On peut }&\textrm{de même étudier des développements en $x=+\infty$ en remplaçant $x$ par $u=1/x$ qui tend vers 0:}\\
	\frac{x}{x+1} &= \frac{1}{1+ 1/x} = \frac{1}{1+u} =_{u \rightarrow 0} 1 - u + u^2 +o(u^2) =_{x \rightarrow + \infty} 1 - \frac{1}{x} + \frac{1}{x^2} + o(\frac{1}{x^2})
\end{align*}
````

## Méthode: Approximation en physique
_On aura très rarement une variable x qui tend explicitement vers 0. Les DL sont avant tout utilisés en physique comme des approximations pour des études de comportements asymptotiques ou la simplification d'équations différentielles complexes (linéarisation => ordre 1). Une approximation revient en général à négliger un terme devant un autre, c'est-à-dire qu'on aura souvent comme condition $r \ll a$, c'est-à-dire r négligeable devant a. C'est alors la grandeur $\frac{r}{a}$ qui tend vers 0: on fera donc un DL limité de la fonction quand $r/a$ tend vers 0._


````{admonition} Exercice 
:class: attention
On est arrivé au résultat suivant: $PM = \sqrt{r^2 + a^2 - 2ar \cos \theta}$ (PM est une longueur). On cherche à simplifier cette expression dans le cas où $r\gg a$.
````

````{topic} Correction
```{sidebar}
Attention: On ne peut négliger un terme s'il n'y a pas de terme très grand devant lui. Par exemple, dans $\frac{r}{r+a}$ où $r\ll a$. Au dénominateur, on peut négliger r devant a mais au numérateur, on doit laisser r car il est seul (donc négligeable devant rien). On a donc: $\frac{r}{r+a} \approx \frac{r}{a}$ (c'est un développement limité à l'ordre 1, pour s'en rendre compte, il faut factoriser par a au dénominateur).
```
On commence par factoriser par r pour faire apparaître la grandeur $a/r \ll 1$

\begin{equation}
PM = r \sqrt{1 + 2 cos \theta\frac{a}{r} + \frac{a^2}{r^2}}
\end{equation}

* A l'ordre 0: $PM \approx r$
* A l'ordre 1:
    * on néglige sous la racine le terme d'ordre 2: $PM \approx r \sqrt{1 + 2 cos \theta \frac{a}{r}}$
    * puis on utilise le DL de $\sqrt{1+x}$ autour de 0 avec $x = 2 cos \theta \frac{a}{r}$:

\begin{equation}
PM \approx r (1 + \cos \theta \frac{a}{r}) = r + \cos \theta a
\end{equation}
````

