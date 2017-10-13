# Parsing de données

## Introduction

Dans cet atelier nous allons créer un modèle de données correspondant à la base de TheMovieDB.

Cela nous permettra de commencer à utiliser les concepts de Swift. Notamment les optionnels et les variables.

Notions nécessaires : optionals (init et cast), MVC, déclaration de variables, extensions, MVC, format de dates, format de string

# Étape 1
Dans un nouveau projet Xcode (Single View Template) créez une classe Movie avec :
un titre,
un synopsis,
une note moyenne (Float),
une date de sortie

# Étape 2
Le but va être de parser le fichier suivant : BestMovie.json

1) Ajoutez le fichier à votre projet
2) Transformez le contenu du fichier en un tableau de dictionnaire
3) Parcourez ces dictionnaires pour créer des objets de type Movie
4) Ajoutez une fonction description à la classe movie et faites un print des objets récupérés

Pour vous faire gagner du temps, importez le fichier Swift suivant : JSONHelper.swift . Il vous permttra de récupérer facilement un tableau de dictionnaires à partir d'un fichier json local.

Conseil : dans un premier temps considérez que les données sont parfaitement remplie. Cela va vous faire gagner du temps avec les optionnals.

Dans un deuxième temps, faites un parsing plus robuste.

# Étape 3
Adaptez votre projet pour qu'il utilise le protocole Codable.

# Étape 4
Remplissez l'écran créé dans l'atelier précédent avec les données du premier film

