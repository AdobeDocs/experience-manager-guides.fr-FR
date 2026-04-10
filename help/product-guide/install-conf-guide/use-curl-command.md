---
title: Utilisation des commandes curl
description: Découvrez comment utiliser les commandes curl sur le contenu chargé dans Experience Manager Guides.
feature: Migration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 1%

---

# Utilisation des commandes curl

Vous pouvez également utiliser des commandes curl pour créer un dossier dans la gestion des ressources numériques, charger des fichiers et ajouter des métadonnées au contenu chargé.

## Créer un dossier

Exécutez la commande suivante pour créer un dossier dans le référentiel AEM :

```curl
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Spécifiez les paramètres suivants pour créer un dossier :

- `<username>:<passowrd>` : indiquez le nom d’utilisateur et le mot de passe pour accéder au référentiel AEM. Cet utilisateur doit disposer des privilèges de création de dossier.

- `jcr:primaryType=sling:Folder` : spécifiez ce paramètre *en l’état* pour créer une ressource de type dossier.

- `<server folder path>` : chemin d’accès complet du dossier, y compris le nom du nouveau dossier que vous souhaitez créer dans le référentiel AEM. Par exemple, si vous définissez le chemin d’accès sur `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, le dossier `AEM-Guides` est créé dans le dossier `projects` dans la gestion des ressources numériques.


## Chargement d’un fichier

Exécutez la commande suivante pour charger un fichier dans le référentiel AEM :

```curl
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Spécifiez les paramètres suivants pour télécharger un fichier :

- `<username>:<passowrd>` : indiquez le nom d’utilisateur et le mot de passe pour accéder au référentiel AEM. Cet utilisateur doit disposer de droits d’écriture sur le `server folder path`.

- ``local file path`` : chemin d’accès complet au fichier sur le système local que vous souhaitez charger.

- `<server folder path>` : chemin complet du dossier sur le serveur AEM sur lequel vous souhaitez télécharger le fichier.


## Ajouter des métadonnées

Exécutez la commande suivante pour ajouter des métadonnées à un fichier :

```curl
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Spécifiez les paramètres suivants pour ajouter des informations de métadonnées :

- `<username>:<passowrd>` : indiquez le nom d’utilisateur et le mot de passe pour accéder au référentiel AEM. Cet utilisateur doit disposer de droits d’écriture sur le ``metadata node path``.

- ``-F<attribute name>=<value>`` : le `<attribute name>` est le nom de l’attribut de métadonnées, tel que `audience`, et le `<value>` peut être `internal`. Vous pouvez spécifier plusieurs paires nom-valeur d’attribut séparées par un espace.

- `<metadata node path>` : chemin complet du dossier, y compris le nom du fichier et son nœud de métadonnées. Par exemple, si vous définissez le chemin d’accès sur `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, les informations de métadonnées spécifiées sont définies sur `intro.xml` fichier .