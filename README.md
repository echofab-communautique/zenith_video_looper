# ZENITH_Video_Looper

Vidéo documentation du ZENITH video looper:
{{#ev:youtube|g1TefG2o2JQ|500|right|}}

## À propos
  * Le //ZENITH vidéo looper// est un projet réalisé par Roby Provost Blanchard dans le cadre d'un cour de programmation (IMCA 398B) en collaboration avec [[http://www.echofab.org/|échoFab]].
  * Il s'agit d'un vieux réveil-radio transformé en //looper// vidéo. Tous les potentiomètres et //switchs// ont été réassigné à un microcontroleur Arduino Uno.
  * Une des idées derrière ce projet était d'avoir une interface originale, loin de l'outil traditionnel d'un VJ.

## Spécifications
  * 3 Inputs
  * 180 Frames Max Loop
  * Toggle Switch : Record
  * Switch : Input / Loop
  * Knob : Loop Lenght
  * Knob : Looop Start
  * Knob : 3 Input Selector

## Fonctionnement
  * Le ZENITH a 3 entrées vidéo indépendante, sélectionnable avec un encodeur électromécanique. L'encodeur envoie la source sélectionnée dans la carte de capture vidéo ADVC-55 qui la renvoie dans MAX/MSP.
  * Le traitement vidéo est fait dans un patch MAX/MSP, puis est renvoyé à l'écran. La résolution de la vidéo est de 640x480. Bien que certains effets vidéo sont présent dans la patch, aucun n'est présentement utilisable dans la version actuelle du projet. Une switch permet de passer de la boucle à la source sélectionnée, ce qui permet d'avoir un idée de ce que l'on enregistre. Cette fonction permet aussi de créer des rythmes dynamiques en situation de live. 
  * Le maximum d'image dans la boucle est 180. Les images sont jouées à 30 images par secondes. 
  * Deux potentiomètres assurent la longueur de la boucle ainsi que son point d'entrée. Puisque que la boucle s'allonge par son endpoint, un deuxième potentiomètre permet de régler le point d'entrée. 
  * Une switch à 4 positions permet de voir les fonctions de chaque bouton, la longueur de la boucle, ainsi que modèle actuel du looper.

## Matériel
**Software**: MAX/MSP et Arduino
**Hardware**: Canopus ADVC-55, Arduino UNO, Mac Mini, beaucoup de fils.
## Notes
* Cette machine devient vraiment intéressante lorsqu'on utilise au moins 2 sources vidéos.
* Il semblait important de ne pas connecter les //ground// des signaux vidéo avec le //ground// du système (dans le cas du "switcher" vidéo).
* Sur MAX/MSP, s'assurer que l'on ouvre le port série après le //clock//. Et qu'on spécifie en ordre; le port puis le //baudrate//.

## Média

![Zenith1](https://user-images.githubusercontent.com/65183668/84666574-8ba74c00-af21-11ea-8ced-1846bc7556dc.png)
![ZENITH1k](https://user-images.githubusercontent.com/65183668/84666576-8c3fe280-af21-11ea-9b93-1715bcaa1383.jpg)
![Zenith2](https://user-images.githubusercontent.com/65183668/84666578-8cd87900-af21-11ea-98a5-83d6066d33be.png)
![Zenith3](https://user-images.githubusercontent.com/65183668/84666582-8d710f80-af21-11ea-8b24-50703bd05d99.png)
![Zenith4](https://user-images.githubusercontent.com/65183668/84666585-8d710f80-af21-11ea-85b0-34e1e1914134.png)
![Zenithclose](https://user-images.githubusercontent.com/65183668/84666586-8e09a600-af21-11ea-9c62-fe30463e51de.png)
La machine!

Screen Shot 2013-11-25 at 13.11.46.png
Screenshot

loopermaxmsp.png
Patch max/MSP


## Journal de bord

### État
  * Fonctionnel en 0.5

### Objectifs
  * Début de la 0.6
    - Correction du fameux bug de la frame lorsqu'on passe de la source au loop. 
    - Optimiser le code**
    - Mode sample //un après l'autre//
    - Remplacer Arduino UNO par Teensy
    - Réparer le 3ième input.
    - Utiliser les boutons à l'arrière (Slow / Fast)
    - *Master Clock à 60 avec spliter (//counter 1/2 -> sel 1// pour splitter le temps)

  * Installer un écran LED
    - Afficher le mode
    - Insérer un menu pour les effects


####17 Fev 2014
  * Fin de la v0.5
    - Longueur de loop avec pot.

#### 25 Nov 2013
  * Boitier terminé (assemblé, et trous pour vidéo input)
  * 2ieme Potentiomètre assigné (offset)
  * Solidification de l'intérieur, tie-wrap

#### 22 Nov 2013
  * Programmation du looper
  * Debut du mode "loop length"
  * Pot "loudness" = nombre de frames (max 180)
  * Retrait de certaines fonction pour simplifier le code (Chroma / Text / Rota / Sampler)
