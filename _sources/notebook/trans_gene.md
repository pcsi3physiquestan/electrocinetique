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
# Régime transitoire (1): Caractéristiques générales

````{admonition} Compétences
:class: tip
* Distinguer, sur un relevé expérimental (évolution temporelle), régime transitoire et régime permanent.
* Interpréter et utiliser les continuités de la tension aux bornes d'un condensateur ou de l'intensité dans une bobine.
* Établir les conditions initiales d'un circuit.
* Établir l'équation différentielle vérifiée par une grandeur électrique dans un circuit.
* Déterminer analytiquement la réponse temporelle à partir de l'équation différentielle qu'elle doit vérifiée.
* Déterminer l'état d'un système dans un régime forcé indépendant du temps en utilisant les comportements des bobines et condensateurs dans ce genre de régime.
````

Jusqu'à présent, nous avons uniquement étudier des régimes indépendant du temps. Si ces régimes peuvent être très utiles, il n'en reste pas moins que dans de nombreux cas, le système va évoluer dans le temps.

En effet, il peut s'opérer des perturbations extérieures où la variation rapide d'une grandeur (une commande, un élément extérieur, la fermeture/ouverture d'un interrupteur). Le système va alors évoluer pour s'acheminer vers un nouveau régime __forcé__ par la nouvelle configuration du système.

Durant cette évolution - ce __régime transitoire -__ toutes les grandeurs vont évoluer dans le temps suivant des caractéristiques imposées par le circuit. Ces caractéristiques seront accessibles par l'étude du circuit et des réponses, soit par des études graphiques (évolution temporelle), soit par une étude analytique (établissement de __l'équation différentielle__ qui régit l'évolution des grandeurs). On pourra ainsi distinguer plusieurs impacts :

* l'__état initial__ du circuit, qui sera représenté analytiquement par __les conditions initiales__ de l'équation différentielle influencera notamment les constantes d'intégration. Nous apprendrons à déterminer ces conditions initiales en étudiant le circuit avant et après la brusque perturbation  initiale. Nous aurons besoin d'étudier des circuits dans des régimes indépendants du temps mais __comportant des bobines et des condensateurs__ et de savoir comment traiter la discontinuité introduite par la perturbation. Apparaîtront ainsi des grandeurs qui sont nécessairement __continues__ et qui sont fondamentales pour l'étude des régimes transitoires.

* l'__état final__ du circuit, qui correspond au nouveau régime forcé. Dans un premier temps, ce régime forcé sera indépendant du temps et donc analysable comme tel. De plus, la résolution de l'équation différentielle permettra de le déterminer d'une autre manière.

* l'__évolution durant le régime transitoire__ qui sera déterminée graphiquement ou par résolution de l'équation différentielle. Nous observerons notamment les différences et similitudes entre les équations différentielles qui régissent l'évolution de différentes grandeurs d'un même circuit.

