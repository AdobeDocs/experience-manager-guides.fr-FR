---
title: Plug-in Oxygen pour Adobe Experience Manager Guides
description: Découvrez comment utiliser le plug-in Oxygen pour Adobe Experience Manager Guides afin de créer et de gérer votre contenu.
hide: true
exl-id: 9a140564-27eb-404e-93a5-f5c81364e7f7
feature: Oxygen Plugin, Authoring, Web Editor
role: User, Admin
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
workflow-type: tm+mt
source-wordcount: '6522'
ht-degree: 1%

---

# Plug-in Oxygen pour Adobe Experience Manager Guides {#id1645H6010Q5}

Le plug-in Oxygen pour Adobe Experience Manager Guides \(plus tard appelé plug-in Oxygen pour AEM Guides dans le guide\) vous permet de connecter l’auteur XML Oxygen au référentiel Adobe Experience Manager \(AEM\) pour la création et la gestion de contenu. Vous pouvez utiliser le plug-in pour parcourir, rechercher et ouvrir des fichiers, extraire et archiver des fichiers, charger des dossiers et des fichiers sur le référentiel AEM. Le panneau AEM Guides de l’application de bureau vous permet de marquer les dossiers souhaités \(du référentiel AEM\) vers la liste des dossiers favoris pour un accès rapide. De plus, vous pouvez installer un package dans l’interface web d’AEM et ouvrir vos fichiers DITA dans Oxygen XML Author directement depuis l’interface web d’AEM.

## Télécharger et installer {#id1826M0L0PUI}

Le module externe Oxygen pour AEM Guides est disponible via votre portail de distribution logicielle Adobe. Recherchez « oxygène » dans l’onglet Experience Manager, puis téléchargez le programme d’installation du plug-in depuis votre [portail de distribution de logiciels Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).

>[!NOTE]
>
>Vérifiez la compatibilité de la version du connecteur Oxygen dans les notes de mise à jour pour l’Adobe Experience Manager Guides spécifique.

Une fois que vous disposez du programme d’installation, installez-le sur votre ordinateur local où est installé Oxygen XML Author. Avant de commencer le processus d’installation, vous devez vous assurer que votre système répond aux exigences techniques d’installation du plug-in Oxygen pour AEM Guides.

### Exigences techniques

- Oxygen XML Author version 26.1

- Adobe Experience Manager Guides version 4.6 ou ultérieure

- Adobe Experience Manager version 6.5 avec pack de services 21, 20 et 19

- Système d&#39;exploitation pris en charge par Oxygen XML Author version 26.1

- Java Development Kit
   - Oracle SE 8 JRE 1.8

### Installation du plug-in sous Windows

>[!IMPORTANT]
>
>Si une ancienne version du plug-in est installée sur votre système, veillez à le désinstaller avant de lancer le processus d’installation. Pour obtenir des instructions de désinstallation **reportez-vous à la section** Désinstallation des packages de l’article [Comment utiliser les packages](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/package-manager.html).

Effectuez les étapes suivantes sur le système sur lequel Oxygen XML Author est installé :

1. Lancez le fichier `.exe` du programme d’installation.

   L’écran de bienvenue de l’assistant d’installation s’affiche.

1. Cliquez sur **Suivant** et accédez à l’emplacement où se trouve le fichier .exe Oxygen XML Author.

1. Sélectionnez le fichier, puis cliquez sur **Ouvrir**.

   L&#39;emplacement du fichier sélectionné est ajouté dans l&#39;assistant d&#39;installation.

1. Cliquez sur **Suivant**.

1. Cliquez sur **Installer**.

1. Cliquez sur **Terminer** pour fermer l’assistant d’installation.
1. Lancez Oxygen XML Author.

   Le panneau AEM Guides s’affiche dans l’instance de création XML Oxygen.

   ![Connecteur ](images/oxygen-aem-connector.png){width="800" align="left"}

   >[!NOTE]
   >
   >Si le panneau AEM Guides n’est pas visible, consultez les solutions de contournement disponibles dans la section de dépannage —[panneau AEM Guides manquant](#id192BH200ZAX).


### Installation du plug-in sur Mac

>[!IMPORTANT]
>
>Si une ancienne version du plug-in est installée sur votre système, veillez à le désinstaller avant de lancer le processus d’installation. Voir la section **Désinstallation des packages** dans l’article [Comment utiliser les packages](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/package-manager.html) pour obtenir des instructions de désinstallation.

Effectuez les étapes suivantes sur le système sur lequel Oxygen XML Author est installé :

1. Recherchez le fichier .dmg du plug-in sur votre système.

1. Double-cliquez sur le fichier .dmg pour ouvrir le contenu du fichier.

   Le fichier .dmg contient un dossier aem-connector-x.x et un fichier aem-connector-x.x-setup .

   >[!NOTE]
   >
   >x.x dans les noms de fichier est le numéro de version du plug-in.

1. Copiez le dossier aem-connector-x.x dans le dossier plugins de l’auteur XML Oxygen.
1. Double-cliquez sur le fichier aem-connector-x.x-setup pour lancer le programme d’installation.

1. Lancez Oxygen XML Author.

   Le panneau AEM Guides s’affiche dans l’instance de création XML Oxygen.

   ![Mac du connecteur AEM](images/oxygen-aem-connector-mac.png) {width="800" align="left"}

   >[!NOTE]
   >
   >Si le panneau AEM Guides n’est pas visible, consultez les solutions de contournement disponibles dans la section de dépannage —[panneau AEM Guides manquant](#id192BH200ZAX).


### Installez le package pour activer la fonctionnalité d’édition de documents depuis l’interface web d’AEM {#id182CE0Q0TY4}

En tant qu&#39;auteur, vous pouvez ouvrir et modifier vos plans ou rubriques DITA dans Oxygen XML Author directement à partir de l&#39;interface web d&#39;AEM. Pour activer cette fonctionnalité dans l’interface web d’AEM, votre administrateur AEM doit installer un package dans votre instance de création AEM.

En tant qu’administrateur AEM, procédez comme suit pour installer le package :

1. Récupérez le fichier .zip du package auprès de votre équipe informatique.
1. Connectez-vous à votre instance AEM *\(en tant qu’administrateur\)* puis accédez au gestionnaire de packages CRX. L’URL par défaut pour accéder au gestionnaire de packages est .

   `http://<server name>:<port>/crx/packmgr/index.jsp`

   Le gestionnaire de packages gère les packages sur votre installation AEM locale. Pour plus d’informations sur l’utilisation du gestionnaire de packages, consultez [ Utilisation des packages ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developer-tools/package-manager.html?lang=en) dans la documentation d’AEM.

   ![Gestionnaire de packages](images/package-manager.png) {width="650" align="left"}

1. Pour télécharger le package Oxygen, cliquez sur **Télécharger le package**.
1. Dans la boîte de dialogue Charger le package, accédez au fichier du package Oxygène que vous avez téléchargé à l’étape 1 et cliquez sur OK.

   Le package est chargé sur votre instance AEM.

1. Pour lancer le processus d’installation, cliquez sur **Installer**.

   ![Emballage d&#39;oxygène](images/oxygen-package.png){width="650" align="left"}

1. Dans la boîte de dialogue Installer le package , cliquez sur **Installer**.
1. Une fois l’installation terminée, cliquez sur le bouton Accueil dans le coin supérieur gauche du gestionnaire de packages CRX.
1. Sélectionnez un fichier DITA dans votre dossier de ressources.

   L’option **Modifier dans Oxygène** est disponible dans la barre d’outils. Pour plus d&#39;informations sur l&#39;utilisation de cette option, voir [Ouvrir la rubrique DITA dans Oxygen XML Author depuis l&#39;interface web d&#39;AEM](#id182CE0I905Z).

   >[!NOTE]
   >
   >L&#39;option **Modifier dans l&#39;oxygène** est visible lorsque vous sélectionnez une rubrique DITA. Si vous sélectionnez plusieurs rubriques, l’option n’est pas visible.


## Configuration du plug-in Oxygen pour AEM Guides {#id1826KF00AHS}

Après avoir téléchargé et installé le plug-in, vous devez configurer les éléments suivants pour qu’il fonctionne :

- **Paramètres d’authentification web** : paramètres d’authentification SSO dans le plug-in d’AEM Guides.
- **Paramètres généraux** : paramètres de connexion du plug-in, tels que l’URL du serveur AEM, les informations de connexion, etc.
- **Préférence pour la personnalisation des attributs de profilage et des noms de fichier dans les références croisées** : cette configuration est requise pour les schémas d’attributs de profilage des jeux de documentation.

### Paramètres d’authentification web

JxBrowser est utilisé pour l’authentification SSO par le plug-in du connecteur Oxygen. Il s’agit d’un navigateur au chrome. Pour Java 9+, l’accès aux API non publiques est requis et vous devez explicitement accorder cet accès à JxBrowser. Pour plus d’informations, voir [Dépannage de JxBrowser](https://jxbrowser-support.teamdev.com/docs/guides/troubleshooting/issues.html).

Mettez à jour les fichiers donnés pour configurer les paramètres d’authentification web dans le plug-in Oxygen pour AEM Guides :

>[!NOTE]
>
>Effectuez une sauvegarde du fichier avant de le mettre à jour.

**Pour Mac et Oxygène 26.1**

Ajoutez les lignes suivantes dans env.sh

```java
--illegal-access=permit\
--add-opens=java.desktop/javax.swing.plaf.basic=ALL-UNNAMED\
--add-exports=javafx.controls/com.sun.javafx.scene.control=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.javafx.stage=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.javafx.scene=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.javafx.scene.traversal=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.javafx.tk=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.glass.ui=ALL-UNNAMED\
--add-opens=javafx.graphics/com.sun.glass.ui=ALL-UNNAMED\
--add-opens=javafx.graphics/javafx.stage=ALL-UNNAMED\
--add-opens=javafx.graphics/com.sun.javafx.tk.quantum=ALL-UNNAMED\
--add-exports=java.desktop/sun.awt=ALL-UNNAMED\
--add-opens javafx.swing/javafx.embed.swing=ALL-UNNAMED
```

Ajoutez les lignes suivantes dans le fichier oxygenAuthor.sh

```java
-Djdk.module.illegalAccess=permit\-Djava.ipc.external=true\
```

**Pour Windows et Oxygen 26.1**

Ajoutez les lignes suivantes dans env.bat :

```java
--illegal-access=permit --add-opens=java.desktop/javax.swing.plaf.basic=ALL-UNNAMED --add-exports=javafx.controls/com.sun.javafx.scene.control=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.javafx.stage=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.javafx.scene=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.javafx.scene.traversal=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.javafx.tk=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.glass.ui=ALL-UNNAMED --add-opens=javafx.graphics/com.sun.glass.ui=ALL-UNNAMED --add-opens=javafx.graphics/javafx.stage=ALL-UNNAMED --add-opens=javafx.graphics/com.sun.javafx.tk.quantum=ALL-UNNAMED --add-exports=java.desktop/sun.awt=ALL-UNNAMED --add-opens javafx.swing/javafx.embed.swing=ALL-UNNAMED
```

Ajoutez les lignes suivantes dans le fichier oxygor.bat :

```java
-Djdk.module.illegalAccess=permit -Djava.ipc.external=true
```

>[!NOTE]
>
>Vous devez exécuter oxygène à partir de oxygenAuthor.sh pour Mac et oxygenAuthor.bat pour Windows en tant qu’administrateur.

### Paramètres généraux

Pour configurer les paramètres de connexion dans le plug-in Oxygen pour Adobe Experience Manager Guides, procédez comme suit :

1. Dans le panneau AEM Guides, cliquez sur l’icône des paramètres, puis sélectionnez **Paramètres**.

   ![Paramètres de connexion ](images/settings.png){width="800" align="left"}

1. Spécifiez les détails suivants :
   - **URL du serveur** : URL du serveur AEM, par exemple :

     ```http
     http[s]://<host>:<port>
     ```

     Dans l’URL ci-dessus, spécifiez le nom d’hôte et le port du serveur sur lequel le serveur AEM est déployé.

     >[!IMPORTANT]
     >
     >Si votre serveur AEM est déployé sur le port 80 ou 443, il n’est pas nécessaire de le spécifier dans l’URL.

   - **Authentification :** choisissez entre **Nom d’utilisateur/mot de passe de base\)** ou **Authentification web**. Si vous sélectionnez l’authentification **de base**, vous devez saisir le **nom d’utilisateur** et le **mot de passe** dans la boîte de dialogue Préférences.

     Si vous sélectionnez Authentification web, l’écran de connexion d’AEM s’affiche. Saisissez vos informations de connexion et cliquez sur le bouton **Se connecter**. Une fois la connexion établie, l’écran de connexion AEM se ferme et le panneau AEM Guides affiche la liste des fichiers du serveur AEM.

   - **Délai de connexion** : indiquez le délai, en secondes, pendant lequel le client attend une réponse du serveur AEM. Si aucune réponse du serveur n’est reçue dans le délai spécifié, la requête est interrompue. La valeur par défaut est de 20 secondes.

   - **Dossier local** : emplacement sur votre ordinateur local où les fichiers du référentiel AEM sont stockés après l’extraction. Si vous spécifiez un emplacement qui n’existe pas sur le lecteur, le plug-in crée cet emplacement.
   - **Ouvrir le fichier lors de l’extraction** : si cette option est sélectionnée, ouvre les fichiers lors de l’extraction.
   - **Fermer le fichier lors de l&#39;archivage** : si cette option est sélectionnée, les fichiers sont fermés lors de l&#39;archivage. Avant de fermer le fichier, un pop-up s’affiche et vous permet de spécifier les commentaires de version.
   - **Afficher la boîte de dialogue Archiver lors de la fermeture d’un fichier** : si cette option est sélectionnée, un pop-up s’affiche lors de la fermeture d’un fichier. Dans le pop-up, vous pouvez choisir d’archiver le fichier ou de fermer le fichier sans l’archiver.
   - **Extraction automatique du fichier à l’ouverture** : si cette option est sélectionnée, double-cliquer sur un fichier l’extrait automatiquement et l’ouvre pour le modifier. Si le fichier est déjà extrait, il est simplement ouvert pour être modifié. Si cette option n&#39;est pas sélectionnée, ouvrir un fichier sur lequel vous n&#39;avez pas de verrou l&#39;ouvre en mode lecture seule.
1. Cliquez sur **OK**.

### Préférence pour la personnalisation des attributs de profil et des noms de fichier dans les références croisées {#id1827K0D0OHT}

Vous devez configurer les préférences dans l’auteur XML Oxygen pour utiliser l’attribut de profilage associé aux rubriques DITA dans le référentiel AEM. Vous devez également configurer la préférence pour afficher les noms de fichier à la place des GUID dans les références croisées.

Pour configurer les attributs de profilage et les références croisées, procédez comme suit :

1. Dans Oxygen XML Author, cliquez sur **Options** \> **Préférences**.
1. Dans l&#39;onglet **Association de type de document**, sélectionnez **DITA**, puis cliquez sur **Étendre**.

   ![association de type de document](images/document_type_association.png){width="650" align="left"}

1. Dans l’onglet **Classpath**, sélectionnez `com.adobe.o2.connector` dans le menu déroulant **Utiliser le chargeur de classe parent à partir du plug-in avec ID**.

   ![Onglet Chemin d’accès de la classe](images/dita-extension.png){width="650" align="left"}

1. Dans l’onglet **Extensions**, effectuez les modifications suivantes :

   - Cliquez sur **Choisir** en regard du lot **Extensions** et sélectionnez `LinkResolverExtensionBundle - com.adobe.o2.framework.extn` dans la liste **Classe**. Cliquez sur **OK**.
     ![ Extension configurée pour les rubriques DITA ](images/dita-map-extenstion-link-resolve.png) {width="650" align="left"}
   - Cliquez sur **Choisir** en regard de l’**Listener d’état de l’extension de création** sous **Extensions individuelles** et sélectionnez `CustomAuthorExtensionStateListener - com.adobe.o2.framework.extn` dans la liste **Classe**. Cliquez sur **OK**.
   - Cliquez sur **Choisir** en regard de l’**Éditeur de valeur d’attribut personnalisé de création** sous **Extensions individuelles** et sélectionnez `CustomValueEditor - com.adobe.o2.framework.extn` dans la liste **Classe**. Cliquez sur **OK**.
   - Cliquez sur **Choisir** en regard du **Gestionnaire d’insertion d’objet externe de création** sous **Extensions individuelles** et sélectionnez `CustomURLInsertionHandler - com.adobe.o2.ui ` dans la liste **Classe**. Cliquez sur **OK**.


   La capture d&#39;écran suivante montre l&#39;onglet **Extension** configuré pour les rubriques DITA :
   <img src="images/dita-topic-extension-tab.png" alt="Extension configurée pour les rubriques DITA" width="650" border="2px">
1. Cliquez sur **OK** dans toutes les boîtes de dialogue pour enregistrer vos modifications.

### Configurer l&#39;extension DITA map

La configuration de l&#39;extension DITA map est requise pour permettre l&#39;ouverture des fichiers map dans Oxygen XML Author directement à partir de l&#39;interface web d&#39;AEM. Ces configurations sont similaires à celles des attributs de profilage effectuées dans la procédure précédente.

Effectuez les étapes suivantes pour configurer l&#39;extension de plan DITA :

1. Dans Oxygen XML Author, cliquez sur **Options** \> **Préférences**.
1. Dans l&#39;onglet **Association de type de document**, sélectionnez **DITA Map**, puis cliquez sur **Étendre**.
1. Dans l’onglet **Classpath**, sélectionnez com.adobe.o2.connector dans le menu déroulant **Utiliser le chargeur de classe parent à partir du plug-in avec ID**.
1. Dans l’onglet **Extensions**, effectuez les modifications suivantes :
   - Cliquez sur **Choisir** en regard du lot **Extensions** et sélectionnez `com.adobe.o2.framework.extn.LinkResolverDITAMapExtensionBundle` dans la liste **Classe**. Cliquez sur **OK**.

   - Cliquez sur **Choisir** en regard de l’**Listener d’état de l’extension de création** sous **Extensions individuelles** et sélectionnez `CustomDITAMapAuthorExtensionStateListener - com.adobe.o2.framework.extn` dans la liste **Classe**. Cliquez sur **OK**.

   - Cliquez sur **Choisir** en regard du **Gestionnaire d’insertion d’objet externe de création** sous **Extensions individuelles** et sélectionnez `CustomURLInsertionHandler - com.adobe.o2.ui ` dans la liste **Classe**. Cliquez sur **OK**.

   - Cliquez sur **Choisir** en regard de l’**Éditeur de valeur d’attribut personnalisé de création** sous **Extensions individuelles** et sélectionnez `CustomValueEditor - com.adobe.o2.framework.extn` dans la liste **Classe**. Cliquez sur **OK**.

   - Cliquez sur **Choisir** en regard du **Résolveur de références** sous **Extensions individuelles** et sélectionnez `CustomDITAMapReferenceResolver - com.adobe.o2` dans la liste **Classe**. Cliquez sur **OK**.
   - *\(Facultatif\)* Si vous ne souhaitez pas résoudre les références lors de l’ouverture d’un fichier de mappage, vous devez effectuer la configuration supplémentaire suivante :

   La capture d’écran suivante présente l’onglet **Extension** configuré :
   <img src="images/dita-map-extension-tab.png" alt="Extension configurée pour le mappage DITA" width="650" border="2px">

1. Cliquez sur **OK** dans toutes les boîtes de dialogue pour enregistrer vos modifications.

## Utilisation du plug-in Oxygen pour AEM Guides {#id1826JG00WY4}

### Panneau AEM Guides

L’écran suivant présente le panneau AEM Guides.

![panneau connecteur](images/connector-panel.png){width="550" align="left"}

**A**\) Affiche la barre de recherche.

**B**\) Affiche le dossier Favoris. Par défaut, il est vide. Vous pouvez ajouter des dossiers du référentiel AEM en tant que favoris. Les dossiers favoris sont ensuite affichés ici.

**C**\) Le dossier DAM affiche le référentiel AEM. Vous pouvez développer et réduire la vue du dossier.

**D**\) Icône Paramètres \(engrenage\) avec les options suivantes :

- **Connexion** : sélectionnez cette option pour vous connecter au serveur AEM. Cette option est désactivée lorsque l’auteur XML Oxygen est connecté au serveur AEM.
- **Actualiser** : sélectionnez cette option pour obtenir le dernier statut des fichiers et du dossier à partir du référentiel AEM.

  >[!NOTE]
  >
  >Veillez à enregistrer vos fichiers avant de les actualiser. Lorsque vous sélectionnez l’option **Actualiser**, un avertissement s’affiche pour vous permettre d’enregistrer vos fichiers avant de les actualiser. Si vous n’avez pas enregistré vos fichiers, vous pouvez cliquer sur **Annuler** et les enregistrer.

- **Paramètres** : vous pouvez utiliser cette option pour ouvrir la boîte de dialogue Préférences générales du module externe.
- **Déconnexion** : sélectionnez cette option pour fermer la connexion au serveur AEM. Cette option est disponible uniquement si vous utilisez le mode d’authentification Web.

### Fonctions du menu contextuel

Les fonctions du module externe Oxygen pour AEM Guides sont disponibles en cliquant avec le bouton droit sur un dossier ou un fichier dans le référentiel AEM. Les fonctions disponibles pour les dossiers sont différentes des fichiers. Voici la liste complète des fonctions du menu contextuel Plug-in Oxygen pour AEM Guides :

- **Ouvrir** : ouvre le fichier sélectionné ou développe le dossier sélectionné.
- **Ouvrir dans** : vous pouvez choisir d’ouvrir le fichier sélectionné dans l’éditeur web d’AEM Guides, dans le tableau de bord des cartes ou dans l’éditeur de cartes. Pour plus d’informations sur ces options, voir [ Ouvrir un fichier dans l’éditeur d’AEM Guides ](#id195GH0V30KX).
- **Extraire** : extrait un fichier du référentiel AEM. Pour plus d’informations, voir [Extraction de fichiers](#id195HC020TS4).
- **Extraction avec personnes à charge** : extrait un fichier avec ses références directes. Pour plus d’informations, voir [Extraction de fichiers](#id195HC020TS4).
- **Extraire avec des personnes à charge en lecture seule** : extrait le fichier sélectionné avec ses personnes à charge. Vous ne pouvez pas apporter de modifications aux fichiers dépendants. Pour plus d’informations, voir [Extraction de fichiers](#id195HC020TS4).
- **Annuler l’extraction** : annule le fichier extrait, ferme le fichier de l’éditeur et rétablit la dernière version du fichier enregistrée sur le serveur.
- **Actualiser** : dans le cas d’un fichier, récupère la dernière copie du fichier à partir du référentiel AEM. Pour un dossier, il récupère la structure du dossier et le statut du fichier. Cela signifie qu’un fichier est ajouté, puis il s’affiche dans la vue AEM Guides. En outre, si un fichier est extrait sur le serveur AEM, une actualisation dans l’auteur Oxygen affichera le fichier comme extrait. Toutefois, cela ne met pas à jour la liste des fichiers dans la vue *Fichiers extraits dans AEM Guides*.
- **Actualiser les fichiers extraits** : actualise la liste des fichiers extraits dans la vue *Fichiers extraits dans AEM Guides*. Si un fichier est extrait sur le serveur AEM, une actualisation met à jour la liste des fichiers extraits dans la vue *Fichiers extraits dans AEM Guides*. Cependant, si un nouveau fichier a été ajouté ou si l’état d’un fichier a changé, il ne le met pas à jour dans l’arborescence d’AEM Guides. Pour mettre à jour le statut des fichiers sur AEM, vous devez effectuer une actualisation.
- **Archiver** : consigne les fichiers que vous avez extraits. Pour plus d’informations, voir [ Archiver un fichier ](#id182CF0J0FHS).
- **Archivage avec personnes à charge** : si vous avez extrait des fichiers avec des personnes à charge, cette option intègre le fichier principal avec ses personnes à charge. Pour plus d’informations, voir [ Archiver un fichier ](#id182CF0J0FHS).
- **Créer un dossier** : permet de créer un dossier dans le référentiel AEM. Cette option est disponible uniquement au niveau du dossier.
- **Charger le(s) fichier(s)\)** : charge un ou plusieurs fichiers. Pour plus d’informations, voir [Charger des fichiers et des dossiers](#id195HC03F03J).
- **Charger avec personnes à charge** : charge les fichiers DITA \(XML, DITA, Book Map ou DITA map\) avec ses personnes à charge. Pour plus d’informations, voir [Charger des fichiers et des dossiers](#id195HC03F03J).
- **Charger le dossier** : charge un dossier sur le référentiel AEM. Pour plus d’informations, voir [Charger des fichiers et des dossiers](#id195HC03F03J).
- **Ajouter aux favoris** : ajoute un dossier au dossier *Favoris* dans le panneau AEM Guides. Il est recommandé d’ajouter votre dossier de travail ici, ce qui facilite la synchronisation des fichiers et du statut du fichier à partir d’AEM.
- **Supprimer des favoris** : supprime un dossier des *favoris*. Pour plus d’informations, voir [ Ajouter ou supprimer des favoris ](#id195HC04405P).
- **Afficher les métadonnées** : affiche les métadonnées telles que la classe DITA, le titre du document, le type, l&#39;UUID et d&#39;autres informations associées à un fichier. Pour plus d’informations, voir [Affichage des métadonnées d’un fichier](#id195GHN0H05C).
- **Afficher les versions** : affiche l’historique des versions d’un fichier. Pour plus d’informations, voir [Afficher l’historique des versions d’un fichier](#id195GI000D5Q).

### Ouvrez un fichier dans Oxygen XML Author {#id195GHJ0A0UB}

Une fois que vous êtes connecté au référentiel AEM, vous pouvez ouvrir des fichiers à modifier dans l’instance de création XML d’Oxygen. Effectuez les étapes suivantes pour ouvrir un fichier pour le modifier dans l’auteur XML Oxygen :

1. Dans le panneau AEM Guides, cliquez avec le bouton droit de la souris sur un fichier que vous souhaitez ouvrir pour le modifier.

1. Sélectionnez **Ouvrir** dans le menu contextuel. Vous pouvez également double-cliquer sur le fichier pour l’ouvrir.

   Le fichier est ouvert dans l’éditeur de l’auteur Oxygen XML.

   ![GUID dans l’onglet Fichier](images/guid-in-file-tab.png) {width="800" align="left"}

   Lorsque vous placez le pointeur de la souris sur l’onglet d’un fichier, le chemin d’accès au serveur et son UUID s’affichent. Dans la capture d’écran ci-dessus, l’UUID du document est mis en surbrillance.

>[!NOTE]
>
>Pointez sur les images ou les vidéos d’une rubrique dans l’éditeur de création XML d’oxygène pour afficher uniquement l’UUID de l’élément sélectionné. Pour le localiser dans le référentiel, cliquez avec le bouton droit de la souris sur l’image affichée ou sur la balise de l’objet (uniquement dans le cas de fichiers vidéo, audio et autres fichiers multimédias), puis sélectionnez **Afficher dans le référentiel**.



Si vous avez sélectionné l’option **Extraction automatique du fichier à l’ouverture** \(dans la boîte de dialogue Préférences\), lors de l’ouverture d’un fichier, ce dernier est automatiquement extrait et peut être modifié. Pour ouvrir un fichier, vous pouvez double-cliquer sur un nom de fichier ou cliquer avec le bouton droit de la souris sur le nom de fichier et choisir **Ouvrir** dans le menu contextuel. Si cette option n’est pas sélectionnée, le fichier est ouvert en mode lecture seule.


### Ouvrir le fichier dans l’éditeur d’AEM Guides {#id195GH0V30KX}

Si vous souhaitez utiliser les éditeurs disponibles dans AEM Guides, vous pouvez le faire en sélectionnant l&#39;option souhaitée dans le menu contextuel. Effectuez les étapes suivantes pour utiliser l’éditeur d’AEM Guides à la place de l’éditeur de création XML Oxygen :

1. Dans le panneau AEM Guides, cliquez avec le bouton droit de la souris sur un fichier que vous souhaitez ouvrir pour le modifier.

1. Sélectionnez **Ouvrir dans** dans le menu contextuel, puis choisissez l’une des options suivantes :

   - **Éditeur de rubriques web** : si le fichier que vous ouvrez est un fichier .xml ou .dita, vous pouvez l’ouvrir pour le modifier dans l’éditeur web. Choisissez l’option **Éditeur de rubriques web** pour ouvrir le fichier sélectionné afin de le modifier dans l’éditeur web.

   - **Map Dashboard** : vous pouvez choisir de modifier un fichier .ditamap dans le tableau de bord de mappage, où vous pouvez effectuer diverses opérations sur le fichier de mappage. Ces opérations dépendent du rôle/groupe auquel vous appartenez.

   - **Web DITA Map Editor** : si vous souhaitez ouvrir le fichier .ditamap pour le modifier dans l&#39;éditeur de carte, choisissez cette option. L&#39;option Éditeur de mappage DITA vous permet d&#39;ajouter ou de supprimer des rubriques, d&#39;ajouter des tables de relation et d&#39;effectuer d&#39;autres opérations sur votre mappage.


### Extraction de fichiers {#id195HC020TS4}

Lorsque vous extrayez un fichier, il est stocké localement sur votre système et verrouillé pour modification dans le référentiel AEM. Procédez comme suit pour extraire un fichier :

1. Vous pouvez extraire vos fichiers de l’une des manières suivantes :
   - Cliquez avec le bouton droit sur un fichier dans le panneau AEM Guides.
   - Cliquez avec le bouton droit de la souris sur l&#39;onglet Map dans le panneau DITA Maps Manager.
   - Cliquez avec le bouton droit de la souris sur un fichier dans le panneau DITA Maps Manager.
   - Cliquez avec le bouton droit sur l’onglet Fichier lorsque vous ouvrez une carte ou une rubrique dans l’éditeur.

1. Sélectionnez l’une des options suivantes :
   - **Extraire :** extrait un fichier du référentiel AEM et le rend disponible pour modification.
   - **Extraction avec personnes à charge** : extrait un fichier avec ses références directes. Cette option vous permet d’apporter des modifications aux pages parents et enfants. Le plug-in Oxygen pour AEM Guides prend en charge l’extraction d’un niveau de personnes à charge. Par exemple, Mappez A fait référence à la rubrique A et à la rubrique A fait référence à la rubrique B. La récupération de la carte A va récupérer la rubrique A, quel que soit son niveau dans la hiérarchie de la table des matières. Cependant, il ne va pas extraire le Topic B parce qu&#39;il n&#39;est pas directement lié à partir de la Map A.
   - **Extraire avec des personnes à charge en lecture seule** : extrait un fichier et télécharge ses personnes à charge sur votre ordinateur local en tant que copies en lecture seule. Vous ne pouvez pas apporter de modifications aux fichiers dépendants.

Si vous avez sélectionné l’option **Ouvrir les fichiers lors de l’extraction** \(dans la boîte de dialogue Préférences\), lors de l’extraction d’un fichier, celui-ci est automatiquement ouvert pour modification.

Si vous avez sélectionné l’option **Extraction automatique du fichier à l’ouverture** \(dans la boîte de dialogue Préférences\), le fichier est automatiquement extrait à l’ouverture et peut être modifié. Pour ouvrir un fichier, vous pouvez double-cliquer sur un nom de fichier ou cliquer avec le bouton droit de la souris sur le nom de fichier et choisir **Ouvrir** dans le menu contextuel.

Lorsqu’un fichier est extrait, son icône change et affiche son statut de verrouillage.

![Extraire un fichier](images/check-out-file.png){width="650" align="left"}

Dans la capture d’écran ci-dessus, un fichier extrait par un autre utilisateur s’affiche avec une icône de cadenas noire \(A\). Le fichier extrait par l&#39;utilisateur actuel s&#39;affiche avec un cadenas vert \(B\).

>[!NOTE]
>
>Si le fichier extrait est supprimé ou déplacé vers un autre dossier d’AEM, un message d’erreur s’affiche lorsque vous archivez le fichier. Assurez-vous que le fichier extrait n’est pas déplacé ou supprimé à l’aide de l’interface web d’AEM.

### Archiver un fichier {#id182CF0J0FHS}

Lorsque vous archivez un fichier, la copie locale de votre système est stockée dans le référentiel AEM et le verrouillage du fichier est supprimé. Procédez comme suit pour archiver un fichier :

1. Enregistrez votre fichier en cliquant sur **Fichier** \> **Enregistrer**.

1. Faites un clic droit sur un fichier extrait ou un mappage dans l’un des emplacements suivants :
   - Panneau AEM Guides
   - Panneau DITA Maps Manager
   - Onglet Fichier lorsque vous ouvrez une carte ou une rubrique dans l’éditeur.
   - Onglet Carte du panneau du gestionnaire de cartes DITA.

1. Choisissez l’une des deux options suivantes :

   - **Archiver** : enregistre le fichier sélectionné dans le référentiel AEM à partir de votre système local.
   - **Archivage avec personnes à charge :** si vous avez extrait un fichier avec ses personnes à charge, utilisez cette option pour archiver tous les fichiers dépendants en une seule opération. Lorsque vous sélectionnez cette option, la boîte de dialogue Archiver s&#39;affiche avec tous les fichiers dépendants. Cliquez sur OK pour archiver tous les fichiers à la fois.

   Si vous n&#39;avez pas extrait les fichiers dépendants, puis que vous choisissez cette option, seuls les fichiers dépendants que vous avez extraits \(séparément\) seront archivés. Une liste des fichiers qui n’ont pas pu être archivés s’affiche :

   ![erreurs d’archivage](images/check-in-error.png){width="800" align="left"}

   Il est vivement recommandé de ne pas déplacer un fichier extrait. Cependant, si un fichier extrait est déplacé vers un autre emplacement, vous devez annuler l’extraction de ce fichier. Si vous souhaitez effectuer des mises à jour sur ce fichier, extrayez à nouveau le fichier, apportez des modifications, puis réarchivez-le. Si vous essayez d’archiver un fichier qui a été déplacé depuis son emplacement d’origine, une erreur s’affiche.

   Si un fichier dépendant est extrait dans AEM, l&#39;option Archiver avec les personnes à charge n&#39;affiche pas le fichier dépendant dans la boîte de dialogue Archiver. Pour obtenir la liste des fichiers dépendants qui sont extraits dans AEM, vous devez effectuer une actualisation du dossier.

   De même, si vous avez archivé un fichier dépendant via AEM, la liste des fichiers n’est pas actualisée dans l’auteur Oxygen tant que vous n’avez pas effectué une actualisation des dossiers et des fichiers extraits. Si vous archivez avec des personnes à charge avec des fichiers archivés via AEM, une erreur s’affiche pour répertorier les fichiers qui n’ont pas pu être archivés.

1. \(Facultatif\) Dans la boîte de dialogue **Archiver** ou **Archiver avec personnes à charge**, ajoutez un commentaire dans la zone de texte **Commentaires de version**.

   >[!NOTE]
   >
   >Ce commentaire s’affiche dans l’historique des versions AEM du fichier.

1. Ajoutez un ou plusieurs libellés dans la zone de texte **Libellé** de la boîte de dialogue **Archiver** ou **Archiver avec les personnes à charge** . Saisissez un libellé, puis appuyez sur Entrée. Par exemple, version *2307*.

   Si votre administrateur a prédéfini une liste de libellés et les a chargés dans le fichier `label.json`, ces libellés s’affichent sous forme de liste déroulante. Vous pouvez choisir un ou plusieurs libellés dans la liste déroulante.

   ![Boîte de dialogue Archiver](images/checkin-dropdown-labels.png){width="550" align="left"}

   Vous pouvez ajouter plusieurs libellés (séparés par des virgules) à la même version d’une rubrique.  Par exemple, **, *AEM*, *Guides*.
Cependant, vous ne pouvez pas ajouter le même libellé aux différentes versions d’une rubrique. Si vous ajoutez une étiquette que vous avez déjà ajoutée à une version antérieure, elle est ajoutée à la dernière version et supprimée de la version antérieure.

   >[!NOTE]
   > 
   > Ces libellés s’affichent dans l’historique des versions AEM du fichier.


1. Cliquez sur **OK**.

>[!NOTE]
>
>Si le fichier extrait est supprimé ou déplacé vers un autre dossier d’AEM, un message d’erreur s’affiche lorsque vous archivez le fichier. Assurez-vous que le fichier extrait n’est pas déplacé ou supprimé à l’aide de l’interface web d’AEM.

### Fichiers extraits dans la vue AEM Guides

Lorsque vous avez dans plusieurs dossiers, il n’est pas facile de déterminer le nombre de fichiers à extraire dans une seule vue. AEM Guides fournit des fichiers extraits dans la vue AEM Guides qui donnent un instantané complet des fichiers actuellement extraits. Cette vue vous permet de déterminer facilement les fichiers que vous avez vérifiés dans le référentiel AEM à l’aide d’AEM Guides. Effectuez les étapes suivantes pour accéder à cette vue et l’utiliser :

1. Cliquez sur **Fenêtre** \> **Afficher** \> **Fichiers extraits dans AEM Guides**.

   Les fichiers extraits dans la vue AEM Guides s’affichent.

   ![fichiers extraits](images/files-checkedout-view.png){width="550" align="left"}

1. Cliquez avec le bouton droit de la souris sur un fichier dans cette vue pour obtenir les options suivantes :

   - [Ouvrir](#id195GH0V30KX)
   - [Ouvrir dans](#id195GH0V30KX)
   - Annuler l’extraction
   - [Archiver](#id182CF0J0FHS)
   - [Archivage avec des personnes à charge](#id182CF0J0FHS)
   - [Afficher les métadonnées](#id195GHN0H05C)
   - [Afficher les versions](#id195GI000D5Q)

**Notes sur les fichiers extraits dans la vue AEM Guides :**

- La vue *Fichiers extraits dans AEM Guides* conserve les sessions des utilisateurs. Cela signifie que les fichiers extraits par l’utilisateur actuel sont stockés et conservés dans la vue sur toutes les sessions du même utilisateur \(ou cache\).

- Si l’utilisateur modifie les informations d’identification de connexion du serveur AEM, les données du fichier extrait \(ou du cache\) dans la vue sont réinitialisées. L’utilisateur doit exécuter manuellement une commande *Actualiser les fichiers extraits* sur chaque dossier à partir duquel les fichiers ont été extraits précédemment. Pour simplifier, il est recommandé d’ajouter vos dossiers de travail aux *Favoris* à partir desquels vous pouvez rapidement actualiser le dossier.

- Vous pouvez trier la liste des fichiers en fonction de leur nom de fichier, de leur titre ou de leur chemin d’accès. Si un nouveau fichier est extrait, il apparaît dans l&#39;ordre de tri dans la vue.


### Chargement de fichiers et de dossiers {#id195HC03F03J}

Effectuez les étapes suivantes pour charger des fichiers ou des dossiers :

1. Cliquez avec le bouton droit sur un dossier dans le panneau AEM Guides.
1. Sélectionnez l’une des options suivantes :
   - **Charger le(s) fichier(s)\)** : sélectionnez cette option pour charger un ou plusieurs fichiers dans le dossier sélectionné dans le référentiel AEM. Dans la boîte de dialogue Sélectionner les fichiers \(s\) à charger, sélectionnez les fichiers et cliquez sur **Ouvrir**.
   - **Télécharger avec personnes à charge** : sélectionnez cette option pour télécharger un fichier DITA avec ses personnes à charge. Dans la boîte de dialogue Sélectionner le fichier à charger, sélectionnez les fichiers et cliquez sur **Ouvrir**.
   - **Charger le dossier** : sélectionnez cette option pour charger un dossier dans le référentiel AEM. Dans la boîte de dialogue Choisir, sélectionnez le dossier et cliquez sur **Choisir**.

**Remarques supplémentaires sur l’utilisation des fichiers basés sur UUID** :

Lors du déplacement ou de la copie de contenu de votre système local vers le référentiel AEM, tenez compte des points suivants :

- Lors du chargement d&#39;un ou plusieurs fichiers, un nouvel UUID est généré pour les fichiers sans UUID. Cet UUID est ajouté dans le `topic id` d&#39;un fichier DITA.

- Lors de la copie d&#39;un dossier, les références aux fichiers \(dans le dossier\) sont automatiquement mises à jour dans tous les plans DITA référençant des fichiers dans ce dossier.

- Lors de la copie d&#39;un fichier de mappage DITA, les références UUID contenues dans le fichier de mappage ne sont pas modifiées.

- Si un fichier ou un dossier est en conflit ou en double, un nom de fichier unique est généré pour le nouveau fichier copié ou déplacé.

- Deux fichiers ne peuvent pas avoir le même UUID. Un UUID unique est affecté à tous les nouveaux fichiers.

- Si un fichier est chargé par deux utilisateurs différents en même temps, le fichier qui est traité ultérieurement remplace le fichier précédent. Toutefois, une telle pratique devrait être évitée.

- Lorsque vous extrayez du contenu du référentiel AEM et que vous apportez des modifications à votre système local, assurez-vous que le nom du fichier n’est pas modifié au moment du chargement du fichier.

- Lorsque vous insérez une référence dans le gestionnaire de plans DITA ou l&#39;éditeur, il affiche le titre du fichier et non l&#39;UUID. Si le titre n’est pas présent, il affiche le nom du fichier.

### Ajouter ou supprimer des favoris {#id195HC04405P}

Pour ajouter ou supprimer un dossier dans le dossier Favoris du panneau AEM Guides, procédez comme suit :

- Cliquez avec le bouton droit sur un dossier et sélectionnez **Ajouter aux favoris**. Vous pouvez ajouter un dossier aux favoris s’il ne figure pas dans les favoris.
- Vous pouvez supprimer un dossier des favoris des manières suivantes :
   - Cliquez avec le bouton droit sur un dossier dans le dossier **Favoris** et sélectionnez **Supprimer des favoris**.
   - Cliquez avec le bouton droit sur un dossier déjà ajouté en tant que favori dans le référentiel AEM sous **DAM** et sélectionnez **Supprimer des favoris**.

### Affichage de l’historique des versions d’un fichier {#id195GI000D5Q}

Pour afficher l’historique des versions d’un fichier, procédez comme suit :

1. Cliquez avec le bouton droit de la souris sur un fichier dans le panneau AEM Guides.

1. Sélectionnez **Afficher les versions** dans le menu contextuel.

   L’historique des versions du fichier s’affiche dans la boîte de dialogue Versions .

   ![ Historique des versions ](images/version-history.png){width="550" align="left"}


### Affichage des métadonnées d’un fichier {#id195GHN0H05C}

Pour afficher les métadonnées d’un fichier, procédez comme suit :

1. Cliquez avec le bouton droit de la souris sur un fichier dans le panneau AEM Guides.

1. Sélectionnez **Afficher les métadonnées** dans le menu contextuel.

   Les métadonnées du fichier telles que la classe DITA, l&#39;état du document, la date de modification, la taille, le titre et l&#39;UUID s&#39;affichent dans la boîte de dialogue Métadonnées.

   ![Affichage des métadonnées](images/metadata.png){width="550" align="left"}


## Recherche d’une rubrique dans le référentiel AEM {#id1826J20405Z}

Vous pouvez rechercher des rubriques dans le référentiel AEM à l’aide de la barre de recherche du panneau AEM Guides. Vous pouvez effectuer une recherche dans l’ensemble du dossier DAM ou sélectionner un dossier, puis rechercher une rubrique dans ce dossier. Le résultat de la recherche affiche les rubriques dont le texte correspond à votre requête.

Pour rechercher des rubriques, procédez comme suit :

1. Dans le référentiel AEM, sélectionnez le dossier dans lequel vous souhaitez rechercher une rubrique.
1. Saisissez la requête de recherche \(par exemple, `introduction`\) dans la barre de recherche du plug-in Oxygen pour AEM Guides.
1. Cliquez sur le bouton de recherche ou appuyez sur Entrée.

   Le résultat s’affiche dans l’onglet Résultats de la recherche sous la forme d’une liste avec le chemin d’accès au fichier. S’il n’existe aucun résultat correspondant à votre requête, Aucun résultat trouvé dans le message &lt;chemin du dossier sélectionné\> ne s’affiche.

   ![Résultats de la recherche](images/search.png){width="550" align="left"}

1. \(Facultatif\) Double-cliquez sur un fichier dans les résultats de recherche pour l’ouvrir dans Oxygen XML Author.
1. Pour revenir à la vue Référentiel AEM, effectuez l’une des opérations suivantes :
   - Pour afficher la vue du référentiel AEM sans effacer les résultats de la recherche, cliquez sur l’onglet **Parcourir**.
   - Pour effacer les résultats de la recherche et afficher le référentiel AEM, cliquez sur l’icône Supprimer la recherche .

## Ouvrez la rubrique DITA dans Oxygen XML Author à partir de l’interface web d’AEM. {#id182CE0I905Z}

Vous pouvez ouvrir et modifier votre rubrique DITA dans Oxygen XML Author à partir de l&#39;interface web d&#39;AEM. Vous devez installer un package dans AEM pour activer cette option. Pour plus d’informations sur l’installation du package, voir [Installer le package pour activer la fonctionnalité d’édition de documents à partir de l’interface web d’AEM](#id182CE0Q0TY4).

>[!NOTE]
>
>L&#39;option **Modifier dans l&#39;oxygène** est accessible à partir de différents emplacements dans AEM : lorsqu&#39;une rubrique est sélectionnée, lorsqu&#39;une rubrique est prévisualisée ou depuis l&#39;onglet Rubriques et rapports de la console Plan DITA. Si vous sélectionnez plusieurs rubriques, l’option n’est pas visible dans la barre d’outils.

**Ouvrir une rubrique DITA**

Effectuez les étapes suivantes pour ouvrir une rubrique DITA dans Oxygen XML Author :

1. Sélectionnez une rubrique dans vos ressources et cliquez sur l’option **Modifier dans Oxygène** dans la barre d’outils.

   >[!NOTE]
   >
   >Si la rubrique n&#39;est pas extraite, elle est d&#39;abord extraite, puis ouverte dans Oxygen en mode édition.

1. Sélectionnez Oxygen XML Author *&lt;version\>* dans la zone de message **Lancer l’application**. Vous pouvez sélectionner l’option **Mémoriser mon choix pour les liens AEM** pour enregistrer vos préférences.

**Modifier une rubrique DITA**

Pour modifier une rubrique DITA dans Oxygen XML Author, procédez comme suit :

1. Sélectionnez et extrayez une rubrique dans vos ressources.
1. Cliquez sur l’option **Modifier dans Oxygène** dans la barre d’outils.

   >[!NOTE]
   >
   >Si la rubrique n&#39;est pas extraite, elle est d&#39;abord extraite, puis ouverte dans Oxygen en mode édition.

1. Sélectionnez Oxygen XML Author *&lt;version\>* dans la zone de message **Lancer l’application**. Vous pouvez sélectionner l’option **Mémoriser mon choix pour les liens AEM** pour enregistrer vos préférences.
1. Modifiez la rubrique dans Oxygen XML Author.
1. Consultez la rubrique à partir du plug-in Oxygen pour AEM Guides.

   Pour plus d’informations sur l’archivage d’une rubrique à l’aide du plug-in Oxygen pour AEM Guides, voir [Archiver un fichier](#id182CF0J0FHS).

   >[!NOTE]
   >
   >Veillez à archiver la rubrique à l’aide du module externe Oxygen pour AEM Guides. Si vous archivez à partir de l’interface web d’AEM, les modifications que vous apportez dans l’auteur XML Oxygen ne sont pas enregistrées dans la version archivée de la rubrique.

**Insérer une référence à une rubrique à partir du référentiel Experience Manager Guides**

Vous pouvez également faire glisser et déposer une rubrique pour insérer la référence dans une rubrique ou un plan DITA.
>[!NOTE]
>
> Vous devez extraire un fichier avant d&#39;y ajouter toute référence.

Les éléments suivants sont ajoutés en fonction du type de références :

Si vous faites glisser vers l’éditeur une rubrique ouverte :
- Une référence est ajoutée avec `<image>` élément pour les images.
- Un élément d’objet est ajouté pour une vidéo ou un fichier audio.
- L’élément `<xref>` est ajouté pour toutes les autres références telles que topic, map, DITAVAL, PDF, ZIP et XML.

Si vous accédez à l&#39;éditeur ou au gestionnaire de plans DITA avec un plan ouvert :
- L&#39;élément `<mapref>` est ajouté pour les références de mappage, qui incluent un mappage DITA, un bookmap ou un schéma d&#39;objet.
- L’élément `<topicref>` est ajouté pour toutes les autres références telles que topic, map, DITAVAL, PDF, ZIP et XML.


## Utilisation de profils d’attributs {#id1827JA002YK}

AEM Guides vous permet de créer et d&#39;associer facilement des attributs conditionnels à l&#39;aide des attributs DITA appropriés. Vous pouvez définir des attributs conditionnels au niveau global ou au niveau du dossier. Les conditions définies globalement sont visibles dans tous les projets et les conditions au niveau du dossier ne sont visibles que dans les projets créés dans le dossier spécifié. Les auteurs de contenu peuvent utiliser ces attributs conditionnels pour conditionner le contenu de leurs rubriques ou mappages DITA qu&#39;ils créent ou utilisent. Pour en savoir plus sur la création d’attributs conditionnels dans AEM à l’aide d’AEM Guides, consultez la section *Configurer des attributs conditionnels pour les profils globaux ou au niveau du dossier* dans Installation et configuration d’Adobe Experience Manager Guides.

>[!NOTE]
>
>Assurez-vous d’avoir ajouté les attributs conditionnels dans AEM et défini [Préférence pour la personnalisation des attributs de profil](#id1827K0D0OHT) avant d’ajouter des attributs conditionnels à votre contenu.

Effectuez les étapes suivantes pour ajouter des attributs conditionnels à votre contenu dans l’instance de création XML Oxygen :

1. Consultez et ouvrez une rubrique à partir du *module externe Oxygen pour AEM Guides*.
1. Sélectionnez la partie du contenu à laquelle vous souhaitez appliquer les attributs conditionnels.
1. Double-cliquez sur l’attribut conditionnel dans le panneau Attributs de l’auteur XML Oxygen.

   ![panneau attributs](images/attribute-panel.png){width="300" align="left"}

1. Dans la colonne **Disponible** de la boîte de dialogue Modifier l’attribut , sélectionnez le ou les attributs\(s\), puis cliquez sur **Ajouter**.

   L’écran suivant affiche les attributs `audience`.

   ![ Boîte de dialogue Modifier les attributs ](images/edit-attributes.png){width="550" align="left"}

1. Cliquez sur **OK**.

   Les attributs sont ajoutés au contenu.


## Résolution des problèmes courants {#id188ABC00RY4}

Cette rubrique couvre certains des problèmes les plus courants auxquels vous pouvez être confronté lorsque vous utilisez le plug-in, ainsi que leurs solutions.

### Panneau AEM Guides manquant {#id192BH200ZAX}

**Problème** - Si le panneau AEM Guides n’est pas visible dans l’instance de création XML d’oxygène, essayez les solutions suivantes :

Solution 1 :

1. Dans Oxygen XML Author, activez le plug-in .

   Cliquez sur **Options** \> **Préférences** \> **Modules externes** et sélectionnez **Module externe Oxygen pour Adobe Experience Manager Guides.**

1. Relancez Oxygen XML Author.


Solution 2 :

1. Si le panneau AEM Guides n’apparaît toujours pas, activez la fenêtre AEM Guides .

   Dans l’auteur XML Oxygen, cliquez sur **Fenêtre** \> **Afficher la vue** \> **AEM Guides**.

Solution 3 :

1. Désinstallez et réinstallez le plug-in Oxygen pour Adobe Experience Manager Guides.

   - Sous Windows, désinstallez le plug-in de la liste **Ajouter ou supprimer des programmes**. Réinstallez ensuite le plug-in .

   - Sur Mac, accédez au dossier aem-connector-x.x dans le dossier plugins de l’auteur XML Oxygen et déplacez-le vers **Corbeille**. Ensuite, videz le dossier **Trash**.


### Configurer le port pour la transformation DITA-OT

**Problème** - Lorsque vous exécutez une transformation DITA-OT sur des fichiers traités par le module externe, la transformation échoue avec l’erreur suivante :

![Erreur d’échec de la transformation DITA-OT](images/proxy-server-path-error-new.png){width="800" align="left"}

**Solution** - Ce problème a été corrigé en ajoutant un serveur proxy entre DITA-OT et le plug-in. Ce serveur proxy traite et partage tous les fichiers demandés par DITA-OT pour les transformations. Le port par défaut sur lequel ce serveur a été configuré est : `5972`. Si vous utilisez ce port pour un autre serveur, vous pouvez spécifier un autre port pour le serveur proxy.

Effectuez les étapes suivantes pour modifier le port par défaut du serveur proxy :

1. Accédez au répertoire racine \(user&#39;s\).
1. Créez un fichier nommé aem\_connector\_proxy.
1. Ouvrez le fichier dans n’importe quel éditeur de texte et ajoutez un numéro de port disponible dans la première ligne du fichier.
1. Enregistrez et fermez le fichier.
1. Redémarrez Oxygen XML Author et exécutez la transformation DITA-OT.


### Le panneau AEM Guides ne recherche pas l’emplacement du fichier ouvert

Problème : lorsque vous choisissez d’ouvrir un fichier en vue de le modifier dans Oxygen XML Author à partir du serveur AEM, le fichier est ouvert en vue de le modifier dans Oxygen XML Author. Toutefois, le panneau AEM Guides n’affiche pas l’emplacement du fichier dans l’arborescence de navigation.

Solution : ce problème a été observé dans des scénarios où le chemin d’accès au fichier contient /content/dam deux fois. Par défaut, toutes les ressources d’AEM sont stockées dans le dossier /content/dam . Si vous téléchargez ou créez une structure de dossiers contenant également /content/dam, ce problème est observé. Vous pouvez effectuer toutes les opérations normales sur ces fichiers, mais leur emplacement dans l’arborescence de navigation n’est pas affiché par défaut. Pour accéder à ce fichier dans l’arborescence de navigation, vous devez accéder manuellement à l’emplacement du fichier. Notez que dans l’arborescence de navigation, le chemin d’accès /content/dam en double est remplacé par /content/assets.

### Configuration de la journalisation

Problème : par défaut, le plug-in Oxygen pour AEM Guides ne génère aucun journal, ce qui rend difficile le débogage des scénarios d’erreur.

Solution : Effectuez les étapes suivantes pour configurer les enregistreurs pour Oxygen et JxBrowser :

1. Fermer Oxygen XML Author

1. Créez un fichier nommé `logback.xml` avec le contenu suivant :

   ```xml
   <configuration>
       <appender name="R2" class="ch.qos.logback.core.rolling.RollingFileAppender">
           <file>${user.home}/Desktop/oxygenLog/oxygen.log</file>
           <rollingPolicy class="ch.qos.logback.core.rolling.FixedWindowRollingPolicy">
               <fileNamePattern>${user.home}/Desktop/oxygenLog/oxygen%i.log.gz</fileNamePattern>
               <minIndex>1</minIndex>
               <maxIndex>20</maxIndex>
           </rollingPolicy>
           <triggeringPolicy class="ch.qos.logback.core.rolling.SizeBasedTriggeringPolicy">
               <maxFileSize>100MB</maxFileSize>
           </triggeringPolicy>
           <encoder>
               <pattern>%r %marker %p [ %t ] %c - %m%n</pattern>
           </encoder>
       </appender> 
   
       <root level="debug">
           <appender-ref ref="R2" />
       </root>
   </configuration>   
   ```

1. Enregistrez le fichier dans le répertoire `Oxygen Author 26`. (Par exemple, le chemin serait : `C:\Program Files\Oxygen XML Author 26\logback.xml`)

1. Fermez le fichier . Cela activera les journaux oXygen, qui seront disponibles au chemin : `${user.home}/Desktop/oxygenLog/oxygen.log`
1. Ouvrez le fichier `oxygenAuthor.bat` dans un éditeur de texte.
1. Configurez les journaux liés à JxBrowser en ajoutant le paramètre .
   `-Denable.aem.jx.log=true`. Cela active les journaux liés à JxBrowser, que vous pouvez afficher au chemin : `${user.home}\AppData\Local\Temp\Oxygen_Plugin_Javax_Log.log` :




   ```java
   SET OXYGEN_JAVA=java.exe
   if exist "%JAVA_HOME%\bin\java.exe" set OXYGEN_JAVA="%JAVA_HOME%\bin\java.exe"
   if exist "%~dp0\jre\bin\java.exe" SET OXYGEN_JAVA="%~dp0\jre\bin\java.exe"
   rem Set environment variables
   call "%~dp0\env.bat"
   %OXYGEN_JAVA% -XX:-OmitStackTraceInFastThrow -XX:SoftRefLRUPolicyMSPerMB=10 -Djdk.module.illegalAccess=permit -Djava.ipc.external=true 
   -Denable.aem.jx.log=true -Dsun.java2d.noddraw=true -Dsun.awt.nopixfmt=true -Dsun.java2d.dpiaware=true -Dsun.io.useCanonCaches=true -Dsun.io.useCanonPrefixCache=true 
   -Dsun.awt.keepWorkingSetOnMinimize=true -Dcom.oxygenxml.app.descriptor=ro.sync.exml.AuthorFrameDescriptor
    -Dcom.oxygenxml.ApplicationDataFolder="%APPDATA%" -cp %CP% ro.sync.exml.Oxygen %*
   ```


Avec les étapes précédentes, les journaux seront activés et vous pourrez les utiliser pour déboguer les problèmes.
