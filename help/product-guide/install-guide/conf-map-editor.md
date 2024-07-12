---
title: Définir l’éditeur de mappage avancé comme valeur par défaut
description: Découvrez comment définir l’éditeur de mappage avancé comme valeur par défaut
exl-id: ecc023f6-48eb-4afd-97a2-4b3cdd5a8991
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# Définir l’éditeur de mappage avancé comme valeur par défaut {#id181AI0003PN}

AEM Guides est fourni avec un éditeur de cartes de base et un éditeur de cartes avancé. L’éditeur de carte de base vous offre toutes les fonctionnalités nécessaires pour créer votre fichier de carte. L’éditeur de cartes avancé est bien plus riche en fonctionnalités et intégré à l’éditeur web. L’éditeur de mappage avancé permet aux auteurs de créer et de modifier des fichiers de mappage DITA avec une interface conviviale.

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
