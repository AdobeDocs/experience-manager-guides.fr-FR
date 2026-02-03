---
title: Experience Manager Guides et Edge Delivery Services (Beta)
description: Découvrez comment Edge Delivery Services (Beta) étend les possibilités de création et de publication de Experience Manager Guides.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 5808d42c530e55e309f192c99a0e71334c888b57
workflow-type: tm+mt
source-wordcount: '1532'
ht-degree: 0%

---

# Experience Manager Guides et Edge Delivery Services (Beta)

Adobe Experience Manager Guides vous permet de publier votre contenu DITA directement dans Edge Delivery Services (EDS), actuellement disponible dans *Beta*, par le biais d’un profil de publication GitHub dédié. Cette fonctionnalité permet aux entreprises de fournir des expériences de documentation réactives et haute performance tout en conservant des workflows de création basés sur DITA dans Experience Manager Guides.

Pour plus d’informations sur l’utilisation d’EDS dans Adobe Experience Manager, consultez la [Présentation de Edge Delivery Services](https://experienceleague.adobe.com/fr/docs/experience-manager-cloud-service/content/edge-delivery/overview).

Pour activer la publication de Experience Manager Guides vers EDS (Beta), vous devez effectuer une série d’étapes de configuration sur GitHub et Experience Manager Guides. Les sections ci-dessous décrivent chaque étape dans l’ordre et expliquent comment elles fonctionnent ensemble dans le workflow de publication global.

1. [Installer et configurer GitHub pour EDS (Beta)](#set-up-and-configure-github-for-eds-beta)
2. [Créer et configurer un profil de publication pour EDS (Beta) dans Experience Manager Guides](#create-and-configure-a-publish-profile-for-eds-beta-in-experience-manager)
3. [Personnaliser la sortie à l’aide de blocs EDS](#customize-output-using-eds-blocks)

Pour une présentation vidéo rapide, reportez-vous à la section [Publication dans AEM Guides](https://experienceleague.adobe.com/fr/docs/experience-manager-guides/using/knowledge-base/expert-session/publishing-in-aem-guides-aug25).



## Installer et configurer GitHub pour EDS (Beta)

Cette section décrit comment configurer GitHub en vue de son utilisation avec EDS (Beta). Il couvre la création d’un référentiel à l’aide du standard Adobe, la connexion de GitHub à Adobe Experience Manager par le biais de la synchronisation du code AEM, la configuration des applications GitHub et OAuth requises, et la définition du point de montage du référentiel utilisé pour publier du contenu.

### Créer un référentiel GitHub pour EDS (Beta)

EDS (Beta) nécessite un référentiel GitHub avec une structure prédéfinie. Adobe fournit un référentiel standard officiel spécialement conçu pour les utilisateurs de Experience Manager Guides.

Pour créer votre référentiel, procédez comme suit :

1. Ouvrez le [`aem-guides-boilerplate`](https://github.com/adobe/aem-guides-boilerplate) de référentiel de modèles standard Experience Manager Guides .
   ![](assets/eds-boilerplate-template.png){align="left"}

2. Créez un référentiel à l’aide de ce modèle. En savoir plus sur la [création d’un référentiel à partir d’un modèle](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template). Assurez-vous que la visibilité du référentiel est définie sur *Public* afin qu’il soit accessible par EDS.

   ![](assets/eds-create-new-repo.png){align="left"}

Le référentiel est maintenant créé et s’aligne sur la structure du modèle standard.

![](assets/eds-repo-created-github-view.png){align="left"}

### Connecter GitHub à Adobe via la synchronisation de code AEM

Adobe Experience Manager utilise une application GitHub appelée **Synchronisation du code AEM** pour pousser le contenu de Experience Manager Guides vers GitHub.

Pour installer et configurer l’application *AEM Code Sync*, procédez comme suit :

1. Accédez à la page [Synchronisation du code AEM](https://github.com/apps/aem-code-sync) et sélectionnez **Installer**.
2. *La synchronisation du code AEM* surveille les modifications du référentiel et s’assure que les mises à jour sont correctement transmises à GitHub.

   >
   >
   > Lors de l’installation de l’application, veillez à utiliser le même compte GitHub propriétaire du référentiel.

   ![](assets/eds-aem-code-sync-page.png){align="left"}
3. Sur la page suivante, accordez l’accès au référentiel que vous avez créé. Pour ce faire, sélectionnez l’option **Sélectionner uniquement les référentiels**, puis sélectionnez votre référentiel dans la liste déroulante.

   ![](assets/eds-aem-code-sync-install-authorize.png){width="350" align="left"}
4. Sélectionnez **Installer et autoriser**.

Vous êtes redirigé vers la page de configuration GitHub, confirmant l’enregistrement réussi de l’application *AEM Code Sync*. Vous pouvez également enregistrer l’aperçu et les URL dynamiques pour votre site web à partir de cette page.

![](assets/eds-aem-code-sync-registered.png){align="left"}

### Créer une application GitHub

1. Sur GitHub, accédez à la barre latérale gauche et sélectionnez **Paramètres du développeur**.
2. Dans la barre latérale gauche, sélectionnez **Applications GitHub**.
3. Sélectionnez **Nouvelle application GitHub**.

   ![](assets/eds-new-github-app.png){width="650" align="left"}
4. Sur la page **Enregistrer la nouvelle application GitHub**, fournissez les détails suivants :
   - **Nom de l’application GitHub** : saisissez un nom pour votre application. Par exemple, `USERNAME-eds-app` où USERNAME correspond à votre nom d’utilisateur GitHub.
   - **URL de la page d’accueil** : saisissez l’URL de l’instance Experience Manager Guides.

     Exemple d&#39;URL (format) : `https://<aem-author-url>/libs/fmdita/clientlibs/xmleditor/page.html`

     Exemple d’URL : `https://author-p16602-e335172-cmstg.adobeaemcloud.com/libs/fmdita/clientlibs/xmleditor/page.html`
   - **URL de rappel** : identique à l’URL de la page d’accueil.
   - **URL Webhook** : désactivez cette option.
   - **Autorisations de référentiel** : définissez **autorisations de lecture et d’écriture** pour les *actions, administration et attestation*.
5. Sélectionnez **Créer une application GitHub**.

Votre application est maintenant prête. Vous êtes redirigé vers la page **Paramètres** de votre application GitHub.

![](assets/eds-github-app-registered-page.png){align="left"}

### Créer une application OAuth

Une application OAuth est requise pour authentifier les utilisateurs lors de la création d’un profil de publication EDS (Beta) dans Experience Manager Guides. Il active un flux de connexion sécurisé à l’aide d’un *ID client* et d’un *Secret client*.

Pour créer une application OAuth, procédez comme suit :

1. Sur GitHub, accédez à la barre latérale gauche et sélectionnez **Paramètres du développeur**.
2. Dans la barre latérale gauche, sélectionnez **Applications OAuth**.
3. Sélectionnez **Nouvelle application OAuth**.

   ![](assets/eds-new-oauth-app.png){width="650" align="left"}
4. Enregistrez votre application en fournissant les informations obligatoires suivantes :
   - **Nom de l’application** : saisissez le nom de votre référentiel EDS
   - **URL de la page d’accueil** : saisissez l’URL de l’instance Experience Manager Guides. (Pour obtenir un exemple de format d’URL, reportez-vous à l’étape 4 de la section [Création d’une application GitHub](#create-a-new-github-app)).
   - **URL de rappel d’autorisation** : identique à l’URL de la page d’accueil
5. Sélectionnez l’option **Activer le flux d’appareils** puis sélectionnez **Enregistrer l’application** pour terminer l’enregistrement.

   ![](assets/eds-new-github-app-register.png){width="650" align="left"}

Votre application est maintenant prête. Notez l’*ID client*. Vous pouvez générer jusqu’à cinq *Secrets client* maintenant ou ultérieurement lors de la configuration du profil de publication dans Experience Manager Guides.

![](assets/eds-new-oauth-app-page.png){align="left"}


### Configuration de l’URL du point de montage dans le référentiel EDS (Beta)

EDS (Beta) lit le contenu à partir d’un chemin de référentiel GitHub défini comme une URL *point de montage* dans le fichier `fstab.yaml`.

Pour configurer l’URL du point de montage dans le fichier `fstab.yaml` :

1. Ouvrez le fichier `fstab.yaml` dans votre référentiel et mettez à jour les éléments suivants :
   - `your-user-name`
   - `your-repo-name`

   >
   >
   > Dans l’URL du point de montage, `main` indique la branche sur laquelle vous souhaitez publier le contenu et `docs` indique le dossier racine du référentiel EDS (Beta) sur lequel vous travaillez. Si vous préférez modifier le nom de la branche sur GitHub, vous devez mettre à jour le même nom de branche dans l’URL *point de montage* (dans le fichier `fstab.yaml`) et le profil de publication EDS correspondant dans Experience Manager Guides.

   ![](assets/eds-fstab-yaml-file.png){width="650" align="left"}
2. Sélectionnez **Valider les modifications**, saisissez les détails de validation, puis confirmez.
3. Revenez à [Paramètres du développeur](https://github.com/settings/apps), recherchez votre application, puis sélectionnez **Modifier**.

   ![](assets/eds-edit-github-app.png){width="650" align="left"}
4. Accédez à la page **Installer l’application** et sélectionnez **Installer**.

   ![](assets/eds-install-eds-app.png){width="650" align="left"}
5. Répétez les étapes 2 et 3 de la section [Connexion de GitHub à Adobe via la synchronisation de code AEM](#connect-github-to-adobe-via-aem-code-sync) pour autoriser le référentiel.

## Créer et configurer un profil de publication pour EDS (Beta) dans Experience Manager

Les sections ci-dessous décrivent chaque étape dans l’ordre et expliquent comment configurer un profil de publication EDS (Beta), configurer un paramètre prédéfini de sortie et générer une sortie à l’aide d’EDS (Beta) dans Experience Manager Guides.

### Création du profil de publication EDS (Beta)

1. Accédez à **[Paramètres Workspace]** **>** **Publier des profils**.
2. Sélectionnez l’icône **+** pour créer un profil de publication et fournissez les détails suivants :
   - **Type de serveur** : sélectionnez **GitHub Edge Delivery Services (Beta)** dans la liste déroulante.
   - **Nom** : saisissez un nom pour ce profil .
   - **Nom du référentiel** : utilisez le nom du référentiel GitHub créé à partir du standard.
   - **Nom d’utilisateur** : saisissez votre nom d’utilisateur GitHub.
   - **Branche principale** : définissez sur principale (par défaut).
   - **Dossier racine** : défini sur docs (par défaut).
   - **ID client et secret client** : récupérez-les à partir de votre application GitHub (voir la section [Créer une application OAuth](#create-a-new-oauth-app) pour plus d’informations).
3. Sélectionnez **Connexion** pour vous authentifier.

   ![](assets/eds-publish-profile.png){width="650" align="left"}
4. Une fois l’authentification réussie, sélectionnez **Enregistrer**.

Votre profil de publication EDS (Beta) est maintenant configuré.

### Création d’un paramètre prédéfini de sortie pour EDS (Beta) et génération de la sortie

1. Ouvrez votre carte dans la console Carte.
2. Dans l’onglet **Paramètres prédéfinis de sortie**, sélectionnez **+** pour créer un paramètre prédéfini de sortie.
3. Dans la boîte de dialogue **Nouveau paramètre prédéfini de sortie**, fournissez les détails suivants :
   - **Type** : sélectionnez **Service Edge Delivery (Beta)**
   - **Nom** : attribuez un nom à ce paramètre prédéfini
4. Sélectionnez **Ajouter**.

   ![](assets/eds-output-preset.png){width="650" align="left"}
5. Ouvrez le paramètre prédéfini de sortie EDS (Beta) que vous venez de créer et accédez à l’onglet **Config**.
   - Sélectionnez le profil de publication créé à l’étape précédente.
   - Activez **Push to live**.

   Lorsque l’option **Push to live** est activée, la sortie générée est validée dans GitHub et les mises à jour correspondantes sont propagées immédiatement au site web actif.

   ![](assets/eds-output-preset-config-tab.png){width="650" align="left"}

6. Sélectionnez **Enregistrer**, puis **Générer la sortie**.

>
>
> La sortie générée est stockée dans le dossier **docs** du référentiel EDS (Beta).

La sortie EDS (Beta) est maintenant générée. Le contenu est présenté dans une mise en page propre et réactive. Il comprend des éléments standard tels que le titre de la page, les chemins de navigation, le contenu du corps et les blocs utilisés dans la rubrique. La table des matières à gauche (générée à partir de la carte) vous permet de naviguer entre les rubriques, tandis qu’une mini-table des matières à droite met en surbrillance les sections de la page active. L’ensemble de la sortie est entièrement réactif, ce qui garantit une expérience de lecture optimisée et cohérente sur tous les appareils.

![](assets/eds-site-output.png){align="left"}

## Personnaliser la sortie à l’aide de blocs EDS

EDS utilise des `blocks` pour contrôler le style et l’affichage des différentes parties de votre contenu. Vous pouvez modifier des blocs existants ou en créer des personnalisés.

Les exemples présentés ci-dessous vous guident tout au long de la personnalisation d’un bloc existant et de la création d’un bloc pour appliquer un style à la sortie EDS (Beta) finale dans Experience Manager Guides.

### Personnaliser un bloc de chemin de navigation pour mettre à jour sa couleur de texte

Les chemins de navigation sont utilisés sur plusieurs pages pour aider les utilisateurs à comprendre où ils se trouvent dans la documentation. Comme ce bloc apparaît de manière cohérente sur l’ensemble du site web, la mise à jour de son style permet une mise à jour de conception unifiée.

Effectuez les étapes suivantes pour personnaliser un bloc de chemin de navigation pour mettre à jour sa couleur de texte :

1. Accédez à votre référentiel GitHub et ouvrez le dossier `blocks` .
2. Sélectionnez le bloc **chemin de navigation**.

   ![](assets/eds-breadcrumbs.png){width="650" align="left"}
3. Ouvrez le fichier `css` et mettez à jour la couleur du texte.
4. Validez les modifications dans GitHub.
5. Actualisez le site Web en ligne pour afficher les mises à jour.

### Mise à jour des scripts EDS (Beta) pour créer un élément personnalisé dans la sortie publiée

Dans certains cas, vous pouvez ne mettre en forme qu’une partie spécifique de votre contenu. Effectuez les étapes suivantes pour y parvenir à l’aide d’un bloc personnalisé.

1. Ouvrez le fichier de rubrique et sélectionnez le texte dans un élément de balise.

   Dans la capture d’écran suivante, le contenu à l’intérieur de la balise `example` est sélectionné.
   ![](assets/eds-example-tag-org-output.png){width="650" align="left"}
2. Pour configurer le texte dans la balise `example` :
   - Accédez à **Propriétés du contenu**.
   - Ajoutez l’attribut `outputclass` .
   - Définissez sa valeur sur `example eds-force-block`.
   - Sélectionnez **Ajouter**.
     ![](assets/eds-example-tag.png){width="650" align="left"}
3. Enregistrez et régénérez la sortie.
4. Créez un dossier portant le même nom que le `outputclass` dans le répertoire `blocks`. Découvrez comment [ajouter des fichiers à un référentiel](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository#adding-a-file-to-a-repository-using-the-command-line).

   ![](assets/eds-example-folder.png){width="650" align="left"}
5. Ajoutez les `css` requis et les fichiers `js` facultatifs.

   ![](assets/eds-example-folder-subfolders.png){width="650" align="left"}
6. Validez les modifications et régénérez la sortie.

Le contenu sélectionné affiche désormais le style personnalisé défini dans votre bloc.

![](assets/eds-example-output.png){width="650" align="left"}