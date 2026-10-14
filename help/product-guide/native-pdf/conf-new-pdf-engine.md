---
title: Activer le nouveau moteur PDF
description: Découvrez comment activer le nouveau moteur PDF dans Experience Manager Guides
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
source-git-commit: f89becea89888f7dec81e18c9220dcabda8f4e7d
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 4%
---

# Configuration du moteur PDF natif v2

Le nouveau moteur de publication pour le PDF natif, c’est-à-dire _le moteur PDF natif v2_, fournit des fonctionnalités de rendu PDF mises à jour et des correctifs pour les problèmes _le moteur PDF natif v1_.

>[!BEGINTABS]
>[!TAB Tab]

Suivez les instructions fournies dans [Remplacements de la configuration](../install-conf-guide/download-install-config-override.md) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails (propriété) suivants :

| PID | Clé de la propriété | Valeur de la propriété |
|-----|--------------|----------------|
| `com.adobe.fmdita.publish.config.GuidesPublishConfiguratorService` | `guides.publish.config` | `{"PDF_ENGINE": "v2"}` <br> Valeur par défaut : `v1` |

>[!TAB  On-Premise ]


Pour les déploiements On-Premise, sa disponibilité dépend des versions AEM et Java.

Le moteur _Native PDF engine v2_ nécessite **Java 17 ou une version ultérieure**.

- **AEM 6.5:** Le moteur de publication natif PDF v2 n’est pas pris en charge, car AEM 6.5 s’exécute sur Java 8.
- **AEM 6.5 LTS:** Le moteur de publication natif PDF v2 est activé par défaut. Aucune configuration supplémentaire n’est nécessaire.

Si vous préférez revenir au moteur _Native PDF engine v2_ avec AEM 6.5 LTS, désinstallez le package de l’éditeur PDF :
`/crx/packmgr/index.jsp#/etc/packages/com.adobe.guides/pdf-publisher-package-3.0.0.zip` à partir du gestionnaire de packages CRX.

>[!ENDTABS]

