---
title: Framework Jui
description: Présentation De La Structure De L’Interface Utilisateur
role: User, Admin
exl-id: c193cf90-5916-4d8c-88f1-be5014beca1c
TQID: https://experienceleague.adobe.com/AQFEy2bHTDHXq6QH8KTBOEzUvtA3Hf2ojhxvD0dsI7o
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: c6d09140-3c91-45d3-b7ed-b681af752f43id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 268
ht-degree: 1%

---

# Framework Jui

Avant d’aborder la manière d’écrire des extensions, nous allons comprendre l’architecture du framework.
Afin que nous puissions l&#39;étendre efficacement.

## Présentation

JUI est un framework MVC qui complète les composants React et Adobe React Spectrum. JUI est l’interface utilisateur JSON. Il se compose de plusieurs référentiels Git.

JUI-Core est la bibliothèque principale avec toute la logique pour convertir la configuration JSON en composants React fonctionnels et la lier à une instance de classe de contrôleur appropriée.
La bibliothèque JUI-React-Spectrum comporte des widgets wrapper des composants React Spectrum d’Adobe

## Conception principale de l’interface utilisateur graphique

### Conception de l’interface utilisateur MVC

![flux MVC JUI](./imgs/jui-mvc-flow.png)

### Widget

- A un ID unique.
- Dispose d’un fichier JSON individuel à afficher.
- Peut avoir un contrôleur propre ou partagé.
- Peut utiliser le modèle parent ou un nouveau modèle.
- Peuvent avoir des éléments d’interface utilisateur (composants React).
- Peut avoir d’autres widgets
- L’application est un widget

![ Widget JUI ](./imgs/jui-widget.png)

### Elément

- Est un composant HTML/React.
- N’a aucun modèle, il utilise le modèle de widget parent.

### Gestionnaire d&#39;événements

- Next(eventOpts)
   - Pour déclencher un événement avec des options
- Subscribe(callback)
   - Obtention d’une notification indiquant que l’événement est déclenché avec la configuration

### Application/modèle global

- Suivant(nouvelle valeur)
   - Pour publier une nouvelle valeur
- Subscribe(callback)
   - Pour obtenir une notification de modification de valeur
   - Première fois que vous obtenez de l’ancienne valeur
- GetValue()
   - Pour obtenir la valeur actuelle

### Contrôleur

- Il doit être étendu à partir de la classe Controller
- API
- CreateModel
   - Pour créer un modèle séparé de widget enfant
- InitEventHandler
   - Pour créer un gestionnaire d’événements distinct de widget enfant
- RegisterCommands
   - Pour enregistrer des événements locaux, parents ou d’application
- Next(eventName, eventHandler)
   - Pour déclencher l’événement d’un gestionnaire d’événements de widget enfant, d’un gestionnaire d’événements de widget parent ou d’application
- Subscribe(callback, eventHandler)
- SubscribeAppModel(callback)

### Exemple de conception d’application

![Exemple d’application](./imgs/jui-sample-app.png)
