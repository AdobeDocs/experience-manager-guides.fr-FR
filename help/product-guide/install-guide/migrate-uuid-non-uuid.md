---
title: Migration de contenu non UUID vers UUID
description: Découvrez comment migrer du contenu non-UUID vers UUID
exl-id: f8b723bf-84c0-4fe6-936e-63970fb3e417
feature: Migration
role: Admin
level: Experienced
source-git-commit: e38cd858201ea657ce276eb4b358b0d4eff502b2
workflow-type: tm+mt
source-wordcount: '205'
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
| 4.3.1 non-UUID | 4.3.2 UUID | Après la migration vers la version 4.3.2 UUID, vous pouvez directement installer 4.6.0 (UUID). Une fois que vous êtes dans la version 4.6.0, effectuez la mise à niveau vers la version 5.1.0, puis installez le pack de services 1 d’ 5.1.0. |
| 4.6.0 Service Pack 4 non-UUID | 4.6.1 UUID | Après la migration vers la version 4.6.1 de l’UUID, vous pouvez directement effectuer la mise à niveau vers la version 5.1.0 (UUID). Une fois la mise à niveau terminée, installez la version 5.1.0 du pack de services 1. |

Pour obtenir des instructions détaillées sur la migration de votre contenu, reportez-vous aux articles suivants :

- [**4.3.1 migration de contenu non UUID vers 4.3.2 UUID**](./migrate-non-uuid-4-3.md)
- [**4.6.0 Service Pack 4 - Migration de contenu non UUID vers 4.6.1 UUID**](./migrate-non-uuid-uuid-4-6.md)



