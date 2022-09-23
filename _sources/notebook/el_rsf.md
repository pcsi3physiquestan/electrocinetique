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
# Régime sinusoïdal forcé

````{admonition} Compétences
:class: tip
* Savoir que la réponse forcée d'un système linéaire à une excitation sinusoïdale est sinusoïdale de même fréquence
* Réaliser une étude fréquentielle pour étudier les caractéristiques d'un système ou sa réponse à une excitation sinusoïdale
* Utiliser une étude fréquentielle pour prévoir la réponse à un signal décomposé spectralement
* Établir et connaître l'impédance d'une résistance, d'un condensateur, d'une bobine en régime harmonique
* Remplacer une association série ou parallèle de deux impédances par une impédance équivalente
* Utiliser la construction de Fresnel et les méthodes complexes pour étudier un régime sinusoïdal for
* Relier l'acuité d'une résonance au facteur de qualité
* Mettre en évidence le rôle du facteur de qualité pour l'étude d'une résonance en tension (pour un RLC série)
* Déterminer la pulsation propre et le facteur de qualité à partir de graphes de réponse en amplitude et en phase
* Expliquer la complémentarité des informations présentes sur les graphes d'amplitudes et de phase, en particulier dans le cas d'une résonance en tension (pour un RLC série) de facteur de qualité modéré.
````

Nous avons étudié précédemment le régime forcé indépendant du temps. Mais très souvent, la grandeur (tension) d'entrée n'est pas constante et le régime forcé non plus. Nous allons voir ici l'étude d'un régime forcé particulier: le régime sinusoïdal forcé, c'est-à-dire lorsque l'entrée est un sinusoïde.

