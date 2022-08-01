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
# Fonctions mathématiques

## Etude générale
````{margin} Généralités
On rappelle les caractéristiques générales : domaines de définition, limites...
````

````{sidebar} __Interprétation de la dérivée première__

La dérivée première donne la pente de la tangente de la fonction au point $x_0$.

Le signe de la dérivée donne la monotonie de la fonction (croissante ou décroissante). Lorsque la dérivée s'annule, on a un extremum local (maximum ou minimum).

```{figure} ./images/mathematiques_derivee_tangente.jpg
:name: deriv_tangente
:align: center
```
````
````{note} __Nombre dérivé et fonction dérivée__

Le nombre dérivé de la fonction f en $x = x_0$ est définie comme la limite du taux de variation de la fonction en ce point (on présuppose ici son existence):

$$
f'(x_0) = \lim\limits_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0}= \lim\limits_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h}
$$

La (fonction) dérivée de f est la fonction qui associe à tout x de l’intervalle de dérivabilité le nombre dérivé de f en x.
````

````{important} __Formulaire de dérivation__

* Dérivée du produit: $\left (u \times v \right)' = u'v + uv'$
* Dérivée d'une composé: $\left (u \circ v \right)' = \left ( u' \circ v\right )\times v'$
* Il est bon aussi d'une dérivée usuelle: puissance réelle, trigonométrique, exponentielle et sa réciproque... 
````

## Fonctions usuelles


````{note} __Polynôme__

Ils sont sous la forme:

$$
\sum\limits_{k=0}^{N}a_k x^k
$$

La puissance maximale donne le degré du polynôme.

Le cas du polynôme de degré 2 doit être parfaitement maîtrisé.
````

````{note} __Exponentielle et Logarithme__

La fonction exponentielle $e^x$ est définie sur $\mathbb{R}$. Elle est strictement croissante de 0 vers $+\infty$ (plus rapidement qu'un polynôme).

Elle ne s'annule jamais et vaut 1 en 0 (où sa pente est 1). Sa dérivée est $e^x$. Sa réciproque est le logarithme népérien.

La fonction logarithme népérien $\ln$ est définie sur $\mathbb{R}_{+}^{*}$. Elle est strictement croissante et tend vers $-\infty$ en $0^{+}$ et vers $+\infty$ en $+\infty$ (plus lentement qu'un polynôme). Elle s'annule en $x=1$ (sa pente est alors de $1$). Sa dérivée est $1/x$.
								
La fonction réciproque est la fonction exponentielle. Le tracé des deux fonctions est donc symétrique par rapport à la première diagonale d'équation $y=x$.

```{figure} ./images/mathematiques_exp_ln.jpg
:name: exp_ln
:align: center
```
````

````{important} __Propriétés__

\begin{align*}
	\ln\left(a \times b\right) &= \ln \left(a\right) + \ln \left(b\right)\\
	\ln\left(a^b\right) &= b\ln\left(a\right)\\
	b^a &= e^{a \ln b}
\end{align*}
````

````{note} __Fonctions trigonométriques__

Les trois fonctions trigonométriques sont $\sin(x), \cos(x), \tan(x)$. Elles sont toutes les trois périodiques de période $2 \pi$ (en radians).

Les fonctions cos et sin sont à valeurs dans $[-1;1]$ et on a $\sin(x) =\cos(x-\pi/2)$ ce qui signifie comme nous le verrons par la suite que le tracé de la fonction sinus est le même que le tracé de la fonction cosinus mais décalé de $+ \pi/2$ horizontalement.

La fonction cosinus s'annule en $\pm \pi/2$ et atteint ses extrema en 0 (1) et $\pi$ (-1). Pour le sinus, c'est l'inverse. De plus cos est paire et sin impaire. On a $\cos' = -\sin$ et $\sin' = \cos$.

La fonction tan est définie par $\tan = \frac{\sin}{\cos}$: elle a donc les mêmes points d'annulation que la fonction sinus et diverge quand le cosinus s'annule. Elle est strictment croissante et sa dérivée vaut $\tan' = \frac{1}{cos^2} = 1 + tan^2$.

```{figure} ./images/mathematiques_cos_sin_tan.jpg
:name: sin_tan
:align: center
```

Les fonctions réciproques sont arccos, arcsin et arctan. Arccos et arcsin ont un domaine de définition restreint à [-1;1] alors que arctan a un domaine de définition étendu à $\mathbb{R}$. Arccos est à valeurs dans __$[0;\pi]$__ et arcsin est à valeur dans __$[-\pi/2;\pi/2]$__. Arctan est à valeur dans __$[-\pi/2;\pi/2]$__.
````

````{important} __Relations trigonométriques__

\begin{align*}
 	\cos^2(x) + \sin^2(x) &= 1 \\
 	\cos(2x) &= \cos^2(x)-\sin^2(x) = 2 \cos^2(x)-1=1-2\sin^2(x) \\
 	\sin(2x) &= 2 \sin(x)\cos(x) \\
    \cos(a+b) &= \cos(a)\cos(b) - \sin(a)\sin(b) \\
    \cos(a-b) &= \cos(a)\cos(b) + \sin(a)\sin(b) \\
    \sin(a+b) &= \sin(a)\cos(b) + \cos(a)\sin(b) \\
    \sin(a-b) &= \sin(a)\cos(b) - \cos(a)\sin(b) \\
    \cos(a)\cos(b) &=\frac{\cos(a+b)+\cos(a-b)}{2} \\
    \sin(a)\sin(b) &=\frac{\cos(a-b)-\cos(a+b)}{2} \\
    \sin(a)\cos(b) &=\frac{\sin(a+b)+\sin(a-b)}{2} \\
    \frac{1}{\tan(x)} = \tan\left(\frac{\pi}{2} - x\right)
\end{align*}

\begin{align*}
    \cos(\arcsin(x)) &= \sqrt{1-x^2}\\
    \sin(\arccos(x)) &= \sqrt{1-x^2}\\
    \cos(\arctan(x)) &= \sqrt{\frac{1}{1+x^2}}\\
    \sin(\arctan(x)) &= \sqrt{\frac{x^2}{1+x^2}}\\
    \tan(\arcsin(x)) &= \sqrt{\frac{x^2}{1-x^2}}\\
    \tan(\arccos(x)) &= \sqrt{\frac{1-x^2}{x^2}}
\end{align*}
````

## Transformations usuelles
````{topic} Introduction
Il faut pouvoir prévoir le tracé d'une fonction en repérant qu'il s'agit d'une fonction usuelle transformée par: symétrie, homothétie (agrandissement ou rétrécissement), translation... 

Nous allons voir ici quelles sont les principales transformations utiles et comment les reconnaître dans une expression mathématique d'une fonction.

Nous verrons au fil des chapitres que repérer ces transformations mathématiques permet aussi de faire des raisonnements physiques.
````

### Transformations suivant l'axe vertical
````{margin}
Les transformations d'une fonction usuelle (ou pas) suivant l'axe vertical correspondent à un modification de l'expression globale de la fonction.
````

````{important} __Translation verticale__
Considérons une fonction $f$ et une fonction $g(x) = x+a$. La composition $h(x)=g \circ f(x)$ correspond graphiquement à la translation verticale de la représentation graphique de $f$ de $+a$.
````
````{topic} Exemple : Translation verticale
Soit la fonction $f(x) = xln(x)$. La fonction $h(x)=x\ln x - 2$ est possède la même représentation graphique mais "décalée" de 2 unités vers le bas.

```{figure} ./images/mathematiques_translation_verticale.jpg
:name: tr_verticale
:align: center
```
````

````{important} __Dilatation verticale__

Considérons une fonction $f$ et une fonction $g(x)=kx$ avec $k>0$. La composition $h(x)=g\circ f(x)$ correspond graphiquement à la dilatation de la courbe verticale d'un facteur $k$.
````
````{topic} Exemple : Dilatation verticale
Soit la fonction $f(x) = \sqrt{4-x^2}$ définie sur $[-2;2]$. La fonction $h(x) = 4 \sqrt{4-x^2}$ possède la même représentation graphique mais dilatée d'un facteur $4$ verticalement (d'un cercle on passe à une ellipse étirée vers le haut

```{figure} ./images/mathematiques_dilatation_verticale.jpg
:name: dil_verticale
:align: center
```
````

````{important} __Symétrie par rapport à l'axe des abscisses__

Soit une fonction $f(x)$. La représentation graphique de la fonction $-f(x)$ s'obtient par symétrie par rapport à l'axe des abscisses.
````

### Transformations suivant l'axe horizontal
````{margin}
Les transformations d'une fonction usuelles (ou pas) suivant l'axe horizontal correspondent à un modification de l'expression de la fonction au plus près de la variable.
````

````{sidebar} Translation horizontale et physique

La translation horizontale apparaît souvent en physique dans des phénomènes retardés (ou avancés): la fonction qui dépend du temps, étant retardée, va avoir une expression de la forme $f(t - t_0)$ où $t_0$ est le retard.
````
````{important} __Translation horizontale__
Considérons une fonction $f$ et une fonction $g(x) = x-a$. La composition $h(x)=f \circ g(x)$ correspond graphiquement à la translation horizontale de la représentation graphique de $f$ de $+a$.
````

````{topic} Exemple : Translation horizontale
Soit la fonction $f(x) = xln(x)$. La fonction $h(x)=(x-2)\ln(x-2)$  possède la même représentation graphique mais "décalée" de 2 unités vers la droite.

```{figure} ./images/mathematiques_translation_horizontale.jpg
:name: tr_horizon
:align: center
```
````

````{sidebar} Dilatation horizontale et physique
La dilatation horizontale est très importante en physique car elle correspond à des lois d'échelle.

Dans des fonctions du temps, si l'on a une fonction de la forme $f(\frac{t}{\tau})$, il s'agit d'une fonction qui sera d'autant plus lente à évoluer que $\tau$ est grand (dilatation horizontale).

On verra de la même manière des exemples de dilatation dans l'espace.
````
````{important} __Dilatation horizontale__

Considérons une fonction $f$ et une fonction $g(x)=kx$ avec $k>0$. La composition $h(x)=f\circ g(x)$ correspond graphiquement à la dilatation de la courbe horizontale d'un facteur $1/k$ (donc contraction de facteur $k$).
````

````{topic} Exemple : Dilatation horizontale
Soit la fonction $f(x) = \sqrt{4-x^2}$ définie sur $[-2;2]$. La fonction $h(x) = \sqrt{4-{(2x)}^2}$ possède la même représentation graphique mais dilatée d'un facteur $1/2$ horizontalement (d'un cercle on passe à une ellipse contractée horizontalement.

```{figure} ./images/mathematiques_dilatation_horizontale.jpg
:name: dil_horizon
:align: center
```
````

````{important} __Symétrie par rapport à l'axe des ordonnées__
Soit une fonction $f(x)$. La représentation graphique de la fonction $f(-x)$ s'obtient par symétrie par rapport à l'axe des ordonnées.
````
