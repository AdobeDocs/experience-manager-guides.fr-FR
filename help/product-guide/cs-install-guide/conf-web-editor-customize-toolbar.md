---
title: Barre d’outils Personnaliser
description: Découvrez comment personnaliser la barre d’outils
exl-id: ba82af48-9357-4f29-90ce-6793366ab432
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 0%

---

# Barre d’outils Personnaliser {#id172FB00L0V6}

Par défaut, l’éditeur web est fourni avec les fonctionnalités éditoriales les plus courantes requises par n’importe quel éditeur DITA. Des fonctionnalités telles que l’insertion d’éléments de type liste \(numérotée ou à puces\), référence croisée, référence de contenu, tableau, paragraphe et mise en forme des caractères sont disponibles dans l’éditeur. Outre ces éléments de base, vous pouvez personnaliser l’éditeur Web pour insérer les éléments utilisés dans votre environnement de création.

La barre d’outils de l’éditeur Web peut être personnalisée de deux façons :

- Ajouter une nouvelle fonctionnalité à la barre d’outils

- Supprimer toutes les fonctionnalités existantes de la barre d’outils


## Ajouter une fonction dans la barre d’outils

L’ajout d’une fonctionnalité à l’éditeur Web implique deux tâches principales : l’ajout d’une icône pour la fonctionnalité dans le fichier *ui\_config.json* et l’ajout de la fonctionnalité d’arrière-plan dans JavaScript.

Pour ajouter une fonction à la barre d’outils de l’éditeur web, procédez comme suit :

1. Pour télécharger le fichier de configuration de l’interface utilisateur, connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et sélectionnez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils et cliquez sur le **Profil de dossier**.
1. Cliquez sur la mosaïque **Profil global** .
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et cliquez sur l’icône **Modifier** en haut
1. Cliquez sur l’icône **Télécharger** pour télécharger le fichier ui\_config.json sur votre système local. Vous pouvez ensuite apporter des modifications au fichier, puis charger le même fichier.
1. Dans le fichier `ui_config.json`, ajoutez la définition de la nouvelle fonctionnalité dans la section des barres d’outils. Enregistrez le fichier et téléchargez-le.

   En règle générale, vous pouvez créer un groupe de boutons de barre d’outils et y ajouter un ou plusieurs boutons. Vous pouvez également ajouter un nouveau bouton de barre d’outils dans un groupe existant. Les détails suivants sont requis pour créer un groupe de barres d’outils :

   **type** :   Spécifiez `blockGroup` comme valeur `type`. Cette valeur indique que vous créez un groupe de blocs qui contiendra un ou plusieurs groupes de barres d’outils.

   **extraclass** :   Nom de la ou des classes séparées par un espace.

   **items** :   Spécifiez la définition de tous les groupes dans la barre d’outils. Chaque groupe peut contenir une ou plusieurs icônes de barre d’outils. Pour définir des icônes dans un groupe de barres d’outils, vous devez définir à nouveau l’attribut `type` dans le `items`, puis définir sa valeur sur `buttonGroup`. Spécifiez un ou plusieurs noms de classe dans la propriété `extraclass`. Indiquez le nom de la fonctionnalité dans la propriété `label`. Le fragment de code suivant du fichier `ui_config.json` affiche la définition du bloc de barre d’outils principal, suivie de la définition `buttonGroup` :

       &quot;
       &quot;toolbar&quot;: {
       &quot;type&quot;: &quot;blockGroup&quot;,
       &quot;extraclass&quot;:
       &quot;toolbar operations&quot;,
       &quot;items&quot;: [
       {
       &quot;type&quot;: &quot;buttonGroup&quot;,
       &quot;extraclass&quot;: &quot;left-control&quot;,
       &quot;label&quot;: &quot;Contrôles à gauche&quot;,
       &quot;items&quot;: [
       &quot;
   
   Dans la collection `items`, vous devez spécifier la définition d’une ou de plusieurs icônes de barre d’outils.

   Pour ajouter une icône de barre d’outils, vous devez définir les propriétés suivantes :

   **type** :   Spécifiez `button` comme valeur `type`. Cette valeur indique que vous ajoutez un bouton de barre d’outils.

   **icon** :   Indiquez le nom de l’icône Coral que vous souhaitez utiliser dans la barre d’outils.

   **variant** :   Spécifiez `quiet` comme valeur `variant`.

   **title** :   Spécifiez l’info-bulle de l’icône.

   **on-click** :   Spécifiez le nom de commande défini pour la fonction dans le fichier JavaScript. Si votre commande nécessite des paramètres d’entrée, indiquez le nom de la commande comme suit :

       &quot;Javascript
       &quot;on-click&quot;: {&quot;name&quot;: &quot;AUTHOR_INSERT_ELEMENT&quot;, &quot;args&quot;: &quot;simpletable&quot;}
       &quot;
   
   **afficher ou masquer** :   Si vous définissez la propriété `show`, spécifiez les modes d’affichage de l’icône. Les valeurs possibles sont : `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(affichage dans tous les modes\) ou `false` \(masquage dans tous les modes\).

   Au lieu de `show`, vous pouvez également définir la propriété `hide`. Les valeurs possibles sont identiques à celles de la propriété `show` avec la seule différence que l’icône ne s’affiche pas pour le mode spécifié.

   L’exemple suivant illustre le numéro de version d’AEM Guides lorsque l’utilisateur clique sur l’icône Afficher la version de la barre d’outils.

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

1. Créez un dossier *clientlib* et ajoutez votre JavaScript dans ce dossier.

1. Mettez à jour la propriété categories du dossier *clientlib* en lui affectant la valeur *apps.fmdita.xml\_editor.page\_overrides*.

1. Enregistrez le fichier *ui\_config.json* et rechargez l’éditeur Web.


## Suppression d’une fonction de la barre d’outils

Parfois, vous pouvez ne pas proposer toutes les fonctionnalités actuellement disponibles dans l’éditeur web. Dans ce cas, vous pouvez supprimer la fonction indésirable de la barre d’outils de l’éditeur web.

Pour supprimer toute fonction indésirable de la barre d’outils, procédez comme suit :

1. Pour télécharger le fichier de configuration de l’interface utilisateur, connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et sélectionnez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils et cliquez sur le bouton **Profils de dossier**.
1. Cliquez sur la mosaïque **Profil global** .
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et cliquez sur l’icône **Modifier** en haut
1. Cliquez sur l’icône **Télécharger** pour télécharger le fichier ui\_config.json sur votre système local. Vous pouvez ensuite apporter des modifications au fichier, puis charger le même fichier.

   Le fichier `ui_config.json` comporte trois sections :

   1. **toolbars** :   Cette section contient la définition de toutes les fonctionnalités disponibles dans la barre d’outils de l’éditeur, telles que Insérer/Supprimer la liste numérotée, \(fichier\) Fermer, Enregistrer, Commentaires, etc.

   1. **raccourcis** :   Cette section contient la définition des raccourcis clavier affectés à une fonction particulière de l’éditeur.

   1. **templates** :   Cette section contient la structure prédéfinie des éléments DITA que vous pouvez utiliser dans votre document. Par défaut, la section Modèles contient des définitions de modèle pour un paragraphe, un tableau simple, un tableau et des éléments de corps. Vous pouvez créer une définition de modèle pour n’importe quel élément en ajoutant une structure XML valide pour l’élément souhaité. Par exemple, si vous souhaitez ajouter un élément `p` avec chaque nouvel élément `li` dans une liste, vous pouvez ajouter le code suivant à la fin de la section des modèles pour obtenir ce résultat :

   ```css
   "li": "<li><p></p></li>"
   ```

1. Dans la section des barres d’outils, supprimez l’entrée de la fonction que vous ne souhaitez pas afficher à vos utilisateurs.

1. Enregistrez le fichier *ui\_config.json* et rechargez l’éditeur Web.


**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
