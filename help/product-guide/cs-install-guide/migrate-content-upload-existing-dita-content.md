---
title: Chargement de contenu DITA existant
description: Découvrez comment télécharger du contenu DITA existant
exl-id: 2b385eef-00a7-4c25-9e78-367a0c9e44ba
feature: Migration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# Chargement de contenu DITA existant {#id176FF000JUI}

Vous disposez probablement d’un référentiel de contenu DITA existant que vous souhaitez utiliser avec AEM Guides. Pour ce contenu existant, vous pouvez utiliser l’une des méthodes prises en charge décrites dans la section [Ajout de ressources numériques à Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html).

## Configuration du modèle de nom de fichier UUID

Lorsque vous importez du contenu, il n’est pas nécessaire que vos noms de fichier soient basés sur l’UUID. Dans un système qui utilise des noms de fichier UUID, il est obligatoire que tous les fichiers soient référencés à l’aide de leur UUID plutôt que de leur nom de fichier d’origine. Si un fichier importé ne comporte pas de nom de fichier basé sur l’UUID, vous pouvez configurer le système pour ajouter un UUID à sa propriété de fichier. Cet UUID est ensuite utilisé pour faire référence aux fichiers pour lesquels l’UUID n’est pas utilisé pour nommer les fichiers.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer le modèle de nom de fichier UUID :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `uuid.regex` | Chaîne spécifiant l’expression régulière du modèle de nom de fichier UUID. <br> Si un fichier ne suit pas le modèle spécifié, un UUID est ajouté à la propriété du fichier et toutes les références au fichier sont mises à jour avec l’UUID affecté au fichier. <br> **Valeur par défaut** : `"^GUID-(?<id>.*)"` |

## Utilisation des commandes curl

Vous pouvez également utiliser des commandes curl pour créer un dossier dans DAM, charger des fichiers et ajouter des métadonnées sur le contenu chargé.

**Créer un dossier**

Exécutez la commande suivante pour créer un dossier dans AEM référentiel :

```
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Spécifiez les paramètres suivants pour créer un dossier :

- `<username>:<passowrd>` : indiquez le nom d’utilisateur et le mot de passe pour accéder au référentiel AEM. Cet utilisateur doit disposer des droits de création de dossier.

- `jcr:primaryType=sling:Folder` : spécifiez ce paramètre *tel quel* pour créer une ressource de type dossier.

- `<server folder path>` : chemin d’accès complet au dossier incluant le nom du nouveau dossier que vous souhaitez créer dans le référentiel AEM. Par exemple, si vous spécifiez le chemin `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, le dossier `AEM-Guides` est créé dans le dossier `projects` de la gestion des ressources numériques.


**Télécharger un fichier**

Exécutez la commande suivante pour charger un fichier dans le référentiel AEM :

```
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Spécifiez les paramètres suivants pour télécharger un fichier :

- `<username>:<passowrd>` : indiquez le nom d’utilisateur et le mot de passe pour accéder au référentiel AEM. Cet utilisateur doit disposer de droits d’écriture sur le `server folder path`.

- ``local file path`` : chemin d’accès complet au fichier sur le système local que vous souhaitez charger.

- `<server folder path>` : chemin d’accès complet au dossier sur le serveur AEM où vous souhaitez charger le fichier.


**Ajouter des métadonnées**

Exécutez la commande suivante pour ajouter des métadonnées à un fichier :

```
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Spécifiez les paramètres suivants pour ajouter des informations de métadonnées :

- `<username>:<passowrd>` : indiquez le nom d’utilisateur et le mot de passe pour accéder au référentiel AEM. Cet utilisateur doit disposer de droits d’écriture sur le ``metadata node path``.

- ``-F<attribute name>=<value>`` : `<attribute name>` est le nom de l’attribut de métadonnées, tel que `audience` et `<value>` peut être `internal`. Vous pouvez spécifier plusieurs paires nom-valeur d’attribut séparées par espace.

- `<metadata node path>` : chemin d’accès complet au dossier incluant le nom du fichier et son noeud de métadonnées. Par exemple, si vous spécifiez le chemin d’accès `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, les informations de métadonnées spécifiées sont définies sur le fichier `intro.xml`.


**Rubrique parente :**[ Migrer le contenu existant](migrate-content.md)
