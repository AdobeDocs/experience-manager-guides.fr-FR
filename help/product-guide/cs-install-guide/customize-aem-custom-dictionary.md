---
title: Personnalisation AEM dictionnaire par défaut
description: Découvrez comment personnaliser AEM dictionnaire par défaut
exl-id: ecffcd14-6728-4938-a209-5c4b12af6fbb
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 1%

---

# Personnalisation AEM dictionnaire par défaut {#id209SD8000WU}

L’éditeur web peut être configuré pour utiliser AEM vérificateur orthographique ou le vérificateur orthographique du navigateur. Si vous choisissez de travailler avec AEM vérificateur orthographique, vous avez la possibilité de définir votre liste de mots personnalisée. Ces mots personnalisés sont ensuite ajoutés au dictionnaire AEM et ces mots ne sont pas marqués \(comme incorrects\) dans l’éditeur web.

Effectuez les étapes suivantes pour créer votre liste de mots personnalisés, qui sont ajoutés dans AEM dictionnaire :

1. Créez le fichier user\_dictionary.txt avec la liste des mots que vous souhaitez définir dans votre dictionnaire personnalisé.

   >[!NOTE]
   >
   > Chaque mot personnalisé doit être défini sur une nouvelle ligne.

1. Enregistrez le fichier à l’emplacement suivant dans votre référentiel Git Cloud Manager :

   /apps/fmdita/config

1. Enregistrez le fichier.

   Validez les modifications et exécutez le pipeline Cloud Manager \(CI/CD\) pour déployer les modifications de configuration.


Les auteurs doivent redémarrer leur session Web Editor pour que la liste des mots personnalisés soit mise à jour dans AEM dictionnaire.

**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
