---
title: Modification des rubriques dans l’éditeur web
description: Découvrez comment modifier des rubriques dans l’éditeur web. Découvrez les différentes fonctions d’édition permettant de modifier vos fichiers de rubrique dans AEM Guides.
feature: Authoring, Web Editor
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 0%

---

# Modification des rubriques dans l’éditeur web {#id2056B040VUI}

L’éditeur web s’accompagne d’un éventail de fonctions d’édition qui vous permettent de créer ou de modifier facilement vos fichiers de rubrique. Pour modifier une rubrique dans l’éditeur web, procédez comme suit.

>[!IMPORTANT]
>
> Si vous rencontrez une erreur d’application lors de l’utilisation de l’éditeur Web, actualisez la page pour continuer à fonctionner.

1. Pour apporter des modifications à votre rubrique, cliquez dans la limite de texte de l’élément requis et commencez à apporter des modifications.

1. Pour insérer un élément spécifique, cliquez à la fin de l’élément après lequel vous souhaitez insérer le nouvel élément et cliquez sur l’icône de l’élément requis dans la barre d’outils. Vous pouvez également utiliser le raccourci clavier `Alt+Enter` pour appeler la fenêtre contextuelle **Insérer l’élément** .

   Une liste d’éléments s’affiche et peut être utilisée dans la rubrique. AEM Guides effectue un placement intelligent d’éléments en fonction de leur emplacement valide dans la rubrique.

   >[!NOTE]
   >
   > Vous pouvez également choisir l’icône à afficher dans la barre d’outils en configurant le fichier `ui_config.json` situé à l’emplacement - `/etc/designs/fmdita/clientlibs/xmleditor/`. Pour plus d’informations sur la personnalisation des fonctionnalités, contactez votre administrateur système.

1. Une fois que vous avez terminé de modifier votre document, cliquez sur **Enregistrer**.

   >[!NOTE]
   >
   > Si vous ne souhaitez pas valider les modifications dans AEM référentiel, cliquez sur **Fermer**, puis sur **Fermer sans enregistrer** dans la boîte de dialogue Modifications non enregistrées.


## Sélection partielle de contenu entre les éléments

Experience Manager Guides vous permet également de sélectionner du contenu sur plusieurs éléments. Après avoir sélectionné le contenu, vous pouvez effectuer les opérations suivantes :
- Mise en forme et suppression : mettez le contenu sélectionné en gras, en italique, en souligné ou supprimez-le. Le contenu des balises ouvertes valides est ensuite fusionné et apparaît sous un seul élément. Vous pouvez par exemple sélectionner le contenu d’un paragraphe et étendre la sélection à un autre paragraphe. Ensuite, si vous mettez le contenu sélectionné en gras, tout le contenu en gras des balises ouvertes est fusionné et s’affiche sous un seul élément de paragraphe.

De même, si vous supprimez le contenu sélectionné, le contenu restant après la suppression dans les balises ouvertes est fusionné.

- Entourez le contenu d’un élément valide : procédez comme suit pour encapsuler le contenu avec un élément valide :
   - Sélectionnez le contenu dans un élément.
   - Sélectionnez l’icône ![add](images/Add_icon.svg) dans la barre d’outils secondaire supérieure pour afficher la boîte de dialogue **Surround with Element**. La boîte de dialogue répertorie les éléments valides pour le contenu sélectionné.
     >[!NOTE]
     >
     > Vous pouvez également afficher la boîte de dialogue Survoler avec l’élément en sélectionnant le menu contextuel du contenu sélectionné.

   - Sélectionnez un élément dans la boîte de dialogue. Le contenu sélectionné est encapsulé sous cet élément. Par exemple, si vous sélectionnez le contenu d’un paragraphe, puis l’élément `<note>` dans la boîte de dialogue **Survoler avec l’élément** , le contenu sélectionné s’affiche sous une note.\
     ![Boîte de dialogue d’élément entouré](./images/surround-element.png) {width="300" align="left"}

## Actualiser le navigateur lors de la modification des fichiers

Experience Manager Guides prend en charge l’actualisation du navigateur lorsque vous modifiez votre contenu dans l’éditeur web. Cette fonctionnalité vous permet de continuer à modifier le contenu si vous rencontrez une erreur d’application pendant que vous travaillez. Si vous appuyez sur l’actualisation du navigateur alors qu’un ou plusieurs fichiers contenant des modifications non enregistrées sont ouverts pour modification, vous êtes averti que les modifications non enregistrées risquent d’être perdues. Vous avez la possibilité d’annuler l’opération d’actualisation et d’enregistrer vos fichiers pour conserver vos modifications.

Même lors de l’actualisation du navigateur, les vues des panneaux gauche et droit sont conservées dans l’éditeur web. Experience Manager Guides restaure le dernier état enregistré des fichiers ouverts dans l’éditeur Web lors de l’actualisation du navigateur. Par exemple, les fichiers ouverts dans le panneau Référentiel sont à nouveau ouverts. Le panneau de mappage est conservé avec la carte précédemment ouverte.

La rubrique active ou le mappage DITA est rouvert dans la zone de modification du contenu.

Le panneau de droite est également rouvert et affiche la même vue qu’avant l’actualisation.

## Indicateur de copie de travail

AEM Guides fournit l’indicateur de copie de travail qui indique si la \(copie de travail\) actuelle du fichier est synchronisée ou non avec la version enregistrée. Si vous avez apporté des modifications à votre copie actuelle et n’avez pas enregistré votre fichier, une marque \* apparaît avec le titre dans l’onglet Fichier du sujet. Cet indicateur sert de rappel pour enregistrer les modifications et disparaît lorsque vous enregistrez votre fichier.

![indicateur de copie de travail](images/working-copy-text-update-indicator.png){width="550" align="left"}

AEM Guides indique également si la dernière copie enregistrée \(en cours\) du fichier est synchronisée ou non avec la version enregistrée. Si vous constatez des modifications non enregistrées entre la copie de travail et la dernière version enregistrée, un signe \* s’affiche avec les informations de version affichées dans le coin supérieur droit de l’onglet du fichier de la rubrique. Cet indicateur sert de rappel pour enregistrer et créer une version à partir de votre copie \(en cours\) actuelle du fichier.

![Indicateur de mise à jour de version](images/version-update-indicator.png){width="550" align="left"}




## Recherche d’un fichier ouvert en mode Référentiel

Lors de l’ouverture d’un fichier dans l’éditeur web, Experience Manager Guides vous permet de localiser le fichier en mode Référentiel. Par exemple, il localise la rubrique en cours pendant que vous la modifiez.

Vous pouvez désactiver la fonction pour localiser le fichier à l’aide de l’option **Toujours localiser les fichiers dans le référentiel** de l’onglet **Apparence** des **préférences utilisateur**.


**Rubrique parente :**[ Utilisation de l’éditeur web](web-editor.md)
