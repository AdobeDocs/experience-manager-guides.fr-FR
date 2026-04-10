---
title: Configurer un modèle de rubrique DITA personnalisé
description: Découvrez comment configurer un modèle de rubrique DITA personnalisé
exl-id: 5a2f4897-9697-4c5c-b5be-8fdb3a211948
feature: Template Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '354'
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

1. [Créer un modèle de création personnalisé](conf-folder-level.md#id1917D0EG0HJ)

1. Ajoutez un modèle personnalisé dans le profil global ou au niveau du dossier, comme expliqué dans la section [&#x200B; Configurer les modèles de création &#x200B;](conf-folder-level.md#id1889D0IL0Y4)


## Configurer le chemin d&#39;accès au dossier du modèle DITA personnalisé {#id191LCF0095Z}

AEM Guides vous permet de configurer un dossier pour stocker votre plan et vos modèles DITA personnalisés. Par défaut, les fichiers de modèle sont stockés dans le dossier suivant de la gestion des ressources numériques :

`/content/dam/dita-templates/`

Pour gérer les fichiers de modèle de rubrique et de mappage, il existe des dossiers dédiés pour stocker les modèles de rubrique et de mappage. Par défaut, tous les modèles de rubrique sont stockés sous le `/content/dam/dita-templates/topics` .

dossier. Tous les modèles de mappage sont stockés dans le dossier `/content/dam/dita-templates/maps` .

En tant qu’administrateur, vous pouvez choisir de créer des modèles de carte ou de rubrique personnalisés dans le dossier par défaut ou de créer votre propre dossier pour stocker les modèles personnalisés. Si vous prévoyez d’utiliser le dossier par défaut, vous pouvez ignorer ce processus.

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour configurer un dossier pour vos modèles de rubrique DITA personnalisés :

>[!IMPORTANT]
>
> Vous pouvez ignorer ce processus si vous souhaitez utiliser le dossier par défaut pour stocker les modèles personnalisés.

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `topic.templates` | Spécifiez un emplacement pour stocker les modèles personnalisés.<br> Si l’emplacement spécifié existe dans la gestion des ressources numériques, tous les modèles de mappage et de rubrique par défaut sont copiés dans ce dossier. Si l’emplacement n’existe pas, le dossier est créé avec tous les modèles de mappage et de rubrique par défaut. |

**Rubrique parente :**&#x200B;[&#x200B; Configurer la rubrique et les modèles de mappage](conf-template-tags.md)
