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

# Dipôles linéaires actifs

## Sources idéales

````{margin} __Source: dipôle polarisé__
Les sources sont des dipôles polarisés. Il est important de préciser le sens dans lequel est orienté la f.e.m. ou le c.e.m.
````
````{important} 
__Source idéale de tension__
```{figure} ./images/elec_gem_ideale.jpg
:name: fig_schema_d_une_source_ideale_de_tension123
:align: center
Schéma d'une source idéale de tension
```
Une source idéale de tension est un dipôle dont la tension est une caractéristique propre du dipôle et ne varie pas, quelque soit l'intensité qui la traverse.

On appelle la tension à ses bornes __force électromotrive (f.e.m.)__
````

````{important} 
__Source idéale de courant__
```{figure} ./images/elec_cem_ideale.jpg
:name: fig_schema_d_une_source_ideale_de_courant124
:align: center
Schéma d'une source idéale de courant
```
Une source idéale de courant est un dipôle dont l'intensité est une caractéristique propre du dipôle et ne varie pas, quelque soit la tensionà ses bornes.

On appelle l'intensité qui la traverse __courant électromoteur (c.e.m.)__
````


````{topic} Caractéristique statique  
* La caractéristique statique d'une source idéale de tension de fem E est une droite verticale d'équation u = E
* La caractéristique statique d'une source idéale de courant de cem I est une droite horizontale d'équation i = I
````

## Source réelle: Electromoteur

````{topic} Comportement réels des sources  
En pratique, une source de tension ne délivre la fem voulue E qu'à vide, c'est-à-dire quand aucun courant ne sort. Lorsqu'on commence à demander une intensité en sortie (donc de la puissance), la fem u tend à diminuer. Expérimentalement, on observe qu'on peut modéliser cette chute par un modèle linéaire: $u = E - Ri$. C'est le modèle des électromoteurs.
````


````{important} 
__Electromoteur__

Un électromoteur linéaire est une __modélisation__ d'une source donc la relation tension-intensité est:

$$
u = E - Ri
$$
où E est la fem (à vide) de l'électromoteur et R sa résistance interne.
````

````{sidebar} __C'est une modélisation__
Le modèle est Thévenin est comme son nom l'indique une modélisation, c'est-à-dire qu'elle permet d'étudier mathématiquement le comportement de la source réelle mais ne traduit pas la composition physique de la source (qui est bien plus complexe).

````
````{important} 
__Modélisation de Thévenin d'un électromoteur__


```{figure} ./images/elec_electromoteur.jpg
:name: fig_125
:align: center
:width: 25%
```
Un électromoteur peut être modélisé par une source idéale de tension de fem E en série avec une résistance R
````

````{topic} Démonstration  
Comme à chaque fois pour prouver/déterminer l'équivalence de deux dipôles, nous allons exprimer la relation intensité tension. Dans le cas de l'électromoteur, on a déjà $u = E - Ri$

La tension aux bornes du modèle proposé est (la résistance est orientée en convention générateur): $u = E + u_R = E - R i$

On a bien identification des équations d'évolution, donc l'électromoteur est modélisable par le modèle de Thévenin.
````

