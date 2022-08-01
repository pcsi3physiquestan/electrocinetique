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
# Méthodes
(et_filtre)=
## Etude d'un filtre
````{admonition} Exercice 
:class: attention

```{figure} ./images/elec_rl_pas_haut.png
:name: fig_201
:align: center
```
1. Déterminer le type de filtre par une étude haute et basse fréquence.
1. Déterminer la fonction de transfert du filtre et en déduire son gain réel, son gain en décibel, sa phase. On introduira la pulsation propre $\omega _0$ telle que:

\begin{equation}
\underline{H} = \frac{A j\frac{\omega}{\omega_0}}{1 + j\frac{\omega}{\omega_0}} = \frac{A jx}{1 + jx}
\end{equation}
On veut tracer le diagramme de Bode. Montrer que:

3. Le gain réel est strictement croissant
3. Il est maximal à haute fréquence. Préciser sa valeur.
3. La fonction $G_{dB}(\log(x))$ possède une asymptote oblique en $\log(x) \to - \infty$ de pente $ + 20 \rm{dB/decade}$.
3. La phase est strictement décroissante. On déterminera ses valeurs asymptotiques.
3. Tracer le diagramme de Bode.
````
````{topic} Correction
__Type de filtre__  
* A basse fréquence la bobine est assimilable à un fil, la tension s est donc nulle.
* A haute fréquence, la bobine se comporte comme un interrupteur ouvert. L'intensité circulant dans la résistance est donc nulle et la tension à ses bornes aussi. Il vient (loi des mailles) que s = e.

Le filtre a une fonction de transfert nulle à basse fréquence et non nulle à haute fréquence. C'est un filtre passe-haut.


__Fonction de transfert__  
La bobine et la résistance forment un pont diviseur de tension. La tension aux bornes de la bobine est donc:

\begin{equation}
\underline{s} = \frac{jL\omega}{R + jL\omega} \underline{e} \Longrightarrow \underline{H} = \frac{j \frac{L}{R}\omega}{1 + j \frac{L}{R}\omega}
\end{equation}
Il vient que la pulsation propre est $\omega_0 = \frac{R}{L}$.

Il vient que les caractéristiques du filtre sont:

\begin{align*}
G = \frac{Ax}{\sqrt{1 + x^2}}\\
G_{dB} = 20 \log A + 20 \log x - 10 \log \left (1 + x^2\right )\\
\varphi = \frac{\pi}{2} - \arctan x
\end{align*}

__Diagramme de Bode__  
* Le gain réel se met sous la forme $G = \frac{1}{\sqrt{1 + \frac{1}{x^2}}}$. Il vient immédiatement que le gain réel est strictement croissant.
* On en déduit la fonction atteint son maximum en $x = + \infty$. Le gain réel vaut alors 1 et le gain en décibel vaut 0. Il vient __que le diagramme de Bode possède une asymptote horizontale__ $G_{dBa,asymp}= 0$ en  $x \to + \infty$ (en $\omega \to + \infty$, c'est-à-dire à haute fréquence).
* A très basse fréquence ($\omega \to 0 \Longrightarrow x \to 0 \Longrightarrow \log x \to - \infty$), le gain réel se réécrit $G \approx x$ soit un gain en décibel $G_{dB} \approx 20 \log x$. __Le gain en décibel s'appproche donc d'une droite en fonction de $\log(x)$ de pente +20. Le gain en décibel s'exprime en...  décibel et l'abscisse $\log(x)$ se compte en décade.__ Le gain en décibel possède donc, sur un diagramme de Bode une asymptote oblique à basse fréquence de pente $+20 \rm{dB/decade}$.
* La fonction arctan étant croissante, la phase est décroissante. Ses valeurs limites sont $\pi/2$ et 0.

On peut donc tracer le diagramme de Bode:
```{figure} ./images/filtre_rl_bode.png
:name: fig_202
:align: center
```
````

````{admonition} Analyse d'un diagramme de Bode
:class: attention

On considère un filtre dont le diagramme de Bode (tracé en fonction de $\log(\omega)$)est donné ci-après.

1. Préciser le type de filtre.
1. On peut déterminer graphiquement la pulsation propre de deux manières: elle se trouve à l'intersection des asymptotes haute et basse fréquence du filtre et pour __ce filtre__, la phase à la pulsation propre vaut $- \pi/2$. Déterminer la pulsation propre par les deux méthodes et vérifier la cohérence des deux résultats.
1. Déterminer l'équation de l'asymptote oblique à la représentation $G_{dB}(log(\omega))$ sur le diagramme de Bode en gain. En déduire, dans cette zone la relation temporelle approchée entre la sortie et l'entrée.
1. On définit une fréquence de coupure comme une fréquence pour laquelle le gain est égal au gain maximal divisé par $\sqrt{2}$. Déterminer numériquement la valeur de la pulsation de coupure.

```{figure} ./images/filtre_graphique_bode.png
:name: fig_208
:align: center

```
````
````{topic} Correction
>Le gain en décibel est non nul à basse fréquence (quand $\log(x)$ tend vers $-\infty$) et nul à haute fréquence (le gain en décibel tend vers $-\infty$). Il s'agit donc d'un filtre passe-haut.
>
>On trouve $\omega_0 \approx 10^3 \rm{rad.s^{-1}}.$
>
>On trouve une pente de $-40dB/decade$. L'ordonnée pour $\log(\omega) = \log(\omega_0)$ est 6. L'équation de l'asymptote est donc $Asymp(\log(\omega)) = 6 - 40 \log(\omega/\omega_0)$. On peut remarquer que la phase est presque égale à $-\pi$. On peut donc considérer que la fonction de transfert est un réel négatif soit: $\underline{H} \approx - \frac{2}{{(\frac{\omega}{\omega_0})}^2}$. En temporelle, celà donne: $s(t) = 2 \omega_0^2 \int (\int (e(t)))$: c'est un comportement double intégrateur.
>
```{margin}
Voici un exemple où la pulsation propre et la pulsation de coupure ne sont pas égales.

Les graduations données ici correspondent à un diagramme semi-logarithmique, c'est-à-dire que les graduations __correspondent à x et non à $\log(x)$__.
```
>On veut un gain réel égal à $G_{\max}/\sqrt{2}$ soit un gain en décibel égal à $G_{dB,\max} - 3dB$ soit 3dB. On trouve $\omega_c = 6 * 10 ^ 2 \rm{rad.s^{-1}}$.
````

## Réponse d'un filtre

````{admonition} Réponse d'un filtre à des sinusoïdes
:class: attention

On reprend le filtre précédent dont la fonction de transfert est $\underline{H} = \frac{jx}{1 + jx}$ avec $x = \frac{\omega}{\omega_0}$ et $\omega_0 = \frac{R}{L}$.

1. Nous allons commencer par établir la réponse exacte du filtre.
    1. Exprimer le signal de sortie $s(t)$ pour un signal d'entrée sinusoïdal de pulsation $\omega$ et d'amplitude $e_m$.
    2. On considère un signal d'entrée $e(t) = e_1 \cos \omega_1 t + e_2 \cos \omega_2 t$ avec $\omega_1 = 0.1 \omega_0$ et $\omega_2 = 10 \omega_0$. Exprimer la réponse exacte du filtre.
2. Nous allons maintenant assimiler la réponse du filtre à sa version idéale.
    1. A basse fréquence, simplifier l'expression du gain et de la phase à l'ordre 0.
    1. A haute fréquence, simplifier l'expression du gain et de la phase à l'ordre 0.
    1. On considère un signal d'entrée $e(t) = e_1 \cos \omega_1 t + e_2 \cos \omega_2 t$ avec $\omega_1 = 0.1 \omega_0$ et $\omega_2 = 10 \omega_0$. Dans le cadre d'approximation par un filtre idéal, exprimer la tension de sortie.
    1. Comparer graphiquement les représentations graphiques de la réponse exacte et de la réponse "tout-ou-rien" qui vient d'être établie.
3. Nous allons maintenant assimiler la réponse du filtre à ses comportements asymptotiques établies lors du tracé du diagramme de Bode.
    1. A basse fréquence, on rappelle qu'on a montré que la fonction de transfert peut se réécrire $\underline{H} = j x$. En déduire la relation temporelle entrée-sortie à basse-fréquence. Comment se comporte le filtre pour un signal dont le spectre est entièrement inférieur à la bande fréquence $\omega_0$ ?
````
````{topic} Correction
```{margin} Réponse exacte
C'est le même principe qu'en RSF. _Attention à ne pas oublier l'amplitude d'entrée et la phase à l'origine de l'entrée.
```
>__Réponse exacte__  
>\begin{align*}
s(t) &= \frac{e_m \frac{\omega}{\omega_0}}{\sqrt{1 + {\left(\frac{\omega}{\omega_0}\right)}^2}}\cos \left(\omega t + \frac{\pi}{2} - \arctan \frac{\omega}{\omega_0}\right)\\
s(t) &= \frac{0.1 e_1}{\sqrt{1.01}}\cos \left(0.1 \omega_0 t + \frac{\pi}{2} - \arctan 0.1\right) + \frac{10 e_1}{\sqrt{101}}\cos \left(10 \omega_0 t + \frac{\pi}{2} - \arctan 10\right)
\end{align*}
>
```{margin} BF et HF
*Basse fréquence = fréquence petite devant $\omega_0$
*Haute fréquence = fréquence grande devant $\omega_0$
```
>__Réponse idéale__  
>A basse fréquence, la fonction de transfert est se résume à $\underline{H} = 0$ d'où un gain de 0 et à haute fréquence, elle se résume à $\underline{H} = 1$ d'où un gain de 1.
>
>Dans le cadre d'approximation par un filtre idéal, on va associer le gain maximal aux fréquences conservées (ici les hautes fréquences, c'est un filtre passe haut) et un gain nul pour les autres (ici les basses fréquences). A haute fréquence la phase est aussi quasi nulle. Il vient donc que: $s(t) = e_2 \cos \left ( 100 \omega_0 t \right )$.
>
>On a représenté ci-dessous la réponse exacte (gauche) et la réponse approchée (droite).On observe que les signaux sont à peu près identiques. L'utilisation du modèle idéal est ici plutôt valable car les fréquences sont suffisamment loin de la fréquence propre pour que la fonction de transfert soit proche de sa valeur limite HF et BF.
>
```{figure} ./images/filtre_rl_somme.png
:name: fig_203
:align: center
```
>
>__Réponse asymptotique__  
>A basse fréquence, la relation se réécrite $\underline{s} = \frac{j \omega}{\omega_0} \underline{e}$ soit en temporel $s(t) = \frac{1}{\omega_0}\frac{\rm{d}e}{\rm{dt}}(t)$. Pour les basses fréquences, le filtre se comporte comme un dérivateur. (On parlera de pseudo-dérivateur car il ne se comporte comme dérivateur que pour une partie du spectre).
````

````{admonition} Cas d'un signal d'entrée périodique - Préambule
:class: attention

On considère le filtre ci-dessous.

1. Déterminer rapidement le type de filtre puis la fonction de transfert. En déduire le gain réel et la phase. On mettra la fonction de transfert sous la forme $\underline{H} = \frac{A}{1 + j x}$ avec x la pulsation réduite.
1. Justifier que le gain réel est strictement décroissant. Montrer que la représentation du gain en décibel sur un diagramme de Bode $G_{dB}(\log(x))$ admet une asymptote oblique à haute fréquence de pente $- 20 \rm{dB/decade}$
1. On définit la bande passante du filtre comme la gamme de fréquence où le gain réel est supérieur au gain maximal divisé par $\sqrt{2}$. Déterminer la bande passante.

```{figure} ./images/elec_rc_passe_bas.jpg
:name: fig_204
:align: center
:width: 40%
```
````
````{topic} Correction
>A basse fréquence, le condensateur se comportant comme un interrupteur ouvert, il impose une intensité nulle. La loi des mailles donne donc s = e. A haute fréquence, le condensateur se comportant comme un fil, il vient s=0. Il s'agit donc d'un filtre passe-haut.
>
>La résistance et le condensateur forment un pont diviseur de tension (on rappelle qu'on étudie le filtre avec une intensité sortante nulle) donc: $\underline{s} = \frac{1}{1 + j RC \omega} \underline{e}$. Il vient une pulsation propre $\omega_0 = \frac{1}{RC}$.
>
>Le gain réel est donc $G = \frac{1}{\sqrt{1 + x^2}}$ et la phase $\phi = - \arctan x$
>
>La décroissance du gain réel est triviale. A haute fréquence, la fonction de transfert devient $\underline{H} \approx \frac{1}{jx}$ soit un gain en décibel $G_{dB} \approx -20 \log x$. Il vient bien une pente de $- 20 \rm{dB/decade}$.
>
```{figure} ./images/filtre_rc_bode.png
:name: fig_205
:align: center
```
>Le gain réel étant strictement décroissant, le gain maximal est le gain à fréquence nulle (gain statique) soit ici 1. On cherche donc à résoudre l'inégalité:
>
>\begin{equation}
\frac{1}{\sqrt{1 + x^2}} \geq \frac{1}{\sqrt{2}} \Longrightarrow x\leq 1 \Longrightarrow \omega \leq \omega_0
\end{equation}
````

````{admonition} Cas d'un signal d'entrée périodique 
:class: attention

On considère le filtre précédent et on envoie en entrée un signal créneau d'amplitude E. On admet que la décomposition spectrale du signal créneau est:

\begin{equation}
e(t) =\frac{4E}{\pi} \sum\limits_{k=0}^{\infty}\frac{\sin \left((2k+1)2\pi f t\right)}{2k+1}
\end{equation}

1. Donner la réponse exacte du filtre pour une fréquence du créneau $f = f_0$ avec $f_0$ la fréquence propre associée à la pulsation propre.
1. Donner une réponse approchée du filtre en assimilant sa réponse à celle d'un filtre idéal lorsque $f = f_0/2$.
1. Déduire de la fonction de transfert la relation temporelle entrée-sortie à haute fréquence. Quel comportement possède le filtre dans ce domaine spectral ? En déduire une réponse approchée du filtre en utilisant ses comportements asympotiques lorsque $f = 10 f_0$
````

````{topic} Correction
>__Réponse exacte__  
>\begin{equation}
s(t) =\frac{4E}{\pi} \sum\limits_{k=0}^{\infty}\frac{1}{\sqrt{1 + {\left(2k+1\right)}^2}} \frac{\sin \left((2k+1)2\pi f t - \arctan (2k+1) \right)}{2k+1}
\end{equation}
>
>__Réponse idéale__  
>Nous avons trouver que la bande passante correspond aux fréquences inférieures à $f_0$. Dans un filtre idéal, le gain dans la bande passante serait le gain maximale soit ici 1. Hors de la bande passante, ce serait un gain nul. Pour $f = f_0/2$, seul le fondamental de fréquence $f_0/2$ est dans la bande passante, la fréquence de l'harmonique suivant étant $3f_0/2$. Il vient que le signal de sortie approché se résume à $s(t) \approx \frac{4E}{\pi} \sin\left (\pi f_0 t\right )$
>
>On représente ci-dessous la réponse exacte (gauche) calculée pour le même signal et la réponse approchée (droite).On remarque que l'utilisation du modèle idéal n'est PAS valable ici. Celà vient du fait qu'un filtre d'ordre 1 n'attenue pas suffisamment les composantes hors de la bande passante qui son proche de la pulsation de coupure: elle influent donc sur l'allure du signal. Cela n'invalide pas l'étude demanière approchée dans le cas général. Nous l'utiliserons souvent mais il faut garder à l'esprit que pour des fréquences trop proches du passage passant-filtré et pour des ordres de filtre faible, cette approximation peut s'écarter de la réponse exacte.
>
```{figure} ./images/filtre_rc_exact_app.png
:name: fig_206
:align: center
```
>__Réponse asymptotique__  
>La fonction de transfert à haute fréquence s'écrit $\underline{H} \approx \frac{1}{j \frac{\omega}{\omega_0}}$ soit en temporelle $s(t) = \omega_0 \int e(t)$. Le filtre se comporte à haute fréquence comme un intégrateur (on parlera de pseudo-intégrateur car il n'intègre pas tout le signal).
>
>Le créneau que l'on envoie possède tout son spectre dans la partie intégrée. Il vient que le signal est intégré. Celà donnera en sortie un signal triangulaire (intégration de parties constantes).
>
>On représente ci-dessous la réponse exacte. On observe qu'effectivement le signal est intégré. La qualité de l'approximation tient du fait qu'une approximation par les asymptotes est plus fine qu'une approximation "tout ou rien" et __que les fréquences sont suffisamment éloignées de la fréquence propre pour être considérées comme haute fréquence.__

```{figure} ./images/filtre_rc_integ.png
:name: fig_207
:align: center
```
````
