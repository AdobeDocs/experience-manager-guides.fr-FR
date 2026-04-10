---
title: Mise à niveau d’AEM Guides pour Cloud Service
description: Découvrez comment mettre à niveau AEM Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: b416334318a83e882c32318bc4769d24268cdd1c
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 2%

---

# Mise à niveau d’AEM Guides pour Cloud Service {#id213BD050YPH}

Effectuez les étapes suivantes pour mettre à niveau AEM Guides :

1. Accédez à votre référentiel Git Cloud Manager.

1. Mettez à jour le fichier `dox/dox.installer/pom.xml`.

1. Mettez à jour la valeur de `dox.version` variable vers les détails de version fournis par Adobe.

1. Validez les modifications et exécutez le pipeline Cloud Manager pour déployer le package mis à niveau.


>[!NOTE]
>
> Pour plus d’informations sur l’utilisation du pipeline CI/CD, voir [Utiliser le pipeline CI/CD dans Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Videz la mémoire cache du navigateur.

Une fois le processus de mise à niveau terminé, tous les utilisateurs doivent vider la mémoire cache du navigateur avant d’utiliser la version mise à niveau d’AEM Guides.
