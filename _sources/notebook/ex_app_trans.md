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

## Homogénéité

````{admonition} Exercice 
:class: attention

Montrer que les grandeurs RC et L/R sont homogènes à des temps et que la grandeur LC est homogène à un temps au carré.

````

## Conditions initiales et régime permanent

````{admonition} Exercice 
:class: attention

On considère le circuit suivant, l'interrupteur est fermé depuis un temps long. A $t=0$, on ouvre l'interrupteur.

```{figure} ./images/elec_app_ci_rp.png
:name: fig_165
:align: center

```
1. Déterminer le régime permanent pour $ t < 0$.
1. Déterminer le régime permanent atteint pour $t \to \infty$.
1. Déterminer les conditions initiales à $t=0^+$

On déterminera toutes les intensités et les tensions.
````

````{dropdown} Correction

 


__Eléments de réponse (sans justification)__  
Toutes les intensités sont orientées vers le bas.
1. $i_L = -i_E = \frac{E}{R}$ et $i_C = 0$. Les tensions sont toutes nulles sauf pour la résistance de gauche (elle vaut E).
1. Toutes les intensités sont nulles ainsi que toutes les tensions sauf la tension aux bornes de l'interrupteur qui vaut E.
1. $i_L = - i_C = \frac{E}{R}$ et $i_E = 0$. $u_C = 0$ et $u_L = u_R = E$ (à orienter correctement).


````