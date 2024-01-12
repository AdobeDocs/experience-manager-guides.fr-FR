---
title: Gestion des versions
description: Découvrez le fonctionnement de la gestion des versions
exl-id: 24e44618-9c4e-4547-a00d-216ef3fb4854
feature: Version Management
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1662'
ht-degree: 0%

---

# Gestion des versions {#id181GB000XY4}

Le contrôle de version est un aspect important de tout système de gestion de contenu. Il vous permet de créer un instantané de votre ressource numérique à un moment donné. Une fois la version d’une ressource numérique en place, vous pouvez restaurer la version requise de la ressource et la mettre à jour. En règle générale, pour créer une version d’une ressource, vous devez extraire et archiver la ressource requise.

En tant qu’administrateur, vous pouvez appliquer des règles qui empêchent les utilisateurs de modifier un fichier sans l’extraire. De même, vous pouvez vous assurer que tous les fichiers extraits sont archivés afin d’éviter toute perte de données.

Dans un environnement à plusieurs utilisations, il est également important de s’assurer que les utilisateurs ne suppriment pas les fichiers du système. Cette exigence est plus critique pour les fichiers extraits par d’autres utilisateurs. Vous pouvez autoriser ou empêcher les utilisateurs d’écraser les fichiers extraits par d’autres utilisateurs. Pour empêcher les utilisateurs de supprimer accidentellement des fichiers extraits du système, AEM Guides fournit une configuration que vous pouvez utiliser. Outre les fichiers extraits, vous pouvez également contrôler la suppression des fichiers qui contiennent des références ou qui sont référencés à partir d’autres fichiers. Vous pouvez également créer une version pour le fichier téléchargé.

## Créer une version pour le fichier téléchargé

>[!NOTE]
>
> Cette configuration s’applique uniquement lors du téléchargement de fichiers.

Pour créer une version du fichier chargé, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le bouton **com.adobe.config.ConfigManager** du lot.

1. Sélectionnez la variable **Créer une version pour le fichier téléchargé** .

   Par défaut, cette option est désactivée.

   Lorsque l’option est sélectionnée, un nouveau mécanisme de gestion de version a lieu et remplace le comportement de chargement par défaut pour tout chargement ultérieur ; il enregistre le contenu du fichier chargé en tant que nouvelle version. Si cette option est désélectionnée, AEM Guides utilise le mécanisme de gestion de version par défaut AEM.

1. Cliquez sur **Enregistrer**.


>[!NOTE]
>
> Si vous activez la propriété , vous pouvez charger des fichiers par lots de 70 ou moins. **Créer une version pour le fichier téléchargé** \(create.ver.new.content\) et utilisez la variable **Interface utilisateur des ressources** pour charger des ressources en masse.

## Configuration des paramètres pour permettre la modification des fichiers extraits

L’éditeur web des Guides d’AEM vous permet de créer et de mettre à jour des rubriques DITA. Vous pouvez configurer l’éditeur Web pour autoriser la modification des documents qui ont été extraits du référentiel uniquement. Cela permet qu’aucun autre auteur ne remplace accidentellement un sujet ouvert pour modification par un autre auteur. Une fois qu’une rubrique est ouverte pour modification, un auteur peut archiver le fichier au moment de la fermeture du fichier.

Une autre règle importante consiste à s’assurer que les fichiers qui ont été extraits sont réarchivés dans le système. Cela empêche les utilisateurs de fermer accidentellement les fichiers sans les réarchiver.

Effectuez les étapes suivantes pour activer ces fonctionnalités :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le bouton **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** du lot.

1. Sélectionnez la variable **Désactiver la modification sans extraction** .

   ![](assets/xml-editor-config.png){width="650" align="left"}

   Avec cette option, les utilisateurs ne verront pas l’option Modifier dans la barre d’outils tant qu’ils n’auront pas extrait un fichier.

1. Sélectionnez la variable **Demander l’archivage à la fermeture** pour afficher un message d’avertissement à chaque fois qu’un fichier extrait est fermé sans être enregistré ou archivé dans le référentiel.

1. Cliquez sur **Enregistrer**.


>[!NOTE]
>
> Que vous activiez ou non cette fonction, les options Extraction et Archivage du fichier sont toujours disponibles dans l’aperçu d’une rubrique.

## Remplacer le fichier extrait lors du chargement

>[!NOTE]
>
> Cette configuration s’applique uniquement lorsque vous créez des fichiers à partir de l’interface utilisateur d’Assets et non lorsque vous chargez des fichiers à l’aide de l’outil WebDAV.

Pour permettre aux utilisateurs de remplacer le fichier qu’ils ont extrait lors du téléchargement par un autre utilisateur ou un autre, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le bouton **com.adobe.config.ConfigManager** du lot.

1. Sélectionnez la variable **Remplacer le fichier extrait lors du téléchargement** .

   Par défaut, cette option est activée. Lorsque cette option est sélectionnée, les utilisateurs peuvent remplacer les fichiers extraits. Si cette option n’est pas sélectionnée, le fichier ne peut pas être remplacé s’il est extrait par lui ou par un autre utilisateur.

1. Cliquez sur **Enregistrer**.


## Empêcher la suppression des fichiers extraits

Pour empêcher les utilisateurs de supprimer accidentellement des fichiers extraits par eux ou par un autre utilisateur, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le bouton **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** du lot.

1. Sélectionnez la variable **Empêcher la suppression du contenu extrait** .

   Par défaut, cette option est activée. Lorsque cette option est sélectionnée, les utilisateurs ne pourront pas supprimer les fichiers extraits.

1. Cliquez sur **Enregistrer**.


Pour prendre en charge cette fonctionnalité, une nouvelle propriété d’index `drivelock` est ajouté dans `oak:index`:

`/oak:index/damAssetLucene/indexRules/dam:Asset/properties/drivelock`

![](assets/index-property-oak-index-drivelock.png){width="800" align="left"}

Outre la nouvelle propriété d’index, assurez-vous que les propriétés suivantes sont définies sur `/oak:index/damAssetLucene`:

- `jcr:primaryType`=`"oak:QueryIndexDefinition"`
- `async`=`"async"`
- `compatVersion`=`"{Long}2"`
- `evaluatePathRestrictions`=`"{Boolean}true"`
- `reindex`=`"{Boolean}false"`
- `reindexCount`=`"{Long}3"` *\(il s’agit du nombre de fois où la réindexation est effectuée, elle est remplacée par l’installation de notre module\)*
- `type`=`"lucene"`

>[!NOTE]
>
> Vous pouvez modifier la valeur de `reindex` to `"{Boolean}true"`. Cela permet d’obtenir des résultats de recherche plus rapides pour les fichiers extraits dans une hiérarchie de dossiers.

## Empêcher la suppression des fichiers référencés

En tant qu’administrateur, vous pouvez contrôler qui peut supprimer des fichiers du référentiel AEM. Plus précisément, si un fichier contient des références ou est référencé par un autre fichier, vous pouvez définir qui peut supprimer ces fichiers.

Cette configuration vous permet d’autoriser ou d’interdire à tous les utilisateurs la suppression de fichiers, ou d’autoriser uniquement un groupe d’utilisateurs spécifique à supprimer des fichiers. Si la suppression de fichier est autorisée, le processus suivant est suivi :

- Si vous supprimez un dossier contenant tous les fichiers référencés et référencés, tous les fichiers sont alors supprimés. Le processus supprime d’abord tous les fichiers qui ne contiennent aucune référence, puis les fichiers qui contiennent des références ou qui sont référencés.

- Si vous supprimez un dossier et que tout fichier du dossier est référencé par un fichier situé en dehors de ce dossier, vous serez invité à supprimer la référence avant de supprimer le fichier.


Pour définir qui peut supprimer un fichier contenant des références ou référencé par d’autres fichiers, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le bouton **com.adobe.config.ConfigManager** du lot.

1. Recherchez la variable **Suppression de blocs pour les ressources référencées** .

1. Selon qui vous souhaitez accorder l’accès à la suppression, spécifiez l’une des constantes suivantes :

   - allow\_unsafe\_delete\_for\_all : autorisez tous les utilisateurs à supprimer des fichiers. Dans ce cas, si le fichier\(s\) contient des références ou est référencé par d’autres fichiers, vous pouvez également supprimer ce(s\) fichier(s\) de manière forcée. Avant de supprimer le fichier, une invite s’affiche avec les références. Vous pouvez annuler l’opération de suppression, supprimer les références, puis supprimer le fichier\(s\). Vous pouvez également supprimer le fichier\(s\) sans supprimer les références.

     ![](assets/allow_unsafe_delete-force-delete.PNG){width="550" align="left"}

   - allow\_unsafe\_delete\_for\_delete\_assets\_group : un administrateur ou un utilisateur appartenant à la variable *delete-assets* Le groupe est autorisé à supprimer des fichiers. Si un autre utilisateur tente de supprimer des fichiers contenant des références, il n’est pas autorisé à les supprimer tant que toutes les références ne sont pas supprimées. La capture d’écran suivante s’affiche lorsqu’un utilisateur, qui ne dispose pas d’autorisations, tente de supprimer des fichiers.

     ![](assets/allow_unsafe_delete_for_delete_assets_group.PNG){width="550" align="left"}

   - block\_unsafe\_delete\_for\_all : interdire à tous les utilisateurs \(y compris les administrateurs\) de supprimer des fichiers jusqu’à ce que les références au fichier\(s\) soient supprimées.

1. Cliquez sur **Enregistrer**.


## Purge des anciennes versions des fichiers DITA

Lorsque vous mettez à jour le contenu et créez de nouvelles versions, les versions précédentes des fichiers DITA sont conservées dans le référentiel. De nombreuses versions peuvent être créées pour vos fichiers DITA sur une période donnée et peuvent occuper collectivement une grande quantité d’espace dans votre référentiel. AEM Guides vous permet de configurer les anciennes versions qui doivent être supprimées du référentiel.

Vous pouvez accéder à cet utilitaire à l’aide de l’URL donnée si vous disposez de droits d’administration :

`<server folder path> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`

La version d’un fichier DITA qui répond à l’un des critères donnés est conservée et non purgée :

- Est la première version d’un fichier
- Est inclus dans une ligne de base
- Est inclus dans tout processus de traduction ou de révision
- Est associé à un libellé
- Respecte l’âge ou le nombre défini de critères de version

Pour purger les anciennes versions, procédez comme suit :

1. Saisissez les informations suivantes sur les fichiers à purger :

   ![](assets/preview-purge-report.png){width="350" align="left"}

1. 
   - **Nombre de versions à conserver à partir de la dernière version**: entrez le nombre de versions qui doivent être conservées et non purgées. Par exemple, si nous saisissons 5 , les 5 dernières versions sont conservées, et les versions antérieures à peuvent être purgées si d’autres conditions de purge sont remplies.
- **Conserver Les Versions Créées Dans La Période \(En Jours\)**: saisissez la page maximale d’une version en jours. Les versions antérieures au nombre de jours donné peuvent être purgées si d’autres conditions de purge sont remplies. Par exemple, si nous entrez 100, toutes les versions créées avant 100 jours sont éligibles pour être purgées si d’autres conditions de purge sont remplies.
- **Chemin**: sélectionnez le chemin d’accès du fichier ou du dossier dont vous souhaitez purger les fichiers.

  >[!NOTE]
  >
  > Vous pouvez uniquement purger les fichiers DITA.

1. Cliquez sur **Aperçu du rapport Purge**.

   >[!NOTE]
   >
   > Il ne peut y avoir qu’une seule tâche de purge à la fois. Si une version est en cours de traitement, vous ne pouvez pas lancer une autre opération de purge de version.

   Le rapport de purge de version est généré.

1. Téléchargez le rapport Purge de version et vérifiez les fichiers et les versions qui seront purgés.
1. Vous pouvez choisir de **Annuler la purge** ou **Commencer la purge**.

   ![](assets/download-purge-report.png){width="350" align="left"}

   L’état de la purge s’affiche.

   Cliquez sur **Télécharger le rapport Purge de version** pour afficher les versions purgées. Ce rapport fournit l’état de purge de toutes les versions ainsi que les raisons pour lesquelles une version spécifique a été conservée ou pourquoi elle a été purgée.


>[!NOTE]
>
> Le rapport est téléchargé à l’emplacement suivant : /var/dxml/versionpurge
