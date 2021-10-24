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
# Caractéristiques générales

## Bande passante et fréquence de coupure

````{important} __Définition : Bande passante__

La __bande passante__ d'un filtre est l'intervalle de fréquence pour lesquelles le gain réel est supérieur au gain maximal divisé par $\sqrt{2}$.

````

````{important} __Définition : Fréquence de coupure__

Les __fréquences de coupure__ sont les fréquences telles que le gain réel soit égal au gain maximal divisé par $\sqrt{2}$.

````


En général, on choisit la bande passante comme la bande de fréquence qu'on désire conserver (ou pour fixer la bande filtrée). Mais les filtres n'est pas idéal (la chute du gain n'est pas brutal à la fréquence de coupure), il est souvent nécessaire de garder une marge.


## Caractère pseudo-dérivateur et pseudo-intégrateur

### Comportement dérivateur

````{important} __Fondamental : Comportement dérivateur__

Un système dérivateur est un système dont la relation temporelle s'écrit $s(t) = \frac{K}{\omega_0}\frac{\rm{d}e}{\rm{dt}}(t)$. La fonction de transfert d'un tel système s'écrit: $\underline{H} = jK \frac{\omega}{\omega_0}$.

En pratique, on ne peut réaliser un dérivateur pur stable (à cause des hautes fréquences). On réalise donc un circuit possèdant un __comportement dérivateur__, c'est-à-dire que la fonction de transfert sera égale (approximativement)à celle d'un dérivateur sur une gamme de fréquence (__les basses fréquences__). On parle de __pseudo-dérivateur__.

````

````{admonition} Exercice Exemple de filtre pseudo-dérivateur
:class: attention

Considérons un filtre dont la fonction de transfert est $\underline{H} = \frac{j \frac{\omega}{\omega_0}}{1 + j \frac{\omega}{\omega_0}}$. A basse fréquence ($\omega \ll \omega_0$), la fonction de transfert devient $\underline{H} \approx j \frac{\omega}{\omega_0}$ soit une relation temporelle de type dérivateur.

````

````{important} __Fondamental : Asymptote sur un diagramme de Bode__

Un comportement pseudo dérivateur se traduit sur un diagramme de Bode par une asymptote oblique de pente $+20 \rm{dB/decade}$

````


__Démonstration__  
Il suffit de prendre le gain réel puis le gain en décibel de la fonction de transfert approchée $\underline{H} \approx jK\frac{\omega}{ \omega_0}$ soit $G_{dB} \approx 20 \log \frac{K}{\omega_0} + 20 \log \omega$.



__N dérivation__  
On pourra généraliser cette étude à une double dérivation et lui associer une asymptote de +40dB/decade sur un diagramme de Bode.


### Comportement intégrateur

````{important} __Fondamental : Comportement intégrateur__

Un système intégrateur est un système dont la relation temporelle s'écrit $s(t) = K \omega_0 \int e(t)$. La fonction de transfert d'un tel système s'écrit: $\underline{H} = \frac{K}{j \omega / \omega_0}$.

En pratique, on ne peut réaliser un intégrateur pur stable (à cause des basses fréquences). On réalise donc un circuit possèdant un __comportement intégrateur__, c'est-à-dire que la fonction de transfert sera égale (approximativement)à celle d'un intégrateur sur une gamme de fréquence (les hautes fréquences). On parle de __pseudo-intégrateur__.

````

````{admonition} Exercice Exemple de filtre pseudo-intégrateur
:class: attention

Considérons un filtre dont la fonction de transfert est $\underline{H} = \frac{1}{1 + j \frac{\omega}{\omega_0}}$. A haute fréquence ($\omega \gg \omega_0$), la fonction de transfert devient $\underline{H} \approx \frac{1}{j \frac{\omega}{\omega_0}}$ soit une relation temporelle de type intégrateur.

````

````{important} __Fondamental : Asymptote sur un diagramme de Bode__

Un comportement pseudo intégrateur se traduit sur un diagramme de Bode par une asymptote oblique de pente $-20 \rm{dB/decade}$

````


__Démonstration__  
Il suffit de prendre le gain réel puis le gain en décibel de la fonction de transfert approchée $\underline{H} \approx \frac{K}{j \omega / \omega_0}$ soit $G_{dB} \approx 20 \log K\omega_0 - 20 \log \omega$.



__N intégration__  
On pourra généraliser cette étude à une double intégration et lui associer une asymptote de pente -40dB/decade sur un diagramme de Bode.


