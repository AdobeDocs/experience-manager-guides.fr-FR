---
title: Configuration de l’enregistrement automatique du fichier dans l’éditeur web
description: Découvrez comment configurer l’enregistrement automatique du fichier dans l’éditeur web
exl-id: 23fe404c-c76d-43ba-9b28-c49ab1e524de
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 1%

---

# Configuration de l’enregistrement automatique du fichier dans l’éditeur web {#id199CC0J0M5Z}

L’une des fonctionnalités les plus courantes de l’éditeur basé sur un navigateur est la possibilité d’enregistrer les données après une période spécifique. L’éditeur web des Guides d’AEM prend également en charge l’enregistrement automatique des fichiers de rubrique et de mappage dans l’intervalle de temps spécifié. Lorsque cette fonction est déclenchée, la copie de travail de la rubrique ou du mappage est enregistrée. Une nouvelle version de la rubrique ou du mappage n’est pas créée. Pour créer une version, vous devez cliquer sur l’icône Enregistrer la révision dans la barre d’outils de l’éditeur web.

La fonction d’enregistrement automatique n’est pas activée par défaut et vous devez l’activer à partir de configMgr. Effectuez les étapes suivantes pour activer la fonction d’enregistrement automatique dans l’éditeur web :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le bouton **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** du lot.

1. Dans le *XmlEditorConfig* , sélectionnez la variable **Enregistrement automatique** .

1. Dans le **Intervalle d’enregistrement automatique** , spécifiez l’intervalle en secondes pour déclencher la fonction d’enregistrement automatique.

1. Cliquez sur **Enregistrer**.


**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)