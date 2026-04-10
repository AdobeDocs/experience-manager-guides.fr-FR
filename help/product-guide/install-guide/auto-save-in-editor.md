---
title: Configuration de l’enregistrement automatique des fichiers dans l’éditeur web
description: Découvrez comment configurer l’enregistrement automatique des fichiers dans l’éditeur web
exl-id: 23fe404c-c76d-43ba-9b28-c49ab1e524de
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 34687ac8f8877d05e545b23cf0830aa0345a25f7
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 1%

---

# Configuration de l’enregistrement automatique des fichiers dans l’éditeur web {#id199CC0J0M5Z}

L’une des fonctionnalités les plus courantes de l’éditeur basé sur un navigateur est la possibilité d’enregistrer les données après une période spécifique. L’éditeur web d’AEM Guides prend également en charge l’enregistrement automatique des fichiers de rubrique et de mappage à l’intervalle de temps spécifié. Lorsque cette fonctionnalité est déclenchée, la copie de travail de la rubrique ou du mappage est enregistrée. Aucune nouvelle version de la rubrique ou du mappage n&#39;est créée. Pour créer une nouvelle version, vous devez cliquer sur l’icône Enregistrer la révision dans la barre d’outils de l’éditeur web.

La fonction d’enregistrement automatique n’est pas activée par défaut et vous devez l’activer à partir de configMgr. Pour activer la fonction d’enregistrement automatique dans l’éditeur web, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** et cliquez dessus.

1. Dans les paramètres *XmlEditorConfig*, sélectionnez l’option **Enregistrement automatique**.

1. Dans le champ **Intervalle d’enregistrement automatique**, spécifiez l’intervalle de temps en secondes pour déclencher la fonction d’enregistrement automatique.

1. Cliquez sur **Enregistrer**.


**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
