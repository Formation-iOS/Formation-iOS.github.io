# Debug, crashs et amélioration du code

## Introduction

Dans cet atelier, vous allez corriger des bugs !

Parfois l'application va planter (« crash »). Parfois son comportement ne va pas être celui attendu.
Des problèmes plus complexes vont également être abordés, comme des bugs liés à la mauvaise utilisation de la mémoire.

Heureusement, Xcode a de nombreux outils qui vont vous permettre de corriger les bugs plus facilement.

Dans cet atelier, nous allons reprendre l'application catalogue de films. Celle-ci est à présent plus complète, mais présente de nombreux bugs.
Votre mission est de corriger les bugs pour pouvoir publier l'application. Il est sûr qu'elle ne passera pas la review d'Apple en l'état ! 

Vous allez utiliser les différents outils fournis par Xcode pour pouvoir étudier et observer le comportement de votre application :
1. La console
2. Le debugger
3. L'outil « Debug memory graph »

**Notions nécessaires :** debug, breakpoint, outlet, UIViewController life cycle, application life cycle,
delegate, optional, utilisation mémoire, retention cycle, threading, main thread

Clonez ce repository qui contient l'application à debugger : [https://github.com/Formation-iOS/Atelier7_Debug](https://github.com/Formation-iOS/Atelier7_Debug).

## Crash numéro 1

Lancez l'application. Premier crash !
A vous de jouer, utilisez la console et le debugger si besoin.

## Crash numéro 2

Vous avez corrigé le crash numéro 1. Entrez votre « username » et « password ».
Vous pouvez à présent voir la liste des « Popular Movies».

Cliquez sur un film de la liste pour voir son détail. Deuxième crash !
Après la correction de ce crash, assurez-vous que l'écran de détail affiche bien le détail du film sélectionné dans la liste.

## Il ne se passe rien quand on essaye d'ajouter un film à la « WatchList »

Vous avez corrigé le crash numéro 2, vous pouvez à présent voir la vue de détail d'un film.

Cliquez sur le bouton « Add to watchlist ». Il ne se passe rien.

## Crash numéro 3

Vous avez fait en sorte qu'il se passe quelque chose lorsque vous cliquez sur le bouton « Ajouter à ma Watchlist ».
Mais à présent un crash se produit juste après.

## La vue de détail d'un film ne s'affiche pas correctement

Une partie de la vue de détail d'un film ne s'affiche pas correctement : la description du film est coupée.

## Les cellules des films n'affichent pas correctement les notes moyennes en rouge

Dans la liste des films, la note d'un film devrait s'afficher en rouge si la note est plus grande que 7,5. Mais ce n'est pas le cas.

## Un problème de mémoire

Cliquez sur quelques films pour voir leur détail.
Ensuite, utilisez l'outil « Debug memory graph » pour observer l'utilisation de la mémoire dans l'application.

Il y a un problème de mémoire. Lequel ?

Si vous avez identifié le problème, mais ne savez pas comment le résoudre, demandez au formateur.

## Le tab « Watchlist » ne se met pas à jour

S'il a déjà été affiché une fois le tab qui affiche la « Watchlist » ne se met pas à jour quand vous ajoutez un film à la « Watchlist ».
Indication : utilisez le [NotificationCenter](https://developer.apple.com/documentation/foundation/nsnotificationcenter).

- d'un côté, faites un « post » : `NotificationCenter.default.post(name: Notification.Name("SomeNotificationName"), object: nil)`
- de l'autre, utilisez un « observer » : `NotificationCenter.default.addObserver(self, selector: #selector(SomeClass.someFunction), name: Notification.Name("SomeNotificationName"), object: nil)`
