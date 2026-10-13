---
title: Personnaliser le dictionnaire par défaut d’AEM
description: Découvrez comment personnaliser le dictionnaire par défaut d’AEM
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 51099b42-706f-42b4-993e-7d9577b5a4f0
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%
---
# Personnaliser le dictionnaire par défaut d’AEM {#id209SD8000WU}

L’éditeur peut être configuré pour utiliser le vérificateur orthographique d’AEM ou le vérificateur orthographique du navigateur. Si vous choisissez de travailler avec le vérificateur orthographique d’AEM, vous avez la possibilité de définir votre liste de mots personnalisés. Ces mots personnalisés sont ensuite ajoutés au dictionnaire AEM et ces mots ne sont pas marqués \(comme incorrect\) dans l’éditeur.

Les onglets ci-dessous fournissent des instructions pour la création de votre liste de mots personnalisée, qui sont ajoutés dans le dictionnaire AEM en fonction de la configuration de Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB Tab]

1. Créez le fichier user\_dictionary.txt avec une liste de mots que vous souhaitez définir dans votre dictionnaire personnalisé.

   >[!NOTE]
   >
   > Chaque mot personnalisé doit être défini sur une nouvelle ligne.

1. Enregistrez le fichier à l’emplacement suivant dans votre référentiel Git Cloud Manager :

   /apps/fmdita/config

1. Enregistrez le fichier.

   Validez les modifications et exécutez le pipeline Cloud Manager \(CI/CD\) pour déployer les modifications de configuration.


Les auteurs doivent redémarrer leur session d’éditeur pour que la liste de mots personnalisés soit mise à jour dans le dictionnaire AEM.

>[!TAB  On-Premise ]

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite .

1. Accédez au nœud suivant :

   /apps/fmdita/config

1. Créez un fichier nommé user\_dictionary.txt.

1. Ouvrez le fichier et ajoutez une liste de mots que vous souhaitez définir dans votre dictionnaire personnalisé.

   La capture d’écran suivante montre la liste des mots personnalisés ajoutée au fichier user\_dictionary.txt :

   ![](assets/custom-words-list-dictionary.png){width="650"}

1. Enregistrez et fermez le fichier.


Les auteurs doivent redémarrer leur session d’éditeur pour que la liste de mots personnalisés soit mise à jour dans le dictionnaire AEM.

>[!ENDTABS]

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur](customize-overview.md)
