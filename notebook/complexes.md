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
# Nombres complexes

## Ecriture des complexes

````{admonition} Définition : Nombre complexe i
:class: tip
On définit le nombre complexe $i$ tel que $i^2 = -1$. Ce nnombre ne fait pas partie du corps des réels.

__En physique, il arrive très souvent que ce nombre soit noté j__ (en électronique surtout, pour ne pas confondre avec l'intensité).
````

````{admonition} Définition : Ecriture cartésienne.
:class: tip
Soit $z$ un nombre complexe. On peut toujours écrire $z$ sous la forme: $z = a + i b$ où a et b sont des réelles.

a est appelée partie réelle: $a = \Re(z)$

b est appelée partie imaginaire: $b = \Im(z)$
````

````{admonition} Fondamental : Egalité de complexes
:class: important
Deux complexes sont égaux si et seulement si leur partie imaginaire et réelle sont égales deux à deux.
````

````{admonition} Définition : Ecriture exponentielle.
:class: tip
Un nombre de complexe peutse mettre sous la forme: $z = r e^{i \theta}$ où r estle module $\left\vert z \right\vert$ et $\theta$ l'argument arg(z) du nombre complexe z.

L'équivalence avec l'écriture cartésienne passe par l'utilisation de la formule: $e^{i\theta} = \cos \theta + i \sin \theta$.
````

````{admonition} Fondamental : Relation entre les écritures
:class: important
__Ces relations sont fondamentales en physique et doivent être sues par coeur.__

\begin{align}
	\vert z\vert &= \sqrt{{\Re(z)}^2 + {\Im(z)}^2}\\
	\cos \theta &= \frac{\Re(z)}{\vert z \vert}\\
	\sin \theta &= \frac{\Im(z)}{\vert z \vert}\\
	\tan \theta &= \frac{\Im(z)}{\Re(z)}
\end{align}\end{basic}
````

````{dropdown} Cas particuliers
Cas d'un réel: $\Im(z) = 0$ et $arg(z) = 0 \textrm{ ou }\pi$ suivant le signe du réel.

Cas d'un imaginaire pur: $\Re(z) = 0$ et $arg(z) = \pm\pi/2$ suivant le signe de la partie imaginaire.
````

## Représentation graphique

````{admonition} Définition : Plan complexe
:class: tip
Le plan complexe est un plan muni d'un repère orthonormé $\left (O, \overrightarrow{u}, \overrightarrow{v} \right )$ tel que l'image d'un nombre complexe z est le point M de coordonnées $\left ( \Re(z), \Im(z)\right )$. L'image vectorielle de z est le vecteur $\overrightarrow{OM}$ et z est appelée affixe du point M.

```{figure} ./images/mathematiques_complexes_ecritures.jpg
:name: fig_332
:align: center
```

Le module de z est la longueur du vecteur$\overrightarrow{OM}$ et l'argument de z est l'angle entre ce vecteur et l'axe des abscisses (ou axe des réels).
````

````{admonition} Fondamental : Somme de complexes
:class: important
Soit $z_1$ et $z_2$ deux complexes dont les images vectorielles sont $\overrightarrow{OM_1}$ et $\overrightarrow{OM_2}$. La somme $z = z_1 + z_2$ a pour image la somme vectorielle $\overrightarrow{OM}=\overrightarrow{OM_1}+\overrightarrow{OM_2}$.

On a de plus: $\Re(z)=\Re(z_1)+\Re(z_2)$ et $\Im(z)=\Im(z_1)+\Im(z_2)$.

```{figure} ./images/mathematiques_complexes_somme.jpg
:name: fig_333
:align: center
```

__Attention, les modules et arguments ne se somment pas.__
````

````{admonition} Fondamental : Produit par un complexe de module
:class: important
Soit $z$ tel que $z=r e^{i \theta}$ avec $r$ et $\theta$ réels (donc les modules et arguments de $z$). Soit un complexe $z_0$ de module 1 qui peut donc s'écrire sous la forme $z_0 = e^{i \theta_0}$. Le produit $z_1 = z z_0$ correspond géométriquement à la rotation de l'image de $z$ d'un angle $\theta_0$.

Le module de $z_1$ est donc $r$ et l'argument $\theta + \theta_0$.

```{figure} ./images/mathematiques_complexes_rotation.jpg
:name: fig_334
:align: center
```
````

````{admonition} Fondamental : Multiplication par un réel
:class: important
Soit $z$ tel que $z=r e^{i \theta}$ avec $r$ et $\theta$ réels (donc les modules et arguments de $z$). Soit $k$ un réel. Le produit $z_1 = k z$ correspond géométriquement à la dilatation de l'image de $z$ d'un facteur $k$.

Le module de $z_1$ est donc $kr$ et l'argument reste $\theta$.

```{figure} ./images/mathematiques_complexes_dilatation.jpg
:name: fig_335
:align: center
```
````

## Opérations sur les complexes
````{admonition} Définition : Conjugaison
:class: tip
Soit un complexe z, on définit le complexe conjugué $\overline{z} $ comme le complexe possédant le même module mais un argument opposé. On peut aussi le définir comme celui ayant la même partie réelle et une partie imaginaire opposée.

\begin{equation}
z = r e^{i \theta} = a + i b \Longrightarrow \overline{z} = r e^{-i \theta} = a - i b
\end{equation}\end{defi}
````


````{admonition} Formulaire
:class: important
__Ces relations sont fondamentales en physique et doivent être sues par coeur.__

\begin{align}
    \Re(z_1 + z_2) &= \Re(z_1) + \Re(z_2)\\
    \Im(z_1 + z_2) &= \Im(z_1) + \Im(z_2)\\
    \vert z_1 z_2 \vert &= \vert z_1 \vert \vert z_2 \vert \\
    \arg(z_1z_2) &= \arg(z_1) + \arg(z_2)\\
    \vert \frac{z_1}{z_2} \vert &= \frac{\vert z_1 \vert}{\vert z_2 \vert}\\
    \arg(\frac{z_1}{z_2}) &= \arg(z_1) - \arg(z_2)\\
    \overline{z_1+z_2} &= \overline{z_1}+\overline{z_2}\\
    \overline{z_1 z_2} &= \overline{z_1} \overline{z_2}\\
    \overline{\frac{z_1}{z_2}} &= \frac{\overline{z_1}}{\overline{z_2}}\\
    \left\vert \frac{1}{z} \right\vert &= \frac{1}{\left\vert z \right\vert}\\
    \arg\left(\frac{1}{z}\right) &= - \arg(z)
\end{align}
````
## Méthode: Calculer le module et l'argument d'un complexe
__Le calcul de l'argument et du module d'un complexe est fondamental en physique__ car nous verrons que l'utilisation des complexes et la détermination de ces deux caractristiques permet l'étude de tout un pan de la physique: l'analyse fréquentielle.


````{admonition} Exercice 
:class: attention

Déterminer le module est l'argument du complexe suivant (x est réel positif):

\begin{equation}
z = \frac{1 - i x}{1 + i x}
\end{equation}
````
````{admonition} Attention : A ne pas faire... 
:class: note, dropdown
Il ne sert à rien (et ça complique même) d'éliminer la partie imaginaire du dénominateur pour calculer un module ou un argument. On va utiliser les relations très utiles sur le rapport de deux complexes.
````


````{dropdown} Correction
\begin{equation}
\left\vert z \right\vert = \frac{\left\vert 1 - ix \right\vert}{\left\vert 1 +ix \right\vert} = \frac{\sqrt{1 + x^2}}{1 + x^2} = 1
\end{equation}

Remarque: on utilise ici la méthode générale à connaître mais dans CE cas particuliers, on aura aussi pu remarquer que le numérateur et le dénominateur sont conjugués et ont donc même module.

\begin{equation}
\arg z = \arg (1 - ix) - \arg(1 + ix) = 2 \arg (1 -ix)
\end{equation}

On utilise ici la propriétés des conjugués d'avoir des arguments opposés. Comme on l'a vue avec la résolution des équations trigonométriques, la connaissance du signe du cosinus et de la valeur de la tangente suffit à caractériser l'angle. On va donc calculer les deux.

Le cosinus est du même signe que la partie réelle, donc ici, il est positif  donc l'argument de 1 - ix est dans l'intervale $[-\pi/2;\pi/2]$. La solution d'une équation $\tan \theta = k$ est donc de la forme $\theta = \arctan k$.

La tangente s'écrit:
\begin{equation}
\tan \left(\arg (1 - ix)\right) = \frac{\Im(1-ix)}{\Re(1-ix)} = -x
\end{equation}

La solution est donc: $\arg (1-ix) = -\arctan x$ donc $\arg(z) = -2 \arctan x$
````