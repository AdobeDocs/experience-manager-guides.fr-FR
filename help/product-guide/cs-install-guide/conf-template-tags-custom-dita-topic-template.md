---
title: Configuration du modèle de rubrique DITA personnalisé
description: Découvrez comment configurer le modèle de rubrique DITA personnalisé
exl-id: 5a2f4897-9697-4c5c-b5be-8fdb3a211948
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 2%

---

# Configuration du modèle de rubrique DITA personnalisé {#id16A7G0O02TD}

AEM Guides est fourni avec les modèles de rubrique DITA suivants :

- Thème

- Tâche

- Concept

- Référence

- Glossaire

- Résolution des problèmes

- Vide


Vous pouvez utiliser l’un de ces modèles pour créer des modèles de rubriques en fonction de vos besoins en matière de création. Le modèle DITA vierge ne contient aucune structure ni aucun élément comme les autres modèles. Vous pouvez utiliser le modèle vierge comme base si votre modèle est hautement personnalisé et n’est basé sur aucun modèle de rubrique DITA classique.

Pour personnaliser le modèle de rubrique DITA et l’utiliser pour la création, vous devez effectuer les trois tâches principales suivantes :

1. *\(Facultatif\)* [&#128279;](#id191LCF0095Z) Configuration du chemin d’accès au dossier de modèle DITA personnalisé

1. [Créer un modèle de création personnalisé](conf-folder-level.md#id1917D0EG0HJ)

1. Ajoutez un modèle personnalisé dans le profil global ou au niveau du dossier, comme expliqué dans la section [Configurer les modèles de création](conf-folder-level.md#id1889D0IL0Y4)


## Configuration du chemin d’accès au dossier de modèle DITA personnalisé {#id191LCF0095Z}

AEM Guides vous permet de configurer un dossier pour stocker vos modèles et mappages DITA personnalisés. Par défaut, les fichiers de modèle sont stockés dans le dossier suivant de la gestion des actifs numériques :

`/content/dam/dita-templates/`

Pour gérer les fichiers de modèle de rubrique et de mappage, il existe des dossiers dédiés pour stocker les modèles de rubrique et de mappage. Par défaut, tous les modèles de rubrique sont stockés sous le `/content/dam/dita-templates/topics`.

dossier. Tous les modèles de mappage sont stockés dans le dossier `/content/dam/dita-templates/maps`.

En tant qu’administrateur, vous pouvez choisir de créer une carte personnalisée ou des modèles de rubrique dans le dossier par défaut ou de créer votre propre dossier pour stocker des modèles personnalisés. Si vous prévoyez d’utiliser le dossier par défaut, vous pouvez ignorer ce processus.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer un dossier pour vos modèles de rubrique DITA personnalisés :

>[!IMPORTANT]
>
> Vous pouvez ignorer ce processus si vous souhaitez utiliser le dossier par défaut pour stocker des modèles personnalisés.

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `topic.templates` | Indiquez un emplacement où stocker les modèles personnalisés.<br> Si l’emplacement spécifié existe dans DAM, tous les modèles de mappage et de rubrique par défaut sont copiés dans ce dossier. Si l’emplacement n’existe pas, le dossier est créé avec tous les modèles de mappage et de rubrique par défaut. |

**Rubrique parente :**&#x200B;[ Configuration de modèles de rubrique et de mappage](conf-template-tags.md)
