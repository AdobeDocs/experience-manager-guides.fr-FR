---
title: Activer le nouveau moteur PDF
description: Découvrez comment activer le nouveau moteur PDF dans Experience Manager Guides
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 40ec0c4ba2bb7fae03dfae32c555f03311f1de64
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 2%

---


# Configuration du moteur PDF natif v2

Le nouveau moteur de publication pour le PDF natif, c’est-à-dire _le moteur PDF natif v2_, fournit des fonctionnalités de rendu PDF mises à jour et des correctifs pour les problèmes _le moteur PDF natif v1_.

Suivez les instructions fournies dans [Remplacements de la configuration](../install-conf-guide/download-install-config-override.md) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails (propriété) suivants :

| PID | Clé de la propriété | Valeur de la propriété |
|-----|--------------|----------------|
| `com.adobe.fmdita.publish.config.GuidesPublishConfiguratorService` | `guides.publish.config` | `{"PDF_ENGINE": "v2"}` <br> Valeur par défaut : `v1` |

