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

# Dipôles linéaires passifs

## Résistance ou conducteur ohmique


__Description physique__  
Tout conducteur dissipe de l'énergie par effet Joule (dissipation de l'énergie des électrons par interaction désordonnée avec le cristal du conducteur). Dans une résistance, on cherche à contrôler et augmenter cet effet (qui est très faible voire négligeable dans un fil de connexion).


````{admonition} Définition : Résistance ou conducteur ohmique
:class: tip

Un conducteur ohmique ou résistance est un dipôle dont l'équation d'évolution est __en convention récepteur:__

\begin{equation}
u(t) = R i(t)
\end{equation}
où R est appelée __résistance__. Son inverse $G = 1 / R$ est appelée __conductance__

```{figure} ./images/elec_resistor.jpg
:name: fig_schema_d_une_resistance114
:align: center
Schéma d'une résistance
```

````

## Condensateur


__Description physique d'un condensateur__  
Une capacitance ou un condensateur est un dipôle construit de la manière suivant: deux conducteurs (des plans, des cylindres... ) se font face. Entre les deux, un isolant empêchent le passage des électrons.

Quand les électrons sont mis en mouvement, ils vont se détacher d'un conducteur (qui se charge positivement) et s'accumuler sur l'autre (qui se charge négativement): la différence de charge créé un champ électrique qui peut mettre en mouvement les charges dans l'autre sens: on crée temporairement une source d'énergie qui peut se décharger dans d'autres dipôles.


````{admonition} Définition : Condensateur et capacité
:class: tip


```{figure} ./images/elec_condensateur.jpg
:name: fig_schema_d_un_condensateur115
:align: center
Schéma d'un condensateur
```


Un condensateur (ou capacitance) est un dipôle linéaire passif constitué de deux armatures métalliques dont l'équation d'évolution est:

$q(t) = C u(t)$

où q(t) est la chargée portée par l'armature où pointe la flèche de la tension u(t).

C est appelée capacité du condensateur.



````

````{admonition} Fondamental : Relation intensité-tension
:class: important

En __convention récepteur__, l'équation d'évolution s'écrit aussi:

\begin{equation}
i(t) = C \frac{du}{dt}(t)
\end{equation}\end{basic}


__Démonstration__  
Il suffit de remarque que la quantité de charge ajoutée dq à l'armature où entre l'intensité pendant un temps dt est la quantité de charge qui a transité dans le fil durant le même temps dt (conservation de la charge et ARQS) soit $i(t) = \frac{dq}{dt}(t) = C  \frac{du}{dt}(t)$


````{dropdown} Remarque

__Caractéristique statique__  
La caractéristique statique d'un condensateur est la droite horizontale i = 0.

Le condensateur est donc assimilable à un __interrupteur ouvert__ en régime indépendant du temps.

````

## Bobine idéale et inductance


__Description physique d'une bobine__  
Une bobine est un dipôle dont le fonctionnement est basé sur le phénomène d'induction: un champ magnétique variable engendre un champ électrique. Dans le cas d'une bobine, on enroule beaucoup de fil pour former des spires. L'intensité qui traverse ces spires crée un champ magnétique et si l'intensité est variable, le champ magnétique aussi. Il naît alors une tension aux bornes des spires.


````{admonition} Définition : Bobine ou inductance
:class: tip


```{figure} ./images/elec_bobine.jpg
:name: fig_schema_d_une_bobine116
:align: center
Schéma d'une bobine
```


Une inductance (ou bobine) est un dipôle dont l'équation d'évolution __en convention récepteur__ est:



\begin{equation}
u(t) = L \frac{di}{dt}(t)
\end{equation}\end{defi}
````
```{dropdown} Remarque

__Caractéristique statique__  
La caractéristique statique d'une bobine est une droite d'équation u(t) = 0

En régime indépendant du temps, une bobine est donc __assimilable à un fil__.

```

````{admonition} Complément : Bobine réelle
:class: hint, dropdown


```{figure} ./images/elec_bobine_reelle.png
:name: fig_117
:align: center

```


Dans les bobines, la longueur des fils et l'utilisation de noyau de fer implique des effets résistifs.

On modélise ces effets par une résistance en série avec l'inductance. On trouvera quelque fois une référence à cette modélisation par une valeur de résistance associée à la valeur de l'inductance.

````

## Puissance perdu par effet Joule


__Effet Joule__  
Dans une résistance, la puissance reçue est toujours positive: $p(t) = R i^2(t) = \frac{u^2(t)}{R}$.

Cette puissance est __irrémédiablement__ perdue par le circuit. On parle d'effet Joule.



__Utilisation et problèmes__  
L'effet Joule est autant un problème qu'un intérêt. Dans les chauffages électriques par exemple, il est le principe même de fonctionnement du système.

A l'inverse, dans de nombreux dispositifs électroniques, les résistances sont utilisées pour contrôler les caractéristiques du circuit et l'effet Joule est une effet supplémentaire non voulu qui tend à chauffer les composants au risque de les dégrader.


## Energie stockée dans une bobine ou condensateur

````{admonition} Fondamental : Energie stockée dans un condensateur
:class: important

Lorsqu'on applique une tension u à ses bornes, un condensateur stocke une énergie :

\begin{equation}
E_{el} = \frac{1}{2} C u^2
\end{equation}
````

````{admonition} Fondamental : Energie stockée dans une bobine
Lorsqu'un courant i circule dans une bobine, celle-ci stocke une énergie :

\begin{equation}
E_{mag} = \frac{1}{2} L i^2
\end{equation}\end{basic}
````

__Justification__  
Nous allons montrer que la puissance reçue par la bobine et le condensateur peut se mettre sous la forme $P = \frac{dE}{dt}$. On observe ainsi qu'on peut exprimer la puissance échangée comme une variation d'énergie. Celle-ci correspondra à la variation d'énergie du dipôle.

La puissance reçue par un condensateur s'écrit (on l'oriente en convention récepteur):

\begin{equation}
p(t) = u(t) i(t) = C u(t) \frac{du}{dt}(t) = \frac{d}{dt}\left ( \frac{1}{2} C u^2(t)\right)
\end{equation}
(on a cherche une primitive à la fonction u(t) u'(t)).

La puissance reçue par une bobine s'écrit (on l'oriente en convention récepteur):

\begin{equation}
p(t) = u(t) i(t) = L i(t) \frac{di}{dt}(t) = \frac{d}{dt}\left ( \frac{1}{2} L i^2(t)\right)
\end{equation}
(on a cherche une primitive à la fonction i(t) i'(t)).

On trouve bien les expressions des deux énergies données précédemment.



__Différence entre effet Joule et énergie stockée__  
Il est important de comprendre la différence de traitement entre la résistance et le condensateur (la bobine). Dans le premier cas, l'énergie est perdue et ne peut plus être récupérée par le même processus physique. Dans le cas du condensateur (de la bobine), l'énergie est stockée est peut-être redonnée au circuit.

On pourra faire une analogie avec la différence entre l'énergie perdue par frottements et l'énergie stockée (ou rendue) sous forme d'énergie potentielle de pesanteur.

