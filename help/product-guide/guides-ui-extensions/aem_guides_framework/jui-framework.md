---
title: Structure Jui
description: Présentation De La Structure Jui
source-git-commit: a61abc0d2b480e276991db916ba0cbf630ca7996
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 1%

---

# Structure Jui

Avant d’aborder comment écrire des extensions, nous allons comprendre l’architecture de la structure.
Pour que nous puissions l&#39;étendre efficacement.

## Présentation

JUI est une structure MVC superposée aux composants React et React Spectrum Adobe. JUI est l’interface utilisateur JSON. Il se compose de plusieurs référentiels Git.

JUI-Core est la bibliothèque principale avec toute la logique nécessaire pour convertir la configuration JSON en composants de réaction fonctionnels et la lier à une instance de classe de contrôleur appropriée.
La bibliothèque JUI-React-Spectrum comporte des widgets wrapper des composants React Spectrum Adobe

## Conception Core de JUI

### Conception de l’IU MVC

![Flux MVC JUI](./imgs/jui-mvc-flow.png)

### Widget

- Comporte un identifiant unique.
- Dispose d’un fichier JSON individuel pour l’affichage.
- Peut avoir un contrôleur propre ou partagé.
- Peut utiliser un modèle parent ou un nouveau modèle.
- Peut comporter des éléments d’interface utilisateur (composants React)
- Peut comporter d’autres widgets
- L’application est un widget

![Widget JUI](./imgs/jui-widget.png)

### Elément

- est un composant HTML/React ;
- N’a aucun modèle, il utilise le modèle de widget parent.

### Gestionnaire d’événements

- Next(eventOpts)
   - Pour déclencher un événement avec certains inclusions
- Subscribe(callback)
   - Recevez une notification indiquant que l’événement est déclenché avec la configuration

### Application/Modèle global

- Next (nouvelle valeur)
   - Pour publier une nouvelle valeur
- Subscribe(callback)
   - Pour que la notification soit modifiée
   - Première fois obtenir une ancienne valeur
- GetValue()
   - Pour obtenir la valeur actuelle

### Contrôleur

- Il doit être étendu à partir de la classe Controller
- API
- CreateModel
   - Pour créer un modèle distinct de widget enfant
- InitEventHandler
   - Pour créer un gestionnaire d’événement distinct de widget enfant
- RegisterCommands
   - Pour enregistrer des événements locaux, parents ou d’application
- Next(eventName, eventHandler)
   - Pour déclencher un événement du gestionnaire d’événements de widget enfant, du gestionnaire d’événements de widget parent ou du gestionnaire d’événements d’application
- Subscribe(callback, eventHandler)
- SubscribeAppModel(callback)

### Exemple de conception d’application

![Exemple d’application](./imgs/jui-sample-app.png)
