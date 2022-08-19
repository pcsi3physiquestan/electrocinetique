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
# Cas passe-bas

````{admonition} Exercice 
:class: attention
1. On considère le circuit RLC série. Déterminer l'expression de la représentation complexe $\underline{u_C}$ de la tension aux bornes du condensateur.
1. Déterminer par une étude haute et basse fréquence la forme canonique compatible puis mettre $\underline{u_C}$ sous cette forme. On déterminera la pulsation $\omega_0$ et le facteur de qualité Q.
1. En déduire l'expression de l'amplitude réelle et du déphasage entre $u_C$ et e en fonction de $Q, \omega_0$ et $e_m$.
1. Montrer que l'amplitude réelle passe par un extremum seulement si $Q > \frac{1}{\sqrt{2}}$. On parle de __résonance__. Déterminer alors la pulsation de résonance, c'est-à-dire la pulsation pour laquelle l'amplitude réelle est maximale.
1. Représenter l'amplitude réelle en fonction de la fréquence pour différentes valeurs de Q.
1. Déterminer les valeurs du déphasage à haute et basse fréquence et représentation le daphasage en fonction de la fréquence.
````

````{important} 
__Bilan : A retenir__

On retiendra:
* les caractéristiques hautes et basses fréquences nécessaires et la forme canonique associées lorsque le système est d'ordre 2.
* la forme générale de la réponse fréquentielle (allure en fonction de la fréquence) en amplitude réelle et en déphasage.
* l'existence d'une __résonance__, c'est-à-dire d'un maximum d'amplitude en fonction de la fréquence/pulsation conditionnée au facteur de qualité: il doit être supérieur à $Q > \frac{1}{\sqrt{2}}$.
* Lorsque la résonance existe, la pulsation de résonance dépend du facteur de qualité.

```{figure} ./images/rlc_tension.jpg
:name: fig_194
:align: center
:width: 75%
```
````

