# Parsing de données

## Introduction

Dans cet atelier nous allons créer un modèle de données correspondant à la base de TheMovieDB.

Cela nous permettra de commencer à utiliser les concepts de Swift. Notamment les optionnels et les variables.

**Notions nécessaires :** optionals \(init et cast\), MVC, déclaration de variables, extensions, format de dates, format de string

## Exercice 1- Création du modèle

Dans un nouveau projet Xcode \(Single View Template\) créez une classe Movie avec :

* un titre : `String`
* un synopsis : `String`
* une note moyenne : `Float`
* une date de sortie : `Date`

## Exercice 2 - Parsing naïf

Le but va être de parser le fichier suivant : [BestMovie.json](/ressources/BestMovie.json)

1. Ajoutez le fichier BestMovie.json à votre projet 
2. Ajoutez le fichier [JSONHelper.swift](/ressources/JSONHelper.swift) \(c'est une extension pour récupérer facilement un tableau de dictionnaires à partir d'un fichier json local en utilisant `JSONSerialization`\)
3. Transformez le contenu du fichier en un tableau de dictionnaire
4. Parcourez ces dictionnaires pour créer des objets de type Movie. Pour la date, utilisez un `DateFormatter`. Pour les autres valeurs, faites un cast.
5. Ajoutez une fonction description à la classe movie et faites un print des objets récupérés

**Conseil :** dans un premier temps considérez que les données sont parfaitement remplies. Cela va vous faire gagner du temps avec les optionnals. Dans un deuxième temps, faites un parsing plus robuste.

## Exercice 3 - Parsing à la mode Swift 4

Le but de l'étape 2 était surtout de vous faire manipuler du Swift. En pratique, on fait rarement ce processus à la main. Depuis Swift 4 on peut utiliser le protocole `Codable` pour cela.

1. Adaptez votre projet pour qu'il utilise le protocole `Codable` et `JSONDecoder`

**Pour aller plus loin**: on est ici dans un cas simple mais le protocole semble suffisament puissant pour couvrir les cas plus complexes : [voir cet excellent tutorial de Ben Scheirman](http://benscheirman.com/2017/06/ultimate-guide-to-json-parsing-with-swift-4/)  pour plus d'infos.

## Exercice bonus - Affichage des données

1. Reprenez l'écran de l'atelier précédent et rajouter la note et la date
Note : ne vous inquiétez pas si le layout s'adapte mal aux tailles d'écrans
2. Remplissez l'écran avec les données du premier film de votre tableau. Utilisez les outlets et changez les valeurs dans `viewDidLoad`. Utilisez le `DateFormater` pour afficher la date correctement.
Note : laissez une image fixe pour l'instant
3. Ajoutez un bouton next qui permet d'afficher le prochain film de la liste (en fin de liste revenez au premier élément)

![](/assets/Parsing_Bonus.png)
