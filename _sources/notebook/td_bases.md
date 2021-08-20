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
# TD Electrocinétique 1: Bases

## Accumulateurs

````{admonition} Exercice 
:class: attention

On considère le circuit suivant où R est une résistance variable et les fem $E_1$ et $E_2$ sont positives et $E_1 > E_2$. Déterminer suivant les valeurs de R le comportement recepteur ou générateur deux fem.

```{figure} ./images/elec_accumulateur.jpg
:name: fig_111
:align: center
```
````

````{dropdown} Correction

__Réponse (sans justification)__  
Valeur critique de R: $R_{eq} = \frac{R_1 E_1}{E_1 - E_2}$. Pour $R_{eq} < R$, $E_2$ a un comportement récepteur et pour $R_{eq} > R$, $E_2$ a un comportement générateur. $E_1$ a toujours un comportement générateur.
````