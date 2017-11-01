# Navigation

## Introduction

Dans cet atelier nous allons créer une liste de film. En cliquant sur un film, nous allons arriver sur la fiche détaillée de ce film

Cela nous permettra de travailler sur les transitions entre les écrans.

**Notions nécessaires :** Différents conteneur de navigation, transitions et type d'affichage, navigationController delegate et data source, segue, cellules statiques et cellules dynamiques

## Exercice 1- TableView statique

1. Créer une TableView avec 4 cellules de film statiques de type Basic. Laissez le layout tel quel.
2. Créez un écran basique avec un fond rouge par exemple
3. Au click sur la cellule ouvrez cet écran en modal (presentModally dans le storyboard)
4. Créer une classe DetailViewController
5. Connectez la vue rouge avec la classe DetailViewController (Custom class : DetailViewController dans le storyboard)
6. Ajoutez un bouton fermer à la vue et créez une IBAction closeButtonClicked: dans le code de DetailViewController
7. Dans le code de closeButtonClicked, cachez la vue modale (dismiss)

![](/assets/Navigation_1.png)


## Exercice 2- Navigation Controller

Nous allons créer une navigation classique à base de 'Push'

1. Intégrez votre liste de film dans un NavigationController
2. Au click sur la cellule ouvrez l'écran rouge en mode push. Pour cela tirez des liens dans le storyboard.

## Exercice 3 - Données dynamiques

Nous allons maintenant afficher les données que l'on a parsé dans l'atelier précédent.

1. Créez une classe MovieCell qui dérive de UITableViewCell avec les outlets pour l'image et le titre
2. Créez un écran de détail de film avec les bons outlets (vous pouvez reprendre l'écran du premier atelier)
3. Au click sur la cellule passez les informations du film à l'écran de détail : utilisation de instantiateViewController pour créer l'écran et  tableView:didSelectRowAtIndexPath: pour réagir au click
![](/assets/Navigation_ListeDynamique.png)




