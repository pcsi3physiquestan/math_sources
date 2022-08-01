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
# Méthodes
_Ces méthodes ont des corrections en ligne._

## Résolution d'équations

### Résoudre graphiquement une équation f(x)=g(x)
On ne peut pas toujours résoudre analytiquement une équation. On peut par contre toujours la résoudre graphiquement et on peut même obtenir des informations importantes sur le rôle de certains paramètres lors de ce genre de résolution.

````{admonition} Exercice 
:class: attention

Déterminer graphiquement les conditions d'existence de solutions non nulles pour l'équation:

\begin{equation}
x = \frac{mg}{k} \sin(x)
\end{equation}

avec k, m et g strictement positifs.
````

````{topic} Résolution graphique
Graphiquement celà revient à chercher l'intersection entre la représentation de deux fonctions: $\frac{k}{mg}x$ et sin(x).

Traçons donc les deux fonctions (on a représenté plusieurs droites puisque la pente varie en fonction des paramètres k, m et g - on rappelle que la pente est nécessairement positive).

```{figure} ./images/mathematique_projection_resolution_graphique.jpg
:name: res_gr
:align: center
```

On remarque que si la pente est trop pentue, la seule intersection est le point x=0, y=0 qu'on ne veut pas. Il y a une seconde intersection seulement si la pente de la droite est inférieure à la tangente du sinus en 0.

Cette condition s'écrit:

\begin{equation}
\boxed{\frac{k}{mg} < 1}
\end{equation}

```{dropdown} Méthode analytique
On peut démontrer analytiquement la propriété précédente en étudier les changements de signe de $h(x) = f(x)-g(x)$ et en utilisant la continuité de $h$. Cette méthode ne sera que très peu demandée en physique.
```
````
### Résoudre un système d'équation 2\*2
La méthode proposée est à __privilégier__ à la méthode de substitution. Elle vous semblera peut-être plus complexe au début mais avec l'entraînement elle permet un énorme gain de temps en physique (à moins que le système soit triangulaire et donc en partie déjà résolu !).


````{admonition} Exercice 
:class: attention

Déterminer les solutions du système suivant:

\begin{align*}
    3x + 4y &= 5 \\
    4x - 5y &= 2
\end{align*}
````

````{topic} Résolution par combinaison
Nous allons utiliser deux fois le système de départ. Une première fois pour éliminer x et obtenir une équation en y puis une seconde fois pour éliminer y et obtenir une équation en x.

Elimination de x:

\begin{equation}
\begin{cases}
    3x + 4y &= 5 \left(\times 4\right)\\
    4x - 5y &= 2 \left(\times -3\right)
\end{cases}
\Longrightarrow 31 y = 14 \Longrightarrow y = \frac{14}{31}
\end{equation}

Elimination de y:

\begin{equation}
\begin{cases}
    3x + 4y &= 5 \left(\times 5\right)\\
    4x - 5y &= 2 \left(\times 4\right)
\end{cases}
\Longrightarrow 31 x = 33 \Longrightarrow x = \frac{33}{31}
\end{equation}
````

## Fonctions

````{admonition} Dérivée d'une composée de fonction 
Déterminer la dérivée de la fonction $f(x) = e^{kx^2}$
````
````{topic} Correction
Il s'agit d'une dérivée d'une composée de fonction: on compose la fonction exponentielle $h(x) =e^x$ avec la fonction carré $g(x) = kx^2$: $f = h \circ g$. La dérivée est donc:

\begin{equation}
f'(x) = (h' \circ g)(x) \times g'(x) = e^{kx^2} \times 2kx
\end{equation}
````

````{admonition} Retrouver les formules trigonométriques des inverses
:class: attention
Montrer que $\sin(\arctan(x)) = \sqrt{\frac{x^2}{1+x^2}}$
````
````{topic} Correction
On va utiliser la relation $\sin^2(y) + \cos^2(y) =1$ avec $y = \arctan(x)$. Divisons par $\sin^2(\arctan(x))$:

\begin{align*}
  1 + \frac{\cos^2 \left(\arctan x\right)}{\sin^2\left(\arctan x\right)} &= \frac{1}{\sin^2\left(\arctan x\right)}\\
  1 + \frac{1}{\tan^2\left(\arctan x\right)} &= \frac{1}{\sin^2\left(\arctan x\right)}\\
  \sin\left(\arctan x\right) &= \frac{x}{\sqrt{1 + x^2}} 
\end{align*}
````

````{admonition} Manipulation de fonction trigonométrique 
:class: attention, full-width
La relation entre les deux expressions données ci-dessous est __fondamentale__ en physique. Vous devez retenir leur égalité et les moyens de passer de l'une à l'autre.

Montrer que:

\begin{equation}
A \cos(x) + B \sin(x) = C \cos \left(x + \varphi\right)
\end{equation}

avec $C = \pm\sqrt{A^2 + B^2},~\tan \varphi = - \frac{B}{A}$ et $sign(\cos \varphi) = sign(\frac{A}{C})$.
````

````{topic} Correction
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

### Transformation d'une fonction cosinus ou sinus
Au delà de l'exemple d'application des propriétés précédentes, les conclusions sur les fonctions trigonométriques sont fondamentales car elles sont très utilisées et les éléments de vocabulaires introduits seront très importants pour la suite. Une simulation donnée [ici](https://stanislas.edunao.com/mod/resource/view.php?id=12959) permet de voir l'effet des différents éléments sur le sinusoïde.


````{admonition} Exercice 
:class: attention
Décrivez graphiquement comment s'effectue la transformation de la fonction cos(t) à la fonction $S_m \cos \left ( \omega t + \varphi_0\right)$
````

````{topic} Caractéristiques d'un sinusoïde.
On multiplie la fonction complète par$ S_m$, il y a donc une dilatation verticale. L'écartement maximal sera maintenant $2S_m$. On appelle $S_m$ __l'amplitude.__

L'argument du cosinus se réécrit: $\omega ( t + \varphi_0 / \omega )$. On a donc: 
* une dilatation horizontale du sinusoïde d'un facteur $\frac{1}{\omega}$. Ainsi la période du sinusoïde est maintenant $T = \frac{2 \pi}{\omega}$ (et plus $2\pi$). $\omega$ est appelée __pulsation__.
* une translation horizontale de $\Delta t_0 = - \frac{\varphi_0}{\omega}$ (un retard ou une avance suivant le signe de $\varphi_0$). On appelle $\varphi_0$, la __phase à l'origine.__

```{figure} ./images/sinusoide_vm_0.png
:name: fig_sinusoide324
:align: center
Sinusoïde
```

Un sens physique plus approfondi sera donné à ces termes par les suite. On retiendra déjà le passage du cosinus simple à l'expression complète et surtout les effets sur la représentation graphique
````

## Méthode: Calculer le module et l'argument d'un complexe
__Le calcul de l'argument et du module d'un complexe est fondamental en physique__ car nous verrons que l'utilisation des complexes et la détermination de ces deux caractristiques permet l'étude de tout un pan de la physique: l'analyse fréquentielle.


````{admonition} Exercice 
:class: attention

Déterminer le module est l'argument du complexe suivant (x est réel positif):

\begin{equation}
z = \frac{i x}{2 + i x}
\end{equation}
````
````{margin} __A ne pas faire...__
Il ne sert à rien (et ça complique même) d'éliminer la partie imaginaire du dénominateur pour calculer un module ou un argument. On va utiliser les relations très utiles sur le rapport de deux complexes.
````
````{topic} Correction
\begin{equation}
\left\vert z \right\vert = \frac{\left\vert ix \right\vert}{\left\vert 1 +ix \right\vert} = \sqrt{\frac{x^2}{4 + x^2}}
\end{equation}

\begin{equation}
\arg z = \arg (ix) - \arg(2 + ix) = \frac{\pi}{2} - \arg(2 + ix)
\end{equation}

__Méthode à utiliser en physique__: La connaissance du signe du cosinus et de la valeur de la tangente suffit à caractériser l'angle (cf. cercle trigonométrique). On va donc calculer les deux.

```{margin}
Si le cosinus est négatif, l'argument du complexe est dans l'intervale $[\pi/2;3\pi/2]$ et la solution d'une équation $\tan \theta = k$ est donc de la forme $\theta = \pi + \arctan k$.

```
Le cosinus est du même signe que la partie réelle, donc ici, il est positif  donc l'argument de 2 + ix est dans l'intervale $[-\pi/2;\pi/2]$. La solution d'une équation $\tan \theta = k$ est donc de la forme $\theta = \arctan k$.

La tangente s'écrit:
\begin{equation}
\tan \left(\arg (2 + ix)\right) = \frac{\Im(2+ix)}{\Re(2+ix)} = \frac{x}{2}
\end{equation}

La solution est donc: $\arg (2+ix) = \arctan \frac{x}{2}$ donc $\arg(z) = \frac{\pi}{2} -\arctan \frac{x}{2}$
````