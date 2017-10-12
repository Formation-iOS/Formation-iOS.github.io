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

### Interface Builder, l'outil de création des interfaces graphiques dans Xcode

#### Vue d'ensemble d'Interface Builder \(ou « IB »\) ![](/assets/interface-builder.png)

#### Activation d'Auto Layout

Tout d'abord, assurez-vous que votre fichier Main.storyboard utilise « Auto Layout ». Cela devrait déjà être le cas. ![](/assets/xcode-ib-use-auto-layout.png)

#### Menus d'ajout des contraintes

Explorez Interface Builder, ses différents menu et onglets.

Il y a tout d'abord les menus d'ajout des contraintes d'Auto Layout, en bas à droite de la zone centrale.![](/assets/add-missing-constraints.png)![](/assets/pin-constraints.png)![](/assets/align.png)

#### Édition des proprietés d'un élément graphique

Si on veut changer les proprietés d'un élément, on peut les modifier dans la partie « Inspector » sur la droite.![](/assets/button-attributes.png)

#### Affichage sur différents devices et orientations

On peut tester son interface graphique sur différents devices \(iPhones ou iPads\), et dans différentes orientations via la zone qui affiche des devices située en bas.![](/assets/ib-devices-orientation.png)

#### Ajouter des contraintes entre 2 éléments de l'interface graphique

En tenant la touche « ctrl » enfoncée, puis en cliquant et en gardant enfoncé sur un élément de l'interface graphique \(ex : un bouton\), un ligne bleue apparaît. En déposant sur un autre élément \(ex : un autre bouton\), on peut faire apparaître un menu d'édition des contraintes Auto Layout liant ces 2 éléments.![](/assets/click-drag.png)![](/assets/click-drag-menu.png)

#### Menu Editor de Xcode

Enfin, certaines actions d'interface builder déjà mentionnées peuvent être retrouvées dans le menu « Editor » d'Xcode.![](/assets/edtior-menu.png)

### Premier exemple avec 2 boutons

### Deuxième exemple en ajoutant une image

### Troisième exemple avec une galerie

## Auto Layout dans les UITableView

## Pour aller plus loin

### Auto Layout dans les UIStackView et UIScrollView

### Création des contraintes d'Auto Layout dans le code

### Size-class

### Mise à jour des contraintes d'Auto Layout



