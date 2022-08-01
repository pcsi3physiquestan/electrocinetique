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
# Activité : Résistance d'entrée et résistance de sortie

````{sidebar} Résistance de sortie d'un GBF
:class: attention

La résistance de sortie d'un GBF est une donnée constructeur. Elle peut être affichée sur la face avant du générateur (comme sur la photo suivante), ou donnée dans une notice ou encore réglable.

```{figure} ./images/elec_gbf_re.png
:name: fig_134
:align: center
```

_La résistance d'entrée d'un voltmètre est en général donnée par le constructeur._
````
````{important} __Résistance d'entrée d'un instrument de mesure__
Un instrument de mesure comme un multimètre ou un oscilloscope possède ses propres caractéristiques électriques. Du point de vue du reste du circuit, ce comportement, en régime indépendant du temps, peut-être __modélisé__ par une résistance qu'on appelle __résistance d'entrée de l'appareil.__
````
````{important} __Résistance de sortie d'un générateur, d'une source__
Lorsqu'on utilise un générateur (GBF comme générateur basse fréquence en TP) en pratique, on règle la tension qu'il doit délivrer. Cela revient à régler la fem de la source étudiée précédemment. Néanmoins, dans une source réelle, l'intensité demandée occasionne une chute de tension qu'on __modélise__ par une résistance en série avec la fem (modèle de Thévenin). Cette résistance est appelée __résistance de sortie__ du générateur.
````

````{topic} Influence de la résistance d'entrée et de sortie  
Comme tout dipôle électrique, la résistance d'entrée d'un voltmètre ou d'un oscilloscope et la résistance de sortie d'un générateur influe sur le reste du circuit. Nous allons voir dans l'exercice à venir quelle propriété doit avoir une résistance de sortie ou une résistance d'entrée pour perturber le circuit le moins possible.

D'un point de vue pratique, on peut retenir que si la tension de sortie du GBF n'est pas la tension réglée sur le GBF, c'est probablement que la résistance de sortie du GBF influe sur le circuit de manière non négligeable.
````

## Utilisation des ponts diviseurs pour étudier l'influence des résistances d'entrée et de sortie.

Le but est autant d'apprendre à utiliser les ponts diviseurs que d'observer théoriquement l'influence des résistances d'entrée et de sortie et d'en déduire les valeurs optimales de ces grandeurs.

Dans les deux exercices posés ici, les circuits ne sont pas dessinés. __Il est vivement conseillé de s'entraîner à les dessiner__.

````{admonition} Exercice 
:class: attention

On considère un circuit constitué d'un générateur modélisé par la représentation de Thévenin $(E ;R_S)$ et d'une résistance R. L'utilisateur règle sur le générateur la tension E et attend normalement que la tension aux bornes de R soit celle qu'il a réglé.

1. Exprimer la tension aux bornes $u_R$ de la résistance R. L'utilisateur obtient ce qu'il attend en toute rigueur.
1. A quelle condition peut-on considérer que $u_R \approx E$ ? En déduire la condition que doit vérifier une impédance de sortie pour ne pas influer sur le circuit.
1. Méthode de la tension de moitié : Si l'on suppose que R est variable, pour quelle valeur de R, la tension $u_R$ vaudra E/2 ? En déduire une méthode expérimentale pour mesurer la résistance interne d'un GBF.
````

````{topic} Correction
__Q1.__  
R et $R_S$ sont en série, elles forment un pont diviseur de tension dont la tension aux bornes est E. Il vient que : $\boxed{u_R = \frac{R}{R + R_S} E}$

__Q2.__  
Il faut que $\frac{R}{R+R_S} \approx 1$ soit $\boxed{R_S << R}$



__Q3.__  
Il vient immédiatement $R = R_S$. Cette observation permet de mesurer $R_S$. C'est ce qu'on appelle la méthode de la tension de moitié.

````

```{important} 
__A retenir__

* __Influence de la résistance interne :__ Pour qu'un GBF influe peu sur le circuit, il faut que sa résistance de sortie soit très faible devant les résistances du circuit. Si cette condition n'est pas réalisée, la tension à la sortie du GBF ne sera pas la tension réglée (sa fem) mais elle sera plus faible.
* __Méthode de la tension de moitié :__ Pour déterminer la résistance de sortie d'un générateur, on réalise deux étapes:
    1. On lui branche une résistance variable $R$ dont on a réglé la valeur assez haute. On peut ainsi mesurer la valeur de la tension $E$ délivrée lorsque $R_S$ est négligeable en mesurant la tension aux bornes de $R$.
    2. On diminue $R$ jusqu'à mesurer une tension $E_2$ aux bornes de $R$. On a alors $R = R_S$.
```

````{admonition} Exercice 
:class: attention

On considère une résistance R dont on veut connaître la tension à ses bornes. On branche un voltmètre de résistance d'entrée $R_e$ en parallèle de R pour mesurer sa tension.

1. Quelle la résistance équivalente $R_{eq}$ de l'ensemble des deux résistances ?
1. On peut considérer que le circuit n'est pas influencé par le voltmètre si la résistance équivalente est à peu près égale à R. A quelle condition sur $R_e$, cette approximation est valable. En déduire les bonnes caractéristiques d'une résistance d'entrée pour un voltmètre.
1. On ne place pas dans l'approximation précédente et une intensité i arrive sur l'ensemble résistance+voltmètre. Quelle est la chute d'intensité $\Delta i = i - i_R$ avec $i_R$ l'intensité circulant dans la résistance ?
````

````{topic} Correction
__Q1.__  
On a deux résistances en parallèle donc : $\boxed{R_{eq} = \frac{R R_e}{R_e + R}}$

__Q2.__  
On veut $\frac{R_e}{R_e+R} \approx 1$ soit $\boxed{R_e >> R}$.

__Q3.__  
On a un pont diviseur de courant entre R et $R_e$ et la chute d'intensité correspond à l'intensité qui circule (loi des noeuds) dans le voltmètre. Il vient :

$\boxed{\Delta i = \frac{\frac{1}{R_e}}{\frac{1}{R}+\frac{1}{R_e}} i = \frac{R}{R_e+R} i}$

On retrouve le fait que plus $R_e$ est grande, plus la chute d'intensité sera négligeable devant i.
````

```{important} 
__A retenir__

* __Influence de la résistance interne :__ Pour qu'un voltmètre influe peu sur un circuit, il faut que son impédance d'entrée soit grande devant les impédances du circuit.
* Attention : pour un ampèremètre, il faudrait une tension faible à ses bornes donc une résistance d'entrée faible.
```