# Première application

## Introduction

Dans cet atelier nous allons créer une première interface simple avec un peu d'interactif.

Cela nous permettra de découvrir XCode, l'organisation d'un projet et le très pratique Interface Builder.

**Notions nécessaires :** MVC, IBOutlet/IBAction, différents types de ficher (.swift, .storyboard, assets), ressources (images, données...), ratio d'image, UILabel et UIImage

## Exercice 1- Première interface

1. Créer un projet "Single view"
2. Récupérez une image de film et ajoutez la au projet
3. Reproduisez l'interface suivante (une image et deux label) :
![](/assets/Bond_UI_1.png)

## Exercice 2- Interactif

Le but ici va être d'ajouter un bouton qui permet de changer de film en changent le titre et l'image affichée à l'écran.

1. Ajoutez un bouton à l'interface
2. Ajoutez une action `buttonClicked` à ce bouton (IBAction)
3. Créez un lien entre l'image, le titre et le code de ViewController (IBOutlet)
4. Dans le code de l'action, changez l'image et le titre affichés à l'écran : `imageView.image =` et  `titleLabel.text = `

## Exercice bonus

Le layout qu'on a crée ne s'adapte pas bien aux différentes tailles de téléphone. Faisons-le de la manière la plus basique avec l'auto-resizing.

1. Testez l'interface sur les différentes tailles d'écran
2. Ajustez les masques d'autoresizing pour avoir une interface qui s'adapte bien

