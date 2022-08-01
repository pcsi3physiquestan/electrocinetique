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
# Caractéristiques d'un système d'ordre 2

On rappelle que dans un système d'ordre 2, les dérivées sont au maximum des dérivées secondes des grandeurs. Nous allons voir que le régime transitoire possède trois régimes possibles suivant les valeurs des composantes du circuit. On pourra se ramener pour déterminer le type de régime (__apériodique, pseudo-périodique ou critique__) à étudier la valeur d'un paramètre : __le facteur de qualité__ (ou de manière équivalente le coefficient d'amortissement).

L'étude de la réponse temporelle permettra de montrer qu'il peut y avoir des __dépassement__ et que cette fois __la rapidité du système dépend du type de régime__. Nous verrons notamment dans une activité que les régimes les plus rapides sont les régimes __proches du régime critique__.

Nous apprendrons aussi à étudier plus particulièrement les caractéristiques de chaque régime, notamment du régime pseudo-périodique (au moyen du __décrément logarithmique__ pour ce dernier) et nous verrons comment distinguer ce régime des autres de manière graphique.

Un bilan énergétique sera aussi proposé.

Nous allons présenter des généralités sur les systèmes d'ordre 2 et nous les mettrons en avant sur un exemple coulissant basé sur le circuit suivant (appelé circuit RLC série en régime libre) :

```{figure} ./images/elec_circuit_rlc_serie.png
:name: fig_170
:align: center

```

Cette fois, on suppose les conditions initiales connues à t=0 :

\begin{align}
i(t=0) &= i_0\\
u_C(t=0) &= 0
\end{align}

## Système d'ordre 2: Différents régimes de fonctionnement

### Système d'ordre 2: Forme canonique

````{important} __Fondamental : Forme canonique des systèmes d'ordre 2__

L'équation différentielle qui régit l'évolution d'un système d'ordre 2 peut se mettre une des formes suivantes:

\begin{align}
\frac{\rm{d^2}X}{\rm{dt^2}}(t) + \frac{\omega_0}{Q} \frac{\rm{d}X}{\rm{dt}}(t) + \omega_0^2 X(t) = F(t)\\
\frac{\rm{d^2}X}{\rm{dt^2}}(t) + 2 \xi \omega_0 \frac{\rm{d}X}{\rm{dt}}(t) + \omega_0^2 X(t) = F(t)
\end{align}
On appelle

* $Q$: le facteur de qualité du système
* $\xi$: le coefficient d'amortissement du système
* $\omega_0$: la pulsation propre du système

````

````{admonition} Exercice Cas du circuit RLC série: La tension uC
:class: attention

On peut appliquer une loi des mailles: $u_L + u_R + u_C = 0$ soit $L \frac{\rm{d}i}{\rm{dt}} + Ri + u_C = 0$. Il reste à utiliser $i = C \frac{\rm{d}u_C}{\rm{dt}}$, il vient en organisant):

$$
\frac{\rm{d^2}u_C}{\rm{dt^2}} + \frac{R}{L}\frac{\rm{d}u_C}{\rm{dt}} + \frac{1}{LC} u_C= 0
$$
Il reste à identifier les facteurs:

\begin{align*}
\omega_0^2 &= \frac{1}{LC} &\Longrightarrow& &\omega_0 &= \frac{1}{\sqrt{LC}}\\
\frac{\omega_0}{Q} &= \frac{R}{L} &\Longrightarrow& &Q &= \frac{1}{R}\sqrt{\frac{L}{C}}
\end{align*}\end{ex}
````

````{admonition} Anciennes équations
:class: hint
Il est conseillé d'essayer de mettre sous forme canonique l'équation trouvée dans le chapitre précédent à titre d'entraînement.

Il est aussi conseillé de vérifier l'homogénéité des résultats et leur cohérence physique, même quand cela n'est pas fait dans le cours.
````

### Système d'ordre 2: type de régime

````{important} __Fondamental : Type de régimes__

La forme mathématique correspondant à la solution dépend de la valeur du facteur de qualité Q (ou du coefficient d'amortissement $\xi$) car ce dernier influe sur la valeur du discriminant de l'équation caractéristique $\Delta$. A chaque expression différente correspond un type de régime:
|  | $\Delta$ | Q | $\xi$ | Forme ESSM |
|:-|:-:|:-:|:-:|-:|
| Régime apériodique | > 0 | < 1/2 | > 1 | $A \exp{r_1 t} + B \exp{r_2 t}$ |
| Régime critique | = 0 | = 1/2 | = 1 | $\exp{r_0 t} \left ( A t + B\right )$ |
| Régime pseudo-périodique | < 0 | > 1/2 | < 1 | $\exp{\lambda t} \left ( A \cos(\Omega t ) + B \sin(\Omega t ) \right )$ |

On rappelle que :

* $r_1$ et $r_2$ sont les solutions de l'équation caractéristiques
* $r_0$ est la solution double lorsque le discriminant est nul
* $\lambda$ et $\Omega$ sont respectivement la partie réelle de $r_1$ et $r_2$ et la partie imaginaire (en valeur absolue) de $r_1$ et $r_2$ lorsque le discriminant est négatif. On appelle $\Omega$ __la pseudo-pulsation__ du système.

````

````{admonition} Relation entre les paramètres
:class: hint
Il est conseillé de s'entraîner à exprimer les paramètres précédents en fonction de $\omega_0$ et Q (ou $\omega_0$ et $\xi$).
````

## Système d'ordre 2 : Régime apériodique

### Régime apériodique: Solution analytique


__Solution de l'équation homogène__  
On rappelle que la solution de l'équation homogène dans le cas où $\Delta > 0$, c'est-à-dire $Q < 1/2$ (ou $\xi > 1$ est:

$$
X(t) = A \exp^{r_1 t} + B \exp^{r_2 t}
$$
avec:

\begin{align*}
r_1 = - \frac{\omega_0}{2Q} + \sqrt{\frac{\omega_0^2}{4Q^2} - \omega_0^2}\\
r_2 = - \frac{\omega_0}{2Q} - \sqrt{\frac{\omega_0^2}{4Q^2} - \omega_0^2}
\end{align*}


__Analyse des expressions__  
Remarquons que dans le cas où les coefficients sont positifs, les deux racines sont négatives: on retrouve le principe de stabilité du système.

Ces racines (la moins grande) seront aussi associées au temps caractéristiques qui dépend donc de $\omega_0$ et de Q.

On pourrait montrer (HP) qu'une telle expression ne peut avoir qu'un seul extremum local (ou 0).


````{admonition} Exemple de tracés temporels et portrait de phase
:class: note
```{figure} ./images/elec_ordre2_aperiodique.png
:name: fig_171
:align: center

```

````

````{admonition} Exemple : Cas du RLC série: Détermination complète
:class: attention

On se propose de rechercher les constantes d'intégration dans le cas particuliers du RLC série en régime libre. (Il est conseillé de s'entraîner à le faire seul avant de regarder la réponse).

On a les expressions:

\begin{align*}
u_C(t) &= A \exp^{r_1 t} + B \exp^{r_2 t}\\
i(t) = C \frac{\rm{d}u_C}{\rm{dt}} &= C A r_1 \exp^{r_1 t} + C B r_2 \exp^{r_2 t}
\end{align*}
soit les conditions initiales:

\begin{align*}
u_C(t=0) &= A + B = 0 \Longrightarrow A = - B\\
i(t=0) &= C (r_1 - r_2) A = i_0 \Longrightarrow A = \frac{i_0}{C (r_1 - r_2)}
\end{align*}
Il vient les expressions:

\begin{align*}
u_C(t) &= \frac{i_0}{C (r_1 - r_2)} \left (\exp^{r_1 t} -  \exp^{r_2 t}\right ) \\\
i(t) = C \frac{\rm{d}u_C}{\rm{dt}} &= \frac{Ci_0}{C (r_1 - r_2)} \left ( r_1 \exp^{r_1 t} - r_2 \exp^{r_2 t} \right)
\end{align*}
````

## Régime critique

### Régime critique: Solution analytique


__Solution de l'équation homogène__  
On rappelle que la solution de l'équation homogène dans le cas où $\Delta = 0$, c'est-à-dire $Q = 1/2$ (ou $\xi = 1$ est:

$$
X(t) = \exp^{r_0 t} \left ( At + B\right)
$$
avec:

$$
r_0 = - \frac{\omega_0}{2Q} = - \omega_0
$$


__Analyse des expressions__  
Remarquons que dans le cas où les coefficients sont positifs, la racine double est négative: on retrouve le principe de stabilité du système.

Cette racine sera aussi associée au temps caractéristiques qui dépend donc de $\omega_0$ et de Q.

On pourrait montrer (HP) qu'une telle expression ne peut avoir qu'un seul extremum local (ou 0).

````{admonition} Exemple de tracés temporels et portrait de phase
:class: note
Remarquons qu'il y a beaucoup de similarités avec le régime apériodique en terme de tracé. Pris séparément, on ne peut pas savoir si un tel tracé vient d'un régime apériodique ou critique.

Nous verrons en activité un moyen de comparer les deux tracés (quand on a les deux).

```{figure} ./images/elec_ordre2_critique.png
:name: fig_172
:align: center

```

````

````{admonition} Exercice Cas du RLC série : Détermination complète
:class: attention

On se propose de rechercher les constantes d'intégration dans le cas particuliers du RLC série en régime libre. (Il est conseillé de s'entraîner à le faire seul avant de regarder la réponse).

On a les expressions:

\begin{align*}
u_C(t) &= \exp^{r_0 t} \left ( At + B\right)\\
i(t) = C \frac{\rm{d}u_C}{\rm{dt}} &= C \exp^{r_0 t} \left ( r_0 A t + r_0 B + A\right)
\end{align*}
soit les conditions initiales:

\begin{align*}
u_C(t=0) &= B = 0\\
i(t=0) &= C A = i_0 \Longrightarrow A = \frac{i_0}{C}
\end{align*}
Il vient les expressions:

\begin{align*}
u_C(t) &= \frac{i_0}{C}\exp^{\omega_0 t} t\\
i(t) = C \frac{\rm{d}u_C}{\rm{dt}} &= i_0 \exp^{\omega_0 t} \left ( \omega_0 t + 1\right)
\end{align*}
````

## Régime pseudo-périodique

### Régime pseudo-périodique: Solution analytique


__Solution de l'équation homogène__  
On rappelle que la solution de l'équation homogène dans le cas où $\Delta < 0$, c'est-à-dire $Q > 1/2$ (ou $\xi < 1$ est:

\begin{align*}
X(t) &= \exp^{-\lambda t}\left( A \sin{\Omega t} + B \cos{\Omega t}\right)\\
&= \exp^{-\lambda t}\left( C \sin{(\Omega t + \phi)} \right)\\
\end{align*}
avec:

\begin{align*}
\lambda &= Re(r_{1,2}) = - \frac{\omega_0}{2Q}\\
\Omega &= \left\vert Im(r_{1,2}) \right\vert = \omega_0 \sqrt{1 - \frac{1}{4Q^2}}
\end{align*}


__Analyse des expressions__  
Remarquons que dans le cas où les coefficients sont positifs, le coefficient de l'exponentielle (issue de la partie réelle des racines) est négatif: on retrouve le principe de stabilité du système.

Ce coefficient (la moins grande) sera aussi associé au temps caractéristiques qui dépend donc de $\omega_0$ et de Q.

Nous étudierons plus en détail la forme temporelle.

````{admonition} Cas du RLC série : Détermination complète
:class: note
On se propose de rechercher les constantes d'intégration dans le cas particuliers du RLC série en régime libre. (Il est conseillé de s'entraîner à le faire seul avant de regarder la réponse).

On a les expressions:

\begin{align*}
u_C(t) &= \exp^{-\lambda t}\left( A \sin^{\Omega t} + B \cos^{\Omega t}\right)\\
i(t) = C \frac{\rm{d}u_C}{\rm{dt}} &= C \exp^{-\lambda t}\left( \left(-\lambda A - \Omega B\right) \sin^{\Omega t} + \left(-\lambda B + \Omega A\right) \cos^{\Omega t}\right)
\end{align*}
soit les conditions initiales:

\begin{align*}
u_C(t=0) &= B = 0\\
i(t=0) &= C \Omega A = i_0 \Longrightarrow A = \frac{i_0}{C \Omega}
\end{align*}
Il vient les expressions:

\begin{align*}
u_C(t) &= \exp^{-\lambda t}\left( \frac{i_0}{C \Omega} \sin^{\Omega t}\right )\\
i(t) &= \exp^{-\lambda t}\left( -\lambda \frac{i_0}{\Omega} \sin^{\Omega t} + i_0 \cos^{\Omega t} \right)
\end{align*}\end{ex}
````

````{admonition} Vérification de résultats
:class: hint
Homogénéité : On pourra observer que $\lambda$ et $\Omega$ sont de même unité ($s^{-1}$) et que $C \Omega$ est bien homogène à R (utiliser le fait que RC est homogène à un temps).
````

### Régime pseudo-périodique: Tracé temporelle


__Tracé temporelle__  
L'expression $X(t) = \exp^{-\lambda t}\left( D \sin^{\Omega t + \phi} \right)$ permet de dessiner facilement l'évolution de X(t) en régime pseudo-périodique.

En effet, on remarque qu'il s'agit d'un signal sinsoïdal de pulsation $\Omega$ ou plutôt __pseudo-sinusoïdal__ car l'amplitude décroît de manière exponentielle.

Pour représenter X(t), il faut d'abord représenter son __enveloppe exponentielle__: $D \exp^{- \frac{\omega_0 t}{2Q}}$. On représente alors à l'intérieur de l'enveloppe un sinusoïde (dont l'amplitude décroît) de __pseudo-période__ $T = \frac{2 \pi}{\Omega}$.

```{figure} ./images/elec_ordre2_pseudoperiodique_temporel.png
:name: fig_173
:align: center

```


````{attention}
__Pseudo-période et période propre__


Il ne faut pas confondre la pseudo-période qu'on peut obtenir d'un tracé temporel et qui est reliée à la pseudo-pulsation et la période propre, reliée à la pulsation propre et qui n'apparaît pas directement dans les tracés temporel.

La période propre, comme la pulsation propre est un élément caractéristique issu de la forme canonique de l'équation : $T_0 = \frac{2\pi}{\omega_0}$.

A l'inverse, la pseudo-période n'intervient pas dans la mise sous forme canonique mais apparaît dans les mesures expérimentales qu'on peut être amené à faire sur un système en régime pseudo-périodique.

Pour relier les deux, il faut le facteur de qualité.

````


__Temps caractéristisque__  
L'analyse précédente permet de déterminer assez simplement le temps caractéristique du système. En effet, c'est l'exponentielle décroissante qui gouverne l'évolution du signal. Donc le temps caractéristique est: $\tau_c = \frac{2Q}{\omega_0}$


### Régime pseudo-périodique: Décrément logarithmique


__Amortissement et décroissance exponentielle__  
Dans le cas d'un régime pseudo-périodique, l'amplitude du pseudo-sinusoïde décroît de manière exponentielle. C'est la vitesse de décroissance qui va déterminer dans ce régime la force de l'amortissement.

Comme cette décroissance est exponentielle, nous allons utiliser un indicateur particulier pour quantifier l'amortissement.


````{important} __Définition : Décrément logarithmique.__

Pour un régime pseudo-périodique de pseudo-période T, on définit le décrément logarithmique $\delta$ par:

$$
\delta = \ln \left( \frac{u(t) - u(t=+\infty)}{u(t+T) - u(t=+\infty)}\right)
$$\end{defi}


__Interprétation__  
On calcule l'écart à la valeur finale à deux instants t et t+T (ce second écart est plus faible pour un système stable). En faisant le rapport, on obtient un nombre d'autant plus grand que l'amortissement est fort. Le décrément est donc une mesure l'amortissement __en régime pseudo-périodique__. 

Le fait que la décroissance soit exponentielle explique que l'on prenne le logarithmique du rapport. Nous allons voir que cela simplifie l'expression.
````

````{important} __Fondamental : Relation entre le décrément logarithmique et le facteur de qualité__

On peut montrer que:

$$
\delta = \frac{2\pi}{\sqrt{4Q^2 - 1}}
$$\end{basic}


__Démonstration__  
\begin{align*}
\delta &= \ln \left( \frac{u(t) - u(t=+\infty)}{u(t+T) - u(t=+\infty)}\right)\\
&= \ln \left( \frac{e^{-\lambda t} \left(C \cos{\Omega t + \varphi} \right)}{e^{-\lambda (t+T)} \left(C \cos{\Omega (t + T) + \varphi} \right)}\right)\\
&= \ln \left( \frac{e^{-\lambda t} \left(\cos{\Omega t + \varphi} \right)}{e^{-\lambda (t+T)} \left(\cos{\Omega t + \Omega T + \varphi} \right)}\right)\\
&= \ln \left( \frac{e^{-\lambda t} \left(\cos{\Omega t + \varphi} \right)}{e^{-\lambda (t+T)} \left(\cos{\Omega t + 2\pi + \varphi} \right)}\right)\\
\end{align*}
soit :

\begin{align*}
\delta &= \ln \left( \frac{e^{-\lambda t} \left(\cos{\Omega t + \varphi} \right)}{e^{-\lambda (t+T)} \left(\cos{\Omega t + \varphi} \right)}\right)\\
&= \ln \left( \frac{e^{-\lambda t}}{e^{-\lambda (t+T)}}\right)\\
&= \ln \left( e^{\lambda T}\right)\\
&= \lambda T\\
\end{align*}
soit :

\begin{align*}
\delta &= \frac{\omega_0}{2Q} \frac{2\pi}{\omega_0 \sqrt{1 - \frac{1}{4Q^2}}}\\
&= \frac{2\pi}{2Q\sqrt{1 - \frac{1}{4Q^2}}}\\
&= \frac{2\pi}{\sqrt{4Q^2 - 1}}
\end{align*}

```{dropdown} Remarque

__Analyse__  
On peut analyser l'expression précédente en remarquant que plus Q augmente, plus $\delta$ diminue. Il vient que __en régime pseudo-périodique__, plus Q est grand, plus l'amortissement est faible. On retrouve d'ailleurs ce principe avec le temps caractéristique qu'on a calculer précédemment.

```
````

````{attention}
__Portée de l'étude précédente__


Tout ce qui est établi ici (définition du décrément logarithmique, son expression en fonction de Q, sens à donner à Q) n'est vrai que __si le régime est un régime pseudo-périodique.__. Sinon, on ne peut pas faire une telle analyse (on ne peut d'ailleurs pas définit de pseudo-période.

````

### Régime pseudo-périodique: Portrait de phase


__Allure du portrait de phase__  
Le portrait de phase en régime pseudo-périodique est une spirale elliptique convergeant vers le régime forcé.

Si l'on représente la dérivée $\dot X(t)$ en fonction de la fonction X(t), la spirale tourne dans le sens horaire.

```{figure} ./images/elec_ordre2_pseudo_p_phase.png
:name: fig_174
:align: center

```


## Réponse indicielle d'un RLC série


On se propose de faire la synthèse des études précédentes sur l'exemple d'une réponse indicielle. On en profitera aussi pour voir la détermination des constantes avec l'autre forme de la solution en régime pseudo-périodique. Il est conseillé de s'entraîner à faire l'exercice avant de regarder les réponses.


````{admonition} Exercice 
:class: attention

On considère le circuit suivant (E est constant). A t=0, le condensateur est complètement déchargé et aucun courant ne circule dans le circuit.

```{figure} ./images/elec_ordre_2_circuit_echelon.png
:name: fig_175
:align: center

```

1. Exprimer la tension aux bornes du condensateur dans le nouveau régime forcé.
1. Déterminer l'équation différentielle qui régit l'évolution de la tension aux bornes du condensateur. En déduire les expressions du facteur de qualité et de la pulsation propre. Les comparer au cas du régime libre.
1. Déterminer l'expression de la tension aux bornes du condensateur pour t>0 dans le cas d'un régime pseudo-périodique.
1. Déterminer l'expression de la tension aux bornes du condensateur pour t>0 dans le cas d'un régime apériodique.
1. Déterminer l'expression de la tension aux bornes du condensateur pour t>0 dans le cas d'un régime critique.
````

````{dropdown} Correction

 


__Q1. Nouveau régime forcé__  
On peut considérer que le nouveau régime forcé est indépendant du temps (puisque E est constant). Le condensateur se comporte donc comme un interrupteur ouvert et l'intensité est donc nulle. Il vient que la tension aux bornes de la résistances est nulle.

La bobine elle se comporte comme un fil. La loi des mailles donne donc que $u_C(t=+\infty) = E$



__Q2. Mise en équation__  
On peut écrire la loi des mailles $E = u_C + u_R + u_L = u_C + R i + L \frac{\rm{d}i}{\rm{dt}} = 0$. Soit avec $i = C \frac{\rm{d}u_C}{\rm{dt}}$:

$$
\frac{\rm{d^2}u_C}{\rm{dt^2}} + \frac{R}{L} \frac{\rm{d}u_C}{\rm{dt}} + \frac{1}{LC} u_C = \frac{1}{LC}E
$$
Il vient $\omega_0 = \frac{1}{LC}$ et $Q = \frac{1}{R}\sqrt{\frac{L}{C}}$ soit les mêmes expressions que dans le cas du régime libre. C'est normal puisqu'il s'agit du même système (RLC série) confronté à une entrée différente (nulle dans un cas et égale à E dans l'autre).



__Q3. Expression temporelle - Cas pseudo-périodique__  
La solution générale ESSM est alors:

$$
u_{c,0}(t) = D \exp^{-\frac{\omega_0 t}{2Q}} \left(\cos{\Omega t + \varphi} \right)
$$
avec $\Omega = \omega_0 \sqrt{1 - \frac{1}{4Q^2}}$ la pseudo-pulsation du système.

On recherche une solution particulière de l'équation avec second membre. On la cherche sous forme constante $u_C = U_0$. Les dérivées étant nulles, on trouve directement $U_0 = E$. La solution complète est donc:

$$
u_{c}(t) = D \exp^{-\frac{\omega_0 t}{2Q}} \left(\cos{\Omega t + \varphi} \right) + E
$$
Il reste à utiliser les conditions initiales en utilisant le fait que $i = C \frac{\rm{d}u_C}{\rm{dt}}$:

\begin{align*}
u_{c}(t=0) &= D \cos{\varphi} + E = 0 \\
i(t = 0) &= C D \left(-\Omega \sin{\varphi} -\frac{\omega_0}{2Q} \cos{\varphi} \right) = 0\\
\Longrightarrow \varphi &= -\arctan{\frac{\omega_0}{2Q \Omega}} =  -\arctan{\frac{1}{\sqrt{4Q^2 - 1}}}\\
\Longrightarrow D &= - \frac{E}{\cos{\varphi}} = - \frac{2Q}{\sqrt{4Q^2-1}}E
\end{align*}



__Q4. Expression temporelle - Cas apériodique__  
La solution générale ESSM est alors:

$$
u_{c,0}(t) = A \exp^{r_1 t} + B \exp^{r_2 t}
$$
avec $r_{1,2} = -\frac{\omega_0}{2Q}(1 - \sqrt{1 - 4Q^2})$.

On recherche une solution particulière de l'équation avec second membre. On la cherche sous forme constante $u_C = U_0$. Les dérivées étant nulles, on trouve directement $U_0 = E$. La solution complète est donc:

$$
u_{c}(t) = A \exp^{r_1 t} + B \exp^{r_2 t} + E
$$
Il reste à utiliser les conditions initiales en utilisant le fait que $i = C \frac{\rm{d}u_C}{\rm{dt}}$:

\begin{align*}
u_{c}(t) = A + B + E = 0\\
u_{c}(t) = A r_1 + B r_2 = 0\\
\Longrightarrow A =-\frac{r_2}{r_2 - r_1}E\\
\Longrightarrow B =-\frac{r_1}{r_1 - r_2}E
\end{align*}


__Q5. Expression temporelle - Cas critique__  
La solution générale ESSM est alors:

$$
u_{c,0}(t) = \exp^{-\frac{\omega_0 t}{2Q}} \left(A t + B\right)
$$
avec $r_{1,2} = -\frac{\omega_0}{2Q}(1 - \sqrt{1 - 4Q^2})$.

On recherche une solution particulière de l'équation avec second membre. On la cherche sous forme constante $u_C = U_0$. Les dérivées étant nulles, on trouve directement $U_0 = E$. La solution complète est donc:

$$
u_{c}(t) = \exp^{-\frac{\omega_0 t}{2Q}} \left(A t + B\right) + E
$$
Il reste à utiliser les conditions initiales en utilisant le fait que $i = C \frac{\rm{d}u_C}{\rm{dt}}$:

\begin{align*}
u_{c}(t) = B + E = 0 \Longrightarrow B = -E\\
u_{c}(t) = -\frac{\omega_0 }{2Q} B + A = 0 \Longrightarrow A =  -\frac{\omega_0 }{2Q} E
\end{align*}

```{admonition} Vérification
:class: hint
On rappelle les vérification d'usage : Nouveau régime permanent et homogénéité. Il est conseillé de vérifier aussi l'homogénéité au niveau de l'équation différentielle, de Q (sans dimension) et de $\omega_0$.

Lorsqu'on détermine des conditions initiales, si le calcul est relativement complexe, il est aussi conseillé de vérifié qu'elles vérifient bien le système de départ.
```

````

