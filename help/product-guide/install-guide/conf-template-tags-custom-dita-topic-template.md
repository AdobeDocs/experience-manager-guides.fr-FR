---
title: Configuration du modèle de rubrique DITA personnalisé
description: Découvrez comment configurer le modèle de rubrique DITA personnalisé
exl-id: a9b2c479-7bf6-4c62-addd-fdfe74dc1f69
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '365'
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

Pour configurer un dossier pour vos modèles de rubrique DITA personnalisés, procédez comme suit :

>[!IMPORTANT]
>
> Vous pouvez ignorer ce processus si vous souhaitez utiliser le dossier par défaut pour stocker des modèles personnalisés.

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot *com.adobe.fmdita.config.ConfigManager*.

1. Dans la propriété **Templates Location**, spécifiez un emplacement pour stocker les modèles personnalisés.

1. Cliquez sur **Enregistrer**.


Si l’emplacement spécifié existe dans la gestion des ressources numériques, tous les modèles de mappage et de rubrique par défaut sont copiés dans ce dossier. Si l’emplacement n’existe pas, le dossier est créé avec tous les modèles de mappage et de rubrique par défaut.

**Rubrique parente :**&#x200B;[ Configuration de modèles de rubrique et de mappage](conf-template-tags.md)
