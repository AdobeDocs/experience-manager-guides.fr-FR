---
title: Personnalisation de l’application
description: Personnalisation de l’application
role: User, Admin
exl-id: 3e454c48-2168-41a5-bbab-05c8a5b5aeb1
TQID: https://experienceleague.adobe.com/7DiEcUTAvp4rT3Fy9pIv4-zaHKwswjokjlaBgx8Pbyo
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 485
ht-degree: 0%

---

# Personnalisation de l’application

## Fonctionnalités exposées dans le framework d’extension

Nous avons exposé un ensemble de fonctions et de getters sous un `proxy` qui peut être utilisé pour accéder aux données, configurer et déclencher des événements. Vous trouverez ci-dessous une liste et comment y accéder.

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

Notre application suit une structure MVC (Modèle, Vue, Contrôleur)

## Modèle

Le modèle définit les différents attributs et stocke leurs valeurs. Les valeurs des différents attributs stockés dans le modèle sont accessibles à partir du contrôleur en utilisant la syntaxe .

```typescript
this.getValue('attributeName')
```

Pour la personnalisation dans l’application, tous les attributs nouvellement créés sont ajoutés sous une carte dans le modèle.
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

La vue définit l’interface utilisateur de l’application. Nous utilisons des fichiers JSON pour définir l’affichage de nos fichiers. Ici, nous définissons les composants, le code css (comme indiqué dans l’extraclasse des composants) et rendons les valeurs stockées dans le modèle.
Dans notre application, chaque vue est définie à l’aide d’un fichier JSON. Les fichiers JSON sont référencés à l’aide de leurs identifiants uniques appelés `id`.

## Contrôleur

Le contrôleur est utilisé pour gérer les événements et traiter les données. Le contrôleur est utilisé pour récupérer et envoyer des données à partir du serveur. Il s’agit de l’interface entre ce qui est affiché sur l’interface utilisateur et stocké sur le serveur principal.

- Pour définir des valeurs à l’initialisation, nous utilisons la fonction `init` .
- Pour ajouter une méthode au contrôleur, nous utilisons la syntaxe suivante :

```typescript
methodName: function(args){
    // functionality
}
```

Le `methodName` sert ici de `key` pour référencer la méthode dans le fichier JSON (vue) ou dans d’autres fonctions

- Pour appeler une méthode dans le contrôleur, nous utilisons la syntaxe

```typescript
this.next('methodName', args)
```

## Exemple

Prenons maintenant un exemple simple pour montrer comment ces 3 composants interagissent les uns avec les autres.
Nous allons ajouter un bouton qui change la valeur de son libellé en un clic

### Afficher l’exemple

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

dans ce cas, `extraProps.buttonLabel` contient le libellé du bouton

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

Sous GIF, le code ci-dessus s’affiche en action
![basic_customization](imgs/basic_customisation.gif "Bouton de personnalisation de base")


### Afficher l’exemple de configuration

Dans ce cas, nous accédons à l’événement de mode de recherche à l’aide de `viewConfig` et déclenchons un événement pour le mettre à jour

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

### Exemple d’abonnement

Dans ce cas, nous ajoutons un abonnement au changement de nom de fichier au journal de la console lorsque l’option de changement de nom de fichier est activée

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

### Exemple d’événement d’application avec abonnement

Dans ce cas, nous modifions le journal de la console sur le document actif (en modifiant les onglets dans l’interface utilisateur de l’éditeur)

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

### Exemple d’événements de modèle d’application avec abonnement

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

### Exemple d’événements du contrôleur parent

Dans ce cas, nous ajoutons un abonnement sur `tabChange` événement qui est un événement `left_panel_container` contrôleur qui agit
en tant que contrôleur parent pour `repository_panel`

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

### Modèle d&#39;application et contrôleur d&#39;application suivant

Ils peuvent être directement déclenchés en connaissant l’événement correct à déclencher et ses données

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
