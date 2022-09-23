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

## Energétique

````{admonition} Exercice 
:class: attention

On appelle résistance 1/4W, une résistance pouvant dissiper au maximum une puissance P=0.25W. Déterminer, en fonction de R et P la tension maximale qu'on peut mettre à ses bornes et estimer la gamme de valeur de tension pour des résistances usuelles.

````

## Etude d'une source réelle

````{admonition} Exercice 
:class: attention
1. On considère une source réelle modélisable soit par un modèle de Thévenin de fem E et de résistance interne $R_1$, soit par une source idéale de courant $\eta$ en parallèle d'une résistance $R_2$. Montrer que les deux sources sont équivalentes à condition d'avoir $R_1 = R_2$ et $E = R_1 \eta$.
1. On considère une source réelle modélisable soit par un modèle de Thévenin de fem E et de résistance interne $R$. Montrer que la puissance maximale que peut délivrer la source est $\frac{E^2}{4R}$
1. On considère un dipôle D dont la caractéristique est donnée ci-dessous. Déterminer les caractéristiques de sa modélisation de Thévenin.

```{figure} ./images/elec_ex_app_carac_source.png
:name: fig_137
:align: center
```

````

## Résistances équivalentes

````{admonition} Exercice 
:class: attention

On considère le réseau de résistances suivantes. Déterminer la résistance équivalente en déterminant la relation u(i).

```{figure} ./images/elec_ex_app_res_eq.png
:name: fig_138
:align: center
```
````

````{topic} Réponses (sans justification)  
$R_e = \frac{3}{2} R$
````

````{admonition} Exercice 
:class: attention

```{figure} ./images/elec_resistance_iterative.jpg
:name: fig_139
:align: center
```
1. Déterminer R' pour que la résistance équivalente entre A et B soit égale à R' du premier circuit ci-dessus.
1. En déduire la valeur de $U_{n+1}$ dans le second circuit ci-dessus si R' a la valeur déterminée à la question précédente.
1. Quelle est la valeur de la résistance équivalente entre $A_0$ et $B_0$ dans le second circuit?
````

````{topic} Réponses (sans justification)  

1. $R' = \left ( \sqrt{3} - 1\right )R$
1. $U_{n+1} = {\left ( \frac{\sqrt{3} - 1}{\sqrt{3} + 1}\right )}^{n+1} U_0$
1. $R'$
````

## Mise en équation

````{admonition} Exercice 
:class: attention

1. Reprendre le montage du pont de Wheatstone et retrouver la tension $U_{AB}$ en utilisant la loi des noeuds en terme de potentiel.
````

````{admonition} Exercice 
:class: attention

Exprimer le rendement $\eta$ du diviseur de tension représenté sur le circuit ci-dessous (le rapport de la puissance  dissipée dans la résistance de charge R à la puissance  fournie  par la tension E) en fonction de $r_1, r_2$ et $R$

```{figure} ./images/elec_rendement.jpg
:name: fig_141
:align: center
```
````

````{topic} Réponses (sans justification)  

$\eta = R \frac{{\left(\frac{r_1}{r_1 + R}\right)}^2}{\frac{r_1 R}{r_1 + R} + r_2}$
````

