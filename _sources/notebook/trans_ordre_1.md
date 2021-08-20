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
# Caractéristiques d'un système d'ordre 1

On rappelle que dans un système d'ordre 1, les dérivées sont au maximum des dérivées premières des grandeurs. Nous allons voir que le régime transitoire possède toujours la même forme (__exponentielle__) et fait apparaître un __temps caractéristique__ qui gouverne complètement la rapidité du système.

L'étude de la réponse temporelle permettra de montrer qu'il ne peut y avoir de __dépassement__.

Un bilan énergétique sera aussi proposé.

Nous allons présenter des généralités sur les systèmes d'ordre 1 et nous les mettrons en avant sur un exemple coulissant basé sur le circuit suivant :

```{figure} ./images/elec_rc_ordre1.png
:name: fig_167
:align: center

```

L'interrupteur étant en position 1 depuis un temps long, il bascule à t=0 en position 2.

## Système d'ordre 1: Forme canonique

````{admonition} Fondamental : Forme canonique de l'équation différentielle.
:class: important

Pour une grandeur dans un système d'ordre 1, l'équation différentielle se met sous la forme canonique suivante:

\begin{equation}
\frac{\rm{d}X}{\rm{dt}}(t) + \frac{1}{\tau} X(t) = F(t)
\end{equation}
Comme on le verra, $\tau$ est le temps caractéristique du système.

````

````{admonition} Cas du circuit RC pour t > 0. Tension aux bornes de C
:class: attention

La loi des mailles s'écrit: $u_R + u_C = 0 = R i + u_C$.

En utilisant l'équation d'évolution du condensateur, il vient:

\begin{equation}
\frac{\rm{d}u_C}{\rm{dt}}(t) + \frac{1}{RC} u_C(t) = 0
\end{equation}
On a donc $\tau = RC.$

````

## Evolution temporelle

### Système d'ordre 1: Evolution temporelle

````{admonition} Fondamental : Forme temporelle
:class: important

La solution générale de l'équation homogène a pour forme $A e^{-t/\tau}$

On rappelle qu'il faut ensuite déterminer la solution particulière qui va dépendre de la tension en entrée.

````

````{admonition} Cas du circuit RC: Evolution temporelle de la tension uC.
:class: attention

La solution générale est donc $A e^{-t/\tau}$ avec $\tau = RC$.

Le second membre étant nul, il n'y a pas de solution particulière à ajouter.

Il faut déterminer la condition initiale (système d'ordre 1 donc il n'y a qu'une condition initiale).

On peut étudier le système à $t=0^-$ en considérant qu'on est en régime forcé. La seule grandeur continue est la tension aux bornes du condensateur. On va déterminer sa valeur.

Le condensateur étant assmilable à un interrupteur ouvert, l'intensite i est nulle donc la tension aux bornes de la résistance aussi. Il vient $u_C(t=0^-) = E$

Par continuité $u_C(t=0^+) = E$.

La condition initiale permet d'écrire A = E soit:

\begin{equation}
u_C(t) = E \exp^{-t/\tau}
\end{equation}\end{ex}
````

````{admonition} Cas du circuit RC: Evolution temporelle de l'intensité
Pas besoin de tout réétudier. Il suffit d'utiliser la relation $i = C \frac{\rm{d}u_C}{\rm{dt}}$:

\begin{equation}
i(t) = -\frac{E}{R} \exp^{-t/\tau}
\end{equation}\end{ex}

```{dropdown} Remarque

__Discontinuité__  
On remarquera que l'intensité est discontinue.
```
````

### Système d'ordre 1: Temps caractéristique

````{admonition} Fondamental : Temps caractéristique d'un système d'ordre 1
:class: important

La forme générale de la solution de l'équation homogène montre tout de suite que $\tau$ est le temps caractéristique du système.

````

````{admonition} Fondamental : Evolution temporelle: tracé
:class: important

On a représenté ci-dessous l'évolution temporelle (t>0) vers un régime forcé indépendant du temps ainsi que le portrait de phase. On peut en tirer plusieurs informations

```{figure} ./images/elec_ordre1_trans.png
:name: fig_168
:align: center

```

Le temps caractéristique fait office de facteur d'échelle comme on peut le voir. On peut le mesurer de deux manières:

* A $t = \tau$, l'écart entre X(t) et l'état final ($X(t=+\infty)$) vaut 37\% de l'écart entre $X(t=0^+)$ et l'état final.
* Si l'on trace la tangeante à X(t) à un instante $t_1$. Son intersection avec l'asymptote horizontale à $+ \infty$ (donc avec la droite $y = X(+\infty)$ se fait à l'instant $t_1 + \tau$.

````

````{admonition} Cas du circuit RC
```{figure} ./images/elec_ordre1_rc_trans.png
:name: fig_169
:align: center

```

On a représenté la charge et non la tension mais on rappelle que les deux sont proportionnelles.

````

## Etude énergétique

### Bilan de puissance dans un circuit


__Cas du circuit RC: Bilan de puissance__  
Nous ne généralisons pas les conclusions obtenues ici mais présentons une méthode permettant de réaliser un bilan de puissance.

Partons de la loi des mailles: $u_R + u_C = 0$ et multiplions là par i. On obtient des puissances reçues: $p_J(t) + p_C(t) = 0$ avec $p_J(t)$ la puissance perdue par effet Joule dans la résistance et $p_C(t)$ la puissance reçue par le condensateur.

Remarquons que $p_C(t) = - \frac{E^2}{R} \exp^{-\frac{2t}{RC}} < 0$ donc le condensateur fournie de la puissance durant toute l'expérience. Cette puissance fournie$-p_C(t)$ égale la puissance dissipée à chaque instant dans la résistance $p_J(t)$


### Bilan énergétique dans un circuit d'ordre 1


__Energie fournie par le condensateur__  
On peut calculer l'énergie fournie par le condensateur de deux manières: en intégrant la puissance qu'il fournit ou en utilisant la variation d'énergie stockée.

S'il faut savoir faire les deux dans un cas simple comme un circuit d'ordre 1, il vaut mieux privilégier l'utilisation de l'énergie stockée si on a le choix. Ici, l'énergie fournie par le condensateur est:

\begin{equation}
\Delta E_C = E_L(0) - E_L(t=+\infty) = \frac{1}{2}C u_C(t=0)^2 - \frac{1}{2}C u_C(t=+\infty)^2 = \frac{C E^2}{2}
\end{equation}


__Energie dissipée par effet Joule dans R__  
Pour la résistance, on a pas le choix, l'énergie dissipée ne peut se calculer qu'en intégrant la puissance reçue soit:

\begin{equation}
E_J = \int_{t=0}^{t=+\infty} \frac{u_R^2(t)}{R} dt = \int_{t=0}^{t=+\infty} \frac{E^2}{R} \exp^{-\frac{2t}{RC}} dt = \frac{CE^2}{2}
\end{equation}


__Bilan énergétique__  
On observe que l'énergie fournie par le condensateur est entièrement dissipée par effet Joule dans la résistance, ce qui est logique puisque cette correspondance était déjà valable à chaque instant.


## Application à la réponse indicielle d'un circuit RC


Nous allons étudier la réponse indicielle qui permettra de rappeler la méthode pour la recherche de la solution particulière. Il est conseillé de s'entraîner à faire l'exercice avant de regarder les réponses.


````{admonition} Exercice 
:class: attention

On considère toujours le circuit RC mais après un temps long en position 2, l'interrupteur bascule à t=0 en position 1.

1. Déterminer avec peu de calculs l'état final de $u_C(t)$
1. Déterminer l'équation différentielle qui régit l'évolution de $u_C(t)$ puis déterminer $u_C(t)$.
1. En déduire i(t).
1. Réaliser un bilan de puissance et un bilan énergétique sur l'ensemble du circuit.
````

````{dropdown} Correction

 


__Q1. Nouveau régime forcé__  
On peut considérer le système comme stable et le régime forcé sera indépendant du temps car E est constant.

Le condensateur se comporte alors comme un interrupteur ouvert et i=0. Il vient $u_C = E$



__Q2. Mise en équation__  
Cette fois la loi des mailles s'écrit: $E - R i(t) - u_C(t) = 0$. On utilise à nouveau la relation tension-intensité du condensateur, il vient:

\begin{equation}
\frac{\rm{d}u_C}{\rm{dt}}(t) + \frac{1}{RC} u_C(t) = \frac{E}{RC}
\end{equation}
On doit déterminer les conditions initiales. Dans le régime forcé indépendant du temps avant t=0, on cherche la grandeur continue, ici la tension aux bornes du condensateur. Le condensateur se comporte comme un interrupteur ouvert donc l'intensité est nulle et donc $u_C(t=0^-) = u_R(t=0^-) = 0$

Par continuité $u_C(t=0^+) = 0$

La solution générale ESSM est toujours $A \exp^{-t/RC}$

On cherche une solution particulière constante $U_0$. En l'introduisant dans l'équation différentielle, il vient $0 + \frac{U_0}{RC} = \frac{E}{RC}$ soit $U_0 = E$

La solution est donc: $A \exp^{-t/RC} + E$

On utilise la condition initiale qui donne A = -E donc:

\begin{equation}
u_C(t) = E (1 - \exp^{-t/\tau})
\end{equation}


__Q3. Intensité__  
Il suffit de dériver et de multiplier par C:

\begin{equation}
i(t) = \frac{E}{R} \exp^{-t/\tau}
\end{equation}


__Q4. Etude énergétique__  
Bilan de puissance: la loi des mailles $E = u_R + u_C$ multiplié par i donne: $P_E = P_J + P_C$. On pourra remarquer que cette fois $P_C > 0$

On observe que la puissance fournie par le générateur va en partie est stockée par le condensateur et en partie dissipée par la résistance.

Bilan énergétique:

On commence par l'énergie fournie par le générateur: 

\begin{equation}
E_E= \int_{t=0}^{t=+\infty} Ei(t) dt = \int_{t=0}^{t=+\infty} \frac{E^2}{R} \exp^{-\frac{t}{RC}} dt = CE^2
\end{equation}
Ensuite l'énergie dissipée par la résistance: 

\begin{equation}
E_J = \int_{t=0}^{t=+\infty} R i^2(t) dt = \int_{t=0}^{t=+\infty} \frac{E^2}{R} \exp^{-\frac{2t}{RC}} dt = \frac{CE^2}{2}
\end{equation}
Enfin l'énergie stockée par le condensateur: 

\begin{equation}
\Delta E_C = E_C(t=+\infty) - E_C(t=0) = \frac{1}{2}C u_C(t=\infty)^2 - \frac{1}{2}C u_C(t=0)^2 = \frac{C E^2}{2}
\end{equation}

```{dropdown} Remarque

__Charge du condensateur__  
Dans un tel montage, le condensateur reçoit de l'énergie. On parle de __charge__ du condensateur.

Lors d'un nouveau basculement de l'interrupteur vers le régime libre, le condensateur va, comme on l'a vu, perdre son énergie: on parlera de __décharge__ du condensateur.

```

````

