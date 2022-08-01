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

# Equations différentielles
````{admonition} Compétences
:class: tip
* Identifier l'ordre d'une équation différentielle
* Résoudre une équation différentielle du premier ordre sans second membre
* Résoudre une équation différentielle du premier ordre avec un second membre constant
* Utiliser l'équation caractéristique d'une équation du second ordre pour trouver la solution générale de l'équation sans second membre.
* Résoudre une équation différentielle du second ordre avec un second membre constant.
* Représenter graphiquement les solutions trouvées à pour une équation d'ordre 1 ou 2.
````

## Equation différentielles linéaire et ordre

````{admonition} __Equation différentielle et ordre.__
:class: note
Une équation différentielle est une équation qui relie une fonction à ses dérivées.

On appelle ordre d'une équation différentielle, le degré le plus haut de la dérivée intervenant dans l'équation différentielle. En physique, on n'apprendra à résoudre analytiquement  des équations linéaires d'ordre 1 ou 2.
````

````{important} __Equation différentielle linéaire__

```{margin}
f(t) peut être une fonction quelconque. n est l'ordre de l'équation.
```
Une équation différentielle est linéaire si elle peut se mettre sous la forme (y(t) est la fonction inconnue) :

\begin{equation}
a_n \frac{\rm{d^n}y}{\rm{dt^n}} (t) + a_{n-1 } \frac{\rm{d^{n-1}}y}{\rm{dt^{n-1}}}(t)  + ... +  a_{1 } \frac{\rm{d^{1}}y}{\rm{dt^{1}}} (t) + a_0 y(t) = f(t)
\end{equation}

````
