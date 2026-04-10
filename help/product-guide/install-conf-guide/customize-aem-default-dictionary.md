---
title: Personnaliser le dictionnaire par défaut d’AEM
description: Découvrez comment personnaliser le dictionnaire par défaut d’AEM
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 2%

---

# Personnaliser le dictionnaire par défaut d’AEM {#id209SD8000WU}

L’éditeur web peut être configuré pour utiliser le vérificateur orthographique d’AEM ou le vérificateur orthographique du navigateur. Si vous choisissez de travailler avec le vérificateur orthographique d’AEM, vous avez la possibilité de définir votre liste de mots personnalisés. Ces mots personnalisés sont ensuite ajoutés au dictionnaire AEM et ne sont pas marqués \(comme incorrect\) dans l’éditeur web.

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


Les auteurs doivent redémarrer leur session de l’éditeur web pour que la liste de mots personnalisés soit mise à jour dans le dictionnaire AEM.

>[!TAB  On-Premise ]

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite .

1. Accédez au nœud suivant :

   /apps/fmdita/config

1. Créez un fichier nommé user\_dictionary.txt.

1. Ouvrez le fichier et ajoutez une liste de mots que vous souhaitez définir dans votre dictionnaire personnalisé.

   La capture d’écran suivante montre la liste des mots personnalisés ajoutée au fichier user\_dictionary.txt :

   ![](assets/custom-words-list-dictionary.png){width="650" align="left"}

1. Enregistrez et fermez le fichier.


Les auteurs doivent redémarrer leur session de l’éditeur web pour que la liste de mots personnalisés soit mise à jour dans le dictionnaire AEM.

>[!ENDTABS]

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](customize-overview.md)
