---
title: Mettre à niveau AEM Guides
description: Découvrez comment mettre à niveau AEM Guides
exl-id: 57ae906f-69e3-4319-89f6-0fa9ddb7a3ff
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 0%

---

# Mettre à niveau AEM Guides {#id213BD050YPH}

1. Accédez à votre référentiel Git Cloud Manager.

1. Mettez à jour le fichier dox/dox.installer/pom.xml .

1. Mettez à jour la valeur de la variable dox.version vers les détails de version fournis par Adobe.

1. Validez les modifications et exécutez le pipeline Cloud Manager pour déployer le package mis à niveau.


>[!NOTE]
>
> Pour plus d’informations sur l’utilisation du pipeline CI/CD, voir [Utilisation du pipeline CI/CD dans Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Effacer le cache du navigateur

Une fois la mise à niveau terminée, tous les utilisateurs doivent vider le cache du navigateur avant d’utiliser la version mise à niveau d’AEM Guides.

**Rubrique parente :**[ Télécharger et installer](download-install.md)
