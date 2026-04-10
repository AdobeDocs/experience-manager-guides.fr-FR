---
title: Personnaliser le dictionnaire par défaut d’AEM
description: Découvrez comment personnaliser le dictionnaire par défaut d’AEM
exl-id: 8bfd3ea7-0be8-4e7a-b389-5face043200b
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 2%

---

# Personnaliser le dictionnaire par défaut d’AEM {#id209SD8000WU}

L’éditeur web peut être configuré pour utiliser le vérificateur orthographique d’AEM ou le vérificateur orthographique du navigateur. Si vous choisissez de travailler avec le vérificateur orthographique d’AEM, vous avez la possibilité de définir votre liste de mots personnalisés. Ces mots personnalisés sont ensuite ajoutés au dictionnaire AEM et ne sont pas marqués \(comme incorrect\) dans l’éditeur web.

Pour créer votre liste de mots personnalisée, procédez comme suit, lesquels sont ajoutés dans le dictionnaire AEM :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite .

1. Accédez au nœud suivant :

   /apps/fmdita/config

1. Créez un fichier nommé user\_dictionary.txt.

1. Ouvrez le fichier et ajoutez une liste de mots que vous souhaitez définir dans votre dictionnaire personnalisé.

   La capture d’écran suivante montre la liste des mots personnalisés ajoutée au fichier user\_dictionary.txt :

   ![](assets/custom-words-list-dictionary.png){width="650" align="left"}

1. Enregistrez et fermez le fichier.


Les auteurs doivent redémarrer leur session de l’éditeur web pour que la liste de mots personnalisés soit mise à jour dans le dictionnaire AEM.

**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
