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
# Entrainement : Bases

## Puissance et énergie

````{admonition} Dipôles linéaires passifs 
:class: attention

Calculer la puissance instantanée reçue puis l'énergie emmagasinée durant une période pour:

1. un condensateur C dont la tension à ses bornes est $u(t) = u_m \cos (\omega t + \phi)$
1. une bobine L dont l'intensité la traversant est $i(t) = i_m \cos (\omega t + \phi)$
1. une résistance R dont la tension à ses bornes est $u(t) = u_m \cos (\omega t + \phi)$
````
````{topic} Réponse (sans justification)  
On trouve que la variation d'énergie sur une période pour la bobine et le condensateur sont toutes les deux nulle (propriété importante de C et L en régime périodique).

Pour la résistance, c'est un piège: elle n'emmagasine pas d'énergie... 
````

````{admonition} Accumulateurs
:class: attention

On considère le circuit suivant où R est une résistance variable et les fem $E_1$ et $E_2$ sont positives et $E_1 > E_2$. Déterminer suivant les valeurs de R le comportement recepteur ou générateur deux fem.

```{figure} ./images/elec_accumulateur.jpg
:name: fig_111
:align: center
```
````
````{topic} Réponse (sans justification)  
Valeur critique de R: $R_{eq} = \frac{R_1 E_1}{E_1 - E_2}$. Pour $R_{eq} < R$, $E_2$ a un comportement récepteur et pour $R_{eq} > R$, $E_2$ a un comportement générateur. $E_1$ a toujours un comportement générateur.
````

_Point utile pour cet exercice_
* _$\Longrightarrow$ [Ponts diviseurs](pont_div)._
* _$\Longrightarrow$ [Lois de Kirchoff](kirchoff)._
* _$\Longrightarrow$ [Puissance électrique](puissance)._

## Applications des lois de Kirchoff

````{admonition} Circuit divers 
:class: attention

On considère le circuit ci-dessous. Déterminer l'intensité i qui traverse la résistance R (de la gauche vers la droite) en utilisant

1. les lois des noeuds et des mailles
1. la loi des noeuds en termes de potentiels

```{figure} ./images/elec_td_circuit_lois.jpg
:name: fig_142
:align: center

```
````
````{topic} Réponse (sans justification)  
$i = -\frac{R_1 E_2 + R_1 R_0 I_0 + (R_0 + R_2)E_1}{(R_0 + R_2) (R_1 + R) + R R_1}$

````
_Point utile pour cet exercice_
* _$\Longrightarrow$ [Loi des noeuds en terme de potentiel](etude_lois)._
* _$\Longrightarrow$ [Lois de Kirchoff](kirchoff)._

````{admonition} Ohmètre à tarage shunt 
:class: attention

On considère le montage suivant qui modélise un ohmmètre à tarage shunt. Il comporte un générateur de f.e.m. E (de résistance interne négligeable), un milliampèremètre de résistance interne r, un rhéostat de résistance variable $R_h$ et des résistors $R_1, R_2$. La résistance X est la résistance à mesurer.

```{figure} ./images/elec_resistance_shunt.jpg
:name: fig_143
:align: center

```

1. Exprimer l'intensité i dans le milliampèremètre en fonction de $E, R_1, R_2, R_h, r, X$. Quelle est cette intensité $i_0$ lorsque B et C (bornes de X) sont court-circuités?
1. L'avantage du tarage shunt est qu'on peut choisir $R_h$ très grande devant r. Donner dans ce cas l'expression de i sous la forme $\frac{kE}{X + R}$ en déterminant k et R.
1. En déduire l'expression de X en fonction de $i, i_0$ et R.
````
````{topic} Réponse (sans justification)  
$i = \frac{R R_h}{(R_2 + X)(rR_1 + R_1 R_h + r R_h) + rR_1 R_h} E$

$k = \frac{R}{R_1 + r}$

$R = R_2 + \frac{R_1 r}{R_1 + r}$

$X = R \left(\frac{i_0}{i} - 1\right)$
````

_Point utile pour cet exercice_
* _$\Longrightarrow$ [Ponts diviseurs](pont_div)._
* _$\Longrightarrow$ [Lois de Kirchoff](kirchoff)._

## Dipôles équivalents

````{admonition} Générateur équivalent 
:class: attention

On considère le circuit suivant.

1. Déterminer le générateur de Thévenin du circuit équivalent entre les bornes A et B.
1. Donner la valeur de E pour laquelle le circuit est équivalent à une résistance pure (entre A et B) dont on précisera la valeur. A.N.: $R = 5 \rm{\Omega}; E_1 = 2 \rm{V}; E_2 = 8 \rm{V}$

```{figure} ./images/elec_source_eq.jpg
:name: fig_144
:align: center

```
````
````{topic} Réponse (sans justification)  
$E_{eq} = \frac{E_1 - E_2 -2E}{3}$

$R_{eq} = \frac{3R}{2}$

````

````{admonition} Maillage carré 
:class: attention

On considère le maillage suivant où chaque segment est une résistance R. Déterminer la résistance équivalente pour le dipôle pris entre $B_1$ et $B_2$ puis entre $O$ et $B_2$.

```{figure} ./images/elec_maillage_carre.jpg
:name: fig_145
:align: center

```
````

````{topic} Réponse (sans justification)  
$R_{B_1 B_2} = \frac{3}{2}R$

$R_{O B_2} = \frac{7}{8}R$

````

_Point utile pour cet exercice_
* _$\Longrightarrow$ [Lois de Kirchoff](kirchoff)._
* _$\Longrightarrow$ [Dipôles équivalents](dip_equiv)._

## Résistances d'entrée et de sortie

````{admonition} Transistor bipolaire 
:class: attention

Un transistor bipolaire est un tripôle qui est toujours utilisé comme un quadripôle en rendant une de ses électrodes communes à l'entrée et la sortie. En régime linéaire basse fréquence, les équations d'un transistor bipolaire en émetteur commun E sont: $u_{be} = r i_B + \mu u_{ce}$ et $i_C = \beta i_B + \frac{u_{ce}}{\rho}$. On désire déterminer les valeurs des différentes grandeurs données dans l'équation.

1. \*Modéliser ce composant à l'aide de composants fondamentaux.
1. On place ensuite un générateur idéal de courant entre B et E et un ampèremètre à la place du générateur de tensions entre C et E. Pour un courant de 10,00mA en entrée, on mesure au multimètre un courant de 0,9981 A. Grâce à une protocole adapté, on mesure $r = 2000 \rm{\Omega}$ et $\rho = 20,00 \rm{k \Omega}$. 
\begin{enumerate}1. Déterminer le gain en tension  et le gain en courant.
1. Connaissant les valeurs de $\mu$ et $\beta$, proposer un protocole expérimental pour mesurer les valeurs de $r$ et $\rho$.
1. L'impédance d'entrée d'un voltmètre étant de $1\rm{M\omega}$ et la chute de tension maximale de l'ampèremètre de 0,2V, a-t-on eu raison de les considérer comme idéaux?
1. Calculer l'amplification $A = \frac{i_c}{i_b}$ quand un résistor $R_L$ est connecté entre les bornes C et E. A.N.: $R_L = 1 \rm{k \Omega}$

```{figure} ./images/elec_transitor.jpg
:name: fig_146
:align: center

```
````


