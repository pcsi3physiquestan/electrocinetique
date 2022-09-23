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
# Equations dans un même circuit.
````{admonition} Exercice 
:class: attention

On reprend le circuit suivant:

```{figure} ./images/elec_circuit_etude_3.png
:name: fig_162
:align: center
```
1. Déterminer les équations différentielles qui régissent les évolutions de:
    * la tension aux bornes du condensateur
    * l'intensité circulant dans le condensateur
    * l'intensité circulant dans la f.e.m.
2. Comparer ces équations et celle obtenues pour $i_L$. On notera les différences et les ressemblances et on les associera aux différences et ressemblances dans la solution de l'équation.
````

````{admonition} A retenir
:class: tip
On retiendra que:
* l'équation homogène __est la même pour toute les grandeurs d'un même circuit__. 
    * Cela signifie que le temps caractéristique sera le même quelque que soit la grandeur, c'est pourquoi on parle de temps caractéristique __du système__. (_Idem pour $\omega_0$ et $Q$_)
* le second membre dépend de la grandeur.
    * Cela signifie que que la solution particulière __et donc le régime forcé__ sera __différent__ pour chaque grandeur du système.
* Ce sera aussi le cas pour les constantes d'intégration qui dépendront _en plus_ des conditions initiales (contrairement au régime forcé qui ne dépend pas de CI).
````