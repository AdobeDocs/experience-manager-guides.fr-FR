---
title: Définir l’éditeur de mappage avancé comme valeur par défaut
description: Découvrez comment définir l’éditeur de mappage avancé comme valeur par défaut
exl-id: ecc023f6-48eb-4afd-97a2-4b3cdd5a8991
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 126cecdaa481b9da1add4ba3664c26c2bc5da068
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 0%

---

# Définir l’éditeur de mappage avancé comme valeur par défaut {#id181AI0003PN}

>[!NOTE]
>
> L’éditeur de cartes de base, auparavant disponible dans Experience Manager Guides, a été abandonné à partir des versions 4.3 et 2307. Vous ne pouvez pas accéder à l’éditeur de cartes de base pour créer et gérer des mappages DITA.
>Il est recommandé d’utiliser l’éditeur de mappage avancé. L’éditeur de carte avancé offre des fonctionnalités améliorées et de meilleures options de personnalisation. Découvrez comment travailler avec l’ [éditeur de carte avancé](../user-guide/map-editor-advanced-map-editor.md).

Pour les versions antérieures aux versions 4.3 et 2307, Experience Manager Guides est fourni avec un éditeur de carte de base et un éditeur de carte avancé. L’éditeur de carte de base vous offre toutes les fonctionnalités nécessaires pour créer votre fichier de carte. L’éditeur de cartes avancé est bien plus riche en fonctionnalités et intégré à l’éditeur web. L’éditeur de mappage avancé permet aux auteurs de créer et de modifier des fichiers de mappage DITA avec une interface conviviale.

Par défaut, chaque fois qu’un nouveau fichier de mappage est créé, il est ouvert dans l’éditeur de mappage de base. Vous pouvez modifier ce comportement en activant le paramètre pour ouvrir l’éditeur de mappage avancé par défaut.

Effectuez les étapes suivantes pour faire de l’éditeur de mappage avancé l’éditeur par défaut des fichiers de mappage :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Sélectionnez l’option **Masquer l’éditeur de cartes de base** .

   Lorsque cette option est sélectionnée, le lien Éditeur de carte de base n’apparaît plus dans l’interface utilisateur. Par défaut, les fichiers de mappage s’ouvrent dans l’éditeur de mappage avancé.
