---
title: Ouvrir la rubrique DITA ou mapper des fichiers dans le même onglet
description: Découvrez comment ouvrir une rubrique DITA ou mapper des fichiers dans le même onglet
exl-id: 466cbea4-c75a-488e-bde2-465cf2c184d5
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 0%

---

# Ouvrir la rubrique DITA ou mapper des fichiers dans le même onglet {#id223HH0301J3}

Dans certains workflows, lorsque vous cliquez sur un lien d’une rubrique ou d’un fichier de mappage, il s’ouvre dans un nouvel onglet. Cela peut entraîner l’ouverture de nombreux onglets dans votre navigateur, ce qui peut avoir un impact sur votre productivité. Vous pouvez modifier ce comportement d&#39;ouverture d&#39;une rubrique ou d&#39;un fichier de mappage dans un nouvel onglet, et forcer son ouverture dans l&#39;onglet actuel.

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour ouvrir une rubrique ou mapper un fichier dans un nouvel onglet :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinsametab` | Booléen \(true/false\). <br> **Valeur par défaut** : `false` |

Ce paramètre affecte les emplacements suivants à partir desquels vous pouvez accéder aux fichiers de rubrique ou de mappage :

- Créer une rubrique DITA \(à la fin du workflow, lorsque vous cliquez sur le bouton **Ouvrir la rubrique**\)

- Créer un plan DITA \(à la fin du workflow, lorsque vous cliquez sur le bouton **Ouvrir le plan**\)

- Onglet Rubriques dans la console de plan DITA

- Onglet Lignes de base dans la console de plan DITA

- Onglet Rapports dans la console de mappage DITA


**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
