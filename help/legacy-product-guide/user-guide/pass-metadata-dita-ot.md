---
title: Transmission des métadonnées à la sortie à l’aide de DITA-OT
description: Découvrez comment transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT dans AEM Guides.
feature: Publishing, Metadata Management
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# Transmission des métadonnées à la sortie à l’aide de DITA-OT {#id21BJ00QD0XA}

Les métadonnées sont des informations supplémentaires sur la sortie. Dans AEM Guides, vous pouvez transmettre les métadonnées existantes ou créer des balises de métadonnées personnalisées. Vous pouvez transmettre des métadonnées à des sorties au format AEM, PDF, HTML5, EPUB et personnalisé à l’aide de la publication DITA-OT.

Effectuez les étapes suivantes pour transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT :

1. Dans l’ **interface utilisateur d’Assets**, accédez au fichier de mappage DITA pour lequel vous souhaitez transmettre les métadonnées à DITA-OT et cliquez dessus.
1. Sélectionnez et modifiez un paramètre prédéfini de sortie auquel vous souhaitez transmettre les champs de métadonnées. Par exemple, sélectionnez le paramètre prédéfini de sortie du PDF.
1. Sélectionnez **DITA-OT** sous l’option Générer &lt;output\> à l’aide du paramètre prédéfini de sortie sélectionné.

   ![](images/custom-meta-data-output-preset.png){width="800" align="left"}

1. Dans la liste déroulante Propriétés , sélectionnez les métadonnées à transmettre à la publication DITA-OT.

   La liste déroulante Propriétés répertorie les propriétés personnalisées et par défaut. Par exemple, dans la capture d’écran ci-dessus, l’auteur est la propriété personnalisée tandis que `dc:description`, `dc:language`, `dc:title` et `docstate` sont les propriétés par défaut.

   >[!NOTE]
   >
   > Ces propriétés sont sélectionnées à partir du fichier metadataList disponible à l’emplacement suivant :`/libs/fmdita/config/metadataList`. Par défaut, quatre propriétés sont répertoriées dans ce fichier : `dc:description`, `dc:language`, `dc:title` et `docstate`.

   Ce fichier peut être superposé à l’emplacement suivant : `/apps/fmdita/config/metadataList`.

   Pour transmettre une propriété personnalisée pour laquelle vous avez déjà défini les valeurs, reportez-vous à la section [Utilisation des métadonnées AEM dans la sortie du PDF DITA-OT](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880).

1. Dans la liste déroulante **Propriétés** , sélectionnez les propriétés personnalisées et par défaut requises. Par exemple, sélectionnez `author`, `dc:title` et `dc:description`. Il s’agit de la norme `metadata/properties` qui est créée une fois que nous avons créé un fichier. Les propriétés sélectionnées sont répertoriées sous la liste déroulante.

   ![](images/selected-metadata-properties.png){width="300" align="left"}

1. Cliquez sur **Terminé** en haut à gauche pour enregistrer les modifications.
1. Générez la sortie.

Les propriétés de métadonnées sélectionnées seront transmises à la sortie générée à l’aide de DITA-OT.

**Rubrique parente :**[ Génération de sortie](generate-output.md)
