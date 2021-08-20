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
# Cahier des charges d'un filtre

## Exploiter un cahier des charges


Cet exercice sera corrigé en classe.


````{admonition} Exercice 
:class: attention

On désire construire un multimètre analogique fonctionnant en mode DC, c'est-à-dire capable de fournir une tension de sortie proportionnelle à la valeur moyenne du signal. On veut utiliser pour cela un filtre linéaire dont le but serait de ne sélectionner que la valeur moyenne du signal. La tension alors mesurée commande la position d'une aiguille sur un cadran calibrée pour permettre la lecteur de la tension correspondante. On suppose que cette commande transforme le signal électrique en signal mécanique sans déformation.

On désire construire un filtre d'ordre 1 permettant de mesurer la valeur moyenne de tout signal de fréquence supérieur à 100Hz. On propose alors le cahier des charges suivants suivant:

* Pour un signal continu, le gain réel doit être de 1
* La pulsation de coupure est supérieure à 10Hz de manière à avoir un gain relativement plat pour les faibles fréquences (si l'utilisateur fait "varier" la valeur moyenne lentement).
* Pour des fréquences supérieures à 100Hz, le gain réel doit être inférieur à 0,2 (Pour pouvoir considérer leur influence en sortie négligeable: on mesure ainsi bien la valeur moyenne, enfin, on espère!)

1. Quel type de filtre doit être utilisé?
1. Que doit valoir le gain statique?
1. Représenter dans un diagramme de Bode (on prendra $\log(f)$ comme abscisse puisqu'on a pas d'information sur la fréquence de coupure) l'allure d'un diagramme de Bode en gain compatible.
1. Quelle est la pente minimale de l'asymptote haute fréquence (on rappelle que les asymptotes se croisent à la pulsation propre). Un filtre d'ordre 1 est-il acceptable ?
1. Proposer un montage simple en précisant les valeurs des composants.
1. Avec la fonction de transfert précédemment choisie, exprimer le rapport: $\eta = \frac{G(100Hz)}{G(10Hz)}$.
1. On envoie sur le filtre un signal $U_E(t) = U_E(1+\cos(2 \pi f t))$ avec $f =100 \rm{Hz}$. Donner l'expression générale de la tension du sortie du filtre sans approximation.
1. On s'arrange pour que l'angle entre la position de l'aiguille au zéro et la position de l'aiguille correspondant à la moyenne $U_E$ soit $90^{\circ}$. Déterminer l'amplitude de la vibration de l'aiguille. Que représenterait cette vibration pour l'expérimentateur. Commenter.
1. On va donc imposer un cahier des charges plus contraignant plus contraignant: on veut que pour un signal comme celui de la question 6., l'amplitude résiduelle due à la partie variable représente moins de $1\%$ de la valeur moyenne. Représenter un diagramme de Bode en gain compatible.
1. Montrer qu'un filtre d'ordre 1 ne peut satisfaire une telle contrainte. Est-ce qu'il filtre d'ordre 2 est compatible ?

````

