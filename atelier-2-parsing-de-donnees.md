# Parsing de données

## Introduction

Dans cet atelier nous allons créer un modèle de données correspondant à la base de TheMovieDB.

Cela nous permettra de commencer à utiliser les concepts de Swift. Notamment les optionnels et les variables.

**Notions nécessaires :** optionals \(init et cast\), MVC, déclaration de variables, extensions, MVC, format de dates, format de string

# Étape 1- Création du modèle

Dans un nouveau projet Xcode \(Single View Template\) créez une classe Movie avec :

* un titre,
* un synopsis,
* une note moyenne \(Float\),
* une date de sortie

# Étape 2 - Parsing naïf

Le but va être de parser le fichier suivant : BestMovie.json

1. Ajoutez le fichier BestMovie.json à votre projet 
2. Ajoutez le fichier JSONHelper.swift \(c'est une extension pour récupérer facilement un tableau de dictionnaires à partir d'un fichier json local\)
3. Transformez le contenu du fichier en un tableau de dictionnaire
4. Parcourez ces dictionnaires pour créer des objets de type Movie
5. Ajoutez une fonction description à la classe movie et faites un print des objets récupérés
6. Pour vous faire gagner du temps, importez le fichier Swift suivant : JSONHelper.swift . Il vous permttra de récupérer facilement un tableau de dictionnaires à partir d'un fichier json local.

**Conseil :** dans un premier temps considérez que les données sont parfaitement remplies. Cela va vous faire gagner du temps avec les optionnals. Dans un deuxième temps, faites un parsing plus robuste.

# Étape 3 - Parsing à la mode Swift 4

Adaptez votre projet pour qu'il utilise le protocole Codable. Notez que le code est maintenant beaucoup plus simple tout en étant robuste.

# Étape 4 - Affichage des données

Remplissez l'écran créé dans l'atelier précédent avec les données du premier film

