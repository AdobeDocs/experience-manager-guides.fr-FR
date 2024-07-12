---
title: Configuration des noms de fichier automatique en fonction de l’UUID
description: Découvrez comment configurer des noms de fichier automatique en fonction de l’UUID
exl-id: bdbdf119-b928-4ed2-bab3-d99370da8aa9
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 1%

---

# Configuration des noms de fichier automatique en fonction de l’UUID {#id205QG070D5Z}

Par défaut, lorsqu’un fichier de rubrique ou de mappage est créé, les auteurs disposent d’une option pour spécifier également le nom du fichier. Les auteurs sont libres d’attribuer les noms de fichier en fonction de leurs besoins. Cela peut toutefois entraîner des incohérences et un large éventail de noms de fichiers est visible dans un système de documentation volumineux. En tant qu’administrateur, vous pouvez empêcher vos auteurs d’affecter des noms de fichier aux fichiers qu’ils créent dans votre système. Pour chaque nouveau fichier de rubrique ou de mappage, vous pouvez choisir d’attribuer automatiquement des noms de fichier UID.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer les noms de fichier automatique en fonction de l’UUID :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uniquefilenames` | Booléen \(true/false\).<br> **Valeur par défaut** : false |

>[!NOTE]
>
> Lorsque cette option est activée, les auteurs ne voient pas l’option permettant de spécifier le nom de fichier lors de la création d’un fichier de rubrique ou de mappage. Un nouveau fichier de rubrique ou de mappage peut être créé à partir de l’interface utilisateur d’Assets et de l’éditeur web.

**Rubrique parente :**[ Configurer les noms de fichier](conf-file-names.md)
