---
title: Personnalisation AEM dictionnaire par défaut
description: Découvrez comment personnaliser AEM dictionnaire par défaut
exl-id: 8bfd3ea7-0be8-4e7a-b389-5face043200b
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 2%

---

# Personnalisation AEM dictionnaire par défaut {#id209SD8000WU}

L’éditeur web peut être configuré pour utiliser AEM vérificateur orthographique ou le vérificateur orthographique du navigateur. Si vous choisissez de travailler avec AEM vérificateur orthographique, vous avez la possibilité de définir votre liste de mots personnalisée. Ces mots personnalisés sont ensuite ajoutés au dictionnaire AEM et ces mots ne sont pas marqués \(comme incorrects\) dans l’éditeur web.

Effectuez les étapes suivantes pour créer votre liste de mots personnalisés, qui sont ajoutés dans AEM dictionnaire :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite.

1. Accédez au noeud suivant :

   /apps/fmdita/config

1. Créez un fichier nommé user\_dictionary.txt.

1. Ouvrez le fichier et ajoutez une liste de mots que vous souhaitez définir dans votre dictionnaire personnalisé.

   La capture d’écran suivante montre la liste de mots personnalisés ajoutée au fichier user\_dictionary.txt :

   ![](assets/custom-words-list-dictionary.png){width="650" align="left"}

1. Enregistrez et fermez le fichier.


Les auteurs doivent redémarrer leur session Web Editor pour que la liste des mots personnalisés soit mise à jour dans AEM dictionnaire.

**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
