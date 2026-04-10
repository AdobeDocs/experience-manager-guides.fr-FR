---
title: Configurer le modèle de nom de fichier UUID
description: Découvrez comment configurer le modèle de nom de fichier UUID
feature: Migration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---

# Configurer le modèle de nom de fichier UUID

Lorsque vous importez du contenu, il n’est pas nécessaire que vos noms de fichier soient basés sur l’UUID. Dans un système qui utilise des noms de fichiers basés sur l’UUID, il est obligatoire que tous les fichiers soient référencés à l’aide de leur UUID plutôt que de leur nom de fichier d’origine. Si un fichier importé ne possède pas de nom de fichier basé sur UUID, vous pouvez configurer le système pour ajouter un UUID à sa propriété de fichier. Cet UUID est ensuite utilisé pour faire référence aux fichiers pour lesquels l’UUID n’est pas utilisé pour nommer les fichiers.

## Étapes de configuration du modèle de nom de fichier UUID

Les onglets suivants fournissent des instructions pour configurer le modèle de nom de fichier UUID en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB ]

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour configurer le modèle de nom de fichier UUID :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `uuid.regex` | Chaîne spécifiant l’expression régulière pour le modèle de nom de fichier UUID. <br> Si un fichier ne suit pas le modèle spécifié, un UUID est ajouté à la propriété du fichier et toutes les références au fichier sont mises à jour avec l’UUID attribué au fichier. <br> **Valeur par défaut** : `"^GUID-(?<id>.*)"` |

>[!TAB  On-Premise ]

Effectuez les étapes suivantes pour vérifier les noms de fichiers par rapport à un modèle UUID et affecter UUID aux fichiers auxquels aucun UUID n’est affecté :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et sélectionnez le lot *com.adobe.fmdita.config.ConfigManager*.

1. Dans la propriété **Modèles de nom de fichier UUID**, spécifiez un modèle pour vérifier les noms des fichiers importés.

   Si un fichier ne suit pas le modèle spécifié, un UUID est ajouté à la propriété du fichier et toutes les références au fichier sont mises à jour avec l’UUID attribué au fichier.

1. Sélectionnez **Enregistrer**.

>[!ENDTABS]





