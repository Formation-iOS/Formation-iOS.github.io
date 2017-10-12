# Auto Layout

## Introduction

Apple a introduit le système Auto Layout de mise en page de l'interface graphique en 2012, pour la sortie de l'iPhone 5.  
Avant, il n'y avait qu'une seule taille d'écran sur les iPhones, et le système de mise en page de l'époque, très simple, suffisait largement.

Aujourd'hui, Apple recommande de supporter iOS 10 et 11. Pour supporter tous les iPhones compatibles, on doit gérer 4 tailles différentes d'écran.  
Pour gérer les iPAds, on rajoute encore 3 autres tailles. A cela vient s'ajouter la gestion de l'affichage en orientation paysage \(« landscape »\), en plus de l'orientation portrait.  
Auto Layout est l'outil indispensable pour répondre à ces problématiques.  
Il permet à l'interface graphique d'une application de s'adapter aux différents devices et orientations.  
Auto Layout réduit, agrandit, ou déplaçe les différents éléments de l'interface graphique, en fonction du device.

Enfin, Auto Layout aide à gérer l'internationalisation d'une app. En effet, il permet à la mise en page de s'adapter en fonction de la longueur du texte.  
Cela se révèle bien utile quand on traduit une application de l'anglais à l'allemand par exemple, car les mots allemands sont en général bien plus longs.

## Auto Layout par la pratique

### Création d'un nouveau projet dans Xcode

Dans Xcode, sélectionnez File-&gt;New-&gt;Project..., puis créez un projet « Single View App», et donnez lui le nom « AutoLayout » par exemple.

### Interface builder, l'outil de création des interfaces graphiques dans Xcode

![](/assets/interface-builder.png)

Tout d'abord, assurez-vous que votre fichier Main.storyboard utilise « Auto Layout ». Cela devrait déjà être le cas. ![](/assets/xcode-ib-use-auto-layout.png)

Explorez Interface Builder, ces différents menu et onglets.

![](/assets/add-missing-constraints.png)![](/assets/pin-constraints.png)![](/assets/align.png)![](/assets/edtior-menu.png)![](/assets/ib-devices-orientation.png)

### Premier exemple avec 2 boutons

### Deuxième exemple en ajoutant une image

### Troisième exemple avec une galerie

## Auto Layout dans les UITableView

## Pour aller plus loin

### Auto Layout dans les UIStackView et UIScrollView

### Création des contraintes d'Auto Layout dans le code

### Size-class

### Mise à jour des contraintes d'Auto Layout



