---
title: Configuration de l’enregistrement automatique des fichiers dans l’éditeur web
description: Découvrez comment configurer l’enregistrement automatique des fichiers dans l’éditeur web
exl-id: 23fe404c-c76d-43ba-9b28-c49ab1e524de
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/-VGsv3zHE6oACLVpnYm24-rX9-H6uUGyz3SEsP2ILBE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 0%

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


**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](conf-web-editor.md)
