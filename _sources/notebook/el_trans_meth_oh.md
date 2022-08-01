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
# Oscillateur harmonique
Nous allons étudié ici le cas d'un oscillateur non amorti appelé __oscillateur harmonique.__ Reconnaître un tel oscillateur passe par l'établissement de son équation différentielle caractéristique. Nous verrons ensuite son évolution. Le régime "transitoire" n'en est pas un puisqu'il ne s’atténue pas (mais il ne diverge pas non plus).

Si la mise en équation sera faite sur un circuit électrique particulier, il s'agit d'un système très important car il se retrouve partout en physique (mécanique, mécanique quantique, électromagnétisme... ) et ses caractéristiques générales doivent être maîtrisées pour être adaptée à n'importe quel système.


````{admonition} Exercice 
:class: attention

On considère le circuit suivant (la bobine est idéale). A $t=0$, le condensateur est chargé à $q(t=0) = q_0$ et l'intensité qui le traverse est $i_0$ (en convention récepteur).

```{figure} ./images/elec_meth_oh.png
:name: fig_166
:align: center

```
1. En appliquant la loi des mailles, montrer que l'évolution de la tension aux bornes du condensateur dans le circuit est régit la l'équation: $\frac{\rm{d}U_C^2}{\rm{dt^2}} + \omega_0^2 U_C =0$
1. Si l'on est en régime indépendant du temps, que vaut alors $U_C(t)$?
1. Montrer que la tension $u_C(t)$ va évoluer de manière sinusoïdale et préciser sa pulsation d'oscillation ainsi que sa période d'oscillation.
1. Exprimer complètement $u_C(t)$ avec les conditions initiales données dans l'énoncé.
1. Exprimer l'énergie $E_{el}(t)$ emmagasinée dans le condensateur.
1. Exprimer l'énergie $E_{mag}(t)$ emmagasinée dans la bobine.
1. En déduire l'énergie totale emmagasinée dans le système LC. Commenter son évolution temporelle.
1. Représenter graphiquement les évolutions de$E_{el}$ et $E_{mag}$. Pourquoi parle-t-on d'échange d'énergie entre deux réservoirs ?
1. Calculer l'énergie moyenne stockée dans le condensateur puis l'énergie moyenne stockée dans la bobine.
````

```{admonition} A retenir
:class: tip
* __Equation d'un oscillateur harmonique.__ Un oscillateur harmonique est un système dont les grandeurs suivent une équation d'évolution sous la forme:

\begin{equation}
\frac{\rm{d^2}X}{\rm{dt^2}}(t) + \omega_0^2 X(t) = F(t)
\end{equation}
$\omega_0$ est appelée la __pulsation propre__ de l'oscillateur.

* __Evolution temporelle.__ Un oscillateur harmonique est une oscillateur non amorti sinusoïdal: sans excitation extérieure (solution de l'équation homogène), ses grandeurs ont une évolution temporelle décrite par __un sinusoïde qui ne s'atténue pas__. La pulsation des oscillations est la pulsation propre.

* __Etude énergétique.__ Un oscillateur harmonique est en général constitué de __deux réservoirs d'énergie qui s'échange l'énergie__ de manière périodique.

    * Ici, c'est l'énergie stockée par le condensateur et celle stockée par la bobine. 
    * Dans un oscillateur mécanique (système masse ressort par exemple), l'énergie est échangée entre l'énergie cinétique et l'énergie de rappel élastique (cf. mécanique).
    * Par contre __l'énergie totale reste constante__. Cela explique que les oscillations ne s'atténuent pas.

```