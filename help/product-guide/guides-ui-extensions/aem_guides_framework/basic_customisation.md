---
sidebar_position: 3
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---

# Personnalisation de l’application

Notre application suit une structure MVC (modèle, vue, contrôleur)

## Modèle

Le modèle définit les différents attributs et stocke leurs valeurs. Les valeurs des différents attributs stockés dans le modèle sont accessibles à partir du contrôleur en utilisant la syntaxe

```typescript
this.model.attributeName
```

Pour la personnalisation dans l’application, tous les attributs nouvellement créés seront ajoutés sous une carte dans le modèle.
Pour définir un nouvel attribut dans le modèle, nous utiliserons la syntaxe suivante dans le contrôleur :

```typescript
this.model.extraProps.set("key", value)
```

Pour accéder à un attribut ajouté au modèle, nous utiliserons la syntaxe suivante :

```typescript
const value = this.model.extraProps.get("key")
```

## Mode

La vue définit l’interface utilisateur de l’application. Nous utilisons des fichiers JSON pour définir l’affichage de nos fichiers. Ici, nous définissons les composants, le CSS (comme indiqué dans l’extraction de composants) et effectuons le rendu des valeurs stockées dans le modèle.
Dans notre application, chaque vue est définie à l’aide d’un JSON. Les fichiers JSON sont référencés à l’aide de leurs identifiants uniques appelés `id`.

## Contrôleur

Le contrôleur est utilisé pour gérer les événements et traiter les données. Le contrôleur est utilisé pour récupérer et envoyer des données à partir du serveur. Il s’agit de l’interface entre ce qui s’affiche sur l’interface utilisateur et ce qui est stocké sur le serveur principal.

- Pour définir des valeurs lors de l’initialisation, nous utilisons la variable `init` de la fonction
- Pour ajouter une méthode au contrôleur, nous utilisons la syntaxe suivante :

```typescript
methodName: function(args){
    // functionality
}
```

La variable `methodName` ici sert de `key` pour référencer la méthode dans le JSON (vue) ou dans d’autres fonctions

- Pour appeler une méthode dans le contrôleur, nous utilisons la syntaxe

```typescript
this.next('methodName', args)
```

## Exemple

Utilisons maintenant un exemple simple pour montrer comment ces trois composants interagissent entre eux.
Nous ajouterons un bouton qui change sa valeur de libellé en un clic

### Exemple d’affichage

Nous définissons ci-dessous le code JSON d’un bouton qui affiche un texte dynamique stocké dans le modèle sous le nom de variable. `buttonLabel`.
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

dans ce cas, `extraProps.buttonLabel` contient le libellé du bouton ;

### Exemple de contrôleur

```typescript
  controller: {
    init: function () {
      this.model.extraProps.set("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.model.extraProps.get("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.model.extraProps.set("buttonLabel", buttonLabel)
    }
  }
```

Le GIF ci-dessous affiche le code ci-dessus en action.
![basic_customization](imgs/basic_customisation.gif "Bouton de personnalisation de base")
