---
title: Chargement de contenu DITA existant
description: Découvrez comment télécharger du contenu DITA existant
exl-id: 1dde8a29-301f-461e-b598-2a8cab61bf3d
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1201'
ht-degree: 0%

---

# Chargement de contenu DITA existant {#id176FF000JUI}

Il est probable que vous disposiez d’un référentiel de contenu DITA existant que vous souhaitez utiliser avec AEM Guides. Pour ce contenu existant, vous pouvez utiliser l’une des méthodes suivantes pour charger votre contenu en masse dans le référentiel AEM.

## Utilisation d’un outil WebDAV

Si vous créez des rubriques et des mappages dans un autre éditeur DITA, vous pouvez utiliser n’importe quel outil WebDAV pour charger vos fichiers. La procédure présentée dans cette section utilise WinSCP comme outil WebDAV pour télécharger du contenu.

Effectuez les étapes suivantes pour utiliser WinSCP pour charger des fichiers :

1. Téléchargez et installez WinSCP sur votre ordinateur.

1. Lancez l’application WinSCP.

   La boîte de dialogue Connexion s’affiche.

1. Dans la boîte de dialogue Connexion, spécifiez un paramètre Nouveau site en choisissant WebDAV comme paramètre **Protocole de fichier** et fournissant d’autres détails de connexion, tels que :

   - l&#39;URL d&#39;hébergement de votre serveur AEM,

   - le numéro de port \(la valeur par défaut est 4502\), et

   - le nom d’utilisateur et le mot de passe pour accéder à votre serveur AEM.

1. Cliquez sur **Ouverture de session**.

   Une fois la connexion établie, le contenu d’AEM Assets s’affiche dans l’interface utilisateur WinSCP. Vous pouvez facilement parcourir, créer, mettre à jour ou supprimer du contenu à l’aide de l’explorateur de fichiers WinSCP.


## Utiliser le FrameMaker

Adobe FrameMaker est fourni avec un puissant connecteur d’AEM qui vous permet de télécharger facilement votre DITA existant et d’autres documents de FrameMaker \(.book et .fm\) dans AEM. Vous pouvez utiliser différentes fonctionnalités de chargement de fichier, telles que le chargement d’un seul fichier, le chargement d’un dossier complet avec ou sans dépendances \(comme les références de contenu, les références croisées et les graphiques\).

Effectuez les étapes suivantes pour utiliser FrameMaker AEM Connector pour télécharger du contenu :

1. FrameMaker de lancement.

1. Ouvrez le **Gestionnaire de connexions** boîte de dialogue.

   ![](assets/fm-aem-connector.png){width="550" align="left"}

1. Saisissez les informations suivantes pour vous connecter au référentiel AEM :

   - **Nom**: saisissez un nom explicite afin d’identifier la connexion à votre serveur AEM.
   - **Serveur**: saisissez l’URL et le numéro de port de votre serveur AEM.

   - **Nom d’utilisateur**/**Password**: saisissez le nom d’utilisateur et le mot de passe pour accéder au serveur AEM.

1. Cliquez sur **Connexion**.

   Une fois la connexion établie, les ressources du référentiel AEM s’affichent dans la fenêtre Gestionnaire de référentiel.

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

1. Recherchez et cliquez sur le bouton *com.adobe.config.ConfigManager* du lot.

1. Dans le **Modèles de nom de fichier UUID** , spécifiez un modèle pour vérifier les noms du fichier importé.

   Si un fichier ne suit pas le modèle spécifié, un UUID est ajouté à la propriété du fichier et toutes les références au fichier sont mises à jour avec l’UUID affecté au fichier.

1. Cliquez sur **Enregistrer**.


## Chargement de contenu avec UUID à l’aide d’un outil WebDav {#id201MI0I04Y4}

Vous pouvez utiliser l’une des méthodes suivantes pour télécharger votre contenu avec l’UUID :

- Glissez-déposez du contenu depuis votre système local.
- Utilisez la variable **Créer** \> **Fichiers** workflow à partir de l’interface utilisateur d’AEM Assets.
- Utilisez un outil tel que WinSCP.

Si vous utilisez un outil tel que WinSCP, vous pouvez définir l’action à effectuer sur un fichier dupliqué en définissant la variable **Déplacer un ancien fichier avec le même UUID vers un nouveau dossier** dans configMgr. Cette option définit l’action effectuée sur un fichier disponible à un autre emplacement du référentiel AEM. Ce paramètre est disponible dans la *com.adobe.config.ConfigManager* dans configMgr.

Par défaut, la variable **Déplacer un ancien fichier avec le même UUID vers un nouveau dossier** est activée. Cela signifie que lorsque le fichier en cours de chargement se trouve dans un autre dossier du référentiel, le fichier existant est déplacé vers l’emplacement actuel et remplacé par le fichier en cours de chargement. Si vous ne sélectionnez pas cette option, le fichier est remplacé à son emplacement existant.

**Remarques supplémentaires sur l’utilisation de fichiers UUID**:

Les points suivants doivent être pris en compte lors du déplacement ou de la copie de contenu dans le référentiel AEM :

- Lors de la copie d’un ou de plusieurs fichiers d’un emplacement vers un autre emplacement, un nouvel UUID est généré pour les fichiers sans UUID. Cet UUID est ajouté aux métadonnées du fichier.

- Si un fichier est en conflit ou a un doublon, un nom de fichier unique est généré pour le nouveau fichier copié ou déplacé.

- Aucun fichier ne peut avoir le même UUID. Un UUID unique est affecté à tous les nouveaux fichiers.


Les points suivants doivent être pris en compte lors du déplacement ou de la copie de contenu de votre système local vers le référentiel AEM :

- Si, en cas de chargement simultané d’un fichier par deux utilisateurs différents, le fichier traité ultérieurement remplace le fichier précédent. Cependant, une telle pratique est rare et doit être évitée.

- Lorsque vous extrayez du contenu du référentiel AEM et apportez des modifications sur votre système local, assurez-vous que le nom du fichier n’est pas modifié au moment du téléchargement du fichier.


## Utilisation des commandes curl

Vous pouvez également utiliser des commandes curl pour créer un dossier dans DAM, charger des fichiers et ajouter des métadonnées sur le contenu chargé.

**Création d’un dossier**

Exécutez la commande suivante pour créer un dossier dans AEM référentiel :

```curl
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Spécifiez les paramètres suivants pour créer un dossier :

- `<username>:<passowrd>`: spécifiez le nom d’utilisateur et le mot de passe pour accéder au référentiel AEM. Cet utilisateur doit disposer des droits de création de dossier.

- `jcr:primaryType=sling:Folder`: indiquez ce paramètre *as is* pour créer une ressource de type dossier.

- `<server folder path>`: chemin d’accès complet au dossier, y compris le nom du nouveau dossier que vous souhaitez créer dans le référentiel AEM. Par exemple, si vous spécifiez le chemin comme `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, puis le dossier `AEM-Guides` est créé dans la fonction `projects` dans DAM.


**Chargement d’un fichier**

Exécutez la commande suivante pour charger un fichier dans le référentiel AEM :

```curl
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Spécifiez les paramètres suivants pour télécharger un fichier :

- `<username>:<passowrd>`: spécifiez le nom d’utilisateur et le mot de passe pour accéder au référentiel AEM. Cet utilisateur doit disposer de droits d’écriture sur la variable `server folder path`.

- ``local file path``: chemin d’accès au fichier complet sur le système local que vous souhaitez charger.

- `<server folder path>`: chemin d’accès au dossier complet sur le serveur AEM où vous souhaitez charger le fichier.


**Ajout de métadonnées**

Exécutez la commande suivante pour ajouter des métadonnées à un fichier :

```curl
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Spécifiez les paramètres suivants pour ajouter des informations de métadonnées :

- `<username>:<passowrd>`: spécifiez le nom d’utilisateur et le mot de passe pour accéder au référentiel AEM. Cet utilisateur doit disposer de droits d’écriture sur la variable ``metadata node path``.

- ``-F<attribute name>=<value>``: la variable `<attribute name>` est le nom de l’attribut de métadonnées, tel que `audience` et la variable `<value>` pourrait être `internal`. Vous pouvez spécifier plusieurs paires nom-valeur d’attribut séparées par espace.

- `<metadata node path>`: chemin d’accès complet au dossier, y compris le nom du fichier et son noeud de métadonnées. Par exemple, si vous spécifiez le chemin comme `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, les informations de métadonnées spécifiées sont définies sur `intro.xml` fichier .


**Rubrique parente :**[ Migration de contenu existant](migrate-content.md)
