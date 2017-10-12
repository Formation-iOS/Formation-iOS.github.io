# Auto Layout

## Introduction

Apple a introduit le système Auto Layout de mise en page de l'interface graphique en 2012, pour la sortie de l'iPhone 5.  
Avant, il n'y avait qu'une seule taille d'écran sur les iPhones, et le système de mise en page de l'époque, très simple, suffisait largement.

Aujourd'hui, Apple recommande de supporter iOS 10 et 11. Pour supporter tous les iPhones compatibles, on doit gérer 4 tailles différentes d'écran. Pour gérer les iPads, on rajoute encore 3 autres tailles. A cela vient s'ajouter la gestion de l'affichage en orientation paysage \(« landscape »\), en plus de l'orientation portrait.

Auto Layout est l'outil indispensable pour répondre à ces problématiques. Il permet à l'interface graphique d'une application de s'adapter aux différents devices et orientations. Auto Layout réduit, agrandit, ou déplace les différents éléments de l'interface graphique, en fonction du device.

Enfin, Auto Layout aide à gérer l'internationalisation d'une app. En effet, il permet à la mise en page de s'adapter en fonction de la longueur du texte. Cela se révèle bien utile quand on traduit une application, de l'anglais à l'allemand par exemple, car les mots allemands sont en général bien plus longs.

## Auto Layout par la pratique

Toutes les corrections des TPs sur Auto Layout sont disponibles sur GitHub.

Dans Xcode, sélectionnez File-&gt;New-&gt;Project..., puis créez un projet « Single View App», et donnez lui le nom « AutoLayout » par exemple.

### Interface builder, l'outil de création des interfaces graphiques dans Xcode

Voici à quoi ressemble la partie Interface Builder de Xcode, dans un projet qui contient déjà un bouton.

![](/assets/interface-builder.png)

### Activation de Auto Layout

Tout d'abord, assurez-vous que votre fichier Main.storyboard utilise « Auto Layout ». Cela devrait déjà être le cas.

![](/assets/xcode-ib-use-auto-layout.png)

### Édition des proprietés d'un élément de l'interface graphique

Les différentes proprietés d'un élément de l'interface graphique peuvent être éditées dans la partie « Inspector », située à droite de la fenêtre Xcode.
Par exemple, pour un UIButton, on peut configurer le titre, la taille du texte, sa couleur etc...

![](/assets/button-attributes.png)

### Menus pour ajouter des contraintes d'Auto Layout

Explorez Interface Builder, ses différents menu et onglets. En bas à droite de la partie centrale d'Interface Builder, on trouve les menus d'ajout de contraintes.

![](/assets/add-missing-constraints.png)
![](/assets/pin-constraints.png)
![](/assets/align.png)

### Affichage sur différents devices et orientations

En bas de la partie centrale d'Interface Builder, on trouve les différents devices et orientations. Ceci permet de prévisualiser le rendu de l'interface graphique, avant même de lancer l'applictaion dans le simulateur.

![](/assets/ib-devices-orientation.png)

#### Erreur dans les contraintes d'Auto Layout

S'il y a une erreur dans les contraintes d'Auto Layout, certaines lignes représentant les contraintes vont apparaître en rouge. Par ailleurs, une flèche dans un rond rouge va apparaître dans la partie « explorateur » des éléments de la vue. Cliquez sur cette flèche pour voir le détail des erreurs.

![](/assets/ib-error.png)

### Menu Editor de Xcode

Dans le menu Editor de Xcode, on retrouve également des actions déjà accessibles à d'autres endroits dans Interface Builder.

![](/assets/editor-menu.png)

### Premier exemple : les 2 boutons

Essayez de re-créer par vous même l'exemple de la demo live avec les 2 boutons de même taille qui restent toujours en bas de l'écran, quelques soient le device et l'orientation.

Pour valider que tout fonctionne comme voulu, sélectionnez les différentes vues de devices dans Interface Builder \(les iPhones et iPads\), et les orientations portrait et paysage. Également, lancez l'app dans différents simulateurs.

![](/assets/autolayout-2buttons-portrait.png)
![](/assets/autolayout-2buttons-landscape.png)

### Deuxième exemple : la galerie

Essayez de re-créer par vous même le 2ème exemple de la demo live, qui affiche un écran découpé en 4 parties égales. Chaque partie est d'une couleur donnée, et affiche une image et un texte.
Pensez bien à tenir compte de la « Safe Area ».
Cet affichage doit fonctionner quelques soient le device et l'orientation. Testez notamment dans le simulateur de l'iPhone X.

![](/assets/galerie-portrait.png)
![](/assets/galerie-landscape.png)

### Auto Layout dans les UITableView

### Auto Layout dans les UIStackView et UIScrollView

## Pour aller plus loin

### Création des contraintes d'Auto Layout dans le code

### Size-class

### Mise à jour des contraintes d'Auto Layout de manière dynamique



