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
# Activités d'application
Cet exercice d'application directe est à faire à la suite du cours pour vérifier votre compréhension des méthodes. Vous pourrez confronter votre travail avec celui de vos camarades et poser des questions sur cet exercice en classe mais il ne sera pas donné de correction complète.

## Circuit RL

````{admonition} Exercice 
:class: attention

On considère le circuit ci-après. L'interrupteur est depuis un temps long fermé. A $t=0$, il s'ouvre.

```{figure} ./images/elec_ex_ap_rl.png
:name: fig_176
:align: center

```

1. Déterminer l'intensité circulant dans la bobine à $t=0$.
1. Déterminer l'équation différentielle qui régit l'évolution de la bobine.
1. Déterminer $i(t)$ pour $t > 0$
1. Tracer l'évolution temporelle de $i(t)$ et le portrait de de la bobine $(i(t); \frac{\rm{d}i}{\rm{dt}})$.
1. Déterminer l'énergie perdue par la bobine de $t=0$ à $t= + \infty$ et l'énergie perdue par effet Joule dans la résistance. Commenter.
````

````{dropdown} Correction

 


__Eléments de réponse.__  
$\tau = \frac{L}{R}$


````

````{admonition} Exercice 
:class: attention

On considère le même circuit ci-après. L'interrupteur est depuis un temps long ouvert. A $t=0$, il se ferme.

1. Déterminer l'intensité circulant dans la bobine à $t=0$.
1. Déterminer l'équation différentielle qui régit l'évolution de la bobine.
1. Déterminer $i(t)$ pour $t > 0$
1. Tracer l'évolution temporelle de $i(t)$ et le portrait de de la bobine $(i(t); \frac{\rm{d}i}{\rm{dt}})$.
1. Déterminer l'énergie perdue par la bobine de $t=0$ à $t= + \infty$ et l'énergie perdue par effet Joule dans la résistance ainsi que l'énergie fournie par la source idéale de courant. Commenter.

````

## Ordre de grandeurs d'une RLC série

````{admonition} Exercice 
:class: attention

On considère un circuit RLC série. Déterminer les intervalles de valeurs de R permettant d'observer un régime apériodique. un régime critique. un régime pseudo-périodique.

* Quel régime observe-t-on si $RC \gg L/R$?

* Quel régime observe-t-on si $RC \ll L/R$?

````

## Analyse graphique

````{admonition} Exercice 
:class: attention

Pour les graphiques ci-dessous, déterminer:

1. si le régime est pseudo-périodique ou apériodique/critique
1. si le système est stable
1. le sens de parcours du portrait de phase
1. les conditions initiales
1. le novueau régime permanent établi lorsqu'il existe

```{figure} ./images/elec_ex_ap_graphique.png
:name: fig_177
:align: center

```

```{figure} ./images/elec_ex_ap_graphique_2.png
:name: fig_178
:align: center

```

````

## Décrément logarithmique


On veut déterminer le décrément logarithmique. Nous allons utiliser une méthode expérimentale très courante.

On supposera dans tout l'exercice que la valeur finale est $u(t=\infty) = 0$.


````{admonition} Exercice 
:class: attention

* Question préliminaire. Montrer que (n est une entier):
\begin{equation}
\delta = \frac{1}{n}\ln \left( \frac{u(t)}{u(t+nT)}\right)
\end{equation}

* Mesurer pour le signal $u(t)$ ci-dessous les valeurs successives des maxima (au moins 6)
* En déduire des valeurs de $\delta$ pour n allant de 1 à 6 puis une valeur moyenne de $\delta$.

Remarque: En séance de travaux pratiques, on réalisera plutôt une régression linéaire car les différentes mesures de delta dépendent l'une de l'autre.

```{figure} ./images/elec_ex_ap_decrement.png
:name: fig_179
:align: center

```

````

## RLC parallèle

````{admonition} Exercice 
:class: attention

On considère une résistance R, une inductance L et un condensateur C branchés en parallèle.

1. Déterminer le facteur de qualité et la pulsation propre du circuit. Les comparer au cas du RLC série.
1. A quelle condition sur R,L et C observe-t-on un régime pseudo-périodique. Donner alors l'expression générale de l'intensité circulant dans la résistance sans calculer les constantes d'intégration.
1. Vers quoi doit tendre la valeur de R pour qu'on obtienne un oscillateur harmonique ? Commenter.
1. On branche en parallèle de R une source idéale de courant de cem $\eta$. A $t=0$, l'intensité dans la bobine est nulle et la tension aux bornes de C est nulle aussi. Déterminer $i(t)$ l'intensité circulant dans la résistance en régime apériodique.

````

