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
# Etude d'un circuit linéaire

Pour étudier un circuit linéaire (ie. trouver une ou plusieurs grandeurs du circuit), il existe différentes méthodes:
* Utiliser les lois des noeuds et des mailles combinées (cf. l'[exemple ici](etude_lois))
* Utiliser une(des) loi(s) des noeuds traduites en terme de potentiel (cf. [le même exemple](etude_lois)) 
* Reconnaître et utilisée des ponts diviseurs comme présentés ci-dessous. Cette méthode est souvent combinée avec l'utilisation de résistances équivalentes.



## Pont diviseur de tension

````{important} 
__Pont diviseur de tension__

Considérons N résistances en série dont les résistances sont $\{R_i \vert i \in [\![1;n]\!]\}$ aux bornes de laquelle la tension est u.

```{figure} ./images/elec_resistance_serie.png
:name: fig_131
:align: center
```

L'intensité circulant dans l'ensemble est:

$$
i = \frac{u}{\sum_{i=1}^{i=n} R_i}
$$
Et la tension u se divise dans chaque dipôle. La tension aux bornes de la résistance $R_k$ est:

$$
u_k = \frac{R_k}{\sum_{i=1}^{i=n} R_i} u
$$
````

````{topic} Démonstration  
On peut utiliser l'additivité des tensions: $u = \sum_{i=1}^{i=n} u_k = \sum_{i=1}^{i=n} R_k i = $ d'où l'expression de l'intensité.

De $u_k = R_k i$, on obtient l'expression de la tension.
````

Cf. [cet exemple](pont_div) pour savoir comment repérer un pont diviseur de tension.

## Pont diviseur de courant
````{important} __Pont diviseur de courant__
Considérons N résistances en parallèle dont les conductances sont $\{G_i \vert i \in [\![1;n]\!]\}$ dans laquelle entre une intensité totale i.

```{figure} ./images/elec_resistance_parallele.png
:name: fig_132
:align: center

```

La tension aux bornes de l'ensemble est:

$$
u = \frac{i}{\sum_{i=1}^{i=n} G_i}
$$
Et le courant i se divise dans chaque branche. L'intensité aux bornes de la résistance $R_k$ est:

$$
i_k = \frac{G_k}{\sum_{i=1}^{i=n} G_i} i
$$
````

````{topic} Démonstration  
On peut écrire une loi des noeuds: $i = \sum_{i=1}^{i=n} i_k = \sum_{i=1}^{i=n} G_k u = $ d'où l'expression de la tension.

De $i_k = G_k u$, on obtient l'expression de l'intensité.
````

