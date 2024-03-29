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

### Lois de mailles

````{important} __Fondamental : __

La somme des tensions d'une maille est nulle en orientant les tensions dans le même sens.

````

__Démonstration__  
Il s'agit de l'application de l'additivité des tensions sur une boucle.


````{admonition} Exercice 
:class: attention

```{figure} ./images/elec_loi_maille.png
:name: fig_96
:align: center

```


Sur le schéma ci-contre :

$U_{AD} + U_{DB} + U_{BE} + U_{EA} = 0$

````

### Loi des noeuds

````{important} __Fondamental : __

L'ensemble des courants entrant dans un noeud est égale à l'ensemble des courant sortant du même noeud.

````

````{dropdown} Remarque

On peut réécrire cette loi en disant que la somme des intensités entrantes est nulle (on compte alors les intensités "sortantes" négativement). On rappelle que les intensités sont des grandeurs algébriques et que leur orientation est arbitraire. On a donc très bien pu orienter une intensité sortante mais où les électrons sortent (i < 0), ce n'est pas faux. Il arrive même que l'intensité change de signe.

````


>__Démonstration__  
>Dans l'ARQS, il ne peut pas y avoir d'accumulation de charge au niveau du noeud, donc le débit entrant égale le débit sortant.

````{admonition} Exercice 
:class: attention

```{figure} ./images/elec_loi_noeud.png
:name: fig_97
:align: center

```
Ici la loi des noeuds s'écrit :

$i_1 + i_2 + i_3 + i_4 = 0$

````

### Méthode : Application des lois de Kirchhoff
Le but est d'apprendre à appliquer les lois de Kirchhoff dans un circuit en vue de déterminer les différentes grandeurs. Comprendre le principe de mise en équation et être capable de le faire est fondamental.


````{admonition} Exercice 
:class: attention

```{figure} ./images/elec_maille.png
:name: fig_98
:align: center

```
On considère le circuit ci-contre. On note $i_2, i_3$ et $i_4$ les intensités circulant respectivement dans les dipôles $D_2,D_3$ et $D_4$ et orientées vers le haut. On s'intéresse aussi aux tensions $U_{AC}$, $U_{BC}$ et $U_{AB}$.

1. Combien de lois de Kirchhoff indépendantes peut-on écrire ?
1. Exprimer ces lois en fonction des grandeurs introduites précédemment.
1. En réalité, on connaît seulement $U_{AC} = E$ et on connaît les relations : $U_{BC} = R i_2$, $U_{AB} = -R i_3$, $U_{AB} = -R i_4$ (où seul R est connu). Déterminer toutes les tensions et intensités en fonction de E et R.
````

````{dropdown} Correction

Q1. Lois de Kirchhoff indépendantes  
Si l'on compte N le nombre de noeuds, alors on ne peut alors établir plus de N-1 lois des noeuds indépendantes. Ici il n'y en a qu'une.

Ici on peut réaliser deux mailles qui ne "coupent" pas de fils (D1+D2+D3) et (D3+D4), c'est le nombre de lois des mailles indépendantes qu'on peut écrire. Ici il n'y en a deux.


```{attention}

Ce n'est pas parce qu'on peut écrire 3 lois de Kirchhoff indépendantes que les trois seront utiles. Le principe est toujours le même : il faut autant d'équations que d'inconnues pour résoudre un système.

Concernant les mailles, on peut compter le nombre de lois indépendantes en comptant le nombre de mailles qui ne "coupent" pas de fils, mais on n'est pas obligé d'utiliser ces mailles pour appliquer la loi des mailles. On peut ainsi choisir d'utiliser la maille (D1+D2+D4) et la maille (D3+D4).

```

Q2. Établir les lois de Kirchhoff  
Pour appliquer une loi des noeuds, il faut choisir une convention (intensité comptée positivement quand elle rentre vers le noeud par exemple). On choisit le noeud du haut (qui est au potentiel $V_A$:

$i_2 + i_3 + i_4 = 0$

Pour appliquer la loi des mailles, il faut choisir un un sens de parcours. Une tension dans le sens de parcours est comptée positivement, une tension dans le sens inverse est comptée négativement.

Ici pour la maille de gauche (vert) :

$U_{AC} - U_{AB} - U_{BC} = 0$

Pour la maille rouge :

$U_{AB} - U_{AB} = 0$

```{figure} ./images/elec_loi_kirchhoff.png
:name: fig_99
:align: center

```


```{dropdown} Remarque

On remarque qu'on a déplacé le point A et le point B. Comme ils sont toujours sur le même fils de connexion, ils sont au même potentiel, on peut donc le faire sans modifier le problème.

Écrite ainsi, la seconde loi des mailles peut sembler inutile mais elle permet de relier la tension aux bornes de $D_3$ et $D_4$ qui peuvent s'exprimer différemment en fonction de $i_3$ et $i_4$.

```

Q3. Utilisation des lois d'évolution et nombre d'inconnues  
Il est important de réaliser quelles sont les inconnues et quelles sont les grandeurs connues. Ici, les grandeurs connues sont données : $E$ et $R$. Quelques fois, la liste des grandeurs données ne sera pas aussi explicite, il faut réfléchir et comprendre le problème.

Les inconnues sont $U_{BC}$, $U_{AB}$, $i_2, i_3$ et $i_4$. (La tension $U_{AC}$ est connue puisqu'elle vaut E). Il nous faut donc 5 équations.

On dispose déjà des trois équations d'évolutions (pour l'instant elle sont données dans l'énoncé, par la suite, elle seront à déterminer à partir du cours). Il suffit de deux équations : la loi des noeuds en A et la loi des mailles de gauche (vert). La dernière loi des mailles n'est pas utile ici (en réalité elle a été utilisée pour dire que $i_3$ ET $i_4$ sont reliés à $U_{AB}$.

Méthode : En général, on introduit les lois d'évolutions dans les lois de Kirchhoff. Il est conseillé de ne garder que des intensités ou que des tensions suivant les besoins. Ici nous allons garder uniquement les intensités. Il vient :

$i_2 + i_3 + i_4 = 0$

$E + Ri_3 - Ri_2 = 0$

On a aussi par les deux dernières équations d'évolutions (ou par la deuxième loi des mailles) : $i_3 = i_4$.

Il ne reste plus qu'à résoudre le système. __On s'entraînera à vérifier que__ :

$i_2 = \frac{2E}{3R}$ et $i_3 = i_4 = -\frac{E}{3R}$

puis : $U_{BC} = \frac{2E}{3}$ et $U_{AB} = \frac{E}{3}$


Vérifier ses résultats  
__Il est important de s'entraîner systématiquement à relire ses calculs et à vérifier ses résultats. La relecture nécessite un ENTRAINEMENT QU'il faut réaliser à chaque TD, exercice, cours, DM... __  

Homogénéité : L'intensité est bien homogène à une tension sur une résistance (loi d'Ohm). Les tensions sont égales à une tension.

Sens physique : Pour l'instant, nous n'avons pas suffisamment d'éléments en électrocinétique pour analyser physiquement cette expression. On peut néanmoins noter que si $E > 0$ (ce qui n'est pas nécessaire) alors les électrons ont tendance à aller du point C (plus faible potentiel électrique donc plus forte énergie potentielle pour les électrons) vers le point A (plus fort potentiel électrique donc plus faible énergie potentielle pour les électrons), donc l'intensité $i_2$ est attendue __positivement__ proportionnelle à E.


```{dropdown} Remarque

En pratique, seule la 3ème question est posée dans un exercice.

```

````

### Méthode : application de la loi des noeuds en termes de potentiels.


Lorsqu'on connaît la relation intensité-tension pour un dipôle (et ce sera toujours le cas), on peut se passer des lois des mailles en travaillant avec les potentiels électriques. On va alors chercher à remplacer les intensités dans les lois des noeuds par des fonction des différences de potentiel.


````{admonition} Exercice 
:class: attention


```{figure} ./images/elec_maille_2.png
:name: fig_100
:align: center

```

On considère le circuit ci-contre. On note $i_2, i_3$ et $i_4$ les intensités circulant respectivement dans les dipôles $D_2,D_3$ et $D_4$ et orientées vers le haut. On donne : $U_{AC} = E$ et on connaît les relations : $U_{BC} = R i_2$, $U_{AB} = -R i_3$, $U_{AB} = -R i_4$ Déterminer les expressions des intensités $i_2, i_3, i_4$ et les tensions $U_{AB}$ et $U_{BC}$ (en utilisant les potentiels électriques).
````

````{dropdown} Correction
_On a déjà déterminé ces grandeurs. Le but est ici de le faire en utilisant les potentiels électriques._

Écrire les lois des noeuds en terme de potentiels se décompose en plusieurs parties :

1. On choisit une référence des potentiels
1. On établit toutes les lois des noeuds indépendantes
1. On remplace les intensités par des expressions avec en fonction des potentiels (des différences de potentiels)
1. On résout le système d'équation ainsi obtenus (en fonction des potentiels inconnus) et on remonte aux grandeurs qui nous intéresse.


```{admonition} Méthode 
:class: attention

1. On va choisir $V_C = 0$ (c'est un choix arbitraire). Il vient directement $V_A = U_{AC} + V_C = E$. On remarque qu'il y a donc bien un seul potentiel inconnu $V_B$, une loi des noeuds devrait donc suffire.
1. $i_2 + i_3 + i_4 = 0$
1. On utilise les relations intensités-tensions qu'on réécrit avec des potentiels. Ainsi :
    1. $i_2 = \frac{U_{BC}}{R} = \frac{V_B - V_C}{R} = \frac{V_B}{R}$
    1. $i_3 = - \frac{U_{AB}}{R} = - \frac{V_A - V_B}{R} = \frac{V_B - E}{R}$
    1. $i_4 = - \frac{U_{AB}}{R} = - \frac{V_A - V_B}{R} = \frac{V_B - E}{R}$
1. La loi des noeuds s'écrit donc : $ \frac{V_B}{R} + \frac{V_B - E}{R} + \frac{V_B - E}{R} = 0$
1. Il vient : $V_B = \frac{2E}{3}$. Outre les intensités, on trouve bien : $U_{BC} = V_B - V_C =  \frac{2E}{3}$ et $U_{AB} = V_A - V_B  = \frac{E}{3}$

```

```{dropdown} Remarque

Cette méthode est extrêmement utile car une fois maîtrisée, elle permet un établissement facile et rapide des grandeurs.

Avec l'expérience, les points 2 et 3 peuvent se faire simultanément mais il est conseillé pour l'instant de les décomposer.

```

````

## Étude énergétique d'un dipôle

L'étude énergétique consiste à déterminer la puissance instantanée reçue ou fournie par un dipôle au reste du circuit puis en déduire l'énergie reçue ou fournie durant une durée $\Delta t$.

Une telle étude demande:

* de savoir si l'on calcule la puissance qu'il reçoit ou qu'il fournit (l'une étant l'opposée de l'autre) : cela dépendra de la convention d'orientation choisie pour la tension et l'intensité
* de savoir comment la calculer, une expression sera établie en fonction des tensions et intensités.
* de savoir analyser le résultat obtenue : le signe de la grandeur calculée permet de savoir si le dipôle fournit (comportement générateur) ou reçoit (comportement récepteur) de la puissance ainsi calculée.
* de savoir intégrer l'expression établie pour faire des calculs d'énergie.
\end{intro}

### Convention générateur et récepteur pour un dipôle

````{important} __Définition : Convention générateur__

Pour un dipôle D, si l'on oriente l'intensité $I_1$ qui le traverse et la tension $U_1$ à ses bornes dans le même sens, on dit qu'il est orienté __en convention générateur.__

```{figure} ./images/elec_conv_gene.png
:name: fig_101
:align: center

```
````

````{important} __Définition : Convention récepteur__
Pour un dipôle D, si l'on oriente l'intensité $I_1$ qui le traverse et la tension $U_1$ à ses bornes en sens contraire, on dit qu'il est orienté __en convention récepteur.__


```{figure} ./images/elec_conv_recep.png
:name: fig_102
:align: center
```
````

````{attention}
__Il s'agit d'une convention !__


Il s'agit d'une convention (très mal nommée!), c'est-à-dire qu'on définit arbitrairement l'orientation du dipôle __peu importe qu'il soit réellement un récepteur ou un générateur__. D'ailleurs, nous rencontrerons des dipôles qui se comporteront alternativement comme des générateurs et des récepteurs (source de tension, condensateur, bobine).

Donc __orienter un dipôle qui se comporte comme un générateur en convention récepteur n'est pas faux__ (et l'inverse non plus).

D'ailleurs, on rappelle que les intensités et les tensions sont des grandeurs __algébriques__. Comme nous allons le voir, c'est le signe relatifs de ces deux grandeurs, suivant leur orientation, qui va définir leur __comportement récepteur ou générateur : c'est-à-dire leur tendance à fournir ou recevoir de l'énergie.__

````

### Puissance échangée entre un dipôle et le reste du circuit

````{important} __Fondamental : Puissance instantanée échangée entre un dipôle et le reste du circuit__

La puissance instantanée échangée entre un dipôle et le reste du circuit a pour expression :

$P = U_1 \times I_1$

avec $U_1$ la tension à ses bornes et $I_1$ l'intensité qui le traverse.

* En convention récepteur, elle correspond à la puissance que reçoit le dipôle du reste du circuit.
* En convention générateur, elle correspond à la puissance que fournit le dipôle au reste du circuit.

````


__Démonstration (pas à connaître)__  
Néanmoins, il est bon de comprendre le principe de cette démonstration qui pointe vers les études que nous ferons plus tard en mécanique.

On se place du point de vue des charges q qui entrent et sortent du dipôle. Durant une durée $\Delta t$, il entre et sort une quantité de charge $\Delta q = I_1 \Delta t$ soit un nombre de particules chargées $\Delta n = \frac{I_1 \Delta t}{q}$ (en supposant qu'elles ont toutes la même charge q).


```{figure} ./images/elec_conv_recep_2.png
:name: fig_103
:align: center

```


__Considérons le cas d'une convention récepteur__ (comme sur le schéma ci-contre) et des charges $q$ positives (le raisonnement est identique pour des charges négatives). Passant de A à B, une charge perd une énergie $E_1 = q (V_A- V_B) = q U_1$. Cette énergie est reçue par le dipôle. Donc l'énergie totale reçue par le dipôle pendant un temps $\Delta t$ est :

$E = \Delta n E_1 = I_1 U_1 \Delta t$.

Il vient que la puissance reçue par le dipôle est $P = \frac{E}{\Delta t} = I_1 U_1$




```{figure} ./images/elec_conv_gene_2.png
:name: fig_104
:align: center

```


__En convention générateur__, l'énergie perdue est toujours $E_1 = q (V_A - V_B) = - U_1$. Il vient donc que la puissance reçue par le dipôle est $P = - I_1 U_1$. Donc la puissance $P = U_1 I_1$ est la puissance fournie par le dipôle.




````{attention}
__Caractère algébrique de la puissance échangée__


La puissance échangée, comme toutes les grandeurs en électricité est algébrique. Ainsi, on peut se placer

1. en convention récepteur
1. calculer la puissance échangée $P = ui$
1. trouver une puissance échangée négative

Cela signifie que physiquement, le dipôle fournit l'énergie $\vert P \vert = - ui$ au reste du circuit. Il se __comporte __donc comme un __générateur__.

Mais avoir choisi une convention récepteur en premier n'est pas faux, puisqu'il s'agit d'un choix arbitraire. __L'important c'est que l'analyse physique soit correcte.__

````

### Comportement générateur et récepteur d'un dipôle


Le __comportement __d'un dipôle n'est pas arbitraire mais exprime ce qui se passe physiquement dans le circuit. Ce dernier ne peut être choisi arbitrairement (contrairement aux conventions) et doit être déterminer par des calculs (nous en verrons par la suite) ou étude (graphique par exemple). C'est le calcul de la__ puissance échangée__ et l'__étude de son signe__ qui déterminer le __comportement du dipôle__.

Le __comportement__ d'un dipôle peut changer au cours d'une expérience.


| | Comportement récepteur | Comportement générateur |
|:-:|:-:|:-:|
| Convention générateur | P < 0 | P > 0 |
|Convention récepteur | P > 0 | P < 0 |

_Il est conseillé de chercher à comprendre pourquoi on obtient tel signe à partir de l'interprétation de la puissance échangée établie précédemment._

### Méthode : Déterminer les comportements récepteurs/générateurs graphiquement.


Il s'agit d'apprendre le principe de base de l'étude des comportements générateurs et récepteurs d'un dipôle et d'observer aussi que ces comportements peuvent changer en régime variable.


````{admonition} Exercice 
:class: attention

On considère un dipôle D dans un circuit. Les évolutions de l'intensité qui le traverse et de la tension à ses bornes en convention générateur sont données ci-après. Déterminer les temps récepteurs et les temps générateurs, c'est-à-dire les moments où le dipôle se comporte comme un récepteur et les moments où le dipôle se comporte comme un générateur.

Remarque : pour cet exercice, peu importe quelle courbe représente l'intensité ou la tension.

```{figure} ./images/elec_comp_rg_graph_1.jpg
:name: fig_105
:align: center

```

````

````{dropdown} Correction
_On rappelle que le comportement d'un dipôle est basé sur le signe de la puissance échangée en déterminant si celle-ci est fournie ou reçue._

Nous sommes en convention générateur, le produit $ui$ est donc la puissance fournie par le dipôle au circuit. Si elle est positive (u et i sont de même signe), le dipôle se comporte comme un générateur, si elle est négative (u et i sont de signes opposés), le dipôle se comporte comme un récepteur.

On a ainsi pu représenter les instants générateurs (en vert) et récepteurs (en jaune) sur le graphique.

```{figure} ./images/elec_comp_rg_graph_2.jpg
:name: fig_106
:align: center
```

```{dropdown} Remarque

* Le dipôle ne se comporte toujours comme un récepteur ou un générateur, il peut passer d'un comportement à un autre.
* Le signe des tensions et intensités ne détermine pas le comportement physique, c'est bien __le signe du produit__ qui est important.
* La durée des temps générateurs et récepteurs ne permet pas de dire seule si le dipôle fournit globalement (sur le temps long de toute l'expérience) de l'énergie ou s'il reçoit globalement de l'énergie. Il faudrait l'expression mathématique de u et i (ici vraisemblablement des sinusoïdes). Nous allons voir comme procéder pour déterminer des comportements globaux qui conduisent à une étude en énergie et non en puissance. Ici, on montrerait que le dipôle se comporte globalement comme un récepteur. Mais cela ne rend pas faux, le choix de la convention générateur.

```
````

### Méthode : Déterminer analytiquement les comportements générateurs/récepteurs

Il s'agit ici de voir comment déterminer une puissance instantanée puis l'énergie échangée durant une période donnée. Les équations données ici correspondent au dipôles étudiées précédemment.


````{admonition} Exercice 
:class: attention

On considère un dipôle D orientée en convention générateur. On a trouvé que l'intensité qui circulait dans le dipôle a pour expression : $i(t) = i_m \sin(\pi t - \frac{\pi}{3})$ et que la tension à ses bornes est $u(t) = u_m \sin(\pi t + \frac{\pi}{2})$ avec $u_m > 0$ et $i_m > 0$

1. Exprimer la puissance instantanée $p(t) = u(t) i(t)$. S'agit-il d'une puissance reçue ou fournie ?
1. Montrer que $p(t)$ est un signal sinusoïdal dont on précisera les caractéristiques. On note T la période de $p(t)$
1. Déterminer l'énergie fournie par le dipôle durant une période T. Le dipôle a-t-il un comportement globalement générateur ou récepteur ?
````

````{dropdown} Correction

__Q1. Calcul de la puissance instantanée__  
$p(t) = i_m u_m \sin(\pi t - \frac{\pi}{3}) \sin(\pi t + \frac{\pi}{2})$.

Nous sommes en convention générateur, donc $p(t)$ est la puissance fournie par le dipôle au circuit.

Il s'agit d'utiliser les formules trigonométriques (__à connaitre__). Ainsi :

\begin{align*}
p(t) &= i_m u_m \sin(\pi t - \frac{\pi}{3}) \sin(\pi t + \frac{\pi}{2})\\
&= \frac{i_m u_m}{2} \left ( - \cos(2 \pi t + \frac{\pi}{6}) + \cos(\frac{5 \pi}{6}) \right )
\end{align*}


$p(t)$ est donc bien sinusoïdal et ses caractéristiques sont :
* amplitude : $\frac{i_m u_m}{2} $
* pulsation : $2 \pi \rm{rad.s^{-1}}$ donc période 1s et fréquence 1Hz (on remarquera que ce n'est pas la période de u et i)
* phase à l'origine : $\frac{\pi}{6} + \pi$ (à cause du signe moins)
* valeur moyenne : $\frac{i_m u_m}{2}\cos(\frac{5 \pi}{6})$



__Q3. Calcul d'énergie__  
On rappelle la relation $p = \frac{dE}{dt}$ où p est la puissance instantanée et E l'énergie (ici l'énergie échangée avec le circuit). On obtient donc l'énergie échangée par intégration de $p(t)$ sur une période ($T = 1s$):

\begin{align*}
E = \int_{t=0}^{t=T} p(t) dt =  \int_{t=0}^{t=T}  \frac{i_m u_m}{2} \left (- \cos(2 \pi t + \frac{\pi}{6}) + \cos(\frac{5 \pi}{6}) \right )dt 
E =  \frac{i_m u_m}{2} \left [ -\frac{1}{2 \pi} \sin(\cos(2 \pi t + \frac{\pi}{6})  \right ]_{t=0}^{t=T} + \frac{i_m u_m}{2}  \cos(\frac{5 \pi}{6}) T
E = \frac{i_m u_m}{2} \cos(\frac{5 \pi}{6}) T < 0
\end{align*}
Le dipôle fournit globalement une énergie négative, c'est-à-dire qu'il reçoit une énergie $\vert E \vert$: il est donc globalement récepteur.


```{dropdown} Remarque

Attention, il faut se rappeler qu'il peut y avoir des temps où le dipôle possède un comportement générateur. Mais globalement, il reçoit de l'énergie plus qu'il n'en fournit.

```

````

### Méthode : Déterminer les comportements de dipôles dans un circuit


On travaille ici en régime indépendant du temps de manière à pouvoir utiliser simplement les lois de Kirchhoff. On considère le circuit ci-après et on donne les caractéristiques suivantes :

* $D_2$ et $D_4$ sont des accumulateurs : leur tension est imposées de l'extérieur. La tension $U_1$ aux bornes de $D_2$ est connue et positive. La tension $U_2$ est réglable (mais constante durant la manipulation) et de signe quelconque.
* $D_1$ et $D_3$ sont deux conducteurs ohmiques : en convention récepteur la relation intensité-tension est : $u = Ri$

```{figure} ./images/elec_circuit_puissance.png
:name: fig_107
:align: center

```


````{admonition} Exercice 
:class: attention

Déterminer, suivant les valeurs de $U_2$ les comportements récepteurs/générateurs des deux dipôles $D_2$ et $D_4$.

````

````{dropdown} Correction
Comme on l'a vu précédemment, il faut choisir déterminer le signe de la puissance échangée. Pour cela, il faut :

1. Paramétrer le circuit en nommant les intensités et tensions (ou potentiels) mises en jeu. En effet, contrairement à l'exercice précédent où nous avons utiliser les lois de Kirchhoff, toutes les grandeurs ne sont pas explicitement définies. Et ce sera en général le cas.
1. Mettre en équation le problème en utilisant les relations intensités-tension et les lois de Kirchhoff.
1. Identifier la(les) grandeur(s) qu'on cherche, identifier les grandeurs qu'on connaît (les données de l'énoncé qu'on peut utiliser dans le résultat final) et les grandeurs qu'on a introduit nous même (et qui doivent être éliminées).
1. On résout le système en cherchant à obtenir ce qu'on veut.

On veut utiliser ensuite la loi des noeuds en terme de potentiel, on paramètre donc des intensités et des points de potentiels.

On en profite aussi pour choisir un point de potentiel nul (la masse). On prend $V_M = 0$.

```{figure} ./images/elec_circuit_puissance_p.png
:name: fig_108
:align: center
```
````{dropdown} Remarque

L'orientation des intensités est arbitraire. Il faut par contre avoir conscience des conventions d'orientation qu'on utilise.

Si on décide d'utiliser les tensions plutôt que les potentiels, le paramétrage serait le suivant. Les tensions $U_{1}$ et $U_3$ sont orientées en convention récepteur pour $D_1$ et $D_3$ de manière à pouvoir utiliser la loi $u=Ri$ qui nous est donnée sans changement de signe.

__Il est vivement conseillé de s'entraîner à appliquer les lois de Kirchhoff à partir de ce paramètrage.__  

```{figure} ./images/elec_circuit_puissance_p_2.png
:name: fig_109
:align: center

```

````

```{figure} ./images/elec_circuit_puissance_p.png
:name: fig_110
:align: center
```

Remarquons que : $V_B = U_2 + V_M = U_2$ et $V_A = U_1 + V_M = U_1$

La loi des noeuds s'écrit $i_1 = i_2 + i_3$ or :

\begin{align*}
i_1 = \frac{U_{AB}}{R} = \frac{V_A - V_B}{R} = \frac{U_1 - U_2}{R}\\
i_2 = \frac{U_{BM}}{R} = \frac{V_B - V_M}{R} = \frac{U_2}{R}\\
i_3 = ?
\end{align*}
Remarque : il arrive que certaines intensités ne soient pas exprimables en fonction des potentiels.

Il vient :

$$
 \frac{U_1- U_2}{R} =\frac{U_2}{R} + i_3
$$

Il convient de se demander que doit-on calculer. Cette étape est fondamentale car son absence est souvent cause de beaucoup d'erreurs. Elle peut être faite avant ou après le paramétrage et souvent avant même la mise en équation. (On la fait ici pour profiter des grandeurs nommées).

* __On cherche__ : les puissances échangées par $D_2$ ($p_2$) et $D_4$ ($p_4$) et plus exactement leur signe. Ce sont les grandeurs dont on doit trouver une "formule" en fonction du reste.
* __On connaît:__ Les grandeurs connues sont : $R, U_1$ et $ U_2$ qui sera notre paramètre variable pour l'étude des signes des puissances. Ces grandeurs pourront appraître dans les "formules" finales qu'on veut établir.
* __Toutes les autres grandeurs doivent disparaître.__  

__4.__  
Les puissances s'expriment comme : $p_2 = U_1 i_1$ et $p_4 = U_2 i_3$ donc c'est la connaissance de $i_1$ et $i_3$ qui est importante (et surtout leur signe).

On a directement :

$i_3 = \frac{U_1 - 2 U_2}{R}$ et $i_1 = i_2 + i_3 =\frac{U_1 - U_2}{R}$

On remarque que $i_3$ change de signe pour $U_2 = \frac{U_1}{2}$ et $i_1$ change de signe pour $U_2 = U_1$. Nous allons utiliser un tableau de signe pour faire la synthèse des résultats et déterminer les signes de $p_2$ et $p_4$.

Attention : pour analyser ces signes, il faut avoir conscience des conventions d'orientation : $D_2$ est en convention générateur, on calcul donc une puissance fournie. $D_4$ est en convention récepteur, on calcule donc une puissance reçue.

```{figure} ./images/table_gr.png
:name: table_rg
:align: center
```

````{admonition} Vérification et interprétation des résultats.
:class: hint
Il s'agit de conseil de relecture.
__Homogénéité :__ On vérifie que les intensités trouvées sont bien homogènes. Ici, il s'agit d'une somme de tensions sur une résistance : les relations sont donc bien homogènes.

__Interprétation physique :__ On porte notre attention sur les puissances.

* Quand $U_2$ est négative, les deux sources de tensions tendent à faire circuler les électrons dans le même sens. Il n'y a pas de compétition et les deux fonctionnements en générateur
* Quand $U_2$ est positive, il y a compétition. Si $U_2$ est trop faible (ici inférieure à $U_1$), il va fonctionner en récepteur.
* En augmentant, il devient assez puissant pour fonctionner en générateur mais $U_1$ étant encore important, il fonctionne aussi en générateur. Les deux dipôles alimentant alors les deux résistances.
* En augmentant encore, $U_2$ devient suffisamment important pour faire fonctionner $D_2$ en récepteur.
````
