---
title: Remplacements de configuration pour Cloud Service
description: Découvrez comment remplacer des configurations
feature: Installation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 0%

---

# Remplacements de configuration pour Cloud Service {#id216IFC003XA}

Pour effectuer les mises à jour de configuration dans Experience Manager Guides as a Cloud Service, l’approche générique suivante doit être utilisée :

1. Accédez à votre référentiel Git Cloud Manager.

1. Créez un fichier JSON à l’emplacement suivant :

   `src/main/content/jcr\_root/apps/fmditaCustom/config/`

1. Nommez le fichier au format suivant :

   `$\{PID\}.cfg.json`

   Ici, le PID est l’identifiant de processus de la configuration.

1. Ajoutez des propriétés dans le fichier JSON à l’aide du format suivant :

   ```
   {
      "aem.adminuname": "updatedUserjson",
      "valid.characters": "[-a-zA-Z0-9_@$]",
      "dita.serialization": true
   }
   ```

1. Validez les modifications et exécutez le pipeline Cloud Manager pour déployer la configuration mise à jour.

