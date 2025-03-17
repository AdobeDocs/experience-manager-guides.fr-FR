---
title: Personnaliser la barre d’outils
description: Découvrez comment personnaliser la barre d’outils
exl-id: ba82af48-9357-4f29-90ce-6793366ab432
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 5778ed2855287d1010728e689abbe6020ad56574
workflow-type: tm+mt
source-wordcount: '1013'
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

Pour ajouter une fonctionnalité à la barre d’outils de l’éditeur web, procédez comme suit :

1. Pour télécharger le fichier de configuration de l’interface utilisateur, connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils, puis cliquez sur le **Profils de dossier**.
1. Cliquez sur la mosaïque **Profil global**.
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et cliquez sur l’icône **Modifier** en haut
1. Cliquez sur l’icône **Télécharger** pour télécharger le fichier ui\_config.json sur votre système local. Vous pouvez ensuite apporter des modifications au fichier , puis le charger.
1. Dans le fichier `ui_config.json`, ajoutez la définition de la nouvelle fonctionnalité dans la section des barres d’outils. Enregistrez le fichier et chargez-le.

   En règle générale, vous pouvez créer un groupe de boutons de la barre d’outils et y ajouter un ou plusieurs boutons. Vous pouvez également ajouter un nouveau bouton de barre d’outils à un groupe de barres d’outils existant. Les informations suivantes sont requises pour créer un groupe de barre d’outils :

   **type** :   Spécifiez `blockGroup` comme valeur `type`. Cette valeur indique que vous créez un groupe de blocs qui contiendrait un ou plusieurs groupes de barres d’outils.

   **extraclass** :   Nom de la ou des classes séparées par un espace.

   **items** :   Spécifiez la définition de tous les groupes dans la barre d’outils. Chaque groupe peut contenir une ou plusieurs icônes de barre d’outils. Pour définir des icônes dans un groupe de barres d’outils, vous devez définir à nouveau l’attribut `type` dans le `items` et définir sa valeur sur `buttonGroup`. Spécifiez un ou plusieurs noms de classe dans la propriété `extraclass`. Spécifiez le nom de la fonction dans la propriété `label`. L’extrait de code suivant du fichier `ui_config.json` affiche la définition du bloc de barre d’outils principal, suivie de la définition du `buttonGroup` :

       « 
       « toolbar » : {
       « type »: « blockGroup »,
       « extraclass »:
        « opérations de la barre d’outils »,
       « items » : [
       {
       « type »: « buttonGroup »,
       « extraclass »: « left-controls »,
       « label »: « Contrôles de gauche »,
       « items » : [
       « 
   
   Dans la collection `items`, vous devez spécifier la définition d’une ou de plusieurs icônes de barre d’outils.

   Vous devez définir les propriétés suivantes pour ajouter une icône de barre d’outils :

   **type** :   Spécifiez `button` comme valeur `type`. Cette valeur indique que vous ajoutez un bouton de barre d’outils.

   **icon** :   Indiquez le nom de l’icône Coral que vous souhaitez utiliser dans la barre d’outils.

   **variante** :   Spécifiez `quiet` comme valeur `variant`.

   **title** :   Spécifiez l’info-bulle de l’icône.

   **en cas de clic** :   Indiquez le nom de commande défini pour la fonction dans le fichier JavaScript. Si votre commande nécessite des paramètres d’entrée, indiquez le nom de la commande comme suit :

       « Javascript 
       « on-click »: {« name »: « AUTHOR_INSERT_ELEMENT », « args »: « simpletable »}
       « 
   
   **afficher ou masquer** :   Si vous définissez la propriété `show` , spécifiez les modes dans lesquels l’icône s’affiche. Les valeurs possibles sont les suivantes : `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(affichage dans tous les modes\) ou `false` \(masquage dans tous les modes\).

   À la place de `show`, vous pouvez également définir la propriété `hide` . Les valeurs possibles sont identiques à celles de `show` propriété , à la différence que l’icône n’est pas affichée pour le mode spécifié.

   L’exemple ci-dessous montre le numéro de version d’AEM Guides lorsque l’utilisateur clique sur l’icône Afficher la version de la barre d’outils.

   Ajoutez le code suivant à un fichier JavaScript :

   ```Javascript
   $(document).ready(setTimeout(function() {
                           fmxml.commandHandler.subscribe({
                           key: 'user.alert',
                           next: function() {
                           alert("AEM Guides version x.x")
                           }
                           })
                           }, 1000))
   ```

   Ajoutez la fonction dans le fichier *ui\_config.json* en tant que :

   ```Javascript
   "type": "button",
   "icon": "alert","variant": "quiet","title": "About AEM Guides","show": "true","on-click": "user.alert"
   ```

1. Créez un dossier *clientlib* et ajoutez-y votre JavaScript.

1. Mettez à jour la propriété categories du dossier *clientlib* en lui affectant la valeur *apps.fmdita.xml\_editor.page\_overrides*.

1. Enregistrez le fichier *ui\_config.json* et rechargez l’éditeur web.


## Supprimer une fonctionnalité de la barre d’outils

Parfois, vous pouvez ne pas vouloir donner toutes les fonctionnalités actuellement disponibles dans l&#39;éditeur Web, dans ce cas, vous pouvez supprimer la fonctionnalité indésirable de la barre d&#39;outils de l&#39;éditeur Web.

Effectuez les étapes suivantes pour supprimer toute fonctionnalité indésirable de la barre d’outils :

1. Pour télécharger le fichier de configuration de l’interface utilisateur, connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils, puis cliquez sur le **Profils de dossier**.
1. Cliquez sur la mosaïque **Profil global**.
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et cliquez sur l’icône **Modifier** en haut
1. Cliquez sur l’icône **Télécharger** pour télécharger le fichier ui\_config.json sur votre système local. Vous pouvez ensuite apporter des modifications au fichier , puis le charger.

   Le fichier `ui_config.json` comporte trois sections :

   1. **barres d’outils** :   Cette section contient la définition de toutes les fonctionnalités disponibles dans la barre d’outils de l’éditeur, telles que Insérer/Supprimer une liste numérotée, \(fichier\) Fermer, Enregistrer, Commentaires, etc.

   1. **raccourcis** :   Cette section contient la définition des raccourcis clavier affectés à une fonctionnalité particulière de l’éditeur.

   1. **modèles** :   Cette section contient la structure prédéfinie des éléments DITA que vous pouvez utiliser dans votre document. Par défaut, la section Modèles contient des définitions de modèle pour un paragraphe, un tableau simple, un tableau et des éléments de corps. Vous pouvez créer une définition de modèle pour n’importe quel élément en ajoutant une structure XML valide pour l’élément souhaité. Par exemple, si vous souhaitez ajouter un élément `p` avec chaque nouvel élément `li` dans une liste, vous pouvez ajouter le code suivant à la fin de la section modèles pour obtenir ce résultat :

   ```css
   "li": "<li><p></p></li>"
   ```

1. Dans la section des barres d’outils, supprimez l’entrée de la fonction que vous ne souhaitez pas présenter à vos utilisateurs.

1. Enregistrez le fichier *ui\_config.json* et rechargez l’éditeur web.


**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
