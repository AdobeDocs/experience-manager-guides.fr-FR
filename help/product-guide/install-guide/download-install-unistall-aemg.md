---
title: Désinstallation d’AEM Guides
description: Découvrez comment désinstaller AEM Guides
exl-id: 6c6b9692-cdec-426f-bc3b-f09d0091da39
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Désinstallation d’AEM Guides {#id21BHG0C0SXA}

Vous pouvez désinstaller AEM Guides à l’aide du gestionnaire de modules CRX. Lors de la désinstallation, le contenu du référentiel est restauré à l’instantané effectué immédiatement avant l’installation du module.

Pour désinstaller AEM Guides, procédez comme suit :

1. Connectez-vous à votre instance AEM et accédez au gestionnaire de modules CRX. L’URL par défaut pour accéder au gestionnaire de packages est la suivante :

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

1. Recherchez le package com.adobe.fmdita .
1. Cliquez sur le module pour le développer.
1. Cliquez sur **Plus** pour ouvrir la liste déroulante.
1. Cliquez sur **Désinstaller** et attendez que la désinstallation soit terminée.
1. Si vous n’avez plus besoin de ce package, cliquez sur **Supprimer** après avoir désinstallé le package.

## Après la désinstallation

Pour nettoyer les fichiers résiduels après la désinstallation, procédez comme suit :

1. Nettoyez le cache du script à l’aide de :

   ```http
   http://<host>:<port>/system/console/scriptcache
   ```

1. Vous pouvez invalider le cache à l’aide de :

   ```http
   http://<host>:<port>/libs/granite/ui/content/dumplibs.rebuild.html?back=true
   ```

1. Cliquez sur **Invalider le cache**.
1. Nettoyez le cache du navigateur.

**Rubrique parente :**&#x200B;[ Télécharger et installer](download-install.md)
