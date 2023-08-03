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
# Applications

(tr_tc)=
## Autour du temps caractéristique

````{admonition} Interprétation d'un temps caractéristique 
:class: attention
On considère le signal ci-après.

$$
e_m \exp (- t / \tau)
$$
1. D'après vos connaissances de terminales, quel est le temps caractéristiques ?
2. Déterminer le temps de réponse à N\%. L'exprimer pour N=95 puis pour N=99 et montrer qu'ils sont proportionnels âu temps caractéristiques. Retrouver ainsi une interprétation de ce dernier.
````

````{admonition} Régime apériodique 
:class: attention
On considère le signal suivant:

$$
2 * e_m \exp(-\frac{2t}{T})  - 4 * e_m \exp(-\frac{5t}{T}) + 3 e_m
$$
En comparant les temps caractéristiques des deux exponentielles, déterminer une estimation du temps caractéristique su signal total après avoir préciser l'état final.
````

````{admonition} Homogénéité
:class: attention
Montrer que les grandeurs RC et L/R sont homogènes à des temps et que la grandeur LC est homogène à un temps au carré.
````

## Conditions initiales et régime permanent

````{admonition} Exercice 
:class: attention

On considère le circuit suivant, l'interrupteur est fermé depuis un temps long. A $t=0$, on ouvre l'interrupteur.

```{figure} ./images/elec_app_ci_rp.png
:name: fig_165
:align: center

```
1. Déterminer le régime permanent pour $ t < 0$.
1. Déterminer le régime permanent atteint pour $t \to \infty$.
1. Déterminer les conditions initiales à $t=0^+$

On déterminera toutes les intensités et les tensions.
````

````{topic} Eléments de réponse (sans justification)
>Toutes les intensités sont orientées vers le bas.
>1. $i_L = -i_E = \frac{E}{R}$ et $i_C = 0$. Les tensions sont toutes nulles sauf pour la résistance de gauche (elle vaut E).
>1. Toutes les intensités sont nulles ainsi que toutes les tensions sauf la tension aux bornes de l'interrupteur qui vaut E.
>1. $i_L = - i_C = \frac{E}{R}$ et $i_E = 0$. $u_C = 0$ et $u_L = u_R = E$ (à orienter correctement).
````

_Point utile pour cet exercice_
* _$\Longrightarrow$ [Conditions initiales](ci)._
* _$\Longrightarrow$ [Régime indépendant du temps](rpit)._


## Circuits d'ordre 1 et 2
````{admonition} Circuit RL 
:class: attention

On considère le circuit ci-après. L'interrupteur est depuis un temps long fermé. A $t=0$, il s'ouvre.

```{figure} ./images/elec_ex_ap_rl.png
:name: fig_176
:align: center
```

1. Déterminer l'intensité circulant dans la bobine à $t=0$.
1. Déterminer l'équation différentielle qui régit l'évolution de la bobine.
1. Déterminer $i(t)$ pour $t > 0$
1. Tracer l'évolution temporelle de $i(t)$ et le portrait de de la bobine $(i(t); \frac{\rm{d}i}{\rm{dt}})$.
1. Déterminer l'énergie perdue par la bobine de $t=0$ à $t= + \infty$ et l'énergie perdue par effet Joule dans la résistance. Commenter.
````

````{topic} Eléments de réponse
>$\tau = \frac{L}{R}$
````

````{admonition} Circuit RL bis
:class: attention

On considère le même circuit. L'interrupteur est depuis un temps long ouvert. A $t=0$, il se ferme.
1. Déterminer l'intensité circulant dans la bobine à $t=0$.
1. Déterminer l'équation différentielle qui régit l'évolution de la bobine.
1. Déterminer $i(t)$ pour $t > 0$
1. Tracer l'évolution temporelle de $i(t)$ et le portrait de de la bobine $(i(t); \frac{\rm{d}i}{\rm{dt}})$.
1. Déterminer l'énergie perdue par la bobine de $t=0$ à $t= + \infty$ et l'énergie perdue par effet Joule dans la résistance ainsi que l'énergie fournie par la source idéale de courant. Commenter.
````

````{admonition} Cas extrêmes 
:class: attention
On considère un circuit RLC série. Déterminer les intervalles de valeurs de R permettant d'observer un régime apériodique. un régime critique. un régime pseudo-périodique.

* Quel régime observe-t-on si $RC \gg L/R$?
* Quel régime observe-t-on si $RC \ll L/R$?
````

````{admonition} Etude graphique 
:class: attention
Pour les graphiques ci-dessous, déterminer:
1. si le régime est pseudo-périodique ou apériodique/critique
1. si le système est stable
1. le nouveau régime permanent établi lorsqu'il existe

```{figure} ./images/elec_ex_ap_graphique.png
:name: fig_177
:align: center
```
````

````{admonition} Décrément logarirthmique 
:class: attention
* Question préliminaire. Montrer que (n est une entier):

$$
\delta = \frac{1}{n}\ln \left( \frac{u(t)}{u(t+nT)}\right)
$$

* Mesurer pour le signal $u(t)$ ci-dessous les valeurs successives des maxima (au moins 6)
* En déduire des valeurs de $\delta$ pour n allant de 1 à 6 puis une valeur moyenne de $\delta$.

Remarque: En séance de travaux pratiques, on réalisera plutôt une régression linéaire car les différentes mesures de delta dépendent l'une de l'autre.

```{figure} ./images/elec_ex_ap_decrement.png
:name: fig_179
:align: center
```
````

````{admonition} RLC parallèle 
:class: attention
On considère une résistance R, une inductance L et un condensateur C branchés en parallèle.
1. Déterminer le facteur de qualité et la pulsation propre du circuit. Les comparer au cas du RLC série.
1. A quelle condition sur R,L et C observe-t-on un régime pseudo-périodique. Donner alors l'expression générale de l'intensité circulant dans la résistance sans calculer les constantes d'intégration.
1. Vers quoi doit tendre la valeur de R pour qu'on obtienne un oscillateur harmonique ? Commenter.
1. On branche en parallèle de R une source idéale de courant de cem $\eta$. A $t=0$, l'intensité dans la bobine est nulle et la tension aux bornes de C est nulle aussi. Déterminer $i(t)$ l'intensité circulant dans la résistance en régime apériodique.
````