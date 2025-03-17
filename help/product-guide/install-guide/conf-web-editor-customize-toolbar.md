---
title: Personnaliser la barre d’outils
description: Découvrez comment personnaliser la barre d’outils
exl-id: 14a82c7e-5c07-43a8-bd9e-b221d80f6d05
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 5778ed2855287d1010728e689abbe6020ad56574
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 0%

---

# Personnaliser la barre d’outils {#id172FB00L0V6}

Par défaut, Web Editor est fourni avec les fonctions éditoriales les plus courantes requises par un éditeur DITA. Des fonctionnalités telles que l’insertion d’éléments de type liste \(numérotée ou à puces\), référence croisée, référence de contenu, tableau, paragraphe et mise en forme de caractères sont disponibles dans l’éditeur. Outre ces éléments de base, vous pouvez personnaliser l’éditeur web afin d’insérer des éléments utilisés dans votre environnement de création.

>[!NOTE]
>
> Lors de la migration de l’ancienne interface utilisateur vers la nouvelle interface utilisateur d’AEM Guides (applicable à partir des versions 2502 et 5.0 d’AEM Guides), les mises à jour apportées à `ui_config` doivent être converties en configurations d’interface utilisateur plus flexibles et modulaires. Ce framework permet d’adopter facilement des modifications dans editor_toolbar et d’autres widgets cibles, le cas échéant. Pour plus d’informations, consultez [Présentation de la configuration de l’interface utilisateur de conversion](https://experienceleague.adobe.com/en/docs/experience-manager-guides-learn/videos/advanced-user-guide/conver-ui-config).

Vous pouvez personnaliser la barre d’outils de l’éditeur web de deux manières différentes :

- Ajouter une nouvelle fonctionnalité à la barre d’outils

- Supprimez toute fonctionnalité existante de la barre d’outils


## Ajout d’une fonctionnalité dans la barre d’outils

L’ajout d’une fonctionnalité à l’éditeur web implique deux tâches principales : l’ajout d’une icône pour la fonctionnalité dans le fichier *ui\_config.json* et l’ajout de la fonctionnalité en arrière-plan dans JavaScript.

**Ajouter une icône dans la barre d’outils**

Pour ajouter une fonctionnalité à la barre d’outils de l’éditeur web, procédez comme suit :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite .

1. Accédez au fichier de configuration par défaut disponible à l’emplacement suivant :

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Créez une copie du fichier de configuration par défaut à l’emplacement suivant :

   `/apps/fmdita/xmleditor/ui_config.json`

1. Accédez au fichier `ui_config.json` et ouvrez-le dans le nœud `apps` pour le modifier.

1. Dans le fichier `ui_config.json`, ajoutez la définition de la nouvelle fonctionnalité dans la section des barres d’outils. En règle générale, vous pouvez créer un groupe de boutons de la barre d’outils et y ajouter un ou plusieurs boutons. Vous pouvez également ajouter un nouveau bouton de barre d’outils à un groupe de barres d’outils existant. Les informations suivantes sont requises pour créer un groupe de barre d’outils :

   - **type:**Spécifiez `blockGroup` comme valeur `type`. Cette valeur indique que vous créez un groupe de blocs qui contiendrait un ou plusieurs groupes de barres d’outils.

   - **extraclass:** Nom de la ou des classes séparées par un espace.

   - **items :** spécifiez la définition de tous les groupes dans la barre d’outils. Chaque groupe peut contenir une ou plusieurs icônes de barre d’outils. Pour définir des icônes dans un groupe de barres d’outils, vous devez définir à nouveau l’attribut `type` dans le `items` et définir sa valeur sur `buttonGroup`. Spécifiez un ou plusieurs noms de classe dans la propriété `extraclass`. Spécifiez le nom de la fonction dans la propriété `label`. L’extrait de code suivant du fichier `ui_config.json` affiche la définition du bloc de barre d’outils principal, suivie de la définition du `buttonGroup` :

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

     Dans la collection `items`, vous devez spécifier la définition d’une ou de plusieurs icônes de barre d’outils.
Vous devez définir les propriétés suivantes pour ajouter une icône de barre d’outils :

   - **type :** spécifiez `button` comme valeur `type`. Cette valeur indique que vous ajoutez un bouton de barre d’outils.

   - **icon :** spécifiez le nom de l’icône Coral que vous souhaitez utiliser dans la barre d’outils.

   - **variante :** spécifiez `quiet` comme valeur `variant`.

   - **titre :** spécifiez l’info-bulle de l’icône.

   - **en cas de clic :** spécifiez le nom de commande défini pour la fonction dans le fichier JavaScript. Si votre commande nécessite des paramètres d’entrée, indiquez le nom de la commande comme suit :

     ```JavaScript
     "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
     ```

   - **afficher ou masquer :** si vous définissez la propriété `show`, indiquez les modes d’affichage de l’icône. Les valeurs possibles sont les suivantes : `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(affichage dans tous les modes\) ou `false` \(masquage dans tous les modes\).

   À la place de `show`, vous pouvez également définir la propriété `hide` . Les valeurs possibles sont identiques à celles de `show` propriété , à la différence que l’icône n’est pas affichée pour le mode spécifié.

1. Créez un dossier *clientlib* et ajoutez-y votre JavaScript.

1. Mettez à jour la propriété categories du dossier *clientlib* en lui affectant la valeur *apps.fmdita.xml\_editor.page\_overrides*.

1. Enregistrez le fichier *ui\_config.json* et rechargez l’éditeur web.


**exemples de code JavaScript**

Cette section fournit deux exemples de code JavaScript qui vous aideront à commencer à ajouter des fonctionnalités personnalisées. L’exemple ci-dessous montre le numéro de version d’AEM Guides lorsqu’un utilisateur clique sur l’icône Afficher la version de la barre d’outils.

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

L&#39;exemple suivant montre comment modifier l&#39;état d&#39;un document d&#39;un fichier actif en « En révision ».

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

## Supprimer une fonctionnalité de la barre d’outils

Parfois, vous pouvez ne pas vouloir donner toutes les fonctionnalités actuellement disponibles dans l&#39;éditeur Web, dans ce cas, vous pouvez supprimer la fonctionnalité indésirable de la barre d&#39;outils de l&#39;éditeur Web.

Effectuez les étapes suivantes pour supprimer toute fonctionnalité indésirable de la barre d’outils :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite .

1. Accédez au fichier de configuration par défaut disponible à l’emplacement suivant :.

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Créez une copie du fichier de configuration par défaut à l’emplacement suivant :

   `/apps/fmdita/xmleditor/ui_config.json`

1. Accédez au fichier `ui_config.json` et ouvrez-le dans le nœud `apps` pour le modifier.
Le fichier `ui_config.json` comporte trois sections :

- **toolbars:**   Cette section contient la définition de toutes les fonctionnalités disponibles dans la barre d’outils de l’éditeur, telles que Insérer/Supprimer une liste numérotée, \(fichier\) Fermer, Enregistrer, Commentaires, etc.

- **raccourcis:**   Cette section contient la définition des raccourcis clavier affectés à une fonctionnalité particulière de l’éditeur.

- **templates:**   Cette section contient la structure prédéfinie des éléments DITA que vous pouvez utiliser dans votre document. Par défaut, la section Modèles contient des définitions de modèle pour un paragraphe, un tableau simple, un tableau et des éléments de corps. Vous pouvez créer une définition de modèle pour n’importe quel élément en ajoutant une structure XML valide pour l’élément souhaité. Par exemple, si vous souhaitez ajouter un élément `p` avec chaque nouvel élément `li` dans une liste, vous pouvez ajouter le code suivant à la fin de la section modèles pour obtenir ce résultat :

```HTML
"li": "<li><p></p></li>"
```

1. Dans la section des barres d’outils, supprimez l’entrée de la fonction que vous ne souhaitez pas présenter à vos utilisateurs.

1. Enregistrez le fichier *ui\_config.json* et rechargez l’éditeur web.


**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
