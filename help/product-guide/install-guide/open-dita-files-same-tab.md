---
title: Ouvrir la rubrique DITA ou mapper des fichiers dans le même onglet
description: Découvrez comment ouvrir une rubrique DITA ou mapper des fichiers dans le même onglet
exl-id: 81ad2e18-3ea7-4cc1-8387-d703d1038a18
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/-QYM6xoQCkvRcpxpsWtnJb5le7-4RirhgOZk94UvzIg'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
    internal-label: Reports
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
source-wordcount: '211'
ht-degree: 0%
---
# Ouvrir la rubrique DITA ou mapper des fichiers dans le même onglet {#id223HI0P202H}

Dans certains workflows, lorsque vous cliquez sur un lien d’une rubrique ou d’un fichier de mappage, il s’ouvre dans un nouvel onglet. Cela peut entraîner l’ouverture de nombreux onglets dans votre navigateur, ce qui peut avoir un impact sur votre productivité. Vous pouvez modifier ce comportement d&#39;ouverture d&#39;une rubrique ou d&#39;un fichier de mappage dans un nouvel onglet, et forcer son ouverture dans l&#39;onglet actuel. Pour ce faire, effectuez les modifications de configuration suivantes :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** et cliquez dessus.

1. Sélectionnez l&#39;option **Ouvrir la rubrique/le plan DITA dans le même onglet**.

1. Cliquez sur **Enregistrer**.


Ce paramètre affecte les emplacements suivants à partir desquels vous pouvez accéder aux fichiers de rubrique ou de mappage :

- Créer une rubrique DITA \(à la fin du workflow, lorsque vous cliquez sur le bouton **Ouvrir la rubrique**\)

- Créer un plan DITA \(à la fin du workflow, lorsque vous cliquez sur le bouton **Ouvrir le plan**\)

- Onglet Rubriques dans la console de plan DITA

- Onglet Lignes de base dans la console de plan DITA

- Onglet Rapports dans la console de mappage DITA


**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
