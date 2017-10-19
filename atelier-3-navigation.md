UITableViewController

Remplir cells dynamiquement

Utiliser Segue pour passer info de la cell cliquée


# Navigation

## Introduction

Dans cet atelier nous allons créer une liste de film. En cliquant sur un film, nous allons arriver sur la fiche détaillée de ce film

Cela nous permettra de travailler sur les transitions entre les écrans.

**Notions nécessaires :** Différents conteneur de navigation, transitions et type d'affichage, navigationController delegate et data source, segue, cellules statiques et cellules dynamiques

## Exercice 1- TableView statique

1. Créer une TableView avec 3 cellules de film statiques :
[SCREENSHOT]
2. Au click sur la cellule ouvrez l'écran de détail en modal (toujours le même écran pour l'instant)

## Exercice 2- Navigation Controller

Nous allons créer une navigation classique à base de 'Push'

1. Intégrez votre liste de film dans un NavigationController
2. Au click sur la cellule ouvrez l'écran de détail en mode push

## Exercice 3 - Données dynamiques

Nous allons maintenant afficher les données que l'on a parsé dans l'atelier précédent.

1. Créez une classe MovieCell avec les outlets pour l'image et le titre
2. Au click sur la cellule passez les informations du film à l'écran de détail (utilisation de tableView:didSelectRowAtIndexPath:)





