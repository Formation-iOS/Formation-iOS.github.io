# Parsing de données

## Introduction

Dans cet atelier nous allons créer un modèle de données correspondant à la base de TheMovieDB.

Cela nous permettra de commencer à utiliser les concepts de Swift. Notamment les optionnels et les variables.

**Notions nécessaires :** optionals \(init et cast\), MVC, déclaration de variables, extensions, MVC, format de dates, format de string

## Étape 1- Création du modèle

Dans un nouveau projet Xcode \(Single View Template\) créez une classe Movie avec :

* un titre,
* un synopsis,
* une note moyenne \(Float\),
* une date de sortie

## Étape 2 - Parsing naïf

Le but va être de parser le fichier suivant : **BestMovie.json**

1. Ajoutez le fichier BestMovie.json à votre projet 
2. Ajoutez le fichier **JSONHelper.swift** \(c'est une extension pour récupérer facilement un tableau de dictionnaires à partir d'un fichier json local\)
3. Transformez le contenu du fichier en un tableau de dictionnaire
4. Parcourez ces dictionnaires pour créer des objets de type Movie
5. Ajoutez une fonction description à la classe movie et faites un print des objets récupérés

**Conseil :** dans un premier temps considérez que les données sont parfaitement remplies. Cela va vous faire gagner du temps avec les optionnals. Dans un deuxième temps, faites un parsing plus robuste.

## Étape 3 - Parsing à la mode Swift 4

Le but de l'étape 2 était surtout de vous faire manipuler du Swift. En pratique, on fait rarement ce processus à la main. Depuis Swift 4 on peut utiliser le protocole Codable pour cela.

1. Adaptez votre projet pour qu'il utilise le protocole Codable.

**Pour aller plus loin **: on est ici dans un cas simple mais le protocole semble suffisament puissant pour couvrir les cas plus complexes : voir ce **tutorial** pour plus d'infos.

## Étape 4 - Affichage des données

1. Complétez l'écran de l'atelier précédent pour rajouter la note, la description et la date
2. Remplissez l'écran avec les données du premier film de votre tableau

## Étape optionelle
1. Ajoutez le fichier **Genre.json** à votre projet
2. Ajouter le titre du genre du film à votre écran

**Conseil :** vous pouvez utiliser des variables/fonctions de classe (static en swift) pour vous simplifier la vie
