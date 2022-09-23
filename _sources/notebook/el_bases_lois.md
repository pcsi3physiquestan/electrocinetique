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
# Étudier un circuit : les bases

## Lois de Kirchhoff

````{important} 
:class: full-width
* __Loi des mailles__ : La somme des tensions d'une maille est nulle en orientant les tensions dans le même sens.

* __Loi des noeuds__ : L'ensemble des courants entrant dans un noeud est égale à l'ensemble des courant sortant du même noeud.
````

````{sidebar} Remarque

On peut réécrire cette loi en disant que la somme des intensités entrantes est nulle (on compte alors les intensités "sortantes" négativement). On rappelle que les intensités sont des grandeurs algébriques et que leur orientation est arbitraire. On a donc très bien pu orienter une intensité sortante mais où les électrons sortent (i < 0), ce n'est pas faux. Il arrive même que l'intensité change de signe.

````
```{topic} Démonstration
>* Loi des mailles : Il s'agit de l'application de l'additivité des tensions sur une boucle.
>* Loi des noeuds : Dans l'ARQS, il ne peut pas y avoir d'accumulation de charge au niveau du noeud, donc le débit entrant égale le débit sortant.
```
<!-- TODO: Mettre plus tard un exercice sur Kirchoff et loi de noeus pootentiel-->


## Étude énergétique d'un dipôle

_L'étude énergétique consiste à déterminer la puissance instantanée reçue ou fournie par un dipôle au reste du circuit puis en déduire l'énergie reçue ou fournie durant une durée $\Delta t$._

````{topic} Raisonnement
Une telle étude demande:

* de savoir si l'on calcule la puissance qu'il reçoit ou qu'il fournit (l'une étant l'opposée de l'autre) : cela dépendra de la convention d'orientation choisie pour la tension et l'intensité
* de savoir comment la calculer, une expression sera établie en fonction des tensions et intensités.
* de savoir analyser le résultat obtenue : le signe de la grandeur calculée permet de savoir si le dipôle fournit (comportement générateur) ou reçoit (comportement récepteur) de la puissance ainsi calculée.
* de savoir intégrer l'expression établie pour faire des calculs d'énergie.
````

### Convention générateur et récepteur pour un dipôle

````{sidebar} ATTENTION
__Il s'agit d'une convention !__

Il s'agit d'une convention (très mal nommée!), c'est-à-dire qu'on définit arbitrairement l'orientation du dipôle __peu importe qu'il soit réellement un récepteur ou un générateur__. D'ailleurs, nous rencontrerons des dipôles qui se comporteront alternativement comme des générateurs et des récepteurs (source de tension, condensateur, bobine).

Donc __orienter un dipôle qui se comporte comme un générateur en convention récepteur n'est pas faux__ (et l'inverse non plus).

D'ailleurs, on rappelle que les intensités et les tensions sont des grandeurs __algébriques__. Comme nous allons le voir, c'est le signe relatifs de ces deux grandeurs, suivant leur orientation, qui va définir leur __comportement récepteur ou générateur : c'est-à-dire leur tendance à fournir ou recevoir de l'énergie.__
````
````{important} __Convention générateur et récepteur__

* Pour un dipôle D, si l'on oriente l'intensité $I_1$ qui le traverse et la tension $U_1$ à ses bornes dans le même sens, on dit qu'il est orienté __en convention générateur.__

```{figure} ./images/elec_conv_gene.png
:name: fig_101
:align: center

```
* Pour un dipôle D, si l'on oriente l'intensité $I_1$ qui le traverse et la tension $U_1$ à ses bornes en sens contraire, on dit qu'il est orienté __en convention récepteur.__


```{figure} ./images/elec_conv_recep.png
:name: fig_102
:align: center
```
````

### Puissance échangée entre un dipôle et le reste du circuit

````{sidebar} __Caractère algébrique de la puissance échangée__
La puissance échangée, comme toutes les grandeurs en électricité est algébrique. Ainsi, on peut se placer

1. en convention récepteur
1. calculer la puissance échangée $P = ui$
1. trouver une puissance échangée négative

Cela signifie que physiquement, le dipôle fournit l'énergie $\vert P \vert = - ui$ au reste du circuit. Il se __comporte__ donc comme un __générateur__.

Mais avoir choisi une convention récepteur en premier n'est pas faux, puisqu'il s'agit d'un choix arbitraire. __L'important c'est que l'analyse physique soit correcte.__
````
````{important} __Puissance instantanée échangée entre un dipôle et le reste du circuit__

La puissance instantanée échangée entre un dipôle et le reste du circuit a pour expression :

$P = U_1 \times I_1$

avec $U_1$ la tension à ses bornes et $I_1$ l'intensité qui le traverse.

* En convention récepteur, elle correspond à la __puissance que reçoit__ le dipôle du reste du circuit.
* En convention générateur, elle correspond à la __puissance que fournit__ le dipôle au reste du circuit.

````

````{topic} Démonstration (pas à connaître)  
>Néanmoins, il est bon de comprendre le principe de cette démonstration qui pointe vers les études que nous ferons plus tard en mécanique.
>
>On se place du point de vue des charges q qui entrent et sortent du dipôle. Durant une durée $\Delta t$, il entre et sort une quantité de charge $\Delta q = I_1 \Delta t$ soit un nombre de particules chargées $\Delta n = \frac{I_1 \Delta t}{q}$ (en supposant qu'elles ont toutes la même charge q).
>
>
```{figure} ./images/elec_conv_recep_2.png
:name: fig_103
:align: center
```
>__Considérons le cas d'une convention récepteur__ (comme sur le schéma ci-contre) et des charges $q$ positives (le raisonnement est identique pour des charges négatives). Passant de A à B, une charge perd une énergie $E_1 = q (V_A- V_B) = q U_1$. Cette énergie est reçue par le dipôle. Donc l'énergie totale reçue par le dipôle pendant un temps $\Delta t$ est :
>
>$E = \Delta n E_1 = I_1 U_1 \Delta t$.
>
>Il vient que la puissance reçue par le dipôle est $P = \frac{E}{\Delta t} = I_1 U_1$
```{figure} ./images/elec_conv_gene_2.png
:name: fig_104
:align: center
```
>
>__En convention générateur__, l'énergie perdue est toujours $E_1 = q (V_A - V_B) = - U_1$. Il vient donc que la puissance reçue par le dipôle est $P = - I_1 U_1$. Donc la puissance $P = U_1 I_1$ est la puissance fournie par le dipôle.
````

### Comportement générateur et récepteur d'un dipôle

* Le __comportement __d'un dipôle n'est pas arbitraire mais exprime ce qui se passe physiquement dans le circuit. Ce dernier ne peut être choisi arbitrairement (contrairement aux conventions) et doit être déterminer par des calculs (nous en verrons par la suite) ou étude (graphique par exemple). C'est le calcul de la__ puissance échangée__ et l'__étude de son signe__ qui déterminer le __comportement du dipôle__.
* Le __comportement__ d'un dipôle peut changer au cours d'une expérience.


| | Comportement récepteur | Comportement générateur |
|:-:|:-:|:-:|
| Convention générateur | P < 0 | P > 0 |
|Convention récepteur | P > 0 | P < 0 |

_Il est conseillé de chercher à comprendre pourquoi on obtient tel signe à partir de l'interprétation de la puissance échangée établie précédemment._

