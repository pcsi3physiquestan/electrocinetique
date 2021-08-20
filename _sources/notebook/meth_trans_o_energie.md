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
# Etude énergétique

````{admonition} Exercice 
:class: attention

On considère un dipôle RLC série en régime libre.

1. Faire un bilan de puissance. Commenter l'évolution de l'énergie emmagasinée par le dipôle RLC.
1. Dans le cas d'un régime apériodique, exprimer l'évolution de l'énergie emmagasinée dans la bobine et dans le condensateur ainsi que l'énergie totale emmagasinée dans le dipôle RLC.

On considère un dipôle RLC série branché à une source idéale de tension E.

1. Faire un bilan de puissance. Commenter l'évolution de l'énergie emmagasinée par le dipôle RLC.
1. Dans le cas d'un régime pseudo-périodique, exprimer l'évolution de l'énergie emmagasinée dans la bobine et dans le condensateur ainsi que l'énergie totale emmagasinée dans le dipôle RLC.
````

````{dropdown} Correction

 

```{admonition} Fondamental : Bilan de puissance et d'énergie.
:class: important

Dans un dipôle RLC en régime libre, la bobine et le condensateur perdent de la puissance. Elle est intégralement dissipée par effet Joule dans la résistance. L'énergie stockée tend à diminuer jusqu'à 0

Lorsqu'on branche une fem E, la puissance reçue par la bobine et le condensateur correspond à la puissance fournir par E moins celle dissipée par la résistance. Suivant que la résistance dissipe plus d'énergie que ne fournit la fem ou l'inverse, l'énergie stockée tend à augmenter ou diminuer. On finit par tendre vers une énergie stockée uniquement dans le condensateur __(pour CE circuit, pas dans tous les cas)__.

```

````

