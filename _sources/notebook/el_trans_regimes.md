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
# Régime transitoire et régime forcé

## Régimes de fonctionnement: régime transitoire et régime forcé

````{margin} Système stable
Un système est dit __stable__ si les grandeurs du système ne divergent pas lorsqu'il est laissé à lui-même.
````

````{important} 
__Différents régimes__

```{figure} ./images/elec_force_transitoire.png
:name: fig_147
:align: center
```
Lorsque la grandeur d'entrée varie brusquement pour passer d'une forme à une autre, le système (ses grandeurs) va évoluer durant un temps fini (non nul) pour tendre (s'il est stable) vers un nouveau régime.

* L'évolution entre le régime forcé précédent et le nouveau régime forcé est appelé __régime transitoire.__
* Si le système est __stable__, les grandeurs du systèmes vont tendre vers un état dépendant du système lui-même, de la grandeur considérée et __de la grandeur d'entrée.__ On parle alors de __régime forcé.__

En général, la forme mathématique des grandeurs du système tend à prendre une forme similaire à la forme mathématique de la grandeur d'entrée. 

````

````{topic} Exemples de régimes forcés
* Si la grandeur d'entrée est une tension constante, alors toutes les grandeurs d'un système stable vont tendre vers une valeur constante. Dans ce chapitre, nous nous limiterons principalement à ce type de régime forcé.
* Si la grandeur d'entrée est une tension sinusoïdale, alors toutes les grandeurs d'un système stable vont tendre vers une forme sinusoïdale de même pulsation. Ce sera l'objet du prochain chapitre.
````

````{topic} Observations supplémentaires
* On remarque une discontinuité qui correspond au moment où la grandeur d'entrée change brusquement de valeur. La présence possible de discontinuité impose la recherche de conditions initiales (valeurs à $t = 0^+$) pour pouvoir résoudre les équations mises en jeu (des équations différentielles).
* En général, on atteint pas mathématiquement le nouveau régime forcé car le régime transitoire est un fonction qui __tend vers 0__: elle ne s'annule pas rigoureusement à un moment donné.
    * Il faut donc un critère (temps de réponse) pour décider quand l'écart au nouveau régime forcé est négligeable: ce sera le moment où l'on considère le régime transitoire comme fini. Le critère choisi dépend des besoins en précision du système par exemple. Nous verrons par la suite que l'on peut déterminer un ordre de grandeur de cette durée qu'on appellera temps caractéristique.

````

## Etude d'un circuit en régime forcé indépendant du temps

### Condensateur et bobine en régime indépendant du temps

````{margin}
Justification : $du/dt=0$ en régime indépendant du temps donc $i=0$ pour le condensateur.
````
````{important} __Condensateur en régime indépendant du temps__
```{figure} ./images/elec_c_equiv.png
:name: fig_148
:align: center
```
En régime indépendant du temps, un condensateur est équivalent à un interrupteur ouvert.
````

````{margin}
Justification : $di/dt=0$ en régime indépendant du temps donc $u=0$ pour la bobine.
````
````{important} __Bobine en régime indépendant du temps__
```{figure} ./images/elec_l_equiv.png
:name: fig_149
:align: center
```
En régime indépendant du temps, une bobine est équivalent à un fil.
````

Cf. [cet exercice](etude_rpit) pour utiliser ces propriétés



## Caractéristiques des régimes transitoires (en ligne)

### Etude expérimentale

````{topic} __Réponse indicielle__  
Comme nous le verrons par la suite, le régime transitoire d'un système possède:
* des caractéristiques qui dépendent du contexte extérieur (tension d'entrée) et de la grandeur considérée
* des caractéristiques qui dépendent de l'état initial du système
* __des caractéristiques qui ne dépendant que du circuit considéré__

Un manière d'étudier un système et notamment de déterminer ces caractéristiques propres au système est d'étudier __sa réponse indicielle__, c'est-à-dire sa réponse __à un échelon de tension__.

```{figure} ./images/elec_echelon.png
:name: fig_153
:align: center

```
* Un échelon de tension est un passage brusque d'une tension $E_0$ à une tension $E_1$. Un échelon de tension permet de simuler une brusque variation de la tension d'entrée.
    * Très souvent les échelons étudiés correspondent à un passage de 0 à E.
* Pour simuler un échelon de tension, on utilise très souvent une source E (pile par exemple) et un interrupteur 3 points. 
    * Le basculement de l'interrupteur de 2 vers 1 permet de simuler un échelon.
    * A l'inverse le basculement de 1 et vers 2 simule un __régime libre__, c'est-à-dire un régime __dans lequel toutes les sources sont éteintes.__
```{figure} ./images/elec_basculement.png
:name: fig_154
:align: center
```
````

### Dépassement

````{topic} Dépassement
Si le régime forcé visé est un régime indépendant du temps, on peut s'intéresse à l'existence ou l'absence de dépassement, c'est-à-dire regarder si le signal va dépasser la valeur finale.

En physique, savoir repérer graphiquement l'existence d'un dépassement est suffisant.

```{figure} ./images/elec_depassement.png
:name: fig_155
:align: center

```
````

### Temps caractéristique et temps de réponse

````{topic} Rapidité d'un système
En pratique, les équations mathématiques prévoit qu'on atteint rigoureusement le nouveau régime permanent que lorsque t tend vers l'infini (nous verrons que des exponentielles tendant vers 0 interviennent dans nos systèmes).

On s'intéresse donc au moment où l'écart au régime permanent reste suffisamment faible pour quantifier la rapidité d'un système. On distinguera deux types de temps pour caractériser la rapidité d'un système:
* les __temps de réponse__ basés sur des définitions précises.
* les __temps caractéristiques__ donnant un ordre de grandeur de la rapidité du système.
````

````{sidebar} Du temps de réponse au temps caractéristique
Les temps de réponses dépendent du pourcentage choisi, mais les études montrent que pour un système donné, les temps de réponses __ont toujours le même ordre de grandeur__ quelque soient les conditions initiales ou le pourcentage choisi.

On peut alors, à partir des équations mathématiques, exhiber une grandeur homogène à un temps qu'on appellera __temps caractéristique__ et qui donnera cet ordre de grandeur du temps de réponse du système.
````
````{topic} Temps de réponse (à titre informatif)
Un __temps de réponse à N\%__ est l'écart de temps entre l'instant de la perturbation et l'instant à l'écart entre le signal étudié et le nouveau régime permanent va rester inférieur à (100-N)\% de l'écart initial entre le signal et le nouveau régime permanent.

_Les temps de réponses les plus utilisés sont les temps de réponse à 95\% et à 99\%._
````

Pour voir le lien entre temps de réponse en temps caractéristique, traiter [cet exercice](tr_tc)

## Etude d'un portrait de phase (en ligne)

````{topic} Portrait de phase
Nous avons jusqu'à présent étudier les évolutions graphiquement au moyen des évolutions temporelles. On peut obtenir d'autres informations en utilisant une représentation particulière appelée __portrait de phase__.

```{figure} ./images/elec_portrait_phase_generalite.png
:name: fig_158
:align: center

```

Un portrait de phase est la représentation de la dérivée de la grandeur $\dot u(t)$en ordonnée en fonction de la grandeur $u(t)$. C'est un tracé orienté (temporellement).

On trace par exemple i en fonction de q pour un condensateur. On parle du portrait de phase du condensateur (car i est proportionnelle à $\frac{\rm{d}u}{\rm{dt}}$).
````