---
title: Charger le contenu DITA existant
description: Découvrez comment télécharger du contenu DITA existant
exl-id: 1dde8a29-301f-461e-b598-2a8cab61bf3d
feature: Migration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '1201'
ht-degree: 0%

---

# Charger le contenu DITA existant {#id176FF000JUI}

Il est probable que vous disposiez d&#39;un référentiel de contenu DITA existant que vous souhaitez utiliser avec AEM Guides. Pour ce type de contenu existant, vous pouvez utiliser l’une des approches suivantes pour charger en bloc votre contenu dans le référentiel AEM.

## Utilisation d’un outil WebDAV

Si vous créez vos rubriques et mappages dans un autre éditeur DITA, vous pouvez utiliser n&#39;importe quel outil WebDAV pour charger vos fichiers. La procédure décrite dans cette section utilise WinSCP comme outil WebDAV pour télécharger du contenu.

Effectuez les étapes suivantes pour utiliser WinSCP pour charger des fichiers :

1. Télécharger et installer WinSCP sur votre ordinateur.

1. Lancez l&#39;application WinSCP.

   La boîte de dialogue Connexion s’affiche.

1. Dans la boîte de dialogue Connexion, spécifiez un paramètre Nouveau site en choisissant WebDAV comme **Protocole de fichier** et en fournissant d’autres détails de connexion, tels que :

   - l’URL d’hébergement de votre serveur AEM,

   - le numéro de port \(4502\ par défaut), et

   - le nom d’utilisateur et le mot de passe pour accéder à votre serveur AEM.

1. Cliquez sur **Ouverture de session**.

   Une fois la connexion établie, le contenu d&#39;AEM Assets s&#39;affiche dans l&#39;interface utilisateur WinSCP. Vous pouvez facilement parcourir, créer, mettre à jour ou supprimer du contenu en utilisant l&#39;explorateur de fichiers WinSCP.


## Utilisation de FrameMaker

Adobe FrameMaker s’accompagne d’un puissant connecteur AEM qui vous permet de télécharger facilement vos documents DITA et autres documents FrameMaker \(.book et .fm\) dans AEM. Vous pouvez utiliser diverses fonctionnalités de chargement de fichier, telles que le chargement d’un seul fichier ou d’un dossier complet avec ou sans dépendances \(comme les références de contenu, les références croisées et les graphiques\).

Effectuez les étapes suivantes pour utiliser le connecteur AEM FrameMaker afin de charger du contenu :

1. Lancez FrameMaker.

1. Ouvrez la boîte de dialogue **Gestionnaire de connexions**.

   ![](assets/fm-aem-connector.png){width="550" align="left"}

1. Saisissez les informations suivantes pour vous connecter au référentiel AEM :

   - **Nom** : saisissez un nom explicite pour identifier la connexion à votre serveur AEM.
   - **Serveur** : saisissez l’URL et le numéro de port de votre serveur AEM.

   - **Nom d’utilisateur**/**Mot de passe** : saisissez le nom d’utilisateur et le mot de passe pour accéder au serveur AEM.

1. Cliquez sur **Connexion**.

   Une fois la connexion établie, les Assets du référentiel AEM s’affichent dans la fenêtre Gestionnaire de référentiel .

   ![](assets/fm-repo-manager.png){width="550" align="left"}

   Cliquez avec le bouton droit de la souris sur un fichier ou un dossier pour effectuer les opérations associées. Par exemple, si vous cliquez avec le bouton droit de la souris sur un dossier, vous obtenez des options pour charger un fichier , charger un fichier avec des dépendances, charger un dossier entier, etc.


## Configurer le modèle de nom de fichier UUID

Lorsque vous importez du contenu, il n’est pas nécessaire que vos noms de fichier soient basés sur l’UUID. Dans un système qui utilise des noms de fichiers basés sur l’UUID, il est obligatoire que tous les fichiers soient référencés à l’aide de leur UUID plutôt que de leur nom de fichier d’origine. Si un fichier importé ne possède pas de nom de fichier basé sur UUID, vous pouvez configurer le système pour ajouter un UUID à sa propriété de fichier. Cet UUID est ensuite utilisé pour faire référence aux fichiers pour lesquels l’UUID n’est pas utilisé pour nommer les fichiers.

Effectuez les étapes suivantes pour vérifier les noms de fichiers par rapport à un modèle UUID et affecter UUID aux fichiers auxquels aucun UUID n’est affecté :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot *com.adobe.fmdita.config.ConfigManager* et cliquez dessus.

1. Dans la propriété **Modèles de nom de fichier UUID**, spécifiez un modèle pour vérifier les noms des fichiers importés.

   Si un fichier ne suit pas le modèle spécifié, un UUID est ajouté à la propriété du fichier et toutes les références au fichier sont mises à jour avec l’UUID attribué au fichier.

1. Cliquez sur **Enregistrer**.


## Télécharger du contenu avec UUID à l’aide d’un outil WebDav {#id201MI0I04Y4}

Vous pouvez utiliser l’une des méthodes suivantes pour charger votre contenu avec l’UUID :

- Glissez-déposez du contenu à partir de votre système local.
- Utilisez le workflow **Créer** \> **Fichiers** à partir de l’interface utilisateur d’AEM Assets.
- Utilisez un outil comme WinSCP.

Si vous utilisez un outil tel que WinSCP, vous pouvez définir l&#39;action à effectuer sur un fichier dupliqué en définissant l&#39;option **Déplacer l&#39;ancien fichier avec le même UUID vers le nouveau dossier** dans configMgr. Cette option définit l’action à effectuer sur un fichier disponible à un autre emplacement du référentiel AEM. Ce paramètre est disponible dans le lot *com.adobe.fmdita.config.ConfigManager* dans configMgr.

Par défaut, l’option **Déplacer l’ancien fichier avec le même UUID vers le nouveau dossier** est activée. Cela signifie que lorsque le fichier en cours de chargement se trouve dans un autre dossier du référentiel, le fichier existant est déplacé vers l’emplacement actuel et remplacé par le fichier en cours de chargement. Si vous ne sélectionnez pas cette option, le fichier est remplacé à son emplacement existant.

**Remarques supplémentaires sur l’utilisation des fichiers basés sur UUID** :

Lors du déplacement ou de la copie de contenu dans le référentiel AEM, tenez compte des points suivants :

- Lors de la copie d&#39;un ou plusieurs fichiers d&#39;un emplacement à un autre, un nouvel UUID est généré pour les fichiers sans UUID. Cet UUID est ajouté dans les métadonnées du fichier.

- Si un fichier est en conflit ou en double, un nom de fichier unique est généré pour le nouveau fichier copié ou déplacé.

- Deux fichiers ne peuvent pas avoir le même UUID. Un UUID unique est affecté à tous les nouveaux fichiers.


Lors du déplacement ou de la copie de contenu de votre système local vers le référentiel AEM, tenez compte des points suivants :

- Si un fichier est chargé par deux utilisateurs différents en même temps, le fichier qui est traité ultérieurement remplace le fichier précédent. Cependant, une telle pratique est rare et doit être évitée.

- Lorsque vous extrayez du contenu du référentiel AEM et apportez des modifications à votre système local, assurez-vous que le nom du fichier n’est pas modifié au moment du téléchargement du fichier.


## Utilisation des commandes curl

Vous pouvez également utiliser des commandes curl pour créer un dossier dans la gestion des ressources numériques, charger des fichiers et ajouter des métadonnées au contenu chargé.

**Créer un dossier**

Exécutez la commande suivante pour créer un dossier dans le référentiel AEM :

```curl
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Spécifiez les paramètres suivants pour créer un dossier :

- `<username>:<passowrd>` : indiquez le nom d’utilisateur et le mot de passe pour accéder au référentiel AEM. Cet utilisateur doit disposer des privilèges de création de dossier.

- `jcr:primaryType=sling:Folder` : spécifiez ce paramètre *en l’état* pour créer une ressource de type dossier.

- `<server folder path>` : chemin d’accès complet du dossier, y compris le nom du nouveau dossier que vous souhaitez créer dans le référentiel AEM. Par exemple, si vous définissez le chemin d’accès sur `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, le dossier `AEM-Guides` est créé dans le dossier `projects` dans la gestion des ressources numériques.


**Charger un fichier**

Exécutez la commande suivante pour charger un fichier dans le référentiel AEM :

```curl
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Spécifiez les paramètres suivants pour télécharger un fichier :

- `<username>:<passowrd>` : indiquez le nom d’utilisateur et le mot de passe pour accéder au référentiel AEM. Cet utilisateur doit disposer de droits d’écriture sur le `server folder path`.

- ``local file path`` : chemin d’accès complet au fichier sur le système local que vous souhaitez charger.

- `<server folder path>` : chemin complet du dossier sur le serveur AEM sur lequel vous souhaitez télécharger le fichier.


**Ajout de métadonnées**

Exécutez la commande suivante pour ajouter des métadonnées à un fichier :

```curl
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Spécifiez les paramètres suivants pour ajouter des informations de métadonnées :

- `<username>:<passowrd>` : indiquez le nom d’utilisateur et le mot de passe pour accéder au référentiel AEM. Cet utilisateur doit disposer de droits d’écriture sur le ``metadata node path``.

- ``-F<attribute name>=<value>`` : le `<attribute name>` est le nom de l’attribut de métadonnées, tel que `audience`, et le `<value>` peut être `internal`. Vous pouvez spécifier plusieurs paires nom-valeur d’attribut séparées par un espace.

- `<metadata node path>` : chemin complet du dossier, y compris le nom du fichier et son nœud de métadonnées. Par exemple, si vous définissez le chemin d’accès sur `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, les informations de métadonnées spécifiées sont définies sur `intro.xml` fichier .


**Rubrique parente :**&#x200B;[&#x200B; Migrer le contenu existant](migrate-content.md)
