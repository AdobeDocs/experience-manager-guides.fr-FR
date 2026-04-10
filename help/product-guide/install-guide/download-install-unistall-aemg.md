---
title: Désinstallation d’AEM Guides
description: Découvrez comment désinstaller AEM Guides
exl-id: 6c6b9692-cdec-426f-bc3b-f09d0091da39
feature: Installation
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Désinstallation d’AEM Guides {#id21BHG0C0SXA}

Vous pouvez désinstaller AEM Guides à l’aide du gestionnaire de packages CRX. Lors de la désinstallation, le contenu du référentiel est restauré à l’instantané réalisé immédiatement avant l’installation du package.

Procédez comme suit pour désinstaller AEM Guides :

1. Connectez-vous à votre instance AEM et accédez au gestionnaire de packages CRX. L’URL par défaut pour accéder au gestionnaire de packages est :

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

1. Recherchez le package com.adobe.fmdita.
1. Cliquez sur le package pour le développer.
1. Cliquez sur **Plus** pour ouvrir la liste déroulante.
1. Cliquez sur **Désinstaller** et attendez la fin de la désinstallation.
1. Si vous n’avez plus besoin de ce package, cliquez sur **Supprimer** après l’avoir désinstallé.

## Après la désinstallation

Pour nettoyer les fichiers résiduels après la désinstallation, procédez comme suit :

1. Nettoyez le cache de script à l’aide de :

   ```http
   http://<host>:<port>/system/console/scriptcache
   ```

1. Vous pouvez invalider le cache à l’aide des éléments suivants :

   ```http
   http://<host>:<port>/libs/granite/ui/content/dumplibs.rebuild.html?back=true
   ```

1. Cliquez sur **Invalider le cache**.
1. Nettoyez le cache du navigateur.

**Rubrique parente :**&#x200B;[&#x200B; Télécharger et installer](download-install.md)
