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

````{margin}
__En physique, il arrive très souvent que ce nombre soit noté j__ (en électronique surtout, pour ne pas confondre avec l'intensité).
````
````{important} __Ecriture complexe__
* On définit le nombre complexe $i$ tel que $i^2 = -1$. Ce nnombre ne fait pas partie du corps des réels.
* Soit $z$ un nombre complexe. On peut toujours écrire $z$ sous la forme: $z = a + i b$ où a et b sont des réelles.
    * a est appelée partie réelle: $a = \Re(z)$
    * b est appelée partie imaginaire: $b = \Im(z)$
```{margin} Equivalence
L'équivalence avec l'écriture cartésienne passe par l'utilisation de la formule: $e^{i\theta} = \cos \theta + i \sin \theta$.
```
* Un nombre de complexe peutse mettre sous la forme: $z = r e^{i \theta}$ où 
    * r est le module $\left\vert z \right\vert$
    * $\theta$ l'argument arg(z) du nombre complexe z.
````

````{important} __Relation entre les écritures__
__Ces relations sont fondamentales en physique et doivent être sues par coeur.__

\begin{align}
	\vert z\vert &= \sqrt{{\Re(z)}^2 + {\Im(z)}^2}\\
	\cos \theta &= \frac{\Re(z)}{\vert z \vert}\\
	\sin \theta &= \frac{\Im(z)}{\vert z \vert}\\
	\tan \theta &= \frac{\Im(z)}{\Re(z)}
\end{align}\end{basic}
````

````{topic} Cas particuliers
Cas d'un réel: $\Im(z) = 0$ et $arg(z) = 0 \textrm{ ou }\pi$ suivant le signe du réel.

Cas d'un imaginaire pur: $\Re(z) = 0$ et $arg(z) = \pm\pi/2$ suivant le signe de la partie imaginaire.
````

## Représentation graphique

````{important} __Plan complexe__
Le plan complexe est un plan muni d'un repère orthonormé $\left (O, \overrightarrow{u}, \overrightarrow{v} \right )$ tel que l'image d'un nombre complexe z est le point M de coordonnées $\left ( \Re(z), \Im(z)\right )$. L'image vectorielle de z est le vecteur $\overrightarrow{OM}$ et z est appelée affixe du point M.

```{figure} ./images/mathematiques_complexes_ecritures.jpg
:name: fig_332
:align: center
```

Le module de z est la longueur du vecteur$\overrightarrow{OM}$ et l'argument de z est l'angle entre ce vecteur et l'axe des abscisses (ou axe des réels).
````

## Opérations sur les complexes
````{important} __Conjugaison__

Soit un complexe z, on définit le complexe conjugué $\overline{z} $ comme le complexe possédant le même module mais un argument opposé. On peut aussi le définir comme celui ayant la même partie réelle et une partie imaginaire opposée.

\begin{equation}
z = r e^{i \theta} = a + i b \Longrightarrow \overline{z} = r e^{-i \theta} = a - i b
\end{equation}\end{defi}
````


````{important} Formulaire
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