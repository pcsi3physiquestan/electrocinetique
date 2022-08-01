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

````{important} __Définition : Source idéale de tension__


```{figure} ./images/elec_gem_ideale.jpg
:name: fig_schema_d_une_source_ideale_de_tension123
:align: center
Schéma d'une source idéale de tension
```


Une source idéale de tension est un dipôle dont la tension est une caractéristique propre du dipôle et ne varie pas, quelque soit l'intensité qui la traverse.

On appelle la tension à ses bornes __force électromotrive (f.e.m.)__



````

````{important} __Définition : Source idéale de courant__


```{figure} ./images/elec_cem_ideale.jpg
:name: fig_schema_d_une_source_ideale_de_courant124
:align: center
Schéma d'une source idéale de courant
```


Une source idéale de courant est un dipôle dont l'intensité est une caractéristique propre du dipôle et ne varie pas, quelque soit la tensionà ses bornes.

On appelle l'intensité qui la traverse __courant électromoteur (c.e.m.)__



````

````{attention}
__Source: dipôle polarisé__


Les sources sont des dipôles polarisés. Il est important de préciser le sens dans lequel est orienté la f.e.m. ou le c.e.m.

````


__Caractéristique statique__  
La caractéristique statique d'une source idéale de tension de fem E est une droite verticale d'équation u = E

La caractéristique statique d'une source idéale de courant de cem I est une droite horizontale d'équation i = I


## Source réelle: Electromoteur


__Comportement réels des sources__  
En pratique, une source de tension ne délivre la fem voulue E qu'à vide, c'est-à-dire quand aucun courant ne sort.

Lorsqu'on commence à demander une intensité en sortie (donc de la puissance), la fem u tend à diminuer.

Expérimentalement, on observe qu'on peut modéliser cette chute par un modèle linéaire: u = E - Ri. C'est le modèle des électromoteurs.


````{important} __Définition : Electromoteur__

Un électromoteur linéaire est une __modélisation__ d'une source donc la relation tension-intensité est:

$u = E - Ri$ ou $i = \eta - G u$

E est la fem (à vide) de l'électromoteur et R sa résistance interne.

$\eta$ est le cem (à vide) de l'électromoteur et G sa conductance interne.

````


__Lien entre les grandeurs__  
On peut passer d'une équation à l'autre puisque les grandeurs $E, \eta, R$ et G peuvent être reliées entre elles.


````{important} __Fondamental : Modélisation de Thévenin d'un électromoteur__


```{figure} ./images/elec_electromoteur.jpg
:name: fig_125
:align: center

```


Un électromoteur peut être modélisé par une source idéale de tension de fem E en série avec une résistance R



````


__Démonstration__  
Comme à chaque fois pour prouver/déterminer l'équivalence de deux dipôles, nous allons exprimer la relation intensité tension. Dans le cas de l'électromoteur, on a déjà $u = E - Ri$

La tension aux bornes du modèle proposé est (la résistance est orientée en convention générateur): $u = E + u_R = E - R i$

On a bien identification des équations d'évolution, donc l'électromoteur est modélisable par le modèle de Thévenin.


````{attention}
__C'est une modélisation__


Le modèle est Thévenin est comme son nom l'indique une modélisation, c'est-à-dire qu'elle permet d'étudier mathématiquement le comportement de la source réelle mais ne traduit pas la composition physique de la source (qui est bien plus complexe).

````

## Méthode: Déterminer un modèle de Thévenin équivalent


Cet exercice propose d'apprendre à montrer qu'un dispositif peut être remplacé par un modèle de Thévenin en déterminant ses caractéristiques. Nous étudierons deux méthodes: l'établissement de l'équation d'évolution comme utilisé précédemment pour la détermination d'un dipôle équivalent et le calcul de deux points particuliers.


````{admonition} Exercice 
:class: attention

Montrer que le circuit ci-dessous est équivalent à un modèle de Thévenin entre les bornes A et B dont on déterminera les caractéristiques.

```{figure} ./images/elec_th_eq_exc_1.png
:name: fig_126
:align: center

```

````

````{dropdown} Correction

On commence par paramétrer le circuit et à bien réfléchir aux grandeurs:
* qu'on doit chercher. Ici on veut exprimer la relation tension-intensité. On va donc chercher u en fonction de i ou i en fonction de u. Pour des raisons totalement arbitraires, on décide chercher u en fonction de i.
* qu'on connaît: la fem E, le cem $I_0$, la valeur de résistance R. L'intensité i devient aussi une grandeur qu'on "connait" puisqu'on veut exprimer u en fonction de i.
* les grandeurs qui restent doivent être éliminées (il n'est même pas utile de les déterminer en fonction des données du problème puisqu'elle ne sont pas utiles à l'étude demandée). En général, ce sont des grandeurs que nous avons introduites, ici $i_1, u_1, i_2$
* On a donc 4 inconnnues ($u, i_1, u_1, i_2$). Il faudra donc quatre équations.

```{figure} ./images/elec_th_eq_exc_2.png
:name: fig_127
:align: center

```

```{dropdown} Remarque

__Orientation des grandeurs__  
On a orienté i et u en convention générateur de manière à pouvoir identifier la relation u(i) à la relation attendue du modèle de Thévenin en convention __générateur__ $u = E_{Th} - R_{Th} i$

On a orienté $i_2$ de cette façon pour que la résistance soit en convention récepteur. Le but est de pouvoir utiliser directement la loi d'Ohm (écrite en convention récepteur) sans se tromper dans les signes. Encore une fois, le choix de la convention étant arbitraire, on aurait pu choisir une convention générateur. Il est judicieux de choisir une convention récepteur, non pas pour des raisons physiques, mais pour ne pas se tromper dans les formules... 

```

On réalise la mise en équation (nous utilisons ici les lois des mailles et des noeuds mais il est vivement conseillé de s'entraîner à cet exercice en appliquant la loi des noeuds en terme de potentiel):

\begin{align}
i_1 + i_0 &= i + i_2\\
E - u_1 - u &= 0
\end{align}
Avec les deux lois d'Ohm $u_1 = R i_1$ et $u = R i_2$ on dispose de 4 équations donc d'autant d'équations que inconnues.


Remarque : __Sur la loi des noeuds__  

```{figure} ./images/elec_th_eq_exc_3.png
:name: fig_128
:align: center
```
La loi des noeuds peut sembler à certains étranges puisque les intensités ne semble pas courir en un noeud. Néanmoins, on rappelle que sur un fil de connexion, le potentiel est identique partout et le point de raccordement du noeud importe alors peu. On a reproduit ci-contre le schéma équivalent au précédent permettant de faire apparaître le noeud où l'on applique la loi de Kirchhoff.


La __règle principale est d'éliminer les grandeurs qui ne nous intéresse pas ET DE GARDER JUSQU'AU BOUT LA GRANDEUR QU'ON VEUT CALCULER.__. Ici, on va éliminer $u_1$ et $i_2$ en utilisant les lois d'Ohm. Il vient :

\begin{align}
i_1 + i_0 &= i + \frac{u}{R}\\
E - R i_1 - u &= 0
\end{align}
En multipliant par R la première équation et en sommant, il vient:

$$
u = \frac{E + R i_0 - R i}{2}
$$
Par identification, on trouve:

\begin{align}
E_{Th} &= \frac{E + R i_0}{2}\\
R_{Th} &= \frac{R}{2}
\end{align}
````

````{dropdown} Correction - Autre méthode
On propose d'utiliser une autre méthode pour déterminer les caractéristiques du modèle de Thévenin équivalent. Le principe est basé sur le fait qu'une caractéristique statique d'un dipôle linéaire est une droite. Il suffit donc de connaître deux points de la droite pour connaître ses caractéristiques.

On va choisir deux points simples à étudier:

* Le cas où l'on impose i = 0 (on parle de coupe-circuit). On cherche u.
* Le cas où l'on impose u = 0 (on parle de court-circuit). On cherche i.

__Cas i = 0__  
La loi des noeuds s'écrit $i_1 + i_0 = i_2 = \frac{u}{R}$

La loi des mailles s'écrit: $E - R i_1 = u$

Une combinaison linéaire pour éliminer $i_1$ donne $E + R i_0 = 2 u$

__Cas u = 0__  
La loi des noeuds s'écrit $i_1 + i_0 = i + i_2 = i$

La loi des mailles s'écrit: $E - R i_1 = u = 0$

Une combinaison linéaire pour éliminer $i_1$ donne $E + R i_0 = R i$


La droite du modèle de Thévenin doit donc passer par les points $(0;\frac{E}{R} + i_0)$ et $(\frac{E + R i_0}{2}; 0)$

On cherche une droite de la forme $u = E_{Th} - R_{Th} i$ passe par les deux point précédents (attention les coordonnées sont (u ; i)).

Une recherche mathématique classique du coefficient directeur donne $R_{Th} = R / 2$.

La valeur de la fem est directement donnée au point i=0.
````
