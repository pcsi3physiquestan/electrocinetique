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
# Stabilité des systèmes linéaires d'ordre 1 et 2

## Stabilité des systèmes linéaires d'ordre 1 et 2

````{important} __Condition de stabilité des systèmes linéaires d'ordre 1 et 2__
Un système linéaire d'ordre 1 ou 2 est stable si et seulement si les coefficients de __l'équation homogène__ sont tous de même signe.
````

````{topic} __Précaution sur cette propriété__
* Cette propriété n'est valable que pour __des systèmes linéaires d'ordre 1 et 2__. Pour des ordres supérieurs ou pour des systèmes non linéaires, on ne peut conclure.
* Ce sont les coefficients de l'équation homogène qui doivent être de même signe. Si il y a un signe différent dans le second membre, ça n'empêche pas la stabilité du système.
* Ils doivent être de même signe mais pas forcément positifs. Ils peuvent être tous négatifs.
````

````{admonition} Démonstration: Ordre 1
:class: tip
Considérons un système d'ordre 1 dont l'équation s'écrit: $a \frac{\rm{d}X}{\rm{dt}}(t) + b X(t) = F(t)$.

On rappelle que la solution se décomposer en deux parties: une solution générale de l'équation sans second membre et une solution particulière de l'équation avec second membre. On choisit comme solution particulière le régime forcé (par exemple la solution constante si F(t) est une constante). Notons que ce régime forcé ne sera atteint que si le reste de l'expression tend vers 0, soit si la solution générale de l'équation homogène tend vers 0.

Cette solution générale est $A \exp^{- \frac{b}{a}t}$. Elle ne tendra vers 0 (condition de stabilité donc) que si b/a est positif soit si b et a sont __de même signe__.

La réciproque est triviale puisque l'exponentielle tendra vers 0.
````

````{admonition} Démonstration: Ordre 2
:class: tip
Considérons un système d'ordre 2 dont l'équation s'écrit: $a \frac{\rm{d^2}X}{\rm{dt^2}}(t) + b \frac{\rm{d}X}{\rm{dt}}(t) + c X(t) = F(t)$. On rappelle que la stabilité du système nécessite que la solution générale ESSM tend vers 0.

Les solutions de l'équation caractéristiques sont: $r_{1,2} = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$. Distinguons les cas suivant le signe de $\Delta = b^2 - 4ac$.

Si $\Delta > 0$, les deux racines sont réelles et la solution est une somme de deux exponentielles: $A \exp^{r_1 t} + B \exp{r_2 t}$. Il faut donc que les deux racines soient négatives. Ce qui nécessite que $-b/2a < 0$ donc a et b sont de même signe et que $\sqrt{\Delta} < b$ donc $4ac > 0$ soit a et c de même signe.

Si $\Delta \leq 0$, remarquons que $4ac > 0$ donc a et c sont de même signe. De plus, on a une solution de la forme $\exp{- bt/2a} f(t)$ avec f(t) qui est un polynôme ou une fonction sinusoïdale. Dans tous les cas, cette fonction tendra vers 0 si b/a est positif, donc si b et a sont de même signe.

La réciproque est à nouveau triviale.
````

````{topic} Exemples d'équations stables ou instables
| Systèmes stables | Systèmes instables | On ne peut conclure |
|:-:|:-:|:-:|
| $RC\frac{\rm{d^2}X}{\rm{dt^2}} + \frac{\rm{d}X}{\rm{dt}} + \frac{1}{RC} X = - E$ | $RC\frac{\rm{d^2}X}{\rm{dt^2}} \boxed{-} \frac{\rm{d}X}{\rm{dt}} + \frac{1}{RC} X = E$ |  $\frac{\rm{d^3}X}{\rm{dt^3}} + \frac{\rm{d^2}X}{\rm{dt^2}} + \frac{\rm{d}X}{\rm{dt}} + X = E$ |
| $-RC\frac{\rm{d^2}X}{\rm{dt^2}} - \frac{\rm{d}X}{\rm{dt}} - \frac{1}{RC} X = -E $ | $\boxed{RC}\frac{\rm{d^2}X}{\rm{dt^2}} - \frac{\rm{d}X}{\rm{dt}} - \frac{1}{RC} X = -E$ |  $\frac{\rm{d^3}X}{\rm{dt^3}} + \frac{\rm{d^2}X}{\rm{dt^2}} - \frac{\rm{d}X}{\rm{dt}} + X = E$ |
| $\frac{\rm{d^2}X}{\rm{dt^2}} + \frac{R}{L}\frac{\rm{d}X}{\rm{dt}} + \frac{1}{LC} X = \frac{E}{1-\alpha}$ | $\frac{\rm{d^2}X}{\rm{dt^2}} + \frac{R}{L}\frac{\rm{d}X}{\rm{dt}} \boxed{-} \frac{1}{LC} X = \frac{E}{1-\alpha} $ |  $\frac{\rm{d^2}X}{\rm{dt^2}} + \frac{\rm{d}X}{\rm{dt}} + \sin(X) = E$ |

Le grandeurs utilisées sont toutes positives. On a encadré une façon de voir pourquoi le système est instable.

On ne peut pas conclure soit parce que le système est d'ordre strictement supérieur à 2 (deux premiers cas) soit parce qu'il n'est pas linéaire (troisième cas).
````

