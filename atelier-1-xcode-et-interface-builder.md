# Première application

## Introduction

Dans cet atelier nous allons créer une première interface simple avec un peu d'interactif.

Cela nous permettra de découvrir Xcode, l'organisation d'un projet et le très pratique Interface Builder.

**Notions nécessaires :** MVC, IBOutlet/IBAction, différents types de ficher (.swift, .storyboard, assets), ressources (images, données...), ratio d'image, UILabel et UIImage

## Exercice 1- Première interface

1. Dans Xcode, créez un projet "Single View App"
2. Récupérez une image de film et ajoutez la au projet : [james-bond.jpg](/tutorialFiles/james-bond.jpg)
3. Reproduisez l'interface ci-dessous (une image et deux label).

Pour l'instant, ne vous inquiétez pas si le layout s'adapte mal aux tailles d’écrans.
Dans Interface Builder, sélectionnez "View as iPhone 8", et lancez avec le simulateur iPhone 8 également.

![](/assets/Bond_UI_1.png)

## Exercice 2- Interactif

Le but ici va être d'ajouter un bouton qui permet de changer de film en changent le titre et l'image affichée à l'écran.

1. Ajoutez un bouton à l'interface
2. Ajoutez une action `buttonClicked` à ce bouton (IBAction)
3. Créez un lien entre l'image, le titre et le code de ViewController (IBOutlet)
4. Dans le code de l'action, changez l'image et le titre affichés à l'écran : `imageView.image = UIImage(named:"NOM")` et  `titleLabel.text = `

