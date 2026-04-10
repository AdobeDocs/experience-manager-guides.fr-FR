---
title: Configurer des noms de fichier automatiques en fonction de l’UUID
description: Découvrez comment configurer des noms de fichier automatiques en fonction de l’UUID
exl-id: bdbdf119-b928-4ed2-bab3-d99370da8aa9
feature: Filename Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 1%

---

# Configurer des noms de fichier automatiques en fonction de l’UUID {#id205QG070D5Z}

Par défaut, lorsqu’un fichier de rubrique ou de mappage est créé, les auteurs ont également la possibilité de spécifier le nom du fichier. Les auteurs sont libres d’attribuer les noms de fichier en fonction de leurs besoins. Toutefois, cela peut entraîner des incohérences et un large éventail de noms de fichiers est visible dans un vaste système de documentation. En tant qu’administrateur, vous pouvez empêcher vos auteurs d’attribuer des noms de fichiers aux fichiers qu’ils créent dans votre système. Pour chaque nouvelle rubrique ou fichier de mappage, vous pouvez choisir d&#39;attribuer automatiquement des noms de fichiers basés sur UUID.

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour configurer des noms de fichier automatiques en fonction de l’UUID :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uniquefilenames` | Booléen \(true/false\).<br> **Valeur par défaut** : false |

>[!NOTE]
>
> Lorsque cette option est activée, les auteurs ne voient pas l’option permettant de spécifier le nom du fichier lors de la création d’une rubrique ou d’un fichier de mappage. Vous pouvez créer une nouvelle rubrique ou un fichier de mappage à partir de l’interface utilisateur d’Assets et de l’éditeur web.

**Rubrique parente :**&#x200B;[&#x200B; Configurer les noms de fichier](conf-file-names.md)
