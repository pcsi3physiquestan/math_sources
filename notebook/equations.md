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
# Equations et inéquations

## Résolution d'équations

On rappelle que vous devez pouvoir résoudre des équations simples utilisant des fonctions usuelles et leurs inverses. Il faudra s'entraîner à manipuler de telles équations avec des expressions __littérales__.

### Equation du second degré
Un équation du second degré peut se mettre sous la forme:

\begin{equation}
a x^2 + b x + c = 0
\end{equation}

On ne redonne pas ici la méthode mais il faut pouvoir trouver les solutions d'une telle équation et savoir reconnaître le cas de solutions complexes lorsque le discriminant est négatif.

### Inéquation du second degré
* si a est négatif, le trinôme est négatif à l'extérieur des racines et positif entre les deux.

* si a est positif, le trinôme est positif à l'extérieur des racines et négatif entre les deux.

### Méthode: Résoudre graphiquement une équation f(x)=g(x)
On ne peut pas toujours résoudre analytiquement une équation. On peut par contre toujours la résoudre graphiquement et on peut même obtenir des informations importantes sur le rôle de certains paramètres lors de ce genre de résolution.

````{admonition} Exercice 
:class: attention

Déterminer graphiquement les conditions d'existence de solutions non nulles pour l'équation:

\begin{equation}
x = \frac{mg}{k} \sin(x)
\end{equation}

avec k, m et g strictement positifs.
````

````{dropdown} Résolution graphique
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

````{dropdown} Remarque

On aurait pu garder les fonctions du départ mais dans ce cas, c'est le sinus qui varie en fonction des paramètres. Or il est plus simple de dessiner plusieurs droites de pentes différentes et un seul sinusoïde qu'une droite accompagnée de plusieurs sinusoïdes de tailles différentes. C'est donc un choix purement stratégique pour la résolution.

En physique, dans ce cas la justification graphique suffit. On pourrait faire une démonstration mathématique complète (en utilisant par exemple les dérivées de la différence et le théorème des valeurs intermédiaires) mais une telle démonstration n'est pas attendue en physique.
````


## Systèmes d'équation

### Systèmes d'équations
En physique, il faut bien se poser la question des grandeurs inconnues et des grandeurs cherchées. Il est important lorsqu'on traite un problème:
* de vérifier quelle sont les grandeurs inconnues et leur nombre
* de vérifier qu'on dispose d'autant d'équations que d'inconnues
* d'éliminer __d'abord les inconnues qu'on ne veut pas__ (donc on ne cherche pas à isoler la grandeur qu'on cherche, au contraire).

````{hint}
Privilégier les combinaisons linéaires aux substitutions, surtout pour des systèmes 2*2.
````

### Méthode: Résoudre un système d'équation 2\*2
La méthode proposée est à __privilégier__ à la méthode de substitution. Elle vous semblera peut-être plus complexe au début mais avec l'entraînement elle permet un énorme gain de temps en physique (à moins que le système soit triangulaire et donc en partie déjà résolu !).


````{admonition} Exercice 
:class: attention

Déterminer les solutions du système suivant:

\begin{align*}
    3x + 4y &= 5 \\
    4x - 5y &= 2
\end{align*}
````

````{dropdown} Résolution par combinaison
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

