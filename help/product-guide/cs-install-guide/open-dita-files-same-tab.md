---
title: Ouvrir les fichiers de rubrique ou de mappage DITA dans le même onglet
description: Découvrez comment ouvrir une rubrique DITA ou mapper des fichiers dans le même onglet
exl-id: 466cbea4-c75a-488e-bde2-465cf2c184d5
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 0%

---

# Ouvrir les fichiers de rubrique ou de mappage DITA dans le même onglet {#id223HH0301J3}

Dans certains workflows, lorsque vous cliquez sur un lien d’une rubrique ou d’un fichier de mappage, il s’ouvre dans un nouvel onglet. Cela peut entraîner l’ouverture de nombreux onglets dans votre navigateur, ce qui peut avoir un impact sur votre productivité. Vous pouvez modifier ce comportement en ouvrant un fichier de rubrique ou de mappage dans un nouvel onglet et le forcer à s’ouvrir dans l’onglet actif.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour ouvrir un fichier de rubrique ou de mappage dans un nouvel onglet :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinsametab` | Booléen \(true/false\). <br> **Valeur par défaut**: `false` |

Ce paramètre a un impact sur les emplacements suivants d’où vous pouvez accéder aux fichiers de rubrique ou de mappage :

- Créez une rubrique DITA \(à la fin du processus, lorsque vous cliquez sur l’icône **Ouvrir la rubrique** button\)

- Créez une carte DITA \(à la fin du processus, lorsque vous cliquez sur la **Open Map** button\)

- Onglet Sujets dans la console de mappage DITA

- Onglet Lignes de base dans la console de mappage DITA

- Onglet Rapports dans la console de mappage DITA


**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
