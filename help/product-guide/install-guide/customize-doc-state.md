---
title: Configuration des états du document
description: Découvrez comment configurer des états de document
exl-id: d7603b4e-aae4-48ca-be84-8edb51626405
feature: Document State
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 0%

---

# Configuration des états du document {#id181GB0400UI}

AEM Guides vous permet de définir les états du document des rubriques DITA en fonction des besoins de votre entreprise. Vous pouvez définir différents états de votre document du début à la fin. Par exemple, le premier état peut être Version préliminaire et il peut passer à Révision, Approuvé, Traduit et enfin à Publié.

Un sujet peut passer d’un état à un autre de deux façons : manuelle et automatique. Les états du document définis dans un profil peuvent être utilisés pour modifier manuellement l’état du document. Vous pouvez le faire à partir de la page Propriétés d’un fichier de rubrique. Vous pouvez également définir qui peut déplacer le document d’un état à un autre. Par exemple, un auteur peut créer un document et l’état par défaut du document peut être Version préliminaire. Lorsque l’auteur envoie le document pour révision, il peut modifier l’état du document en In-Review. Le réviseur peut modifier l’état du document en Approuvé ou en Version préliminaire en fonction du processus de révision. Si le document est Approuvé, l’éditeur peut modifier l’état du document en Traduit ou Publié selon le processus.

>[!NOTE]
>
> Si un utilisateur appartient au groupe *administrateurs*, il peut modifier l’état d’un document à partir de n’importe quel état, indépendamment des transitions d’état du document définies dans le système.

## Création d’un état de document

AEM Guides est fourni avec un ensemble d’états de document par défaut. Ces états sont les suivants :

- Brouillon
- Modifier
- En révision
- Approuvé
- Révisé
- Terminé

Ces états par défaut sont disponibles pour toutes les rubriques DITA créées sous DAM. Vous pouvez créer vos propres états de document et les affecter à un dossier spécifique. Tous les fichiers DITA créés sous ce dossier auront alors accès aux états de document nouvellement créés.

Pour créer des états de document à l’aide du profil de dossier, procédez comme suit :

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et sélectionnez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils.
1. Cliquez sur la mosaïque États du document .

   La page Assets States s’affiche. Par défaut, la page affiche un profil par défaut.

1. Cliquez sur **Créer un profil** et saisissez les détails suivants :
   - Saisissez le nom du profil dans le champ Profil .
   - Spécifiez le chemin d’accès auquel appliquer le nouveau profil.
   - Spécifiez les états du document dans les **états autorisés** sous **états**. Les états du document par défaut sont Brouillon, Modifier, En révision, Approuvé et Terminé.-

     Cliquez sur le bouton **Ajouter** pour ajouter un état de document.

      - Cliquez sur l’icône Supprimer pour supprimer un état de document.

     >[!NOTE]
     >
     > Ne supprimez pas un état de document si les documents sont toujours dans cet état. Si vous supprimez un état de document, vous ne pourrez pas modifier l’état du document de ces documents, sauf si vous appartenez au groupe d’utilisateurs *administrator* .

   - Spécifiez l’état de début du document dans l’état **Start State**.
   - Spécifiez l’état de fin du document dans l’état **End State**.
   - Spécifiez la transition d’état du document dans **De** et **À** sous **Transition d’état**.

      - Spécifiez les utilisateurs et les groupes d’utilisateurs qui peuvent modifier l’état du document dans **Groups**.

      - Cliquez sur le bouton **Ajouter** pour ajouter une transition d’état.

      - Cliquez sur l’icône Supprimer pour supprimer une transition d’état.

     >[!NOTE]
     >
     > Ne supprimez pas une transition d’état si les documents sont toujours à l’état `From`. Si vous supprimez une transition d’état, vous ne pourrez pas modifier l’état du document de ces documents, sauf si vous appartenez au groupe d’utilisateurs *administrator* .

1. Cliquez sur **Terminé**.

## Création d’une copie d’un profil d’état de document

Selon vos besoins, vous pouvez créer une copie d’un profil d’état de document existant. Vous pouvez utiliser la copie comme base pour créer un autre profil de document.

Pour créer une copie d’un profil d’état de document, procédez comme suit :

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et sélectionnez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils.
1. Cliquez sur la mosaïque États du document .

   La page Assets States s’affiche.

1. Sélectionnez le profil d’état du document que vous souhaitez dupliquer et cliquez sur **Dupliquer le profil**.
1. Apportez les modifications requises et cliquez sur **Terminé**.

## Suppression d’un état ou d’une transition d’état de document

>[!NOTE]
>
> Ne supprimez pas une transition d’état ou d’état du document si les documents se trouvent toujours à l’état ou dans une transition d’état. Si vous supprimez une transition d’état ou d’état, vous ne pourrez pas modifier l’état du document de ces documents, sauf si vous appartenez au groupe d’utilisateurs *administrator* .

Effectuez les étapes suivantes pour supprimer une transition d’état ou d’état de document d’un profil d’état de document :

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et sélectionnez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils.
1. Cliquez sur la mosaïque États du document .

   La page Assets States s’affiche.

1. Sélectionnez le profil d’état du document à partir duquel vous souhaitez supprimer l’état du document et cliquez sur **Modifier le profil**.
1. Supprimez la transition d’état ou d’état du document et cliquez sur **Terminé**.

## Suppression d’un profil d’état de document

Pour supprimer un profil d’état de document, procédez comme suit :

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et sélectionnez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils.
1. Cliquez sur la mosaïque États du document .

   La page Assets States s’affiche.

1. Sélectionnez le profil d’état du document que vous souhaitez supprimer, puis cliquez sur **Supprimer le profil**.

## Automatiser la modification de l’état du document

Si vous ne souhaitez pas modifier manuellement les états du document, vous pouvez créer un processus et automatiser la modification de l’état du document.

>[!NOTE]
>
> Les workflows automatisés doivent être conformes aux états et aux transitions du document définis dans la configuration. Le système n’effectue aucune vérification des modifications d’état effectuées par le biais de workflows automatisés.

Effectuez les étapes suivantes pour automatiser la modification de l’état du document :

1. Ouvrez la page de workflow à partir de l’URL du serveur AEM.

   `<AEM_Server_URL>:<port>/workflow`

1. Ouvrez un workflow à partir de la page du workflow. Par exemple, consultez la rubrique.
1. Sélectionnez **Étape du processus** dans la section **Workflow** de la boîte de dialogue AEM et effectuez un glisser-déposer sur le workflow.

   ![](assets/process-step-workflow.png)

1. Double-cliquez sur le processus et ouvrez la boîte de dialogue **Propriétés de l’étape**.
1. Saisissez les détails suivants dans l’onglet **Process** de la boîte de dialogue et cliquez sur OK :
   - Sélectionnez **Set Document State for any DAM asset** dans la liste déroulante Process.
   - Cochez la case Avance du gestionnaire .
   - Saisissez le nom de l’état du document dans la zone de texte **Arguments** .

     >[!NOTE]
     >
     > Veillez à saisir l’état correct du document dans la zone de texte Argument . Si vous saisissez un nom incorrect, le document sera défini sur le mauvais état du document.

1. Cliquez sur **Enregistrer** pour enregistrer le workflow.

## Activer le workflow de validation

AEM Guides fournit un processus d’approbation de document qui vous aide à contrôler le cycle de vie de votre processus de développement de documents. Pour activer le workflow de validation, procédez comme suit :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite.

1. Accédez au fichier de configuration par défaut disponible à l’emplacement suivant :

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Créez une copie du fichier de configuration par défaut à l’emplacement suivant :

   `/apps/fmdita/xmleditor/ui_config.json`

1. Accédez au fichier `ui_config.json` et ouvrez-le dans le noeud `apps` pour le modifier.

1. Dans le fichier `ui_config.json`, activez la fonction de processus d&#39;approbation en modifiant la section *features* comme illustré ci-dessous :

   ```json
   "features":  
   { 
      "approvalWorkflow":  true 
   }
   ```
