# Connexion et compte utilisateur

## Introduction

Voici en général à quoi ressemble le 1er écran d'une application iOS lorsqu'un utilisateur la lance pour la 1ère fois :

![](/assets/login-spotify.png)

![](/assets/login-blablacar.png)

L'application demande à l'utilisateur de créer un compte, ou, s'il a déjà un compte, de se connecter.

Dans l'exemple de l'application catalogue de films, vous allez permettre à l'utilisateur de se connecter à son compte, pour pouvoir éditer la liste des films qu'il aimerait voir (sa « Watchlist »).

Pour cela, vous allez :
1. créer un formulaire de connexion
2. connecter ce formulaire à l'API de themoviedb.org
3. persister les informations de connexion, pour que l'utilisateur n'ait pas à rentrer son identifiant et mot de passe à chaque utilisation de l'app
4. informer l'utilisateur que l'app est en train d'effectuer la connexion
5. informer l'utilisateur que l'identifiant ou le mot de passe ne sont pas corrects, le cas échéant

**Notions nécessaires :** Formulaire, UITextField, gestion du clavier, Keychain, UserDefaults, authentification, Swift closures

## 1er exercice : création d'un formulaire de connexion

Ce 1er exercice consiste à réaliser la partie interface graphique uniquement. 
Il s'agit de créer un formulaire comprenant deux champs textes (UITextField), un pour l'identifiant et un pour le mot de passe, ainsi qu'un bouton « Connexion ». 

Pour implémenter ce formulaire, vous allez utiliser un UITableViewController avec des cellules statiques.
L'intérêt d'utiliser un UITableViewController est qu'il va s'occuper de la gestion du clavier pour vous, ce qui n'est pas le cas dans un UIViewController ([Gestion du clavier sans UITableViewController](https://developer.apple.com/library/content/documentation/StringsTextFonts/Conceptual/TextAndWebiPhoneOS/KeyboardManagement/KeyboardManagement.html)).

![](/assets/login.png)

Lorsque le champ texte de l'identifiant est sélectionné, le clavier doit comporter un bouton « Next », comme dans la capture d'écran ci-dessous.
Si l'utilisateur « scroll » vers le bas, les différents éléments de l'écran doivent s'afficher correctement, en particulier le bouton « Connexion ».

![](/assets/login-next.png)

Lorsque le champ texte du mot de passe est sélectionné, le clavier doit comporter un bouton « Done ».
Le champ texte du mot de passe doit cacher le mot de passe, comme dans la capture d'écran ci-dessous.

![](/assets/login-done.png)

Validez que tout fonctionne correctement en lançant l'application dans le simulateur de l'iPhone SE.

## 2ème exercice : connexion à l'API de login et persistence de la session

Vous allez implémenter une fonction "login", que vous appellerez dans votre view controller :

```swift
static func login(username: String, password: String, result: @escaping (Error?) -> Void) {
...
}
```

La connexion à l'API de themoviedb.org est une succession de 3 requêtes GET. Il va falloir enchaîner ces 3 requêtes avec des appels à Alamofire.
A la fin, on obtient un « session_id », qui pourra être utilisé dans la requête qui permet d'ajouter un film à la « Watchlist ».

Note : utilisez URLComponents et URLQueryItem pour créer une URL avec une « query string ». Ceci permet de gérer correctement l'URL encoding.

[Requête de création d'un token](https://developers.themoviedb.org/3/authentication/create-request-token)

```
https://api.themoviedb.org/3/authentication/token/new?api_key=b692eafd258dae823a2d9ed21dbcdeb5
```

```json
{
    "expires_at": "2017-10-23 13:45:51 UTC",
    "request_token": "0181728ec1420301aacecd132ac99d845ac3efaa",
    "success": true
}
```

[Requête de validation du token](https://developers.themoviedb.org/3/authentication/validate-request-token)

```
https://api.themoviedb.org/3/authentication/token/validate_with_login?api_key=b692eafd258dae823a2d9ed21dbcdeb5&username=myusername&password=mypassword&request_token=0181728ec1420301aacecd132ac99d845ac3efaa
```

```json
{
  "success": true,
  "request_token": "0181728ec1420301aacecd132ac99d845ac3efaa"
}
```

[Requête de création d'une session](https://developers.themoviedb.org/3/authentication/create-session)

```
https://api.themoviedb.org/3/authentication/session/new?api_key=b692eafd258dae823a2d9ed21dbcdeb5&request_token=0181728ec1420301aacecd132ac99d845ac3efaa
```

```json
{
  "success": true,
  "session_id": "56e8124c66793653f5abcda02675423ceb3205d9"
}
```

En cas de succès, c'est à dire lorsque l'app récupère un « session_id », vous pouvez sauvegarder l'identifiant et le mot de passe de l'utilisateur, ainsi que le « session_id ».
Ces informations doivent être persistées dans un endroit sécurisé : pour cela, vous allez utiliser la Keychain.

TODO : expliquer la sauvegarde dans la Keychain, et ce qu'est la Keychain.

## 3ème exercice : feedback utilisateur, gestion des cas d'erreurs

Pendant que la requête est en train de se faire en tâche de fond, l'utilisateur n'a aucun feedback. Ce serait encore plus flagrant si le réseau était lent.
Pour que l'expérience utilisateur soit bonne, il est important de l'informer du fait que l'app est en train de réaliser la connexion.

Pour cela, on peut utiliser le pod « MBProgressHUD » de la manière suivante :

```swift
let hud = MBProgressHUD.showAdded(to: view, animated: true)
hud.label.text = "Connexion en cours..."

...

hud.hide(animated: true)
```

Note : il existe un outil pour simuler un réseau lent sur macOS : le Network Link Conditioner.
Ce dernier peut être installé via le package « Additional Tools for Xcode », disponible sur le Developer portal d'Apple. 

![](/assets/network-link-conditioner.png)

Le Network Link Conditioner est également disponible sur iPhone dans l'app Réglages, dans la section « Développeur ».
C'est un outil très utile. Il n'est pas rare que les utilisateurs des applications iOS n'aient pas des conditions idéales de réseau (pas comme les développeurs) !
Il est donc important de tester une app en conditions réelles, et c'est justement à ça que sert le Network Link Conditioner.

![](/assets/network-link-conditioner-iphone.png)

## 4ème exercice (optionel) : implémenter l'ajout à la « Watchlist »

Si vous avez le temps, vous pouvez implémenter l'ajout d'un film à la « Watchlist ». Voici la requête à effectuer : [https://developers.themoviedb.org/3/account/add-to-watchlist](https://developers.themoviedb.org/3/account/add-to-watchlist).

## Avancé

### Connection avec Facebook

TODO

### Gestion du clavier en dehors d'un UITableViewController

TODO

