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
# Dipôles électriques: Généralités
_Les lois de Kichhoff sont insuffisantes. Il faut aussi pouvoir relier tension et intensité.Ces relations dépendront du type de dipôle dans le circuit._

## Point de fonctionnement et caractéristique statique

````{sidebar} __Caractère statique__

Il s'agit d'un ensemble d'états statiques possibles regroupés sur le même graphique. Le système ne passe pas dynamiquement d'un point de fonctionnement à un autre puisque ces points sont établis dans un régime indépendant du temps.

Une caractéristique statique permet simplement de visualiser l'ensemble des états __statiques__ possibles d'un dipôles.
````
````{important} __Point de fonctionnement__
* Un __point de fonctionnement__ d'un dipôle est un couple $(U;I)$ de tension et intensité pouvant exister pour le dipôle en fonctionnement indépendant du temps.
* La __caractéristiques statique__ d'un dipôle est l'ensemble des points de fonctionnement du dipôle.
```{figure} ./images/elec_carac_statique.png
:name: fig_112
:align: center
:width: 40%
Caractéristique statique d'un dipôle
```
````


````{topic} Dépendance vis-à-vis d'un paramètre  
_La caractéristique statique peut dépendre d'un paramètre extérieur._

```{figure} ./images/elec_photodiode.png
:name: fig_caracteristique_statique_d_une_photodiode_113
:align: center
Caractéristique statique d'une photodiode.
```
Exemple: Une thermistance possède une caractéristique statique qui dépend de sa température et une photodiode possède une caractéristique qui dépend de l'éclairement (E). Souvent de tels dipôles sont utilisés comme capteur (de température pour le cas de la thermistance, de luminosité pour la photodiode... )
````

## Typologie des dipôles

````{important} __Dipôle symétrique ou polarisé__
* Un dipôle __symétrique__ est un dipôle dont la caractéristique statique est symétrique par rapport à l'origine (0;0).
    * En conséquence, un dipôle symétrique peut-être branché dans les deux sens sans changer son fonctionnement.
* Un dipôle qui n'est pas symétrique est un dipôle __polarisé__
    * Le sens de branchement d'un dipôle polarisé a son importance.
````

````{important} __Dipôle passif ou actif__
* Un dipôle __passif__ est un dipôle dont la caractéristique passe par l'origine.
* Si la caractéristique ne passe pas par l'origine, on dit que le dipôle est __actif.__
````

## Equation d'évolution

````{margin} __Convention d'orientation__
Souvent, les équations d'évolution sont données (ou à connaître) __avec une certaine convention.__
````
````{important} __Equation d'évolution__
L'intensité qui traverse un dipôle est relié à la tension entre ses bornes par une équation mathématique appelée __équation d'évolution du dipôle__
````

````{topic} Exemples d'équation d'évolution
* Pour une diode, l'équation d'évolution est en convention récepteur: $i(u) = I_0 \left ( \exp ^{u/V_S} - 1\right )$
* Pour une bobine, l'équation d'évolution est en convention récepteur: $u(i) = L \frac{di}{dt}$
````

## Dipôle linéaire

````{important} __Dipôle linéaire__
:class: full-width
Un dipôle est dit __linéaire__ si son équation d'évolution est une équation différentielle linéaire.

$$
a_n \frac{d^n u(t)}{dt^n} + a_{n-1} \frac{d^{n-1} u(t)}{dt^{n-1}} + ... + a_1 \frac{d u(t)}{dt} + a_0 u(t)= b_n \frac{d^n i(t)}{dt^n} + ... + b_1 \frac{d i(t)}{dt} + b_0 i(t) + F(t)
$$
_L'ordre de l'équation différentielle est le rang de la dérivée la plus grande._

* __Circuit linéaire__
Un circuit linéaire est un circuit composé uniquement de composants linéaires.
````

````{sidebar} __Caractéristique statique et évolution temporelle__
Seule la caractéristique statique est une droite. On rappelle qu'il s'agit du regroupement de l'ensemble des états possibles dans __des cicuits__ en régime indépendant du temps.

On peut aussi tracer l'évolution (u(t);i(t)) (on parle de caractéristique dynamique) pour un dipôle __dans un circuit donné.__ Il ne s'agit alors pas nécessairement d'une droite.
````
````{important} __Caractéristique statique des dipôles linéaires__
La caractéristique statique d'un dipôle linéaire est une droite dont l'équation s'écrit $a_0 U - b_0 I = F_0$.
````

````{topic} Démonstration  
Pour déterminer la caractéristique statique, il faut éliminer toute variation temporelle de l'équation d'évolution. Dans l'équation d'évolution d'évolution d'un dipôle linéaire, cela revient à annuler toutes les dérivées temporelles (il ne reste que $a_0 u(t)$ et $b_0 i(t)$) et ne garder que le terme constant de F(t) noté ici $F_0$.

```{dropdown} Remarque
__Dipôles linéaires passifs et actifs__  
* Si $F_0 = 0$ le dipôle est passif. Il est alors aussi symétrique.
* Si $F_0 \neq 0$ il est actif (on parle de __source__).
```
````

