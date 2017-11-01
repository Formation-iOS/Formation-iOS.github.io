# Debug, crashs et amélioration du code

## Introduction

Dans cet atelier, vous allez corriger des bugs !

Parfois l'application va planter (« crash »). Parfois son comportement ne va pas être celui attendu.
Des problèmes plus complexes vont également être abordés : bugs liés à la mauvaise utilisation de la mémoire, ou encore à la performance.

Heureusement, Xcode a de nombreux outils qui vont vous permettre de corriger les bugs plus facilement.

Dans cet atelier, nous allons reprendre l'application catalogue de films. Celle-ci est à présent plus complète, mais présente de nombreux bugs.
Votre mission est de corriger les bugs pour pouvoir publier l'application. Il est sûr qu'elle ne passera pas la review d'Apple en l'état ! 

Vous allez utiliser les différents outils fournis par Xcode pour pouvoir étudier et observer le comportement de votre application :
1. La console
2. Le debugger
3. Instruments

**Notions nécessaires :** debug, breakpoint, outlet, UIViewController life cycle, application life cycle,
delegate, optional, utilisation mémoire, retention cycle, problème de performance, threading, main thread

## Crash numéro 1

Lancez l'application. Premier crash !
A vous de jouer, utilisez la console et le debugger si besoin.

## Crash numéro 2

Vous avez corrigé le crash numéro 1, vous pouvez à présent voir la liste des films.

Cliquez sur un film de la liste pour voir son détail. Deuxième crash !

## Il ne se passe rien quand on essaye d'ajouter un film à la « WatchList »

Vous avez corrigé le crash numéro 2, vous pouvez à présent voir la vue de détail d'un film.

Cliquez sur le bouton « Ajouter à ma Watchlist ». Il ne se passe rien.

## Crash numéro 3

Vous avez fait en sorte qu'il se passe quelque chose lorsque vous cliquez sur le bouton « Ajouter à ma Watchlist ».
Mais à présent un crash se produit juste après.

## Le tab « Watchlist » ne se met pas à jour

Le tab qui affiche la « Watchlist » ne se met pas à jour quand vous ajoutez/retirez un film de la « Watchlist ».

## La vue de détail d'un film ne s'affiche pas correctement

Une partie de la vue de détail d'un film ne s'affiche pas correctement.

## La liste des films ne se met pas à jour quand on revient dans l'app

L'écran d'accueil de l'application ne se met pas à jour quand on appuye sur le bouton « home » de l'iPhone, puis qu'on revient dans l'app.
La liste de films affichés sur l'écran d'accueil est une liste de films « trending ».
La dernière date de mise à jour de cette liste est affichée en haut de la liste.

Faites en sorte que cette liste soit mise à jour quand on revient dans l'app.

## Les cellules des films n'ont pas toujours la bonne image

Si vous chargez beaucoup de films dans la liste des films, vous allez remarquer que certaines cellules affichent une image qui ne correspond pas à la description.

## Une app très gourmande en mémoire

L'application crash si vous chargez beaucoup d'images de films.

## Encore un problème de mémoire

Cliquez sur quelques films pour voir leur détail.
Ensuite, utilisez l'outil « Debug memory graph » pour observer l'utilisation de la mémoire dans l'application.

Il y a encore un problème de mémoire. Lequel ?