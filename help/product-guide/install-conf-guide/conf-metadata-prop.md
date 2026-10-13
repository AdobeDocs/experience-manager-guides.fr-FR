---
title: Configuration de la liste d’exclusion des propriétés de métadonnées
description: Découvrez comment configurer la liste d’exclusion pour les propriétés de métadonnées dans AEM Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%
---
# Configuration de la liste d’exclusion des propriétés de métadonnées

Lorsqu’un fichier est modifié, toutes les modifications apportées aux champs de métadonnées disponibles sous **Propriétés du fichier** ou appliquées sur le serveur principal déclenchent l’astérisque (*) sur la version du document. Pour éviter que les mises à jour de métadonnées générées par le système n’affectent cet indicateur, l’administration peut configurer une liste d’exclusion pour les propriétés de métadonnées.

>[!BEGINTABS]

>[!TAB Tab]

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer l’option **Ignorer la propriété des métadonnées pour les versions incorrectes**.


| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.dirtychecker.ignoremetadata` | `<comma-separated list / array of metadata properties>` |

>[!TAB  On-Premise ]

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** et cliquez dessus.

1. Dans les paramètres *XmlEditorConfig*, accédez à l’option **Ignorer la propriété de métadonnées pour les versions incorrectes**.

   Consultez la liste des propriétés de métadonnées par défaut actuellement configurées pour être ignorées.

1. Ajoutez ou supprimez des propriétés de métadonnées selon vos besoins.
1. Sélectionnez **Enregistrer** pour enregistrer la configuration mise à jour.


>[!ENDTABS]

## Propriétés de métadonnées par défaut dans la liste d’exclusion

AEM Guides inclut un ensemble par défaut de propriétés de métadonnées dans la liste d’exclusion. Vous pouvez modifier cette liste pour ajouter ou supprimer des propriétés de métadonnées selon vos besoins.

* « jcr :mixinTypes »,
* « jcr :primaryType »,
* « jcr :frozenMixinTypes »,
* « jcr :frozenPrimaryType »,
* « jcr :frozenUuid »,
* « jcr :uuid »,
* « dam:extracted »,
* « jcr :lastModified »,
* « jcr :lastModifiedBy »,
* « dc:modified »,
* « dam:sha1 »,
* « dam:size »,
* « guides:wordCount »,
* « dam:scene7UploadTimeStamp »,
* « dam:scene7LastModified »

Seules les propriétés de métadonnées qui ne sont pas incluses dans la liste d’exclusion sont prises en compte pour marquer la version d’un document comme sale.

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur](customize-overview.md)
