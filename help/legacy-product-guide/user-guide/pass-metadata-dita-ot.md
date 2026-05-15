---
title: Transmettre les métadonnées à la sortie à l’aide de DITA-OT
description: Découvrez comment transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT dans AEM Guides.
feature: Publishing, Metadata Management
role: User
hide: true
exl-id: 55d70c6d-feb0-43f7-9f18-6d1ccdd1e728
TQID: https://experienceleague.adobe.com/I-DddG1Wq9cXsF1IZt6B0XFzbR1gbtvtKPoO-g2nLM0
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 330
ht-degree: 0%

---

# Transmettre les métadonnées à la sortie à l’aide de DITA-OT {#id21BJ00QD0XA}

Les métadonnées sont des informations supplémentaires sur la sortie. Dans AEM Guides, vous pouvez transmettre les métadonnées existantes ou créer des balises de métadonnées personnalisées. Vous pouvez transmettre des métadonnées à des sorties AEM, PDF, HTML5, EPUB et au format personnalisé à l’aide de la publication DITA-OT.

Effectuez les étapes suivantes pour transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT :

1. Dans l’interface utilisateur ****, accédez au fichier de mappage DITA pour lequel vous souhaitez transmettre les métadonnées au DITA-OT, puis cliquez dessus.
1. Sélectionnez et modifiez un paramètre prédéfini de sortie auquel vous souhaitez transmettre les champs de métadonnées. Par exemple, sélectionnez le paramètre prédéfini de sortie PDF.
1. Sélectionnez **DITA-OT** sous l’option Générer &lt;sortie\> à l’aide du paramètre prédéfini de sortie sélectionné.

   ![](images/custom-meta-data-output-preset.png){width="800"}

1. Dans la liste déroulante Propriétés , sélectionnez les métadonnées que vous souhaitez transmettre à la publication DITA-OT.

   La liste déroulante Propriétés répertorie les propriétés personnalisées et par défaut. Par exemple, dans la capture d’écran ci-dessus, l’auteur est la propriété personnalisée tandis que `dc:description`, `dc:language`, `dc:title` et `docstate` sont les propriétés par défaut.

   >[!NOTE]
   >
   > Ces propriétés sont sélectionnées à partir du fichier metadataList disponible à l’emplacement suivant :`/libs/fmdita/config/metadataList`. Par défaut, ce fichier répertorie quatre propriétés : `dc:description`, `dc:language`, `dc:title` et `docstate`.

   Ce fichier peut être recouvert à l’adresse : `/apps/fmdita/config/metadataList`.

   Pour transmettre une propriété personnalisée pour laquelle vous avez déjà défini les valeurs, reportez-vous à la section [Utilisation des métadonnées AEM dans la sortie PDF DITA-OT](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880).

1. Dans la liste déroulante **Propriétés**, sélectionnez les propriétés personnalisées et par défaut requises. Par exemple, sélectionnez `author`, `dc:title` et `dc:description`. Il s’agit des `metadata/properties` standard qui sont créées une fois que nous créons un fichier. Les propriétés sélectionnées sont répertoriées sous la liste déroulante.

   ![](images/selected-metadata-properties.png){width="300"}

1. Cliquez sur **Terminé** en haut à gauche pour enregistrer les modifications.
1. Générez la sortie.

Les propriétés de métadonnées sélectionnées seront transmises à la sortie générée à l&#39;aide de DITA-OT.

**Rubrique parente :**[ Génération de sortie](generate-output.md)
