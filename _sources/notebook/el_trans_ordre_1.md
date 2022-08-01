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
# Caractéristiques d'un système d'ordre 1
__Dans cette partie et la partie suivante, les résultats sont données mais il faut savoir systématiquement les démontrer avant de les utiliser.__ Un exemple complete d'étude est donné [ici](ex_o1)
## Forme canonique

````{important} __Forme canonique de l'équation différentielle.__
Pour une grandeur dans un système d'ordre 1, l'équation différentielle se met sous la forme canonique suivante:

$$
\frac{\rm{d}X}{\rm{dt}}(t) + \frac{1}{\tau} X(t) = F(t)
$$
Comme on le verra, $\tau$ est le temps caractéristique du système.
````
## Evolution temporelle

````{important} __Forme temporelle__
La solution générale de _l'équation homogène_ a pour forme $A e^{-t/\tau}$
_On rappelle qu'il faut ensuite déterminer la solution particulière qui va dépendre de la tension en entrée._
````

````{important} __Temps caractéristique d'un système d'ordre 1__
La forme générale de la solution de l'équation homogène montre tout de suite que $\tau$ est le temps caractéristique du système.
````

````{important} __Evolution temporelle: tracé__
On a représenté ci-dessous l'évolution temporelle (t>0) vers un régime forcé indépendant du temps ainsi que le portrait de phase. On peut en tirer plusieurs informations

```{figure} ./images/elec_ordre1_trans.png
:name: fig_168
:align: center
```
```{margin}
Ce sont deux méthodes de mesure de $\tau$.
```
Le temps caractéristique fait office de facteur d'échelle comme on peut le voir. On peut le mesurer de deux manières:
* A $t = \tau$, l'écart entre X(t) et l'état final ($X(t=+\infty)$) vaut 37\% de l'écart entre $X(t=0^+)$ et l'état final.
* Si l'on trace la tangeante à X(t) à un instante $t_1$. Son intersection avec l'asymptote horizontale à $+ \infty$ (donc avec la droite $y = X(+\infty)$ se fait à l'instant $t_1 + \tau$.
````

## Etude énergétique
Nous ne généralisons pas les conclusions obtenues ici mais présentons une [méthode permettant de réaliser un bilan de puissance et un bilan d'énergie ici](ex_o1).

