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
# Dipôles et circuits linéaires

````{admonition} Compétences
:class: tip
* Étudier la caractéristique statique d'un dipôle pouvant être non linéaire.
* Utiliser les relations entre l'intensité et la tension
* Connaître les relations intensité-tension dans les cas usuels (résistance, bobine, condensateur, source)
* Citer les ordres de grandeurs des composants R, L et C
* Exprimer la puissance dissipée par effet Joule
* Exprimer l'énergie stockée dans un condensateur ou une bobine
* Remplacer une association série ou parallèle de deux résistances par une résistance équivalente
* Modéliser une source non idéale en utilisant la représentation de Thévenin
* Établir et exploiter les relations de diviseurs de tension ou de courant
* Appréhender les conséquences des résistances d'entrée et de sortie des appareils sur le fonctionnement du circuit.
````

Nous allons ici présenter les informations nécessaires à l'étude des dipôles et principalement les relations intensité-tension appelées aussi __équation d'évolution.__ Nous en profiterons pour voir les caractéristiques des principaux dipôles __linéaires__ utilisés dans les circuits : résistance, bobines, condensateurs et sources.

A travers l'analyse de circuit, nous établirons certaines propriétés d'associations de dipôles (résistances) et la modélisation d'instruments réels par des modèles simple (modèle de __Thévenin__, __résistance d'entrée et de sortie__).

A la fin de ce chapitre, vous devrez être capable de mettre en équation et d'étudier tout circuit __linéaire__ en régime indépendant du temps et à se préparer à étudier des régimes variables.
