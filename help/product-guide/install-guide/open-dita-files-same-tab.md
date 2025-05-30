---
title: Ouvrir les fichiers de rubrique ou de mappage DITA dans le même onglet
description: Découvrez comment ouvrir une rubrique DITA ou mapper des fichiers dans le même onglet
exl-id: 81ad2e18-3ea7-4cc1-8387-d703d1038a18
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# Ouvrir les fichiers de rubrique ou de mappage DITA dans le même onglet {#id223HI0P202H}

Dans certains workflows, lorsque vous cliquez sur un lien d’une rubrique ou d’un fichier de mappage, il s’ouvre dans un nouvel onglet. Cela peut entraîner l’ouverture de nombreux onglets dans votre navigateur, ce qui peut avoir un impact sur votre productivité. Vous pouvez modifier ce comportement en ouvrant un fichier de rubrique ou de mappage dans un nouvel onglet et le forcer à s’ouvrir dans l’onglet actif. Pour ce faire, effectuez les modifications de configuration suivantes :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Sélectionnez l’option **Ouvrir la rubrique/carte DITA dans le même onglet** .

1. Cliquez sur **Enregistrer**.


Ce paramètre a un impact sur les emplacements suivants d’où vous pouvez accéder aux fichiers de rubrique ou de mappage :

- Créez une rubrique DITA \(à la fin du processus, lorsque vous cliquez sur le bouton **Ouvrir la rubrique**\)

- Créez la carte DITA \(à la fin du processus, lorsque vous cliquez sur le bouton **Ouvrir la carte**\)

- Onglet Sujets dans la console de mappage DITA

- Onglet Lignes de base dans la console de mappage DITA

- Onglet Rapports dans la console de mappage DITA


**Rubrique parente :**&#x200B;[ Personnaliser l’éditeur web](conf-web-editor.md)
