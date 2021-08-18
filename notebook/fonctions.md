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

## Fonctions: Etude générale

### Fonctions: Généralités
Si en physique le domaine de définition est sous-entendu, il faut garder à l'esprit que certaines fonctions ne sont pas définies sur $\mathbb{R}$.

On ne redonne pas ici les régles de calcul dans le cas des formes indéterminées. Il est conseillé de bien les revoir pour être capables de calculer des limites dans les différents cas vus jusqu'à présent.

### Fonction: Dérivation

````{admonition} Définition : Nombre dérivé et fonction dérivée
:class: tip

Le nombre dérivé de la fonction f en $x = x_0$ est définie comme la limite du taux de variation de la fonction en ce point (on présuppose ici son existence):

\begin{equation}
f'(x_0) = \lim\limits_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0}= \lim\limits_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h}
\end{equation}

La (fonction) dérivée de f est la fonction qui associe à tout x de l’intervalle de dérivabilité le nombre dérivé de f en x.
````

````{admonition} Fondamental : Formulaire de dérivation
:class: important
* Dérivée du produit: $\left (u \times v \right)' = u'v + uv'$
* Dérivée d'une composé: $\left (u \circ v \right)' = \left ( u' \circ v\right )\times v'$
* Il est bon aussi d'une dérivée usuelle: puissance réelle, trigonométrique, exponentielle et sa réciproque... 
````

````{admonition} Fondamental : Interprétation de la dérivée première
:class: important

La dérivée première donne la pente de la tangente de la fonction au point $x_0$.

Le signe de la dérivée donne la monotonie de la fonction (croissante ou décroissante). Lorsque la dérivée s'annule, on a un extremum local (maximum ou minimum).

```{figure} ./images/mathematiques_derivee_tangente.jpg
:name: deriv_tangente
:align: center
```
````

````{admonition} Fondamental : Interprétation de la dérivée seconde
:class: important
La dérivée seconde définit la concavité de la fonction (tendance à être incurvée vers le haut lorsque la dérivée seconde est positive et incurvée vers le bas sinon).

Lorsque la dérivée seconde s'annule, la courbe change de concavité, on parle de __point d'inflexion.__
````

### Fonction: Tracé

````{admonition} Attention : Importance des tracés
:class: note

Les tracés des fonctions en physique sont très importants car ils permettent de prévoir des comportements avec peu de calcul et une vision globale. Ils doivent donc être réalisés avec soin. Ainsi:

* un graphique doit avoir des axes légendés.
* la trace de la fonction doit respecter le domaine de définition ou d'étude
* la trace de la fonction doit respecter les limites, les valeurs particulières (racines et valeurs remarquables introduites dans le problème) et les comportements asymptotiques
* la trace de la fonction doit respecter l'existence et la position des extrema
* la trace de la fonction doit respecter la monotonie de la fonction
* la trace de la fonction doit respecter la concavité de la fonction
````

### Dérivation de fonction

````{admonition} Exercice 
Déterminer la dérivée de la fonction $f(x) = e^{x^2}$
````

````{dropdown} Correction
Il s'agit d'une dérivée d'une composée de fonction: on compose la fonction exponentielle $h(x) =e^x$ avec la fonction carré $g(x) = x^2$: $f = h \circ g$. La dérivée est donc:

\begin{equation}
f'(x) = (h' \circ g)(x) \times g'(x) = e^{x^2} \times 2x
\end{equation}
````

### Méthode: Déterminer une asymptote oblique.
Voici une méthode très utile en électrocinétique. Il faut la connaître.

````{admonition} Exercice 
:class: attention

Montrer que la fonction f(x) ci-dessous possède une asymptote oblique en $x = + \infty$ et déterminer l'équation de cette asymptote oblique.

\begin{equation}
f(x) = \frac{2x^3 - 3x + 2}{x^2 - 1}
\end{equation}

Un asymptote oblique à la fonction f(x) en $+\infty$ est une droite d'équation y = ax + b telle $f(x) - (ax + b)$ tend vers 0 quand x tend vers $+\infty$.
````

````{dropdown} Correction
Il existe plusieurs méthodes. On en propose deux: la première est complète et la seconde beaucoup plus rapide. Une fois maîtrisée, la seconde suffit en physique même si quelques points de raisonnements ne sont pas complètement prouvés.


__Etude de la différence__

\begin{equation}
f(x) - ax  - b = \frac{2x^3 - 3x + 2 - ax^3 - b x^2 + ax + b}{x^2 - 1} = \frac{(2- a) x^3 - b x^2 + (a - 3) x +2 +b}{x^2 - 1}
\end{equation}

Pour que cette différence tendent vers 0, il faut que  les coefficients devant les puissances cube et carré tendent vers 0 (car la puissance maximale du dénominateur est 2). Il vient a = 2 et b = 0

__Division euclidienne__

On va chercher à écrire le numérateur N sous la forme $N(x) = (ax + b) D(x) + R(x)$ où D(x) est le dénominateur (R(x) sera le reste dela division de N(x) par D(x)).

On pourra poser cette division comme une division euclidienne pour mieux voir le raisonnement. On commence par le coefficient le plus grand ; pour obtenir $2x^3$, il faut multiplier $x^2-1$ par 2x. Il reste alors $R_1(x) = N(x) - 2x \times D(x) = -x + 2$. Le polynôme $R_1(x)$ étant de degré inférieur au polynôme D(x), on ne peut continuer la division, c'est le reste R(x). L'équation de la droite est donc y = 2x

Remarque: l'utilisation de cette méthode présuppose l'existence d'une asymptote oblique. On remarquera qu'une telle existence nécessite, dans le cas d'une fraction rationnelle que le degré du polynôme au numérateur soit égale au degré du polynôme au dénominateur augmenté de 1. Pour des fonctions qui ne sont pas des équations rationnelles... 
````

## Fonctions usuelles

### Fonctions usuelles

````{admonition} Définition : Polynôme
:class: tip

Ils sont sous la forme:

\begin{equation}
\sum\limits_{k=0}^{N}a_k x^k
\end{equation}

La puissance maximale donne le degré du polynôme.

Le cas du polynôme de degré 2 doit être parfaitement maîtrisé.
````

````{admonition} Définition : Exponentielle et Logarithme
:class: tip
La fonction exponentielle $e^x$ est définie sur $\mathbb{R}$. Elle est strictement croissante de 0 vers $+\infty$ (plus rapidement qu'un polynôme).

Elle ne s'annule jamais et vaut 1 en 0 (où sa pente est 1). Sa dérivée est $e^x$. Sa réciproque est le logarithme népérien.

La fonction logarithme népérien $\ln$ est définie sur $\mathbb{R}_{+}^{*}$. Elle est strictement croissante et tend vers $-\infty$ en $0^{+}$ et vers $+\infty$ en $+\infty$ (plus lentement qu'un polynôme). Elle s'annule en $x=1$ (sa pente est alors de $1$). Sa dérivée est $1/x$.
								
La fonction réciproque est la fonction exponentielle. Le tracé des deux fonctions est donc symétrique par rapport à la première diagonale d'équation $y=x$.

```{figure} ./images/mathematiques_exp_ln.jpg
:name: exp_ln
:align: center
```
````

````{admonition} Fondamental : Propriétés
:class: important

\begin{align*}
	\ln\left(a \times b\right) &= \ln \left(a\right) + \ln \left(b\right)\\
	\ln\left(a^b\right) &= b\ln\left(a\right)\\
	b^a &= e^{a \ln b}
\end{align*}
````

### Fonctions trigonométrique

````{admonition} Définition : Fonctions trigonométriques
:class: tip

Les trois fonctions trigonométriques sont $\sin(x), \cos(x), \tan(x)$. Elles sont toutes les trois périodiques de période $2 \pi$ (en radians).

Les fonctions cos et sin sont à valeurs dans $[-1;1]$ et on a $\sin(x) =\cos(x-\pi/2)$ ce qui signifie comme nous le verrons par la suite que le tracé de la fonction sinus est le même que le tracé de la fonction cosinus mais décalé de $+ \pi/2$ horizontalement.

La fonction cosinus s'annule en $\pm \pi/2$ et atteint ses extrema en 0 (1) et $\pi$ (-1). Pour le sinus, c'est l'inverse. De plus cos est paire et sin impaire. On a $\cos' = -\sin$ et $\sin' = \cos$.

La fonction tan est définie par $\tan = \frac{\sin}{\cos}$: elle a donc les mêmes points d'annulation que la fonction sinus et diverge quand le cosinus s'annule. Elle est strictment croissante et sa dérivée vaut $\tan' = \frac{1}{cos^2} = 1 + tan^2$.

```{figure} ./images/mathematiques_cos_sin_tan.jpg
:name: sin_tan
:align: center
```
````

````{admonition} Définition : Fonctions réciproques
:class: tip

Les fonctions réciproques sont arccos, arcsin et arctan. Arccors et arcsin ont un domaine de définition restreint à [-1;1] alors que arctan a un domaine de définition étendu à $\mathbb{R}$. Arccos est à valeurs dans __$[0;\pi]$__ et arcsin est à valeur dans __$[-\pi/2;\pi/2]$__. Arctan est à valeur dans __$[-\pi/2;\pi/2]$__.
````

````{admonition} Fondamental : Relations trigonométriques
:class: important
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
````

````{admonition} Fondamental : Relations réciproques
:class: important
\begin{align*}
    \cos(\arcsin(x)) &= \sqrt{1-x^2}\\
    \sin(\arccos(x)) &= \sqrt{1-x^2}\\
    \cos(\arctan(x)) &= \sqrt{\frac{1}{1+x^2}}\\
    \sin(\arctan(x)) &= \sqrt{\frac{x^2}{1+x^2}}\\
    \tan(\arcsin(x)) &= \sqrt{\frac{x^2}{1-x^2}}\\
    \tan(\arccos(x)) &= \sqrt{\frac{1-x^2}{x^2}}
\end{align*}
````

### Méthode: Retrouver les formules des inverses
Nous allons voir ici une méthode pour retrouver les expressions des grandeurs comme $\sin(\arccos(x))$. Il est conseillé de s'entraîner à retrouver rapidement les autres expressions en cas d'oubli.

````{admonition} Exercice 
:class: attention
Montrer que $\sin(\arctan(x)) = \sqrt{\frac{x^2}{1+x^2}}$
````

````{dropdown} Démonstration
On va utiliser la relation $\sin^2(y) + \cos^2(y) =1$ avec $y = \arctan(x)$. Divisons par $\sin^2(\arctan(x))$:

\begin{align*}
	1 + \frac{\cos^2 \left(\arctan x\right)}{\sin^2\left(\arctan x\right)} &= \frac{1}{\sin^2\left(\arctan x\right)}\\
	1 + \frac{1}{\tan^2\left(\arctan x\right)} &= \frac{1}{\sin^2\left(\arctan x\right)}\\
	\sin\left(\arctan x\right) &= \frac{x}{\sqrt{1 + x^2}} 
\end{align*}
````

### Méthode: Manipulation de fonction trigonométrique
La relation entre les deux expressions données ci-dessous est __fondamentale__ en physique. Vous devez retenir leur égalité et les moyens de passer de l'une à l'autre.


````{admonition} Exercice 
:class: attention

Montrer que:

\begin{equation}
A \cos(x) + B \sin(x) = C \cos \left(x + \varphi\right)
\end{equation}

avec $C = \pm\sqrt{A^2 + B^2},~\tan \varphi = - \frac{B}{A}$ et $sign(\cos \varphi) = sign(\frac{A}{C})$.
````

````{dropdown} Correction
Le plus simple est de partir de $C \cos \left (x + \varphi \right )$ est de développer le sinusoïde. Les deux expressions devant être valable pour tout x, il vient que les coefficients devant le cosinus et le sinus doivent être égaux deux à deux (on pourra s'en convaincre en appliquer l'égalité à x=0 et $x=\pi/2$).

\begin{equation}
A \cos(x) + B \sin(x) = C \cos x \cos \varphi - C \sin x \sin \varphi \Longrightarrow
\begin{cases}
	A &= C \cos \varphi\\
	B &= - C \sin \varphi
\end{cases}
\end{equation}

Le signe de $ \cos \varphi$ et immédiat et en divisant les deux équations, on trouve l'expression de $\tan \varphi$

Il reste à passer les deux équations au carré et à sommer. En utilisant $\sin^2 + \cos^2 = 1$, il vient la relation $C^2 = A^2 + B^2$
````

### Méthode: Linéariser des puissances de cosinus ou sinus.
La méthode de linéarisation d'une puissance de fonction trigonométrique est très courante et doit être maîtrisée, notamment pour les analyses fréquentielles.

````{admonition} Exercice 
:class: attention

Linéariser $\cos^3(x)$ c'est-à-dire exprimer cette fonction comme une combinaison linéaire de fonction du type cos(nx) et sin(nx) avec n entier.
````

````{dropdown} Correction
Le principe est simple, on utilise les formules de duplication et de produit des fonctions trigonométriques.

\begin{align*}
	\cos^3(x) = \cos(x) \times \cos^2(x) &= \cos(x) \frac{1 + \cos(2x)}{2} \\
	&= \frac{1}{2} \cos(x) + \frac{1}{2}\left(\frac{\cos(x + 2x) + \cos(x - 2x)}{2}\right)\\
	&= \frac{1}{4} \cos(3x) + \frac{3}{4} \cos(x)
\end{align*}
````

## Fonctions: Transformations usuelles
Il faut pouvoir prévoir le tracé d'une fonction en repérant qu'il s'agit d'une fonction usuelle transformée par: symétrie, homothétie (agrandissement ou rétrécissement), translation... 

Nous allons voir ici quelles sont les principales transformations utiles et comment les reconnaître dans une expression mathématique d'une fonction.

Nous verrons au fil des chapitres que repérer ces transformations mathématiques permet aussi de faire des raisonnements physiques.

### Transformations suivant l'axe vertical
__Reconnaître une transformation selon l'axe vertical.__  
Les transformations d'une fonction usuelle (ou pas) suivant l'axe vertical correspondent à un modification de l'expression globale de la fonction.

Par exemple, dans la fonction:  $x \to 2x e^{x}$. On peut voir qu'elle correspond à la fonction $y \to y e^y$ où l'on multiplie la fonction __totale__ par 2.

Vous devez pouvoir reconnaître une telle modification et l'associer à la modification de l'allure de la fonction.


````{admonition} Fondamental : Translation verticale
:class: important
Considérons une fonction $f$ et une fonction $g(x) = x+a$. La composition $h(x)=g \circ f(x)$ correspond graphiquement à la translation verticale de la représentation graphique de $f$ de $+a$.
````

````{admonition} Exemple : Translation verticale
:class: note

Soit la fonction $f(x) = xln(x)$. La fonction $h(x)=x\ln x - 2$ est possède la même représentation graphique mais "décalée" de 2 unités vers le bas.

```{figure} ./images/mathematiques_translation_verticale.jpg
:name: tr_verticale
:align: center
```
````

````{admonition} Fondamental : Dilatation verticale
:class: important
Considérons une fonction $f$ et une fonction $g(x)=kx$ avec $k>0$. La composition $h(x)=g\circ f(x)$ correspond graphiquement à la dilatation de la courbe verticale d'un facteur $k$.
````

````{admonition} Exemple : Dilatation verticale
:class: note
Soit la fonction $f(x) = \sqrt{4-x^2}$ définie sur $[-2;2]$. La fonction $h(x) = 4 \sqrt{4-x^2}$ possède la même représentation graphique mais dilatée d'un facteur $4$ verticalement (d'un cercle on passe à une ellipse étirée vers le haut

```{figure} ./images/mathematiques_dilatation_verticale.jpg
:name: dil_verticale
:align: center
```
````

````{admonition} Fondamental : Symétrie par rapport à l'axe des abscisses
:class: important
Soit une fonction $f(x)$. La représentation graphique de la fonction $-f(x)$ s'obtient par symétrie par rapport à l'axe des abscisses.
````

### Transformations suivant l'axe horizontal
__Reconnaître une transformation selon l'axe horizontal.__  
Les transformations d'une fonction usuelles (ou pas) suivant l'axe horizontal correspondent à un modification de l'expression de la fonction au plus près de la variable.

Par exemple, dans la fonction:  $x \to 2x e^{2x}$. On peut voir qu'elle correspond à la fonction $y \to y x^y$ où l'on multiplie la variable par 2 __à chaque endroit.__

Vous devez pouvoir reconnaître une telle modification et l'associer à la modification de l'allure de la fonction.

````{admonition} Fondamental : Translation horizontale
:class: important
Considérons une fonction $f$ et une fonction $g(x) = x-a$. La composition $h(x)=f \circ g(x)$ correspond graphiquement à la translation horizontale de la représentation graphique de $f$ de $+a$.
````

````{admonition} Exemple : Translation horizontale
:class: note
Soit la fonction $f(x) = xln(x)$. La fonction $h(x)=(x-2)\ln(x-2)$  possède la même représentation graphique mais "décalée" de 2 unités vers la droite.

```{figure} ./images/mathematiques_translation_horizontale.jpg
:name: tr_horizon
:align: center
```
````

````{dropdown} Translation horizontale et physique

La translation horizontale apparaît souvent en physique dans des phénomènes retardés (ou avancés): la fonction qui dépend du temps, étant retardée, va avoir une expression de la forme $f(t - t_0)$ où $t_0$ est le retard.
````

````{admonition} Fondamental : Dilatation horizontale
:class: important
Considérons une fonction $f$ et une fonction $g(x)=kx$ avec $k>0$. La composition $h(x)=f\circ g(x)$ correspond graphiquement à la dilatation de la courbe horizontale d'un facteur $1/k$ (donc contraction de facteur $k$).
````

````{admonition} Exemple : Dilatation horizontale
:class: note
Soit la fonction $f(x) = \sqrt{4-x^2}$ définie sur $[-2;2]$. La fonction $h(x) = \sqrt{4-{(2x)}^2}$ possède la même représentation graphique mais dilatée d'un facteur $1/2$ horizontalement (d'un cercle on passe à une ellipse contractée horizontalement.

```{figure} ./images/mathematiques_dilatation_horizontale.jpg
:name: dil_horizon
:align: center
```
````

````{dropdown} Dilatation horizontale et physique
La dilatation horizontale est très importante en physique car elle correspond à des lois d'échelle.

Dans des fonctions du temps, si l'on a une fonction de la forme $f(\frac{t}{\tau})$, il s'agit d'une fonction qui sera d'autant plus lente à évoluer que $\tau$ est grand (dilatation horizontale).

On verra de la même manière des exemples de dilatation dans l'espace.
````

````{admonition} Fondamental : Symétrie par rapport à l'axe des ordonnées
:class: important
Soit une fonction $f(x)$. La représentation graphique de la fonction $f(-x)$ s'obtient par symétrie par rapport à l'axe des ordonnées.
````

````{admonition} Fondamental : Fonction réciproque et représentation graphique
:class: important
Il ne s'agit pas simplement d'une action sur l'axe horizontal mais sur les deux.

La représentation graphique de la fonction réciproque est le symétrique du tracé de la fonction directe par rapport à la première bissectrice: y = x.
````

### Méthode: Transformation d'une fonction cosinus ou sinus
Au delà de l'exemple d'application des propriétés précédentes, les conclusions sur les fonctions trigonométriques sont fondamentales car elles sont très utilisées et les éléments de vocabulaires introduits seront très importants pour la suite.


````{admonition} Exercice 
:class: attention
Décrivez graphiquement comment s'effectue la transformation de la fonction cos(t) à la fonction $S_m \cos \left ( \omega t + \varphi_0\right)$
````

````{admonition} Méthode : Caractéristiques d'un sinusoïde.
:class: important
On multiplie la fonction complète par$ S_m$, il y a donc une dilatation verticale. L'écartement maximal sera maintenant $2S_m$. On appelle $S_m$ __l'amplitude.__

L'argument du cosinus se réécrit: $\omega ( t + \varphi_0 / \omega )$. On a donc: 
* une dilatation horizontale du sinusoïde d'un facteur $\frac{1}{\omega}$. Ainsi la période du sinusoïde est maintenant $T = \frac{2 \pi}{\omega}$. $\omega$ est appelée __pulsation__.
* une translation horizontale de $\Delta t_0 = - \frac{\varphi_0}{\omega}$ (un retard ou une avance suivant le signe de $\varphi_0$). On appelle $\varphi_0$, la __phase à l'origine.__

```{figure} ./images/sinusoide_vm_0.png
:name: fig_sinusoide324
:align: center
Sinusoïde
```

Un sens physique plus approfondi sera donné à ces termes par les suite. On retiendra déjà le passage du cosinus simple à l'expression complète et surtout les effets sur la représentation graphique
````

### Méthode: Transformer une exponentielle
Voici un autre exemple de fonction très utile en physique, basée sur la transformation de l'exponentielle.


````{admonition} Exercice 
:class: attention
Décrivez graphiquement comment s'effectue la transformation de la fonction exp(t) à la fonction $E (1 - \exp(-t/\tau))$ et en déduire le tracé graphique de cette dernière fonction.
````

````{dropdown} Transformations successives
Pour plus de simplifité, on va partir des transformations au plus près de la variable (transformation horizontales) pour aller aux transformations globales.

* On divise la variable t par $\tau$. Il y a donc une dilatation de facteur $\tau$. On peut matérialiser ceci avec la tangente à l'origine: au lieu d'avoir une pente de 1, elle a maintenent une pente de $1/\tau$ puisque la fonction est dilatée. Elle va donc croiser l'axe des abscisses, non pas au point d'abscisse t=1 mais au point d'abscisse $t=-\tau$
* On réalise ensuite une symétrie par rapport à l'axe des ordonnées puisqu'on multiplie la variable par -1 ce qui donne ($exp(-t/\tau)$). On a (cf. second graphique sur la première ligne) maintenant une fonction décroissante dont la tangente à l'origine coupe l'axe des abscisses en $t = \tau$.
* On réalise ensuite une symétrie par rapport à l'axe des abscisses puisque l'exponentielle est multipliée par -1 ce qui donne ($-exp(-t/\tau)$). On retrouve (premier graphique de la deuxième ligne) une fonction croissante  mais qui est maintenant toujours négative.
* On ajoute ensuite 1 à l'ensemble, c'est donc une translation verticale vers le haut de 1. La fonction (deuxième graphique de la deuxième ligne), toujours croissante, change de signe en t=0 pour devenir positive. Elle tend vers une asymptote y=1 qui croise la tangente à l'origine en $t = \tau$ (puisqu'auparavent cette tangente croise en $t=\tau$ la valeur 0 et qu'on a décaler l'ensemble vers le haut de 1).
* On multiplie enfin par E ce qui dilate l'ensemble verticalement. La nouvelle asymptote est E et la tangente à l'origine croise en $t = \tau$, non plus la droite y=1 mais l'asymptote y=E.
````

````{dropdown} Transformations successives - 1

```{figure} ./images/exp_transfo1.png
:name: exp_tr_1
:align: center
```
````

````{dropdown} Transformations successives - 2
```{figure} ./images/exp_transfo2.png
:name: exp_tr_2
:align: center
```
````

````{dropdown} Transformations successives - 3
```{figure} ./images/exp_transfo3.png
:name: exp_tr_3
:align: center
```
````

