---
title: Personnaliser le dictionnaire par défaut d’AEM
description: Découvrez comment personnaliser le dictionnaire par défaut d’AEM
exl-id: ecffcd14-6728-4938-a209-5c4b12af6fbb
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 1%

---

# Personnaliser le dictionnaire par défaut d’AEM {#id209SD8000WU}

L’éditeur web peut être configuré pour utiliser le vérificateur orthographique d’AEM ou le vérificateur orthographique du navigateur. Si vous choisissez de travailler avec le vérificateur orthographique d’AEM, vous avez la possibilité de définir votre liste de mots personnalisés. Ces mots personnalisés sont ensuite ajoutés au dictionnaire AEM et ne sont pas marqués \(comme incorrect\) dans l’éditeur web.

Pour créer votre liste de mots personnalisée, procédez comme suit, lesquels sont ajoutés dans le dictionnaire AEM :

1. Créez le fichier user\_dictionary.txt avec une liste de mots que vous souhaitez définir dans votre dictionnaire personnalisé.

   >[!NOTE]
   >
   > Chaque mot personnalisé doit être défini sur une nouvelle ligne.

1. Enregistrez le fichier à l’emplacement suivant dans votre référentiel Git Cloud Manager :

   /apps/fmdita/config

1. Enregistrez le fichier.

   Validez les modifications et exécutez le pipeline Cloud Manager \(CI/CD\) pour déployer les modifications de configuration.


Les auteurs doivent redémarrer leur session de l’éditeur web pour que la liste de mots personnalisés soit mise à jour dans le dictionnaire AEM.

**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
