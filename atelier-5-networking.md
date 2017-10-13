# Networking

## Introduction

En général, les applications n'ont pas toutes les données dont elles ont besoin en local. Elles appellent des services via le réseau pour récupérer des données, des images etc...

Dans l'exemple de l'application catalogue de films, vous allez connecter l'app à l'API de [themoviedb.org](https://www.themoviedb.org/). Voici sa documentation : [https://www.themoviedb.org/documentation/api](https://www.themoviedb.org/documentation/api).

Pour simplifier le code qui effectue les requêtes vers cette API, nous allons utiliser un « pod », Alamofire : [https://github.com/Alamofire/Alamofire](https://github.com/Alamofire/Alamofire)

Un « pod » est une bibliothèque (« library »), une brique logicielle, pour les projets Swift et Objective-C.
Le système de gestion de dépendances qui gère les « pods » s'appelle « Cocoapods » : [https://cocoapods.org/](https://cocoapods.org/).

## Cocoapods

Tout d'abord, il faut installer Cocoapods sur votre machine. Cocoapods est un outil Ruby, et Ruby est déjà disponible sur macOS.

Ouvrez un terminal, et entrez la ligne de commande suivante :

```bash
$ sudo gem install cocoapods
```

Ensuite, à la racine de votre projet Xcode, vous devez créer un fichier appellé Podfile. Ce fichier décrit les dépendances (« pods ») de votre projet.
Ici on va utiliser le pod de Networking « Alamofire ».

Il est conseillé d'utiliser des versions exactes des pods (exemple : 4.5.1), pour que le build de votre application soit reproductible.

```ruby
platform :ios, '10.0'
use_frameworks!

target 'MyApp' do
  pod 'Alamofire', '4.5.1'
end
```

Ensuite, lancez la commande qui va installer les pods :

```bash
$ pod install
```

*Attention*, à partir de maintenant ouvrez bien le ficher App.xcworkspace dans Xcode, et plus App.xcodeproj, sinon Xcode ne saura pas où trouver les pods dont dépend votre app.

```bash
$ open App.xcworkspace
```

Pour utiliser Alamofire dans votre code, il faut l'importer de la manière suivante :

```swift
import Alamofire
```

## Networking avec Alamofire

Le support de Codable sera ajouté à Alamofire dans sa version 5.

https://github.com/Otbivnoe/CodableAlamofire ?

## Cycle de vie d'un UIViewController

## Cycle de vie d'une app
