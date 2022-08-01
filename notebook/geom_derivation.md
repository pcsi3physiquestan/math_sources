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

# Dérivation d'un vecteur
_On va considérer ici un vecteur $\overrightarrow{u}$ qui dépend d'un paramètre $\xi$ (en général il dépendra du temps mais on va ici traiter un cas général). Le but est de pouvoir exprimer la dérivée du vecteur $\overrightarrow{u}$ en fonction des dérivées de ses composantes._

## Dérivée d'un vecteur
Il ne s'agit pas de donner ici une définition complète de la dérivée vectorielle mais de proposer des méthodes de calculs de telles dérivées.

On considère un vecteur $\overrightarrow{u}$ dépendant d'une variable $\xi$. On peut associer à ce vecteur un point M dont les coordonnées dépendent de $\xi$ (ça peut être un vecteur position, un vecteur vitesse... ).

On pourra donc écrire le vecteur dans les différents systèmes de coordonnées:

\begin{align*}
	\overrightarrow{u}(\xi) &= u_x(\xi) \overrightarrow{e_x}(\xi) +  u_y(\xi) \overrightarrow{e_y}(\xi) +  u_z(\xi) \overrightarrow{e_z}(\xi)\\
	\overrightarrow{u}(\xi) &= u_r(\xi) \overrightarrow{e_r}(\xi) + u_{\theta}(\xi) \overrightarrow{e_{\theta}}(\xi) + u_z(\xi) \overrightarrow{e_z}(\xi)\\
	\overrightarrow{u}(\xi) &= u_r(\xi) \overrightarrow{e_r}(\xi) + u_{\theta}(\xi) \overrightarrow{e_{\theta}}(\xi) + u_{\varphi}(\xi) \overrightarrow{e_{\varphi}}(\xi)
\end{align*}

````{attention}
Dans la plupart des cas, la dépendance des vecteurs en $\xi$ est __implicite__. En effet, celà vient du fait que ces vecteurs dépendant implicitement des coordonnées du point M qui dépendent de $\xi$. Il est donc rare de voir le $(\xi)$ derrière ces vecteurs. Il ne faut pourtant pas oublier qu'ils varient.
````

````{topic} __Position du problème.__  
__Dérivée d'une composante.__  
On peut dérivée une composante $u_1(\xi) \overrightarrow{e_1}(\xi)$ comme on dérive un produit. Ainsi:

$$
\frac{\rm{d}}{\rm{d\xi}}\left(u_1(\xi) \overrightarrow{e_1}(\xi)\right) = \frac{\rm{d}u_1}{\rm{d\xi}}(\xi) \overrightarrow{e_1}(\xi) + u_1(\xi) \frac{\rm{d}\overrightarrow{e_1}}{\rm{d\xi}}(\xi)
$$

Comme on l'a dit. En pratique, les vecteurs d'une base ne dépendent explicitement que des coordonnées du point auquel ils sont associées, dans le cas d'une base locale).

* On a en coordonnées cylindriques $\overrightarrow{e_r}(\theta(\xi))$ et $\overrightarrow{e_{\theta}}(\theta(\xi))$

* On a en coordonnées sphériques $\overrightarrow{e_r}(\theta(\xi), \varphi(\xi))$, $\overrightarrow{e_{\theta}}((\theta(\xi), \varphi(\xi)))$ et $\overrightarrow{e_{\varphi}}( \varphi(\xi)))$. 

Il vient qu'on peut réexprimer la dérivée d'un vecteur d'une base comme la dérive d'une composée.

Dans le cas de coordonnées cylindriques par exemple, il vient:

\begin{align*}
	\frac{\rm{d}\overrightarrow{e_r}}{\rm{dt}}(\xi) = \frac{\rm{d}\overrightarrow{e_r}}{\rm{d\theta}}(\theta) \frac{\rm{d}\theta}{\rm{d\xi}}\\
	\frac{\rm{d}\overrightarrow{e_{\theta}}}{\rm{dt}}(\xi) = \frac{\rm{d}\overrightarrow{e_{\theta}}}{\rm{d\theta}}(\theta) \frac{\rm{d}\theta}{\rm{d\xi}}
\end{align*}

Si la dérivée de $\theta$ va dépendre du problème considéré, la dépendance des vecteurs de la base en $\theta$ est toujours la même. On voit donc qu'on doit connaître les dérivées angulaires des vecteurs des bases locales pour pouvoir dériver un vecteur dans une base cylindrique ou sphériques.
````


````{topic} Remarque
__Cas des coordonnées sphériques.__  
Le cas des coordonneés sphériques est une peu particulier car les vecteurs $\overrightarrow{e_r}$ et $\overrightarrow{e_{\theta}}$ dépendant de deux variables. On développera par la suite la notion de dérivée partielle mais on donne déjà les expressions de ces dérivées:

\begin{align*}
	\frac{\rm{d}\overrightarrow{e_r}}{\rm{dt}}(\xi) = \frac{\partial \overrightarrow{e_r}}{\partial \theta}(\theta, \varphi) \frac{\rm{d}\theta}{\rm{d\xi}} + \frac{\partial \overrightarrow{e_r}}{\partial \varphi}(\theta, \varphi) \frac{\rm{d}\varphi}{\rm{d\xi}}\\
	\frac{\rm{d}\overrightarrow{e_{\theta}}}{\rm{dt}}(\xi) = \frac{\partial \overrightarrow{e_{\theta}}}{\partial \theta}(\theta, \varphi) \frac{\rm{d}\theta}{\rm{d\xi}} + \frac{\partial \overrightarrow{e_{\theta}}}{\partial \varphi}(\theta, \varphi) \frac{\rm{d}\varphi}{\rm{d\xi}}\\
	\frac{\rm{d}\overrightarrow{e_{\varphi}}}{\rm{dt}}(\xi) = \frac{\rm{d}\overrightarrow{e_{\varphi}}}{\rm{dt}}(\varphi) \frac{\rm{d}\varphi}{\rm{d\xi}}
\end{align*}

D'un point de vue opératoire, une dérivée partielle se calcule en maintenant l'autre variable constante (comme si c'était un paramètre dans la fonction).
````

````{topic} 
__Cas des coordonnées cartésiennes.__  
Pour les coordonnées cartésiennes, la base étant global, elle ne dépend pas du point M et les vecteurs de la base ne vont donc pas dépendre de $\xi$ (sauf si le repère est mobile, mais cette configuration ne sera pas vue en première année).

Il vient que la dérivée dans un système de coordonnées cartésien (fixe) est:

$$
\frac{\rm{d}\overrightarrow{u}}{\rm{d\xi}} = \frac{\rm{d}u_x}{\rm{d\xi}} \overrightarrow{e_x} +\frac{\rm{d}u_y}{\rm{d\xi}} \overrightarrow{e_y} +\frac{\rm{d}u_z}{\rm{d\xi}} \overrightarrow{e_z}
$$
````

## Dérivées angulaires: Cas cylindriques
On a vu qu'il fallait connaître la dérivée angulaire (par rapport à la coordonnées angulaires) des vecteurs de la base cylindriques. On rappelle que le vecteur $\overrightarrow{e_z}$ ne dépend pas des coordonnées. Pour les deux autres vecteurs on va:

* exprimer ces vecteurs dans une base globale: la base cartésiennes associées
* dériver les expressions par rapport aux angles (ici il n'y a que $\theta$)
* chercher à réexprimer la grandeurs trouvées dans la base cylindriques.

````{margin} Remarque
Le résultat de ces calculs doit être connus par coeur et peut être utilisé directement.
````
__Dérivée du vecteur radiale.__  
\begin{align*}
	&\overrightarrow{e_r} = \cos\theta \overrightarrow{e_x} + \sin \theta \overrightarrow{e_y}\\
	& \Longrightarrow \frac{\rm{d}\overrightarrow{e_r}}{\rm{d\theta}} = -\sin\theta \overrightarrow{e_x} + \cos \theta \overrightarrow{e_y}\\
	& \Longrightarrow \boxed{\frac{\rm{d}\overrightarrow{e_r}}{\rm{d\theta}} = \overrightarrow{e_{\theta}}}
\end{align*}

__Dérivée du vecteur orthoradiale__  
\begin{align*}
	&\overrightarrow{e_{\theta}} = - \sin\theta \overrightarrow{e_x} + \cos \theta \overrightarrow{e_y}\\
	& \Longrightarrow \frac{\rm{d}\overrightarrow{e_{\theta}}}{\rm{d\theta}} = -\cos\theta \overrightarrow{e_x} - \sin \theta \overrightarrow{e_y}\\
	& \Longrightarrow \boxed{\frac{\rm{d}\overrightarrow{e_{\theta}}}{\rm{d\theta}} = -\overrightarrow{e_{r}}}
\end{align*}


## Dérivées angulaires: Coordonnées sphériques
On a vu qu'il fallait connaître la dérivée angulaire (par rapport aux coordonnées angulaires) des vecteurs de la base sphériques. On va:

* exprimer ces vecteurs dans une base globale: la base cartésiennes associées
* dériver les expressions par rapport aux angles.
* chercher à réexprimer la grandeurs trouvées dans la base sphérique.

````{margin} Remarque
Le résultat de ces calculs doit être connus par coeur et peut être utilisé directement.
````
__Dérivée du vecteur azimuthal.__  
\begin{align*}
	&\overrightarrow{e_{\varphi}} = - \sin\varphi \overrightarrow{e_x} + \cos \varphi \overrightarrow{e_y}\\
	& \Longrightarrow \frac{\rm{d}\overrightarrow{e_{\varphi}}}{\rm{d\varphi}} = -\cos\varphi \overrightarrow{e_x} - \sin \varphi \overrightarrow{e_y}\\
	& \Longrightarrow \frac{\rm{d}\overrightarrow{e_{\varphi}}}{\rm{d\varphi}} = -\cos\varphi \left(-\sin \varphi \overrightarrow{e_{\varphi}} + \cos \varphi \cos\theta \overrightarrow{e_{\theta}} + \cos \varphi \sin \theta \overrightarrow{e_r}\right) \\
	&- \sin \varphi  \left(\cos \varphi \overrightarrow{e_{\varphi}} + \sin \varphi \cos\theta \overrightarrow{e_{\theta}} + \sin \varphi \sin \theta \overrightarrow{e_r}\right)\\
	& \Longrightarrow \boxed{\frac{\rm{d}\overrightarrow{e_{\varphi}}}{\rm{d\varphi}} = -\cos\theta \overrightarrow{e_{\theta}} - \sin \theta \overrightarrow{e_r}}
\end{align*}


__Dérivée du vecteur radiale.__  
On rappelle que dériver partiellement par rapport à $\theta$ à $\varphi$ constant signifie que l'on va considérer dans les expressions $\varphi$ comme un paramètre de la fonction et non plus comme une variables (et inversement quand on dérivée par rapport à $\varphi$).

\begin{align*}
	&\overrightarrow{e_{r}} = \cos \varphi \sin \theta \overrightarrow{e_x} + \sin \varphi \sin \theta \overrightarrow{e_y} + \cos \theta \overrightarrow{e_z}\\
	& \Longrightarrow \frac{\partial \overrightarrow{e_r}}{\partial \theta} = \cos \varphi \cos \theta \overrightarrow{e_x} + \sin \varphi \cos \theta \overrightarrow{e_y} - \sin \theta \overrightarrow{e_z}\\
	& \Longrightarrow \boxed{\frac{\partial \overrightarrow{e_r}}{\partial \theta} = \overrightarrow{e_{\theta}}}
\end{align*}
\begin{align*}
	&\overrightarrow{e_{r}} = \cos\varphi \sin \theta \overrightarrow{e_x} + \sin \varphi \sin \theta \overrightarrow{e_y} + \cos \theta \overrightarrow{e_z}\\
	& \Longrightarrow \frac{\partial \overrightarrow{e_r}}{\partial \varphi} = - \sin\varphi \sin \theta \overrightarrow{e_x} + \cos \varphi \sin \theta \overrightarrow{e_y}\\
	& \Longrightarrow \boxed{\frac{\partial \overrightarrow{e_r}}{\partial \varphi} = \sin \theta \overrightarrow{e_{\phi}}}
\end{align*}


__Dérivée du vecteur orthoradiale__  
\begin{align*}
	&\overrightarrow{e_{\theta}} = \cos\varphi \cos \theta \overrightarrow{e_x} + \sin \varphi \cos \theta \overrightarrow{e_y} - \sin \theta \overrightarrow{e_z}\\
	& \Longrightarrow \frac{\partial \overrightarrow{e_{\theta}}}{\partial \theta} = - \cos\varphi \sin \theta \overrightarrow{e_x} - \sin \varphi \sin \theta \overrightarrow{e_y} - \cos \theta \overrightarrow{e_z}\\
	& \Longrightarrow \boxed{\frac{\partial \overrightarrow{e_{\theta}}}{\partial \theta} = -\overrightarrow{e_{r}}}
\end{align*}
\begin{align*}
	&\overrightarrow{e_{\theta}} = \cos\varphi \cos \theta \overrightarrow{e_x} + \sin \varphi \cos \theta \overrightarrow{e_y} - \sin \theta \overrightarrow{e_z}\\
	& \Longrightarrow \frac{\partial \overrightarrow{e_{\theta}}}{\partial \varphi} = - \sin\varphi \cos \theta \overrightarrow{e_x} + \cos \varphi \cos \theta \overrightarrow{e_y}\\
	& \Longrightarrow \boxed{\frac{\partial \overrightarrow{e_{\theta}}}{\partial \varphi} = \cos \theta \overrightarrow{e_{\phi}}}
\end{align*}


## Dérivée d'un vecteur

````{admonition} Exercice 
:class: attention
On considère un point M dont les coordonnées sont dans un repère cylindrique (la base cylindrique est notée ($(\overrightarrow{e_r}, \overrightarrow{e_{\theta}}, \overrightarrow{e_z}))$:

\begin{align*}
	r(t) = e^{3t}\\
	\theta(t) = 3t\\
	z(t) = 3t
\end{align*}

On considère le vecteur $\overrightarrow{u}(t) = r^2 \overrightarrow{e_r} + \sin \theta \overrightarrow{e_{\theta}}$. Déterminer la dérivée du $\overrightarrow{u}$ par rapport au temps.
````

````{topic} Correction
\begin{align*}
	\frac{\rm{d}\overrightarrow{u}}{\rm{dt}}\overrightarrow{u}(t) &= \frac{\rm{d}}{\rm{dt}}\left(r^2 \overrightarrow{e_r} + \sin \theta \overrightarrow{e_{\theta}}\right)\\
	&= \frac{\rm{d}}{\rm{dt}}\left(e^{6t} \overrightarrow{e_r} + \sin 3t \overrightarrow{e_{\theta}}\right)\\
	&= 6 e^{6t} \overrightarrow{e_r} + e^{6t} \frac{\rm{d}\overrightarrow{e_r}}{\rm{d\theta}}\frac{\rm{d}\theta}{\rm{dt}} + 3 \cos 3t \overrightarrow{e_{\theta}} + \sin 3t \frac{\rm{d}\overrightarrow{e_{\theta}}}{\rm{d\theta}}\frac{\rm{d}\theta}{\rm{dt}}\\
	&= 6 e^{6t} \overrightarrow{e_r} + e^{6t} \frac{\rm{d}\theta}{\rm{dt}} \overrightarrow{e_\theta} + 3 \cos 3t \overrightarrow{e_{\theta}} - \sin 3t \frac{\rm{d}\theta}{\rm{dt}} \overrightarrow{e_r}\\
	&= \left(6 e^{6t} - 3 \sin 3t \right) \overrightarrow{e_r} + \left(3 e^{6t} + 3 \cos 3t \right) \overrightarrow{e_{\theta}}
\end{align*}
````
