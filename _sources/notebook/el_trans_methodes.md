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
# Méthodes d'analyse d'un régime transitoire

Nous avons vu quelques caractéristiques du régime transitoire comme son temps caractéristique ou encore l'étude de régime forcé. L'étude du régime transitoire passe par l'étude de la réponse temporelle qu'il convient de déterminer. Pour cela il faut:

* déterminer l'équation qui régit l'évolution de la grandeur qui nous intéresse. Nous verrons qu'il s'agit d'une équation différentielle et qu'elle possède certaines propriétés importantes
* déterminer les conditions initiales qui permettront de déterminer les constantes d'intégration lors de la résolution. Il faut noter que souvent, ces dernières ne sont pas données mais doivent être déterminées.
* Déterminer l'évolution temporelle (u(t) ou i(t) ou le deux) de la grandeur qui nous intéresse. Cela passe par la résolution de l'équation différentielle établie précédemment en utilisant les conditions initiales.

## Mise en équation
Un exemple de mise en équation est donné [ici](mise_eq). Nous verrons aussi par la suite la mise en équation de circuits RC et RLC série.

(ci)=
## Détermination des conditions initiales

````{margin} Nombre de CI
Le nombre de conditions initiales nécessaire est égale à l'ordre du système.
````
### Continuité des grandeurs

````{topic} Problème de continuité
Comme nous l'avons évoqué précédemment, le système est souvent soumis à une brusque variation de la grandeur d'entrée, souvent modélisée par un échelon.

Cela signifie que la grandeur d'entrée au temps $t_0$ où se produit la perturbation est discontinue. Il vient que les autres grandeurs du système __sont a priori discontinues en $t_0$__.

Pour résoudre ce problème, on va utiliser des grandeurs dont on sait qu'elle sont continues __par propriété__.
````

````{important} __Grandeurs nécessairement continues__
:class: full-width
* La __tension aux bornes d'un condensateur__ est une grandeur nécessairement continue.
* __L'intensité qui circule dans une bobine__ est une grandeur nécessairement continue.
````

```{topic} __Démonstration__  
La dérivée de ces deux grandeurs intervient dans les relations intensité tension de la bobine et du condensateur. Elles sont donc dérivables et donc nécessairement continues.
```

_Une détermination des CI est proposée [ici](eq_ci)._

## Evolution temporelle

__Rappel : Méthode de résolution__  
On rappelle ici la méthode de résolution d'une équation différentielle. Insistons sur le fait que l'ordre de résolution est fondamental.

1. Déterminer à partir de l'équation homogène la solution générale de l'équation sans second membre.
1. Déterminer une solution particulière de l'équation avec second membre. __Ne pas utiliser la méthode de la variation de la constante en physique.__
1. En déduire la solution générale de l'équation avec second membre en sommant les deux fonctions précédentes.
1. Déterminer les constantes d'intégration à partir des conditions initiales.

__Autre études__  
A partir de la solution déterminée précédemment, on peut être amené à:

1. Tracer l'évolution temporelle.
1. Analyser un tracé temporel donné pour l'associer au système ou déterminer certaines caractéristiques (conditions initiales, régime forcé, type de régime pour un circuit d'ordre 2 - cf. suite - ... )
1. Faire un bilan de puissance ou un bilan énergétique en déterminant la puissance reçue/fournie ou l'énergie reçue/fournie par les différents dipôles.
1. ... 

Un exemple est donnée [ici](eq_autre)