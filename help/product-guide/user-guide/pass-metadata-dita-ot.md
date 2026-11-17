---
title: Transmettre les métadonnées à la sortie à l’aide de DITA-OT
description: Découvrez comment transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT dans AEM Guides.
exl-id: 70ca32dc-56c3-45ee-b6b9-0efb8cc79ea1
feature: Publishing, Metadata Management
role: User
TQID: 'https://experienceleague.adobe.com/X840xTCOxbuqBpg8-YYbmFKOuF-KDHX-tGyj8rEG0hE'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
    internal-label: Map console
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
  - id: da9cce28-0561-45e7-851e-4500741b9744
    internal-label: Metadata management
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: bfc6cec48b5e3a50b472e97f456a06d2a32bb8d2
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 0%
---
# Transmettre les métadonnées à la sortie à l’aide de DITA-OT {#id21BJ00QD0XA}

Les métadonnées sont des informations supplémentaires sur la sortie. Dans Adobe Experience Manager Guides, vous pouvez transmettre les métadonnées existantes ou créer des balises de métadonnées personnalisées. Vous pouvez transmettre des métadonnées à des sorties AEM, PDF, HTML5, EPUB et au format personnalisé à l’aide de la publication DITA-OT.

Il existe deux manières de transmettre les métadonnées à Output à l’aide de DITA-OT :

- [Utilisation de la console Carte](#using-map-console)
- [Utilisation du tableau de bord des cartes](#using-map-dashboard)

## Utilisation de la console Carte

Effectuez les étapes suivantes pour transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT :

1. [Ouvrez le fichier de mappage DITA dans la console de mappage](./open-files-map-console.md) pour lequel vous souhaitez transmettre les métadonnées au DITA-OT.
1. Sélectionnez et ouvrez un paramètre prédéfini de sortie auquel vous souhaitez transmettre les champs de métadonnées. Par exemple, sélectionnez le paramètre prédéfini de sortie PDF. Assurez-vous qu&#39;il est créé à l&#39;aide de l&#39;option **DITA-OT**.
1. Dans la liste déroulante **Propriétés du fichier**, sélectionnez les métadonnées que vous souhaitez transmettre à la publication DITA-OT.

   ![](images/custom-metadata-output-preset-new.png)

   La liste déroulante Propriétés répertorie les propriétés personnalisées et par défaut. Par exemple, dans la capture d’écran ci-dessus, `dc:description`, `dc:language`, `dc:title` et `docstate` sont les propriétés par défaut.

   >[!NOTE]
   >
   > Ces propriétés sont sélectionnées à partir du fichier metadataList disponible à l&#39;emplacement suivant : `/libs/fmdita/config/metadataList`. Par défaut, ce fichier contient quatre propriétés : `dc:description`, `dc:language`, `dc:title` et `docstate`.

   Ce fichier peut être recouvert à l’emplacement suivant : `/apps/fmdita/config/metadataList`.

   Pour transmettre une propriété personnalisée pour laquelle vous avez déjà défini les valeurs, affichez [Utiliser les métadonnées AEM dans la sortie PDF DITA-OT](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880).

1. Les propriétés sélectionnées sont répertoriées sous la liste déroulante.

   ![](images/metadata-added-dropdown.png){width="300"}

1. Sélectionnez **Enregistrer** en haut à droite pour enregistrer les modifications.
1. Sélectionnez **Générer la sortie**.

Les propriétés de métadonnées sélectionnées seront transmises à la sortie générée à l&#39;aide de DITA-OT.

>[!NOTE]
>
> Depuis la version 2502 de Experience Manager Guides, la fonctionnalité permettant de transmettre des arguments de métadonnées de carte racine via la ligne de commande DITA-OT est obsolète. Toutefois, afin d’éviter toute perturbation, une nouvelle propriété a été ajoutée dans le `Config.Manager` pour activer ou désactiver la fonctionnalité.  Pour plus de détails, consultez [Configurer les paramètres de génération de sortie](../cs-install-guide/conf-output-generation.md#configure-the-dita-ot-command-line-arguement-field-on-the-dita-map-dashboard).

## Utilisation du tableau de bord des cartes

>[!NOTE]
>
>À compter de la version 2027.01.0 de Cloud Service et de la version 5.4 d’On-Premise de Experience Manager Guides , la fonctionnalité de tableau de bord des cartes sera abandonnée pour les nouveaux clients. Toutefois, elle restera activée pour les clients qui l’utilisent déjà. Si vous souhaitez désactiver le tableau de bord des cartes, contactez votre équipe du succès client. Il est dorénavant recommandé d’utiliser la console Map pour la gestion et la publication des cartes.

Si vous travaillez sur l’**interface utilisateur d’Assets**, procédez comme suit pour transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT :

1. Dans l’**interface utilisateur d’Assets**, accédez au fichier de mappage DITA pour lequel vous souhaitez transmettre les métadonnées au DITA-OT et sélectionnez-le.
1. Sélectionnez et modifiez un paramètre prédéfini de sortie auquel vous souhaitez transmettre les champs de métadonnées. Par exemple, sélectionnez le paramètre prédéfini de sortie PDF.
1. Sélectionnez l&#39;option **DITA-OT** dans le paramètre prédéfini de sortie sélectionné.

   ![](images/custom-meta-data-output-preset.png)

1. Dans la liste déroulante Propriétés , sélectionnez les métadonnées que vous souhaitez transmettre à la publication DITA-OT.

   La liste déroulante Propriétés répertorie les propriétés personnalisées et par défaut. Par exemple, dans la capture d’écran ci-dessus, l’auteur est la propriété personnalisée tandis que `dc:description`, `dc:language`, `dc:title` et `docstate` sont les propriétés par défaut.

   >[!NOTE]
   >
   > Ces propriétés sont sélectionnées à partir du fichier metadataList disponible à l&#39;emplacement suivant : `/libs/fmdita/config/metadataList`. Par défaut, ce fichier contient quatre propriétés : `dc:description`, `dc:language`, `dc:title` et `docstate`.

   Ce fichier peut être recouvert à l’emplacement suivant : `/apps/fmdita/config/metadataList`.

   Pour transmettre une propriété personnalisée pour laquelle vous avez déjà défini les valeurs, affichez [Utiliser les métadonnées AEM dans la sortie PDF DITA-OT](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880).

1. Dans la liste déroulante **Propriétés**, sélectionnez les propriétés personnalisées et par défaut requises. Par exemple, sélectionnez `author`, `dc:title` et `dc:description`. Il s’agit de la valeur `metadata/properties` standard qui est créée une fois le fichier créé. Les propriétés sélectionnées sont répertoriées sous la liste déroulante.

   ![](images/selected-metadata-properties.png){width="300"}

1. Sélectionnez **Terminé** en haut à gauche pour enregistrer les modifications.
1. Générez la sortie.

Les propriétés de métadonnées sélectionnées seront transmises à la sortie générée à l&#39;aide de DITA-OT.



**Rubrique parente :**&#x200B;[&#x200B; Génération de sortie](generate-output.md)
