---
title: Migration de contenu d'On-premise vers les Cloud Service
description: Découvrez comment migrer le contenu du logiciel On-premise vers les Cloud Service
feature: Migration
role: Admin
level: Experienced
source-git-commit: af7b3595c10793a8faf72310083547f90b6568f0
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 5%

---

# Migration de contenu d’On-premise vers Cloud Service

Experience Manager as a Cloud Service constitue une base technologique évolutive, sécurisée et agile pour Experience Manager Assets, Forms et Screens. Cela permet aux spécialistes du marketing et aux professionnels de l’informatique de se concentrer sur la diffusion à grande échelle d’expériences percutantes.
Avec Experience Manager as a Cloud Service, vos équipes peuvent se concentrer sur l’innovation plutôt que sur la planification des mises à niveau de produits. Les nouvelles fonctionnalités du produit sont soigneusement testées et diffusées sans interruption à vos équipes afin qu’elles puissent toujours accéder à la dernière version de Adobe Experience Manager.
Cet article fournit un processus détaillé et détaillé pour la migration de votre contenu On-premise ou Managed Services Experience Manager Guides vers les Cloud Service, assurant une transition fluide vers la plateforme cloud.

## Processus de migration

**Outil de transfert de contenu** est un outil développé par Adobe que vous pouvez utiliser pour lancer la migration de contenu existant d’une instance Adobe Experience Manager On-premise ou Managed Services source vers l’instance d’Experience Manager Cloud Service cible.
Cet outil transfère également automatiquement les entités principales (utilisateurs, utilisatrices ou groupes).

Vous pouvez télécharger l’**outil de transfert de contenu** sous la forme d’un fichier ZIP à partir du portail de **distribution de logiciels** :

1. Sélectionnez l’onglet **AEM as a Cloud Service** sur le portail **Distribution logicielle**.
1. Recherchez **Outil de transfert de contenu**.
1. Sélectionnez **Outil de transfert de contenu** dans la liste et téléchargez-le.

![Télécharger l’outil de transfert de contenu](./assets/content-transfer-tool-software-portal.png)
Installez ensuite le package via **Package Manager** sur votre instance Adobe Experience Manager source. Veillez à télécharger la dernière version.
Pour plus d’informations sur la dernière version, consultez les [notes de mise à jour](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current.html?lang=en).

>[!NOTE]
> 
> Seules les versions 2.0.0 et ultérieures sont prises en charge et il est recommandé d’utiliser la dernière version.

### Conditions préalables

* Adobe Experience Manager 6.4 ou versions ultérieures
* La taille de référentiel de 20 To maximum est prise en charge
* Taille totale de l’index Lucene de 25 Go
* La longueur d’un nom de noeud doit être inférieure à 150 octets


Effectuez les étapes suivantes pour migrer votre contenu Experience Manager Guides vers Experience Manager as a Cloud Service.

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com/) et sélectionnez **Experience Manager**.

   ![experience manager](./assets/migration-experience-manager.png)


1. Cliquez sur **Launch** sur la mosaïque **Cloud Acceleration Manager**.
   ![gestionnaire d’accélération du cloud](./assets/migration-experience-manager-cloud.png)

1. Créez votre premier projet.
   ![créer un projet](./assets/migration-cloud-create-project.png)

1. Ajoutez le nom et la description, puis cliquez sur **Créer**. Votre projet est créé.
1. Sélectionnez le projet créé et ouvrez l’écran du projet.
1. Cliquez sur **Réviser** sur la mosaïque **Transfert de contenu** .

   ![Vérifier le transfert de contenu](./assets/migration-content-transfer-review.png)

1. Cliquez sur **Créer un jeu de migration**.

1. Indiquez le nom et la description du jeu de migration.


   ![create-migration-set](./assets/migration-cloud-create-migration-set.png)


1. Après la création, sélectionnez les trois points et sélectionnez **Copier la clé d’extraction**.


1. Cliquez sur **Copier dans le Presse-papiers**. Créez votre premier projet.
   ![clé d&#39;extraction](./assets/migration-copy-to-clipboard.png)

1. Sélectionnez **Adobe Experience Manager** dans la partie supérieure, puis sélectionnez la mosaïque **Distribution logicielle**.
   ![Portail de distribution de logiciels](./assets/migration-software-portal.png)


1. Sur le portail **Distribution logicielle**, sélectionnez **Adobe Experience Manager comme onglet Cloud Service**, recherchez &quot;outil de transfert de contenu&quot; et téléchargez le package de l’outil de transfert de contenu.

   >[!NOTE]
   >
   >  Veillez à télécharger la dernière version.

1. Téléchargez et installez le package `content-transfer.all-3.0.10.zip` dans le **gestionnaire de modules** de votre instance On-premise.
   ![Télécharger l’outil de transfert de contenu](./assets/content-transfer-tool-software-portal.png)


1. Sur l’instance On-premise, sélectionnez **Outils** > **Opérations** > **Migration de contenu** > **Transfert de contenu**.


1. Sélectionnez **Content Transfer** (Transfert de contenu), créez un jeu de migration, puis collez la clé d’extraction copiée à partir du gestionnaire d’accélération du cloud. Cela établit un lien entre la source et la cible. Ensuite, il vérifie la clé et affiche la validité après avoir saisi la valeur.

1. Activez l’option **Inclure les versions** pour inclure les versions de fichiers.
   ![](./assets/migration-create-migration-set.png)

1. Indiquez le chemin d’accès que vous souhaitez migrer et cliquez sur **Enregistrer**.
Par exemple, `/content/we-retail`
ou
   `/content/dam/wknd-events`
   ![chemins inclus](./assets/migration-included-paths.png)



   >[!NOTE]
   >
   > Vous devez migrer obligatoirement les chemins suivants pour le contenu **Experience Manager Guides**.

   * `/content/dam`
   * `/var/dxml`

   Les chemins suivants sont restreints lors de la création d’un jeu de migration :
   * `/apps`
   * `/libs`
   * `/home`
   * `/etc` Vous pouvez sélectionner certains `/etc` chemins dans CTT.

1. Cliquez sur **Enregistrer**
1. Sélectionnez le **jeu de migration**, puis **Extract** en haut.
   ![extraction de jeu de migration ](./assets/migration-extract.png)

1. Vérifiez les détails dans la fenêtre contextuelle **Migration Set Extraction** pour les chemins et les configurations que vous avez sélectionnés, puis cliquez sur **Extract**. L’extraction prendra des minutes et vous verrez l’état tel que mis à jour.
   ![Extraction du jeu de migration](./assets/migration-set-extraction.png)

1. Une fois l’extraction terminée et indiquée par l’état `finished`, accédez à Cloud Acceleration Manager et sélectionnez le projet que vous avez créé à l’étape 18.
Pour plus d’informations, sélectionnez les trois points, puis **Afficher les détails**.


1. Dans la fenêtre contextuelle Détails du jeu de migration , vérifiez la configuration du jeu de migration et fermez la fenêtre contextuelle. Vous pouvez afficher les chemins et les autres paramètres, comme illustré dans la capture d’écran suivante :
   ![migration-details](./assets/migration-details.png)


1. Cliquez sur **Tâches d’ingestion** > **Nouvelle ingestion**.
1. Acceptez les valeurs de coche requises, puis cliquez sur **Créer**.
   ![accuser les vérifications de migration](./assets/migration-new-ingestion-acknowledge.png)

1. Sélectionnez le jeu de migration, sélectionnez le serveur requis de votre environnement, puis cliquez sur **Ingest**.

   ![nouvelle ingestion](./assets/migration-new-ingestion.png)

## Exécution de l’outil de transfert de contenu sur une instance Publish

Installez l’outil de transfert de contenu sur l’instance Publish source pour déplacer le contenu vers l’instance Publish cible.
L’outil de transfert de contenu ne fait pas la distinction entre le contenu publié et le contenu non publié lors de l’ingestion de contenu dans un environnement Publish. Le contenu spécifié dans le jeu de migration est ingéré dans l’instance cible choisie. L’utilisateur peut ingérer un jeu de migration dans une instance d’auteur, une instance Publish, ou les deux.

### Approche recommandée

Tenez compte des recommandations suivantes :

* Utilisez la même version de l’ **outil de transfert de contenu** utilisé sur l’instance d’auteur.
* Lors de l’ingestion vers Publish, le niveau Publish ne sera pas réduit (contrairement à l’auteur).
* Migrez un seul noeud Publish. Avant de commencer l&#39;extraction, supprimez-la de l&#39;équilibreur de charge.

>[!NOTE]
>
> Par mesure de précaution, assurez-vous qu’aucune opération d’écriture ne se produit sur les instances Publish, y compris les actions initiées par l’utilisateur telles que :
> * La distribution de contenu de la création dans AEM as a Cloud Service à la publication dans cet environnement
> * Synchronisation des utilisateurs entre les instances Publish


## Résolution des problèmes

Si l’extraction échoue en raison de l’erreur suivante, vous pouvez résoudre ce problème en important le certificat d’autorité de certification approprié :

`javax.net.ssl.SSLHandshakeException: sun.security.validator.ValidatorException: PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target`

**Raison** : le serveur Adobe Experience Manager possède des restrictions de pare-feu. Ajoutez donc le point de terminaison suivant à la liste autorisée.

`casstorageprod.blob.core.windows.net`


![journalisation ssl](./assets/migration-ssl-logging.png)


*Activez la journalisation SSL.*




