---
title: Configuration des filtres de prévisualisation SCORM
description: Découvrez comment configurer les filtres d’aperçu SCORM.
feature: Configuration
role: Admin
level: Experienced
source-git-commit: f5b7ae41fe63b31a3b45b38fc73976987a2a5ebe
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 3%

---

# Configuration de l’aperçu SCORM

Cet article explique comment configurer l’aperçu SCORM Experience Manager Guides pour gérer les domaines externes autorisés à diffuser des feuilles de style, des images, des polices, des médias et du contenu incorporé dans la sortie d’aperçu SCORM. Les étapes suivantes expliquent comment configurer différents filtres pour l’aperçu SCORM en fonction de la configuration que vous utilisez :

>[!BEGINTABS]

>[!TAB Tab]

1. Suivez les instructions fournies dans [Remplacements de la configuration](../install-conf-guide/download-install-config-override.md) pour créer le fichier de configuration.

1. Dans le fichier de configuration, fournissez les détails de propriété suivants :

   | PID | Clé de la propriété | Valeur par défaut |
   |---|---|---|
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.style.src` | `https://fonts.googleapis.com` |
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.img.src` | - |
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.font.src` | `https://fonts.gstatic.com` |
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.media.src` | - |
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.frame.src` | `https://www.youtube-nocookie.com`, `https://www.youtube.com` |


1. Enregistrez le fichier de configuration et déployez-le dans votre environnement Cloud Service.

Une fois enregistré, l’aperçu SCORM commence à appliquer la liste autorisée de domaine mise à jour. Les ressources externes provenant de domaines qui n&#39;ont pas été ajoutés à cette configuration ne seront pas disponibles dans l&#39;aperçu.

>[!NOTE]
>
> Cela s’applique uniquement à l’environnement de prévisualisation ; le package SCORM téléchargeable continue de diffuser tout le contenu créé comme prévu.


>[!TAB  On-Premise ]

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot **Guides SCORM Preview Filter (com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter)**.

   ![](assets/scorm-preview-filters.png){width="600"}


1. Dans la configuration du lot, ajoutez les URL de domaine autorisées pour chaque type de ressource selon les besoins :

   | Champ | Description |
   |---|---|
   | **Hôte style-src supplémentaire** | Domaines à partir desquels les feuilles de style CSS externes sont autorisées à charger (par défaut, `https://fonts.googleapis.com`). |
   | **Hôte image-src supplémentaire** | Domaines sur lesquels le chargement des images externes est autorisé. |
   | **Hôte font-src supplémentaire** | Domaines à partir desquels les fichiers de polices externes (OTF, WOFF, etc.) sont autorisés à se charger (par défaut, `https://fonts.gstatic.com`). |
   | **Hôte media-src supplémentaire** | Domaines à partir desquels le chargement des fichiers multimédias externes est autorisé. |
   | **Hôte frame-src supplémentaire** | Domaines à partir desquels l’incorporation de contenu iframe est autorisée (par défaut, `https://www.youtube.com` pour autoriser l’incorporation de vidéos YouTube). |

1. Sélectionnez **Enregistrer**.

Une fois enregistré, l’aperçu SCORM commence à appliquer la liste autorisée de domaine mise à jour. Les ressources externes provenant de domaines qui n&#39;ont pas été ajoutés à cette configuration ne seront pas disponibles dans l&#39;aperçu.

>[!NOTE]
>
> Cela s’applique uniquement à l’environnement de prévisualisation ; le package SCORM téléchargeable continue de diffuser tout le contenu créé comme prévu.

>[!ENDTABS]