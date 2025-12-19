---
title: Migration de contenu non UUID vers UUID
description: Découvrez comment migrer du contenu non-UUID vers UUID
exl-id: f8b723bf-84c0-4fe6-936e-63970fb3e417
feature: Migration
role: Admin
level: Experienced
source-git-commit: 56f1bd81e74ad9b479b2dcbcf04e1ee82e9a9041
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---

# Migration de contenu non UUID vers UUID {#id226TI0U20XA}


Vous pouvez migrer votre contenu non UUID vers UUID en fonction de la version actuelle de Experience Manager Guides que vous utilisez.

>[!IMPORTANT]
>
> Avant de migrer le contenu vers le serveur UUID, vérifiez qu’un serveur non UUID disposant d’une version d’AEM Guides compatible est installé.

## Matrice de compatibilité

Utilisez le tableau suivant pour déterminer le chemin de migration correct en fonction de votre version actuelle non-UUID. Cela permet d’assurer une transition en douceur après la migration.

| Version non-UUID requise pour la migration | Version de l’UUID après la migration | Chemin de mise à niveau pris en charge après la migration |
|---|---|---|
| 4.3.1 non-UUID | 4.3.2 UUID | Après la migration vers la version 4.3.2 UUID, vous devez installer directement la version 4.6.0 (UUID). Une fois que vous êtes dans la version 4.6.0, effectuez la mise à niveau vers la version 5.1.0, puis installez le pack de services 3 d’ 5.1.0. |
| 4.6.0 Service Pack 4 non-UUID | 4.6.1 UUID | Après la migration vers la version 4.6.1 de l’UUID, vous devez effectuer directement la mise à niveau vers la version 5.1.0 (UUID). Une fois la mise à niveau terminée, installez la version 5.1.0 du pack de services 3. |

## Estimation du temps de migration

L’utilitaire de migration traite les ressources à un taux moyen d’environ 50 ms par ressource. Le tableau suivant fournit des estimations du temps de migration pour un système configuré avec 64 processeurs virtuels, 128 Go de RAM et un stockage sur SSD. Les besoins en mémoire peuvent augmenter pour les référentiels les plus volumineux ou les ressources comportant de nombreux rendus ou fichiers binaires haute résolution.

>[!NOTE]
>
> Le temps de migration réel peut varier en fonction des performances matérielles, du débit de stockage, des activités AEM simultanées et de la charge globale du système.


| **Nombre de ressources** | **Environ. Heure** |
|-----------------|-------------------------|
| 10K | ~8-9 minutes |
| 50K | ~42 minutes |
| 100K | ~1,4 heure |
| 250K | ~3,5 heures |
| 500K | ~7 heures |
| 750 000 | ~10,5 heures |
| 1M | ~14 heures |
| 2 M | ~28 heures (~1,2 jour) |
| 3 MOIS | ~42 heures (~1,75 jour) |
| 5M | ~69 heures (~2,9 jours) |
| 10M | ~139 heures (~5,8 jours) |


Pour obtenir des instructions détaillées sur la migration de votre contenu, reportez-vous aux articles suivants :

- [**4.3.1 migration de contenu non UUID vers 4.3.2 UUID**](./migrate-non-uuid-4-3.md)
- [**4.6.0 Service Pack 4 - Migration de contenu non UUID vers 4.6.1 UUID**](./migrate-non-uuid-uuid-4-6.md)



