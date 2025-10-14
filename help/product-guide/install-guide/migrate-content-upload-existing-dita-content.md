---
title: Chargement de contenu DITA existant
description: Découvrez comment télécharger du contenu DITA existant
exl-id: 1dde8a29-301f-461e-b598-2a8cab61bf3d
feature: Migration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1201'
ht-degree: 0%

---

# Chargement de contenu DITA existant {#id176FF000JUI}

Vous disposez probablement d’un référentiel de contenu DITA existant que vous souhaitez utiliser avec AEM Guides. Pour ce contenu existant, vous pouvez utiliser l’une des méthodes suivantes pour charger votre contenu en masse dans le référentiel AEM.

## Utilisation d’un outil WebDAV

Si vous créez des rubriques et des mappages dans un autre éditeur DITA, vous pouvez utiliser n’importe quel outil WebDAV pour charger vos fichiers. La procédure présentée dans cette section utilise WinSCP comme outil WebDAV pour télécharger du contenu.

Effectuez les étapes suivantes pour utiliser WinSCP pour charger des fichiers :

1. Téléchargez et installez WinSCP sur votre ordinateur.

1. Lancez l’application WinSCP.

   La boîte de dialogue Connexion s’affiche.

1. Dans la boîte de dialogue Connexion, spécifiez un paramètre Nouveau site en choisissant WebDAV comme **protocole de fichier** et en fournissant d’autres détails de connexion tels que :

   - l&#39;URL d&#39;hébergement de votre serveur AEM,

   - le numéro de port \(la valeur par défaut est 4502\), et

   - le nom d’utilisateur et le mot de passe pour accéder à votre serveur AEM.

1. Cliquez sur **Ouverture de session**.

   Une fois la connexion établie, le contenu d’AEM Assets s’affiche dans l’interface utilisateur WinSCP. Vous pouvez facilement parcourir, créer, mettre à jour ou supprimer du contenu à l’aide de l’explorateur de fichiers WinSCP.


## Utiliser le FrameMaker

Adobe FrameMaker est fourni avec un puissant connecteur d’AEM qui vous permet de télécharger facilement votre DITA existant et d’autres documents de FrameMaker \(.book et .fm\) dans AEM. Vous pouvez utiliser différentes fonctionnalités de chargement de fichier, telles que le chargement d’un seul fichier, le chargement d’un dossier complet avec ou sans dépendances \(comme les références de contenu, les références croisées et les graphiques\).

Effectuez les étapes suivantes pour utiliser FrameMaker AEM Connector pour télécharger du contenu :

1. FrameMaker de lancement.

1. Ouvrez la boîte de dialogue **Connection Manager** .

   ![](assets/fm-aem-connector.png){width="550" align="left"}

1. Saisissez les informations suivantes pour vous connecter au référentiel AEM :

   - **Nom** : saisissez un nom descriptif pour identifier la connexion à votre serveur AEM.
   - **Serveur** : saisissez l’URL et le numéro de port de votre serveur AEM.

   - **Nom d’utilisateur**/**Mot de passe** : saisissez le nom d’utilisateur et le mot de passe pour accéder au serveur AEM.

1. Cliquez sur **Connect**.

   Une fois la connexion établie, Assets du référentiel d’AEM s’affiche dans la fenêtre Gestionnaire de référentiel.

   ![](assets/fm-repo-manager.png){width="550" align="left"}

   Cliquez avec le bouton droit de la souris sur un fichier ou un dossier pour effectuer les opérations associées. Par exemple, si vous cliquez avec le bouton droit de la souris sur un dossier, vous avez la possibilité de télécharger un fichier, un fichier avec des dépendances, un dossier entier, etc.


## Configuration du modèle de nom de fichier UUID

Lorsque vous importez du contenu, il n’est pas nécessaire que vos noms de fichier soient basés sur l’UUID. Dans un système qui utilise des noms de fichier UUID, il est obligatoire que tous les fichiers soient référencés à l’aide de leur UUID plutôt que de leur nom de fichier d’origine. Si un fichier importé ne comporte pas de nom de fichier basé sur l’UUID, vous pouvez configurer le système pour ajouter un UUID à sa propriété de fichier. Cet UUID est ensuite utilisé pour faire référence aux fichiers pour lesquels l’UUID n’est pas utilisé pour nommer les fichiers.

Effectuez les étapes suivantes pour vérifier les noms de fichier par rapport à un modèle UUID et attribuer un UUID aux fichiers auxquels aucun UID n’est affecté :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot *com.adobe.fmdita.config.ConfigManager*.

1. Dans la propriété **UUID Filename Patterns**, spécifiez un modèle pour vérifier les noms du fichier importé.

   Si un fichier ne suit pas le modèle spécifié, un UUID est ajouté à la propriété du fichier et toutes les références au fichier sont mises à jour avec l’UUID affecté au fichier.

1. Cliquez sur **Enregistrer**.


## Chargement de contenu avec UUID à l’aide d’un outil WebDav {#id201MI0I04Y4}

Vous pouvez utiliser l’une des méthodes suivantes pour télécharger votre contenu avec l’UUID :

- Glissez-déposez du contenu depuis votre système local.
- Utilisez le workflow **Créer** \> **Fichiers** à partir de l’interface utilisateur Assets d’AEM.
- Utilisez un outil tel que WinSCP.

Si vous utilisez un outil tel que WinSCP, vous pouvez définir l’action à effectuer sur un fichier dupliqué en définissant l’option **Déplacer l’ancien fichier avec le même UUID vers le nouveau dossier** dans configMgr. Cette option définit l’action effectuée sur un fichier disponible à un autre emplacement du référentiel AEM. Ce paramètre est disponible dans le lot *com.adobe.fmdita.config.ConfigManager* de configMgr.

Par défaut, l’option **Déplacer l’ancien fichier avec le même UUID vers le nouveau dossier** est activée. Cela signifie que lorsque le fichier en cours de chargement se trouve dans un autre dossier du référentiel, le fichier existant est déplacé vers l’emplacement actuel et remplacé par le fichier en cours de chargement. Si vous ne sélectionnez pas cette option, le fichier est remplacé à son emplacement existant.

**Remarques supplémentaires sur l’utilisation de fichiers UUID** :

Les points suivants doivent être pris en compte lors du déplacement ou de la copie de contenu dans le référentiel AEM :

- Lors de la copie d’un ou de plusieurs fichiers d’un emplacement vers un autre emplacement, un nouvel UUID est généré pour les fichiers sans UUID. Cet UUID est ajouté aux métadonnées du fichier.

- Si un fichier est en conflit ou a un doublon, un nom de fichier unique est généré pour le nouveau fichier copié ou déplacé.

- Aucun fichier ne peut avoir le même UUID. Un UUID unique est affecté à tous les nouveaux fichiers.


Les points suivants doivent être pris en compte lors du déplacement ou de la copie de contenu de votre système local vers le référentiel AEM :

- Si, en cas de chargement simultané d’un fichier par deux utilisateurs différents, le fichier traité ultérieurement remplace le fichier précédent. Cependant, une telle pratique est rare et doit être évitée.

- Lorsque vous extrayez du contenu du référentiel AEM et apportez des modifications sur votre système local, assurez-vous que le nom du fichier n’est pas modifié au moment du téléchargement du fichier.


## Utilisation des commandes curl

Vous pouvez également utiliser des commandes curl pour créer un dossier dans DAM, charger des fichiers et ajouter des métadonnées sur le contenu chargé.

**Créer un dossier**

Exécutez la commande suivante pour créer un dossier dans AEM référentiel :

```curl
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Spécifiez les paramètres suivants pour créer un dossier :

- `<username>:<passowrd>` : indiquez le nom d’utilisateur et le mot de passe pour accéder au référentiel AEM. Cet utilisateur doit disposer des droits de création de dossier.

- `jcr:primaryType=sling:Folder` : spécifiez ce paramètre *tel quel* pour créer une ressource de type dossier.

- `<server folder path>` : chemin d’accès complet au dossier incluant le nom du nouveau dossier que vous souhaitez créer dans le référentiel AEM. Par exemple, si vous spécifiez le chemin `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, le dossier `AEM-Guides` est créé dans le dossier `projects` de la gestion des ressources numériques.


**Télécharger un fichier**

Exécutez la commande suivante pour charger un fichier dans le référentiel AEM :

```curl
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Spécifiez les paramètres suivants pour télécharger un fichier :

- `<username>:<passowrd>` : indiquez le nom d’utilisateur et le mot de passe pour accéder au référentiel AEM. Cet utilisateur doit disposer de droits d’écriture sur le `server folder path`.

- ``local file path`` : chemin d’accès complet au fichier sur le système local que vous souhaitez charger.

- `<server folder path>` : chemin d’accès complet au dossier sur le serveur AEM où vous souhaitez charger le fichier.


**Ajouter des métadonnées**

Exécutez la commande suivante pour ajouter des métadonnées à un fichier :

```curl
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Spécifiez les paramètres suivants pour ajouter des informations de métadonnées :

- `<username>:<passowrd>` : indiquez le nom d’utilisateur et le mot de passe pour accéder au référentiel AEM. Cet utilisateur doit disposer de droits d’écriture sur le ``metadata node path``.

- ``-F<attribute name>=<value>`` : `<attribute name>` est le nom de l’attribut de métadonnées, tel que `audience` et `<value>` peut être `internal`. Vous pouvez spécifier plusieurs paires nom-valeur d’attribut séparées par espace.

- `<metadata node path>` : chemin d’accès complet au dossier incluant le nom du fichier et son noeud de métadonnées. Par exemple, si vous spécifiez le chemin d’accès `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, les informations de métadonnées spécifiées sont définies sur le fichier `intro.xml`.


**Rubrique parente :**&#x200B;[&#x200B; Migrer le contenu existant](migrate-content.md)
