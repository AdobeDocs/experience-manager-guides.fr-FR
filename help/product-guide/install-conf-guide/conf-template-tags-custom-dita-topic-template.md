---
title: Configurer un modèle de rubrique DITA personnalisé
description: Découvrez comment configurer un modèle de rubrique DITA personnalisé
feature: Template Configuration
role: Admin
level: Experienced
exl-id: aaf24a83-3a94-4f77-aa37-7b0398f6ae71
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: df6fa66f-4542-4a6d-90ca-9f146eb5d494
    internal-label: Template configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 2%
---
# Configurer un modèle de rubrique DITA personnalisé {#id16A7G0O02TD}

AEM Guides est fourni avec les modèles de rubrique DITA suivants :

- Thème

- Tâche

- Concept

- Référence

- Glossaire

- Résolution des problèmes

- Vide


Vous pouvez utiliser l’un de ces modèles pour créer des modèles de rubriques en fonction de vos besoins de création. Le modèle DITA vierge ne contient aucune structure ni aucun élément comme les autres modèles. Vous pouvez utiliser le modèle vierge comme base si votre modèle est hautement personnalisé et s&#39;il n&#39;est pas basé sur des modèles de rubrique DITA standard.

Pour personnaliser un modèle de rubrique DITA et l&#39;utiliser pour la création, vous devez effectuer les trois tâches principales suivantes :

1. *\(Facultatif\)* [Configurer le chemin d&#39;accès au dossier du modèle DITA personnalisé](#id191LCF0095Z)

1. [Créer un modèle de création personnalisé](conf-profiles.md#id1917D0EG0HJ)

1. Ajoutez un modèle personnalisé dans le profil global ou au niveau du dossier, comme expliqué dans la section [&#x200B; Configurer les modèles de création &#x200B;](conf-profiles.md#id1889D0IL0Y4)


## Configurer le chemin d&#39;accès au dossier du modèle DITA personnalisé {#id191LCF0095Z}

AEM Guides vous permet de configurer un dossier pour stocker votre plan et vos modèles DITA personnalisés. Par défaut, les fichiers de modèle sont stockés dans le dossier suivant de la gestion des ressources numériques :

`/content/dam/dita-templates/`

Pour gérer les fichiers de modèle de rubrique et de mappage, il existe des dossiers dédiés pour stocker les modèles de rubrique et de mappage. Par défaut, tous les modèles de rubrique sont stockés sous le `/content/dam/dita-templates/topics` .

dossier. Tous les modèles de mappage sont stockés dans le dossier `/content/dam/dita-templates/maps` .

En tant qu’administrateur, vous pouvez choisir de créer des modèles de carte ou de rubrique personnalisés dans le dossier par défaut ou de créer votre propre dossier pour stocker les modèles personnalisés. Si vous prévoyez d’utiliser le dossier par défaut, vous pouvez ignorer ce processus.

Les onglets suivants fournissent des instructions pour configurer le chemin d&#39;accès au dossier du modèle DITA personnalisé en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.


>[!BEGINTABS]

>[!TAB Tab]

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour configurer un dossier pour vos modèles de rubrique DITA personnalisés :

>[!IMPORTANT]
>
> Vous pouvez ignorer ce processus si vous souhaitez utiliser le dossier par défaut pour stocker les modèles personnalisés.

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `topic.templates` | Spécifiez un emplacement pour stocker les modèles personnalisés.<br> Si l’emplacement spécifié existe dans la gestion des ressources numériques, tous les modèles de carte et de rubrique par défaut sont copiés dans ce dossier. Si l’emplacement n’existe pas, le dossier est créé avec tous les modèles de mappage et de rubrique par défaut. |

>[!TAB  On-Premise ]

Pour configurer un dossier pour vos modèles de rubrique DITA personnalisés, procédez comme suit :

>[!IMPORTANT]
>
> Vous pouvez ignorer ce processus si vous souhaitez utiliser le dossier par défaut pour stocker les modèles personnalisés.

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot *com.adobe.fmdita.config.ConfigManager* et cliquez dessus.

1. Dans la propriété **Emplacement des modèles**, spécifiez un emplacement pour stocker les modèles personnalisés.

1. Cliquez sur **Enregistrer**.


Si l’emplacement spécifié existe dans la gestion des ressources numériques, tous les modèles de carte et de rubrique par défaut sont copiés dans ce dossier. Si l’emplacement n’existe pas, le dossier est créé avec tous les modèles de mappage et de rubrique par défaut.


>[!ENDTABS]


**Rubrique parente :**&#x200B;[&#x200B; Configurer la rubrique et les modèles de mappage](conf-template-tags.md)
