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

# Application: Équations différentielles
_Ces exercices d'application directe sont à faire à la suite du cours pour vérifier votre compréhension des méthodes. Vous pourrez confronter votre travail avec celui de vos camarades et poser des questions sur cet exercice en classe mais il ne sera pas donné de correction complète._

## Equation différentielle linéaire d'ordre 1

````{admonition} Exercice 
:class: attention
Résoudre les équations différentielles suivantes. Si aucune condition initiale n'est donnée, ne pas déterminer les constantes d'intégration.

1. $\frac{\rm{d}y}{\rm{dt}}(t) + 3 y(t) = 0$
1. $\frac{\rm{d}y}{\rm{dt}}(t) - 3 y(t) = 0$ avec $y(0) = 2$
1. $5 \frac{\rm{d}y}{\rm{dt}}(t) + 3 y(t) = 1$ avec $y(1) = 1$
1. $\frac{\rm{d}y}{\rm{dt}}(t) + \frac{\lambda}{m} y(t) = - v_0$ avec $y(0) = 0$
1. $RC \frac{\rm{d}y}{\rm{dt}}(t) + y(t) = E$ avec $y(\alpha RC) = U_0$
````

````{topic} Réponses (sans justification)
1. $y(t) = A e^{-3t}$
1. $y(t) = 2 e^{3t}$
1. $y(t) = \frac{1}{3} + \frac{2}{3}e^{-\frac{3}{5}(t-1)}$
1. $y(t) = \frac{m v_0}{\lambda}\left (e^{-\frac{\lambda}{m}t} - 1\right )$
1. $y(t) = E + (U_0 - E) e^{-\frac{1}{RC}t+\alpha}$
````

## Equation différentielle linéaire d'ordre 2

````{admonition} Exercice 
:class: attention
Résoudre les équations différentielles suivantes. Si aucune condition initiale n'est donnée, ne pas déterminer les constantes d'intégration.

1. $\frac{\rm{d^2}y}{\rm{dt^2}}(t) + 5 \frac{\rm{d}y}{\rm{dt}} (t) + 4 y(t) = 0$ avec $\{y(0) = 0; \frac{\rm{d}y}{\rm{dt}}(0) = 1\}$
1. $LC \frac{\rm{d^2}y}{\rm{dt^2}}(t) + RC \frac{\rm{d}y}{\rm{dt}} (t) + y(t) = E$ avec $\{y(0) = 0; \frac{\rm{d}y}{\rm{dt}}(0) = 0\}$ et $RC < L/R$ (R,L et C sont positifs). _Vous pouvez garder la pseudo-pulsation $\Omega$ dans l'expression finale après avoir donné son expression.
1. $\frac{\rm{d^2}y}{\rm{dt^2}}(t) + \frac{R_a C_b + R_b C_b + R_a C_a}{R_a R_b C_a C_b} \frac{\rm{d}y}{\rm{dt}}(t) + \frac{1}{R_a R_b C_a C_b}y(t) = 0$ avec $\{y(0) = 0; \frac{\rm{d}y}{\rm{dt}}(0) = v_0\}$. On montrera que les racines de l'équation caractéristique sont nécessairement réelles.
````

````{topic} Réponses (sans justification)
1. $y(t) = \frac{1}{3}\left (e^{-t} - e^{-4t} \right )$
1. $y(t) = e^{-\frac{R}{2L}t} \left (- E \cos \Omega t - \frac{RE}{2L \Omega} \sin \Omega t\right ) + E$ avec $\Omega = \sqrt{\frac{1}{LC} - \frac{R^2}{4 L^2}}$
1. $y(t) = \frac{v_0}{-\sqrt{\Delta}}\left (e^{-\frac{(b + \sqrt{\Delta})}{2}t} - e^{-\frac{(b - \sqrt{\Delta})}{2}t} \right )$ avec $\Delta = \sqrt{\frac{{(R_a C_b + R_b C_b + R_a C_a)}^2}{4 {(R_a R_b C_a C_b)}^2} - \frac{1}{R_a R_b C_a C_b}}$ et $b = \frac{R_a C_b + R_b C_b + R_a C_a}{2 R_a R_b C_a C_b}$
````
