---
title: Configurer des noms de fichier automatiques en fonction de l’UUID
description: Découvrez comment configurer des noms de fichier automatiques en fonction de l’UUID
exl-id: 2a599228-6d46-494f-a57a-96c3f30e073a
feature: Filename Configuration
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/2oXpOlXt4gZ3GELX7SmwPJoWJYM71f0cZFy2--M6AYM'
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
source-wordcount: '220'
ht-degree: 0%
---
# Configurer des noms de fichier automatiques en fonction de l’UUID {#id205QG070D5Z}

Par défaut, lorsqu’un fichier de rubrique ou de mappage est créé, les auteurs ont également la possibilité de spécifier le nom du fichier. Les auteurs sont libres d’attribuer les noms de fichier en fonction de leurs besoins. Toutefois, cela peut entraîner des incohérences et un large éventail de noms de fichiers est visible dans un vaste système de documentation. En tant qu’administrateur, vous pouvez empêcher vos auteurs d’attribuer des noms de fichiers aux fichiers qu’ils créent dans votre système. Pour chaque nouvelle rubrique ou fichier de mappage, vous pouvez choisir d&#39;attribuer automatiquement des noms de fichiers basés sur UUID.

Pour attribuer automatiquement le nom de fichier basé sur l’UUID à tous les nouveaux fichiers créés dans le système, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot *com.adobe.fmdita.xmleditor.config.XmlEditorConfig* et cliquez dessus.

1. Sélectionnez l’option **Utiliser des noms de fichier système basés sur UUID**.

1. Cliquez sur **Enregistrer**.


>[!NOTE]
>
> Par défaut, cette option est désactivée. Lorsque cette option est activée, les auteurs ne voient pas l’option permettant de spécifier le nom du fichier lors de la création d’une rubrique ou d’un fichier de mappage. Vous pouvez créer une nouvelle rubrique ou un fichier de mappage à partir de l’interface utilisateur d’Assets et de l’éditeur.

**Rubrique parente :**&#x200B;[&#x200B; Configurer les noms de fichier](conf-file-names.md)
