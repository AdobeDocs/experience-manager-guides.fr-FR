---
title: Importez du contenu à partir de référentiels Git avec le connecteur Git (Beta) dans Experience Manager Guides
description: Découvrez comment le connecteur Git (Beta) de Experience Manager Guides vous permet d’importer du contenu des référentiels Git, de récupérer à nouveau les mises à jour, de conserver les GUID et de gérer les conflits.
feature: Authoring, Features of Web Editor
role: User
TQID: https://experienceleague.adobe.com/DDAXW8cUFjvHUeJIbtL6FaHYSU7NW5fkzTai-7n90ms
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 5f626c210e74c6d11e2441f719cfbfeb33bf55c5
workflow-type: tm+mt
source-wordcount: 941
ht-degree: 0%

---

# Importer du contenu à l’aide du connecteur Git (Beta)

>[!IMPORTANT]
>
> Le connecteur Git est actuellement disponible en tant que fonctionnalité Beta et est désactivé par défaut. Pour activer cette fonctionnalité, contactez l’équipe du succès client.

Le connecteur Git vous permet d’importer du contenu des référentiels Git connectés dans Experience Manager Guides. Une fois le contenu importé, vous pouvez utiliser les fonctions de création, de révision, de traduction et de publication de Experience Manager Guides pour développer et diffuser de la documentation.

Lorsque le contenu change dans le référentiel source, vous pouvez récupérer les mises à jour, examiner les conflits et synchroniser les dernières modifications avec Experience Manager Guides.

## Conditions préalables

Avant de commencer à utiliser cette fonctionnalité, assurez-vous des points suivants :

- La fonctionnalité Connecteur Git doit être activée pour votre environnement.
- (*Si activé*) Votre administrateur a configuré le connecteur Git dans votre environnement. Pour plus d’informations, consultez la section [Créer et configurer un connecteur Git à partir de l’interface utilisateur](../install-conf-guide/conf-git-connector.md).
- Vous disposez d’un accès *lecture* au référentiel Git qui contient le contenu que vous souhaitez importer.
- Vous savez quelle branche de référentiel et quel dossier source vous souhaitez importer.
- Vous connaissez le dossier cible dans Experience Manager Guides où sera stocké le contenu importé.

## Importer du contenu à partir du référentiel Git connecté

Une fois que votre administrateur a configuré le connecteur Git, vous pouvez l’utiliser à partir de l’éditeur pour commencer à importer du contenu d’un référentiel Git.  Pour importer du contenu à partir d’un référentiel Git, procédez comme suit :

1. Dans l’éditeur, ouvrez le panneau de gauche.
1. Sélectionnez **Sources de données**.

   Les sources de données connectées s’affichent.

1. Sélectionnez la mosaïque **Connecteur Git**.

1. Sélectionnez l’icône + , puis sélectionnez **Importateur en bloc**.

   La boîte de dialogue **Importateur en bloc** s’affiche.

   ![](images/git-bulk-importer-dialog.png)

1. Dans la boîte de dialogue **Importateur en bloc**, attribuez un nom à l’importation, sélectionnez un sous-dossier dans le référentiel Git que vous avez configuré, puis sélectionnez **Enregistrer et récupérer**.  La liste des fichiers disponibles à l’importation s’affiche dans la boîte de dialogue. Passez en revue la liste et validez le contenu avant de continuer.

   ![](images/git-bulk-importer-import-all.png)

1. Après avoir examiné les fichiers, sélectionnez **Importer tout** pour importer le contenu dans Experience Manager Guides.

   >[!NOTE]
   >
   > Vous pouvez activer la **synchronisation automatique** pour synchroniser et importer automatiquement du contenu de votre référentiel Git vers Experience Manager Guides. Si des erreurs sont détectées, la synchronisation automatique n’est pas déclenchée et l’auteur doit importer manuellement le contenu en sélectionnant **Tout importer**. Une fois activée, la synchronisation automatique ne peut pas être désactivée pour l’importateur.

Une fois le contenu importé, il est stocké sous le **chemin d’accès racine Target AEM** configuré lors de la configuration du connecteur Git.

## Gérer le contenu importé par Git

Une fois le contenu importé dans Experience Manager Guides, vous pouvez utiliser les actions disponibles pour gérer le contenu et le maintenir synchronisé avec les modifications du référentiel source.

![](images/git-connector-imported-content-options.png){width="600"}

- **Aperçu** : aperçu du contenu importé. Si le référentiel source contient des mises à jour, passez en revue les différences et utilisez l’option **Récupérer à nouveau** pour importer les dernières modifications.
- **Supprimer** : supprimez le contenu importé qui n’est plus nécessaire.
- **Renommer** : renommez le contenu importé pour une identification plus facile.
- **Afficher le journal** : affichez le journal d’importation pour consulter les détails de l’opération d’importation.
- **Afficher le rapport** : affichez et téléchargez le **rapport d’importation en bloc** qui comprend des détails tels que :

   - nombre total de fichiers importés
   - nombre d’imports réussis
   - nombre d’imports ayant échoué

  ![](images/git-connector-view-report.png){width="600"}

  Vous pouvez également télécharger le rapport détaillé. Si l’importation de certains fichiers échoue, utilisez **Réessayer les importations ayant échoué** pour réessayer de les importer.

## Vérifier et résoudre les conflits de contenu

Lorsque vous récupérez à nouveau du contenu à partir d’un référentiel Git, les différences de contenu entre la version du référentiel et le contenu correspondant disponible dans Experience Manager Guides s’affichent sous la forme de conflits. Vous devez résoudre et fusionner ces conflits avant d’importer les données dans Experience Manager Guides.

Procédez comme suit pour résoudre les conflits de fusion et :

1. Ouvrez la boîte de dialogue d’importation en bloc et sélectionnez **Récupérer à nouveau**.
1. Si des conflits sont détectés, l’onglet **Fusion requise** s’affiche et répertorie les fichiers contenant des conflits. Sélectionnez l’onglet **Fusion requise**, puis sélectionnez un fichier dans la liste pour examiner et résoudre les conflits.
1. Consultez le contenu dans les sections suivantes :

   ![](images/git-connector-resolve-conflicts.png){width="600"}

   - Dans la section **&#x200B;**, la version actuelle du contenu présent dans Experience Manager Guides s’affiche.
   - Dans la section **Git**, la dernière version du contenu du référentiel s’affiche.
   - Dans la section **Fusionner**, le contenu fusionné s’affiche.

1. Examinez les différences mises en surbrillance dans l’éditeur et résolvez les conflits à l’aide des commandes de fusion :

   - Si vous souhaitez utiliser les dernières modifications du référentiel Git, assurez-vous que la case correspondant au conflit dans la section **Git** est cochée, puis sélectionnez le contrôle de `<<<` correspondant. Le contenu Git sélectionné remplace le contenu en conflit dans la section **Fusion**.

     ![](images/git-connector-replace-with-git.png){width="600"}

   - Si vous souhaitez conserver le contenu des deux versions, décochez la case correspondant au conflit, puis utilisez le contrôle `<<<` pour ajouter le contenu requis à la section **Fusionner** sans remplacer le contenu existant.

     ![](images/git-connector-keep-both-versions.png){width="600"}

   - De même, vous pouvez utiliser la commande `>>>` dans la section AEM pour conserver la version actuellement disponible dans Experience Manager Guides.

     ![](images/git-connector-accept-aem-version.png){width="600"}

1. Après avoir examiné le contenu fusionné, effectuez l’une des actions suivantes :

   - Utilisez **Accepter les modifications de Git** lorsque la version du référentiel doit remplacer le contenu en conflit.
   - Utilisez **Marquer comme fusionné** après avoir révisé et mis à jour la version fusionnée pour vous assurer qu’elle contient le contenu que vous souhaitez conserver.
   - Utilisez **Réinitialiser** pour ignorer toutes les mises à jour fusionnées et restaurer le contenu à son état d’origine.

Une fois que tous les fichiers contenant les conflits sont marqués comme fusionnés, le bouton **Tout importer** est activé. Sélectionnez **Importer tout** pour terminer le processus de résolution des conflits.

Si le référentiel contient du contenu entièrement nouveau, tel qu’une nouvelle rubrique, un nouveau paragraphe ou une nouvelle ligne qui n’entre pas en conflit avec le contenu existant, il est affiché sous **Nettoyer les mises à jour**. Ces mises à jour ne nécessitent pas de résolution de conflit et peuvent être importées directement.

![](images/git-connector-clean-updates.png){width="600"}


