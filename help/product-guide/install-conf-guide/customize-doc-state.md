---
title: Configurer les états du document
description: Découvrez comment configurer les états de document
feature: Document State
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '1434'
ht-degree: 0%

---

# Configurer les états du document {#id181GB0400UI}

AEM Guides vous permet de définir les états du document pour vos rubriques DITA en fonction des besoins de votre entreprise. Vous pouvez définir différents états de votre document du début à la fin. Par exemple, le premier état peut être Brouillon et passer à Révision, Approuvé, Traduit et enfin à Publié.

Un sujet peut passer d&#39;un état à un autre de deux façons : manuellement et automatiquement. Les états du document définis dans un profil peuvent être utilisés pour modifier manuellement l’état du document. Cette opération peut être effectuée à partir de la page Propriétés d’un fichier de rubrique. Vous pouvez également définir qui peut déplacer le document d’un état à un autre. Par exemple, un auteur peut créer un document et l’état par défaut du document peut être Brouillon. Lorsque l’auteur envoie le document pour révision, elle peut modifier le statut du document en Révision. Le réviseur ou la réviseuse peut modifier le statut du document en Approuvé ou à nouveau en Version préliminaire selon le processus de révision. Si le document est approuvé, l’éditeur peut modifier l’état du document en Traduit ou Publié , selon le workflow.

>[!NOTE]
>
> Si un utilisateur appartient au groupe *administrateurs*, il peut changer l’état d’un document à partir de n’importe quel état, indépendamment des transitions d’état de document définies dans le système.

## Créer un état de document

AEM Guides est fourni avec un ensemble d’états de document par défaut. Ces états sont les suivants :

- Brouillon
- Modifier
- En cours de révision
- Approuvé
- Reviewed
- Terminé

Ces états par défaut sont disponibles pour toutes les rubriques DITA créées sous DAM. Vous pouvez créer vos propres états de document et les affecter à un dossier spécifique. Tous les fichiers DITA créés sous ce dossier auront alors accès aux états du document nouvellement créé.

Pour créer des états de document à l’aide du profil de dossier, procédez comme suit :

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils.
1. Cliquez sur la mosaïque États du document .

   La page États d’Assets s’affiche. Par défaut, la page affiche un profil par défaut.

1. Cliquez sur **Créer un profil** et saisissez les détails suivants :
   - Saisissez le nom du profil dans le champ Profil .
   - Indiquez le chemin d’accès auquel vous souhaitez appliquer le nouveau profil.
   - Spécifiez les états du document dans l’**États autorisés** sous **États**.

     Les états par défaut du document sont Brouillon, Modifier, En cours de révision, Approuvé et Terminé.-

   - Cliquez sur le bouton **Ajouter** pour ajouter un état de document.

   - Cliquez sur l’icône Supprimer pour supprimer un état de document.

     >[!NOTE]
     >
     > Ne supprimez pas un état de document si des documents sont toujours dans cet état. Si vous supprimez un état de document, vous ne pourrez pas modifier son état à moins d&#39;appartenir au groupe d&#39;utilisateurs *administrateur*.

   - Spécifiez l’état de début du document dans l’**État de début**.
   - Spécifiez l’état de fin du document dans l’**État de fin**.
   - Spécifiez la transition d’état du document dans **De** et **À** sous **Transition d’état**.

      - Spécifiez les utilisateurs et les groupes d’utilisateurs qui peuvent modifier le statut du document dans **Groupes**.

      - Cliquez sur le bouton **Ajouter** pour ajouter une transition d’état.

      - Cliquez sur l’icône Supprimer pour supprimer une transition d’état.

     >[!NOTE]
     >
     > Ne supprimez pas une transition d’état si les documents sont toujours à l’état `From`. Si vous supprimez une transition d&#39;état, vous ne pourrez pas modifier l&#39;état de ces documents à moins d&#39;appartenir au groupe d&#39;utilisateurs *administrateur*.

1. Cliquez sur **Terminé**.

## Création d’une copie d’un profil d’état de document

Selon vos besoins, vous pouvez créer une copie d’un profil d’état de document existant. Vous pouvez utiliser la copie comme base pour créer un autre profil de document.

Pour créer une copie d’un profil d’état de document, procédez comme suit :

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils.
1. Cliquez sur la mosaïque États du document .

   La page États d’Assets s’affiche.

1. Sélectionnez le profil d&#39;état du document à dupliquer et cliquez sur **Dupliquer le profil**.
1. Apportez les modifications requises, puis cliquez sur **Terminé**.

## Supprimer un état de document ou une transition d&#39;état

>[!NOTE]
>
> Ne supprimez pas un état de document ou une transition d&#39;état si les documents sont toujours dans l&#39;état ou dans la transition d&#39;état. Si vous supprimez un état ou une transition d&#39;état, vous ne pourrez pas modifier l&#39;état du document de ces documents à moins d&#39;appartenir au groupe d&#39;utilisateurs *administrateur*.

Effectuez les étapes suivantes pour supprimer un état de document ou une transition d’état d’un profil d’état de document :

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils.
1. Cliquez sur la mosaïque États du document .

   La page États d’Assets s’affiche.

1. Sélectionnez le profil d’état du document à partir duquel vous souhaitez supprimer l’état du document, puis cliquez sur **Modifier le profil**.
1. Supprimez l&#39;état ou la transition d&#39;état du document et cliquez sur **Terminé**.

## Suppression d’un profil d’état de document

Pour supprimer un profil d’état de document, procédez comme suit :

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils.
1. Cliquez sur la mosaïque **États du document**.

   La page États d’Assets s’affiche.

1. Sélectionnez le profil d&#39;état du document à supprimer, puis cliquez sur **Supprimer le profil**.

## Automatiser le changement d’état du document

Si vous ne souhaitez pas modifier manuellement les états du document, vous pouvez créer un workflow et automatiser le changement d’état du document.

>[!NOTE]
>
> Les workflows automatisés doivent être conformes aux états et transitions du document définis dans la configuration. Le système n’effectue aucune vérification des changements d’état effectués par le biais de workflows automatisés.

Les onglets suivants fournissent des instructions pour automatiser le changement d’état du document en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB Tab]

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez **Workflow** dans la liste des outils.

1. Cliquez sur la mosaïque **Modèles**.

1. Sélectionnez le workflow approprié, par exemple Rubriques de révision.

1. Cliquez sur **Modifier**.

   Le workflow s’ouvre dans un nouvel onglet.

1. Cliquez sur **Modifier** \(en haut à droite\).

1. Ouvrez le navigateur **Étapes** à l’aide de **Activer/désactiver le panneau latéral** à l’extrême gauche de la barre d’outils supérieure.

1. Faites glisser la ou les étapes appropriées vers l’emplacement requis dans le modèle.

1. Cliquez sur la nouvelle étape que vous avez ajoutée dans le modèle de workflow et sélectionnez **Configurer** dans la barre d’outils du composant

1. Ouvrez l’onglet **Processus**.

1. Dans la liste déroulante **Processus**, sélectionnez **Définir l’état du document pour n’importe quelle ressource de gestion des ressources numériques**.

1. Sélectionnez l’option **Avance du gestionnaire**.

   ![](assets/update-workflow-doc-state_cs.png)

1. Dans la zone de texte **Arguments**, saisissez l’état du document auquel vous souhaitez effectuer la transition à partir du workflow sélectionné.

   >[!NOTE]
   >
   > Veillez à saisir l’état correct du document dans la zone de texte Arguments . Si vous saisissez une valeur incorrecte, le document est défini sur un état incorrect.

1. Confirmez la modification avec **Enregistrer et fermer**.

>[!TAB  On-Premise ]

1. Ouvrez la page du workflow depuis l’URL du serveur AEM.

   `<AEM_Server_URL>:<port>/workflow`

1. Ouvrez un workflow à partir de la page de workflow. Par exemple, Rubrique de révision.
1. Sélectionnez **Étape du processus** dans la section **Workflow** de la boîte de dialogue AEM et effectuez un glisser-déposer sur le workflow.

   ![](assets/process-step-workflow.png)

1. Double-cliquez sur le processus et ouvrez la boîte de dialogue **Propriétés de l’étape**.
1. Saisissez les informations suivantes dans l’onglet **Processus** de la boîte de dialogue, puis cliquez sur OK :
   - Sélectionnez **Définir l’état du document pour toute ressource de gestion des ressources numériques** dans le menu déroulant Processus .
   - Cochez la case Avance du gestionnaire .
   - Saisissez le nom de l’état du document dans la zone de texte **Arguments**.

     >[!NOTE]
     >
     > Veillez à saisir l’état correct du document dans la zone de texte Argument . Si vous saisissez un nom incorrect, le document est défini sur un état de document incorrect.

1. Cliquez sur **Enregistrer** pour enregistrer le workflow.

>[!ENDTABS]


## Activer le workflow de validation

AEM Guides fournit un processus d’approbation des documents, qui vous aide à contrôler le cycle de vie de votre processus de développement de documents.

Les onglets suivants fournissent des instructions pour activer le workflow d’approbation en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB Tab]

1. Pour télécharger le fichier de configuration de l’interface utilisateur, connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils, puis cliquez sur le **Profils de dossier**.
1. Cliquez sur la mosaïque **Profil global**.
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et cliquez sur l’icône **Modifier** en haut
1. Cliquez sur l’icône **Télécharger** pour télécharger le fichier ui\_config.json sur votre système local. Vous pouvez ensuite apporter des modifications au fichier , puis le charger.
1. Dans le fichier `ui_config.json`, activez la fonction de workflow de validation en modifiant la section *fonctionnalités* comme illustré ci-dessous :

   ```
   "features":  
   { 
      "approvalWorkflow":  true 
   }
   ```

1. Enregistrez le fichier et chargez-le.

>[!TAB  On-Premise ]

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite .

1. Accédez au fichier de configuration par défaut disponible à l’emplacement suivant :

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Créez une copie du fichier de configuration par défaut à l’emplacement suivant :

   `/apps/fmdita/xmleditor/ui_config.json`

1. Accédez au fichier `ui_config.json` et ouvrez-le dans le nœud `apps` pour le modifier.

1. Dans le fichier `ui_config.json`, activez la fonction de workflow de validation en modifiant la section *fonctionnalités* comme illustré ci-dessous :

   ```json
   "features":  
   { 
      "approvalWorkflow":  true 
   }
   ```

>[!ENDTABS]
