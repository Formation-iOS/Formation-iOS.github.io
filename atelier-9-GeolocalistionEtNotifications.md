# Géolocalisation et notifications

## Introduction

Dans cet atelier nous allons créer une application qui vous prévient quand vous entrez dans le périmètre d'une zone d'interêt.

Cela nous permettra de mettre en place la géolocalisation et les notifications.

**Notions nécessaires :** Gestion des droits utilisateurs, techniques de géolocalisation (déplacements, déplacements signifiants, geofencing, visites), gestion des notifications, debug de position (schema, GPX)

## Exercice 1 - Positionnez l'utilisateur

Nous allons commencer par placer l'utilisateur sur la carte.

1. Demandez le droit de localiser l'utilisateur quand l'application est lancée : requestWhenInUseAuthorization de CLLocationManager dans le framework CoreLocation
Note : vous pouvez utiliser un singleton UserLocationManager pour bien séparer le code ou directement le faire dans votre ViewController
2. Ajoutez la variable NSLocationWhenInUseUsageDescription au fichier info.plist
3. Cochez "Show user Location" pour la MapView dans le storyboard

## Exercice 2 - Ajoutez du geofencing

Nous allons surveiller les points d'interêt pour être prévenu quand l'utilisateur est proche de l'un d'eux

### Première étape :
Pour le geofencing nous avons besoin de la position de l'utilisateur même quand il n'utilise pas l'application (.alwaysAuthorization)
1. Supprimez l'application pour effacer les droits que vous aviez demandé précédemment
2. Demandez le droit de localiser l'utilisateur tout le temps : requestAlwaysAuthorization
3. Ajouter les variables NSLocationAlwaysAndWhenInUseUsageDescription et NSLocationAlwaysUsageDescription dans le info.plist

### Deuxième étape :
Nous allons maintenant ajouter les points de geofencing quand la fonctionnalité est disponible
1. Implémentez la fonction didChangeAuthorization du protocole CLLocationManagerDelegate pour être prévenu quand l'utilisateur choisit le mode de géolocalisation permis
2. Si l'utilisateur accepte (status à `authorizedAlways`), utilisez la fonction startMonitoring de CLLocationManager pour surveiller les FunMapPoints
3. Implémentez les fonctions monitoringDidFailFor et didStartMonitoringFor de CLLocationManagerDelegate pour vérifier que le monotoring est bien en place
4. Implémentez les fonctions didEnterRegion et didExitRegion de CLLocationManagerDelegate. Pour l'instant, faites un print de la Region
5. Testez différentes positions pour le user à l'aide de l'option du simulateur > Debug > Location (notez que vous pouvez également le faire à partir de Xcode ou dans les options du Scheme du projet si vous n'êtes pas dans le simulateur)

Note : didEnterRegion n'est pas activé si l'utilisateur est déjà dans la région au lancement de l'application.

## Exercice 3 - Ajoutez des notifications locales

[TODO]

## Exercice bonus - Gérez le cas où l'utilisateur n'accepte pas de donner sa position tout le temps
Le Region Monitoring fonctionne uniquement avec .authorizedAlways et pas avec .authorizedWhenInUse. Aidons l'utilisateur à comprendre ce qu'il se passe.

1. En cas de .authorizedWhenInUse, afficher une alerte pour expliquer à l'utilisateur qu'il ne sera pas au tenu au courant s'il arrive dans un endroit fun
2. Ajoutez un bouton qui permet d'aller changer rapidement l'option de géolocalisation en authorizedAlways
Note : je vous conseille fortement le Pod SwiftMessages pour ce type d'alerte. En étant moins intrusif, vous aurez plus de chances d'être lu.

## Exercice bonus - Surveiller une infinité de positions
 L'API de geofencing limite à 20 points d'interêts maximum.
Imaginez que l'on a plus de 20 positions à surveiller. Comment feriez-vous ?

Astuce : vous pouvez être prévenu quand l'utilisateur bouge grâce à la fonction didUpdateLocations du protocol CLLocationManagerDelegate
