---
title: Personnalisation de l’application
description: Personnalisation de l’application
role: User, Admin
exl-id: 3e454c48-2168-41a5-bbab-05c8a5b5aeb1
source-git-commit: 3615928117ce1be527dc3c6d2ec8ddd115b78b0a
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 0%

---

# Personnalisation de l’application

## Fonctionnalités exposées sous la structure d’extension

Nous avons exposé un ensemble de fonctions et de getters sous un `proxy` qui peuvent être utilisés pour accéder aux données, aux configurations et aux événements déclencheurs. Vous trouverez ci-dessous une liste et comment y accéder.

```typescript
interface EventData {
  key?: string,
  keys?: string[]
  view?: any,
  next?: any,
  error?: any,
  completed?: any,
  id?: any
}

* getValue(key)
* setValue(key, value)
* subject // getter
* subscribe(opts: EventData)
* subscribeAppEvent(opts: EventData)
* subscribeAppModel(key, next)
* subscribeParentEvent(opts: EventData)
* parentEventHandlerNext(eventName: string, opts: any)
* appModelNext(eventName:string, opts) 
* appEventHandlerNext(eventName:string, opts)
* next(eventName:string, opts, eventHandler?)
* viewConfig //getter
* args //getter
```

Notre application suit une structure MVC (modèle, vue, contrôleur)

## Modèle

Le modèle définit les différents attributs et stocke leurs valeurs. Les valeurs des différents attributs stockés dans le modèle sont accessibles à partir du contrôleur en utilisant la syntaxe

```typescript
this.getValue('attributeName')
```

Pour la personnalisation dans l’application, tous les attributs nouvellement créés seront ajoutés sous une carte dans le modèle.
Pour définir un nouvel attribut dans le modèle, nous utiliserons la syntaxe suivante dans le contrôleur :

```typescript
// If a key is not already in model then it will be added to extraProps
this.setValue('key', value)
```

Pour accéder à un attribut ajouté au modèle, nous utiliserons la syntaxe suivante :

```typescript
const value = this.getValue("key")
```

## Mode

La vue définit l’interface utilisateur de l’application. Nous utilisons des fichiers JSON pour définir l’affichage de nos fichiers. Ici, nous définissons les composants, le CSS (comme indiqué dans l’extraction de composants) et effectuons le rendu des valeurs stockées dans le modèle.
Dans notre application, chaque vue est définie à l’aide d’un JSON. Les fichiers JSON sont référencés à l’aide de leurs identifiants uniques appelés `id`.

## Contrôleur

Le contrôleur est utilisé pour gérer les événements et traiter les données. Le contrôleur est utilisé pour récupérer et envoyer des données à partir du serveur. Il s’agit de l’interface entre ce qui s’affiche sur l’interface utilisateur et ce qui est stocké sur le serveur principal.

- Pour définir des valeurs lors de l’initialisation, nous utilisons la fonction `init` .
- Pour ajouter une méthode au contrôleur, nous utilisons la syntaxe suivante :

```typescript
methodName: function(args){
    // functionality
}
```

`methodName` sert ici de `key` pour référencer la méthode dans le JSON (vue) ou dans d’autres fonctions.

- Pour appeler une méthode dans le contrôleur, nous utilisons la syntaxe

```typescript
this.next('methodName', args)
```

## Exemple

Utilisons maintenant un exemple simple pour montrer comment ces trois composants interagissent entre eux.
Nous ajouterons un bouton qui change sa valeur de libellé en un clic

### Exemple d’affichage

Nous définissons ci-dessous le JSON d’un bouton qui affiche un texte dynamique stocké dans le modèle sous le nom de variable `buttonLabel`.
Dans cet exemple, cliquer sur le bouton modifie son libellé.

```JSON
{
    "component": "button",
    "label": "@extraProps.buttonLabel",
    "variant": "cta",
    "on-click": "switchButtonLabel",
}
```

### Exemple de modèle

dans ce cas, `extraProps.buttonLabel` contient le libellé du bouton.

### Exemple de contrôleur

```typescript
  controller: {
    init: function () {
      this.setValue("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.getValue("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.setValue("buttonLabel", buttonLabel)
    }
  }
```

Le GIF ci-dessous affiche le code ci-dessus en action.
![basic_customisation](imgs/basic_customisation.gif "Bouton de personnalisation de base")


### Exemple de configuration

Dans ce cas, nous accédons à un événement de mode de recherche en utilisant `viewConfig` et déclenchons un événement pour le mettre à jour.

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        console.log('Logging view config ', this.viewConfig)
        this.next(this.viewConfig.items[1].searchModeChangedEvent, { searchMode: true })
      }
    }
  }
```

### Exemple d&#39;abonnement

Dans ce cas, nous ajoutons l’abonnement au changement de nom de fichier au journal de la console lorsque l’option de changement de nom de fichier est sélectionnée.

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribe({
          key: 'rename',
          next: () => { console.log('rename using extension') }
        })
      }
    }
  }
```

### Exemple d’abonnement à un événement d’application

Dans ce cas, nous vous connectons à la console lorsque le document actif a été modifié (modification des onglets dans l’interface utilisateur de l’éditeur).

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeAppEvent({
          key: 'app.active_document_changed',
          next: () => { console.log('Extension: active document changed') }
        })
      }
    }
  }
```

### Exemple d’abonnement à des événements de modèle d’application

Exemple d’abonnement à des événements de modèle d’application tels que `app.mode`

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeAppModel('app.mode',
          () => { console.log('app mode subs') }
        )
      }
    }
  }
```

### Exemple d’événements de contrôleur parent

Dans ce cas, nous ajoutons un abonnement à l’événement `tabChange` qui est un événement du contrôleur `left_panel_container` qui agit
comme contrôleur parent pour `repository_panel`

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeParentEvent({
          key: 'tabChange',
          next: () => { console.log('tab change subs') }
        })
        this.parentEventHandlerNext('tabChange', {
          data: 'map_panel'
        )
      }
    }
  }
```

### Modèle d’application et contrôleur d’application suivant

Elles peuvent être déclenchées directement en sachant que l’événement correct à déclencher et ses données

```typescript
  { 
    id: 'file_options', 
    controller: {
      init: function () {
        this.appModelNext('app.mode', 'author')
        this.appEventHandlerNext('app.active_document_changed', 'active doc changed')   
      }
    }
  } 
```
