---
title: Configurer des noms de fichier automatiques en fonction de l’UUID
description: Découvrez comment configurer des noms de fichier automatiques en fonction de l’UUID
exl-id: bdbdf119-b928-4ed2-bab3-d99370da8aa9
feature: Filename Configuration
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/HxTJaPGbwH31vitQ-Cu6wPyCuzZSWDXtq6xMY4hXEAI'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
    internal-label: Filename configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '197'
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
