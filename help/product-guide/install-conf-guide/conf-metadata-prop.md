---
title: Configuration de la liste d’exclusion des propriétés de métadonnées
description: Découvrez comment configurer la liste d’exclusion pour les propriétés de métadonnées dans AEM Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: f74c71d6a4a293bfbae55e9e57c62b7478d0a88a
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 1%

---

# Configuration de la liste d’exclusion des propriétés de métadonnées

Lorsqu’un fichier est modifié, toutes les modifications apportées aux champs de métadonnées disponibles sous **Propriétés du fichier** ou appliquées sur le serveur principal déclenchent l’astérisque (*) sur la version du document. Pour éviter que les mises à jour de métadonnées générées par le système n’affectent cet indicateur, l’administration peut configurer une liste d’exclusion pour les propriétés de métadonnées.

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer l’option **Ignorer la propriété des métadonnées pour les versions incorrectes** :


| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.dirtychecker.ignoremetadata` | `<comma-separated list / array of metadata properties>` |

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

**Rubrique parente :**[ Personnaliser l’éditeur web](customize-overview.md)
