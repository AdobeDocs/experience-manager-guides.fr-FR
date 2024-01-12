---
title: Barre d’outils Personnaliser
description: Découvrez comment personnaliser la barre d’outils
exl-id: 14a82c7e-5c07-43a8-bd9e-b221d80f6d05
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 0%

---

# Barre d’outils Personnaliser {#id172FB00L0V6}

Par défaut, l’éditeur web est fourni avec les fonctionnalités éditoriales les plus courantes requises par n’importe quel éditeur DITA. Des fonctionnalités telles que l’insertion d’éléments de type liste \(numérotée ou à puces\), référence croisée, référence de contenu, tableau, paragraphe et mise en forme des caractères sont disponibles dans l’éditeur. Outre ces éléments de base, vous pouvez personnaliser l’éditeur Web pour insérer les éléments utilisés dans votre environnement de création.

La barre d’outils de l’éditeur Web peut être personnalisée de deux façons :

- Ajouter une nouvelle fonctionnalité à la barre d’outils

- Supprimer toutes les fonctionnalités existantes de la barre d’outils


## Ajouter une fonction dans la barre d’outils

L’ajout d’une fonctionnalité à l’éditeur Web implique deux tâches principales : l’ajout d’une icône pour la fonctionnalité dans la fonction *ui\_config.json* et ajouter la fonctionnalité d’arrière-plan dans JavaScript.

**Ajouter une icône dans la barre d’outils**

Pour ajouter une fonction à la barre d’outils de l’éditeur web, procédez comme suit :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite.

1. Accédez au fichier de configuration par défaut disponible à l’emplacement suivant :

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Créez une copie du fichier de configuration par défaut à l’emplacement suivant :

   `/apps/fmdita/xmleditor/ui_config.json`

1. Accédez à et ouvrez le `ui_config.json` dans le fichier `apps` pour la modification.

1. Dans le `ui_config.json` , ajoutez la définition de la nouvelle fonctionnalité dans la section barres d’outils. En règle générale, vous pouvez créer un groupe de boutons de barre d’outils et y ajouter un ou plusieurs boutons. Vous pouvez également ajouter un nouveau bouton de barre d’outils dans un groupe existant. Les détails suivants sont requis pour créer un groupe de barres d’outils :

   - **type :**spécifiez `blockGroup` comme la propriété `type` . Cette valeur indique que vous créez un groupe de blocs qui contiendra un ou plusieurs groupes de barres d’outils.

   - **extraclass :** Nom de la ou des classes séparées par un espace.

   - **items :** Spécifiez la définition de tous les groupes dans la barre d’outils. Chaque groupe peut contenir une ou plusieurs icônes de barre d’outils. Pour définir des icônes dans un groupe de barres d’outils, vous devez définir à nouveau le `type` dans l’attribut `items`, puis définissez sa valeur sur `buttonGroup`. Spécifiez un ou plusieurs noms de classe dans la variable `extraclass` . Indiquez le nom de la fonction dans la variable `label` . Le fragment de code suivant de la fonction `ui_config.json` affiche la définition du bloc de barre d’outils principal, suivie de la propriété `buttonGroup` définition :

     ```json
     "toolbar": {    
       "type": "blockGroup",    
       "extraclass": 
       "toolbar operations",    
         "items": [      
           {        
             "type": "buttonGroup",        
             "extraclass": "left-controls",        
             "label": "Left Controls",        
             "items": [
     ```

     Dans le `items` , vous devez spécifier la définition d’une ou de plusieurs icônes de barre d’outils.
Pour ajouter une icône de barre d’outils, vous devez définir les propriétés suivantes :

   - **type :** Spécifier `button` comme la propriété `type` . Cette valeur indique que vous ajoutez un bouton de barre d’outils.

   - **icon :** Indiquez le nom de l’icône Coral que vous souhaitez utiliser dans la barre d’outils.

   - **variant :** Spécifier `quiet` comme la propriété `variant` .

   - **title:** Spécifiez l’info-bulle de l’icône.

   - **en cliquant :** Spécifiez le nom de commande défini pour la fonction dans le fichier JavaScript. Si votre commande nécessite des paramètres d’entrée, indiquez le nom de la commande comme suit :

     ```JavaScript
     "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
     ```

   - **afficher ou masquer :** Si vous définissez la variable `show` , puis spécifiez les modes d’affichage de l’icône. Les valeurs possibles sont : `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(affichage dans tous les modes\) ou `false` \(masquer dans tous les modes\).

   À la place de `show`, vous pouvez également définir la variable `hide` . Les valeurs possibles sont les mêmes que dans `show` avec la seule différence que l’icône ne s’affiche pas pour le mode spécifié.

1. Créez un *clientlib* et ajoutez votre JavaScript dans ce dossier.

1. Mettez à jour la propriété categories du *clientlib* en lui attribuant la valeur de *apps.dita.xml\_editor.page\_overrides*.

1. Enregistrez le *ui\_config.json* et rechargez l’éditeur Web.


**Exemples de code JavaScript**

Cette section fournit deux exemples de code JavaScript pour vous aider à commencer à ajouter des fonctionnalités personnalisées. L’exemple suivant montre le numéro de version des Guides d’AEM lorsqu’un utilisateur clique sur l’icône Afficher la version dans la barre d’outils.

Ajoutez le code suivant à un fichier JavaScript :

```JavaScript
/**
* This file contains an example to show AEM Guides version 
* number when a user clicks on the Show Version icon in the toolbar. 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  window.addEventListener('DOMContentLoaded', function () {
    fmxml.ready(function () {
      fmxml.eventHandler.subscribe({
        key: 'user.alert',
        next: function next() {
          alert("AEM Guides version x.x");
        }
      });
    });
  });
})(window);
```

Ajoutez la fonction dans le fichier ui\_config.json en tant que :

```json
 {
      "type": "button",
      "icon": "alert",
      "title": "About AEM Guides",
      "variant": "quiet",

  "show": "true",
      "on-click": "user.alert"
  } 
```

L’exemple suivant montre comment modifier l’état d’un fichier actif d’un document en &quot;In-Review&quot;.

```JavaScript
/**
* This file contains an example to set the document state of an active *open documen to "In-Review". 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  //Wait for the page has been completely loaded 

  window.addEventListener('DOMContentLoaded', function () {

    //Wait for the xml editor to start
    fmxml.ready(function () {

      //Subscribe to 'user.docstate.to.in-review' event
      fmxml.eventHandler.subscribe({
        key: 'user.docstate.to.in-review',
        next: function next() {
          var docstate = "In-Review"; // New docstate name
          var filePath = fmxml.curEditor.filePath; 
// Get the file path of active open file
          if (filePath) {
            //Call API to change the doc state
            $.ajax({
              type: 'POST',
              url: '/bin/fmdita/states',
              data: {
                paths: filePath,
                operation: "setdocstates",
                docstate: docstate
              }
            }).fail(function (xhr, textStatus, errorThrown) {
              console.error("Cannot update docstate to " + docstate);
            }).success(function (data) {
              console.log('docstate updated to ' + docstate);
            });
          }
        }
      });
    });
  });
})(window);
```

Ajoutez la fonction dans le fichier ui\_config.json en tant que :

```json
 {
      "type": "button",
      "icon": "actions",
      "title": "Change document state to In-Review",
      "variant": "quiet",
      "show": "true",
      "on-click": "user.docstate.to.in-review"
    } 
```

## Suppression d’une fonction de la barre d’outils

Parfois, vous pouvez ne pas proposer toutes les fonctionnalités actuellement disponibles dans l’éditeur web. Dans ce cas, vous pouvez supprimer la fonction indésirable de la barre d’outils de l’éditeur web.

Pour supprimer toute fonction indésirable de la barre d’outils, procédez comme suit :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite.

1. Accédez au fichier de configuration par défaut disponible à l’emplacement suivant : .

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Créez une copie du fichier de configuration par défaut à l’emplacement suivant :

   `/apps/fmdita/xmleditor/ui_config.json`

1. Accédez à et ouvrez le `ui_config.json` dans le fichier `apps` pour la modification.
La variable `ui_config.json` comporte trois sections :

- **barres d’outils :**   Cette section contient la définition de toutes les fonctionnalités disponibles dans la barre d’outils de l’éditeur, telles que Insérer/Supprimer la liste numérotée, \(fichier\) Fermer, Enregistrer, Commentaires, etc.

- **raccourcis :**   Cette section contient la définition des raccourcis clavier affectés à une fonction particulière de l’éditeur.

- **templates :**   Cette section contient la structure prédéfinie des éléments DITA que vous pouvez utiliser dans votre document. Par défaut, la section Modèles contient des définitions de modèle pour un paragraphe, un tableau simple, un tableau et des éléments de corps. Vous pouvez créer une définition de modèle pour n’importe quel élément en ajoutant une structure XML valide pour l’élément souhaité. Par exemple, si vous souhaitez ajouter une `p` élément avec chaque nouveau `li` dans une liste, vous pouvez ajouter le code suivant à la fin de la section templates pour obtenir ce résultat :

```HTML
"li": "<li><p></p></li>"
```

1. Dans la section des barres d’outils, supprimez l’entrée de la fonction que vous ne souhaitez pas afficher à vos utilisateurs.

1. Enregistrez le *ui\_config.json* et rechargez l’éditeur Web.


**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
