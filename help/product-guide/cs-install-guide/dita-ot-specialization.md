---
title: Utilisation de la spécialisation DITA-OT et DITA personnalisée
description: Découvrez comment utiliser la spécialisation DITA-OT et DITA personnalisée
exl-id: 4d3e0fc1-b684-44f9-ab0d-411033024019
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1697'
ht-degree: 0%

---

# Utilisation de la spécialisation DITA-OT et DITA personnalisée {#id181GAJ0005Z}

Le DITA Open Toolkit \(DITA-OT\) est un ensemble d’outils Java Open Source qui fournissent le traitement des mappages DITA et du contenu des rubriques. AEM Guides vous permet d’importer et d’utiliser facilement des modules externes DITA-OT personnalisés. Une fois importés, AEM Guides peuvent être configurés pour utiliser le plug-in DITA-OT personnalisé pour générer une sortie dans n’importe quel format. Au moment de générer la sortie, sélectionnez simplement l’option DITA-OT et les AEM Guides utilisent le module externe DITA-OT personnalisé pour générer la sortie requise.

Si vous souhaitez traiter les paramètres Ant lors de la publication d’une sortie, AEM Guides vous permet de le faire facilement. Vous pouvez spécifier les paramètres Ant que vous souhaitez utiliser et les mêmes paramètres sont ensuite traités par le processus de publication.

>[!NOTE]
>
> AEM Guides est fourni avec la version 3.3.2 de DITA-OT. Toutefois, AEM Guides prend en charge DITA-OT version 1.7 et ultérieure. Pour obtenir la liste complète des versions de DITA-OT, voir [Versions DITA-OT](http://www.dita-ot.org/download).

>[!TIP]
>
> Voir *Configuration des profils DITA-OT* et *Utilisation de DITA-OT personnalisé* des sections du guide Bonnes pratiques pour connaître les bonnes pratiques relatives à l’utilisation des modules externes DITA-OT personnalisés.

## Utilisation des modules externes DITA-OT personnalisés {#id181NH1020L7}

Vous pouvez utiliser le module externe DITA-OT personnalisé pour la publication en chargeant le module externe DITA-OT personnalisé dans le référentiel AEM. Par défaut, AEM Guides est fourni avec un profil préconfiguré qui contient les configurations des modèles par défaut à utiliser pour la modification et la publication de contenu. Vous pouvez créer des profils personnalisés avec des modèles personnalisés à utiliser lors de la modification de documents et de modules externes DITA-OT personnalisés pour publier du contenu.

Le package DITA-OT par défaut disponible avec AEM Guides est fourni avec le processeur Apache FOP XSL-FO, qui ne prend pas en charge le rendu des équations MathML. Si vous utilisez des équations MathML dans votre contenu, assurez-vous d’avoir intégré un module externe de moteur de rendu MathML pour Apache FOP ou d’utiliser un autre processeur XSL-FO.

Effectuez les étapes suivantes pour charger le module externe DITA-OT personnalisé dans le référentiel AEM :

1. Téléchargez le fichier DITA-OT.zip à partir du lien partagé dans l’e-mail de bienvenue.

1. Extrayez le contenu du fichier zip sur votre système.

1. Utilisez un mécanisme d’intégration de module externe DITA-OT pour intégrer la nouvelle version de DITA-OT à votre module externe DITA-OT personnalisé.

1. Créez à nouveau le fichier ZIP en conservant le même nom \(`DITA-OT.ZIP`\) et la structure de dossiers.

1. Téléchargez à nouveau le fichier ZIP mis à jour dans le référentiel AEM.

   Vérifiez les vérifications suivantes avant de télécharger le fichier ZIP :

   - Exécutez l’intégrateur \(pour installer le module externe personnalisé\) sur un système d’exploitation Mac/Linux afin d’éviter des problèmes de séparateurs de fichiers. Comme Windows et Linux OS ont des séparateurs de fichiers différents, le module externe intégré à Mac/Linux OS est compatible avec la configuration de Windows et Linux.
   - Assurez-vous que la variable `DITA-OT.ZIP` contient un dossier nommé &quot;DITA-OT&quot; qui contient tous les modules externes et fichiers appropriés.
   - Vérifiez que `DITA-OT.ZIP` Le fichier que vous créez est de type mime : &quot;nt:file&quot; \(il correspond au type principal du fichier ZIP lors de son téléchargement vers AEM\). Utilisez un outil WebDAV ou un déploiement de code pour télécharger ce fichier ZIP vers le chemin d’accès souhaité dans AEM. \(N’utilisez pas AEM gestionnaire de packages pour déployer ce fichier ZIP, car ce fichier ZIP n’est pas un module de contenu AEM mais simplement un fichier d’archive.\)

   >[!NOTE]
   >
   > Il est recommandé de ne pas remplacer le package DITA-OT par défaut. Vous devez charger votre package DITA-OT personnalisé contenant votre dossier /var/dxml/dita\_resources/dita-ot . Vous pouvez également le faire à l’aide du pipeline Cloud Manager, voir [Déploiement sur AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=fr) dans la documentation d’AEM pour plus d’informations.

1. Vous pouvez choisir de modifier le profil par défaut, de créer un nouveau profil ou de dupliquer les paramètres du profil par défaut pour créer un nouveau profil.

   >[!NOTE]
   >
   > Vous pouvez mettre à jour le profil par défaut, mais vous ne pouvez pas le supprimer. Cependant, tous les nouveaux profils que vous créez peuvent être modifiés et supprimés.

1. Configurez les propriétés suivantes pour utiliser le module externe DITA-OT personnalisé :

   | Nom de la propriété | Description |
   |-------------|-----------|
   | **Propriétés du profil** |
   | Nom du profil | Attribuez un nom unique à ce profil. |
   | Réutiliser la sortie | *\(Facultatif\)* Si votre profil est basé sur un profil existant, sélectionnez cette option. Si vous sélectionnez cette option, AEM Guides n’extrait pas à nouveau le contenu du module DITA-OT et réutilise le module DITA-OT existant. |
   | Chemin d’extraction de profil | *\(Facultatif\)* Spécifiez le chemin d’accès où DITA-OT est conservé sur le disque. Par défaut, AEM Guides regroupe un package DITA-OT dans son référentiel et il est extrait sur le disque à l’emplacement suivant. <br> **REMARQUE** Vous pouvez définir ce chemin à l’aide de n’importe quelle variable ou propriété système existante. Voir la description de [Variables d’environnement DITA-OT](#id181NH0YN0AX) pour plus d’informations. |
   | Chemin attribué | \(*Facultatif*\) Spécifiez le chemin d’accès dans votre référentiel de contenu pour lequel ce profil est applicable. Vous pouvez spécifier plusieurs emplacements. |
   | **Propriétés DITA-OT** |
   | Délai d’expiration DITA-OT | \(*Facultatif*\) Spécifiez l’heure \(en secondes\) pendant laquelle les Guides d’AEM attendent une réponse du module externe DITA-OT. Si aucune réponse n’est reçue à l’heure indiquée, AEM Guides interrompt la tâche de publication et la tâche est marquée comme en échec. En outre, les logs d’échec sont rendus disponibles dans le fichier journal de génération de sortie. <br> Valeur par défaut : 300 secondes \(5 minutes\) |
   | Arguments du PDF DITA-OT | Spécifiez les arguments de ligne de commande qui sont traités par le module externe DITA-OT personnalisé pour générer la sortie du PDF. Pour tous les profils DITA-OT personnalisés, spécifiez l’argument de ligne de commande suivant :`-lib plugins/org.dita.pdf2.fop/lib/` |
   | Arguments AEM DITA-OT | \(*Facultatif*\) Spécifiez les arguments de ligne de commande personnalisés qui sont traités par le plug-in DITA-OT personnalisé pour générer la sortie Site AEM. |
   | Chemins de la bibliothèque DITA-OT | \(*Facultatif*\) Spécifiez les chemins d’accès aux bibliothèques supplémentaires du module externe DITA-OT. |
   | XML de création DITA-OT | \(*Facultatif*\) Spécifiez le chemin d’accès du script de génération Ant personnalisé fourni avec le module externe DITA-OT personnalisé. Ce chemin d’accès est relatif au répertoire DITA-OT de votre système de fichiers. |
   | Dossier de script Ant DITA-OT | \(Facultatif\) Spécifiez le chemin d’accès du dossier de script Ant DITA-OT. Ce chemin d’accès est relatif au répertoire DITA-OT de votre système de fichiers. |
   | Variables d’environnement DITA-OT | *\(Facultatif\)* Spécifiez les variables d’environnement à transmettre au processus DITA-OT. Par défaut, les AEM Guides ajoutent quatre variables : `ANT_OPTS`, `ANT_HOME`, `PATH`, et `CLASSPATH`. <br> Vous pouvez réutiliser n’importe laquelle des variables ou propriétés d’environnement système existantes pour créer de nouvelles variables d’environnement. Par exemple, si vous avez `JAVA_HOME` variable système définie dans votre système et que vous souhaitez définir une nouvelle variable d’environnement appelée `JAVA_BIN` qui est créé à l’aide de `JAVA_HOME`. Vous pouvez ensuite ajouter la définition de `JAVA_BIN` en tant que :`JAVA_BIN= ${JAVA_HOME}/bin` <br> **Remarque :** Vous pouvez également utiliser les propriétés du système Java pour créer des variables d’environnement. Par exemple, si AEM script de démarrage définit une propriété système Java `java.io.tmpdir` dans un répertoire temporaire, vous pouvez utiliser cette propriété pour définir la nouvelle variable comme suit : `${java.io.tmpdir}/fmdita/dita_ot`. <br> **Important :** Pour réutiliser une variable ou une propriété système existante, elle doit être incluse dans `${}`. |
   | Remplacer la sortie DITA-OT | Indiquez si la sortie DITA-OT doit être écrasée. Conservez cette option sélectionnée. |
   | AEM chemin du fichier zip DITA-OT | Spécifiez le chemin d’accès complet où le fichier DITA-OT.zip personnalisé est stocké dans votre référentiel AEM. |
   | Chemin du module externe DITA-OT | Chemin d’accès du plug-in personnalisé. Ce module externe est automatiquement intégré au module DITA-OT principal. |
   | Intégration de catalogues | \(*Facultatif*\) Chemin des fichiers DTD et XSD catalog.xml personnalisés dans le référentiel AEM. Cela ne doit être fourni que lorsque les catalogues sont manquants dans le package DITA-OT. Ces catalogues sont automatiquement intégrés avec le DITA-OT principal en tant que module externe. |
   | Ajout d’un catalogue d’identifiants système | \(*Facultatif*\) Sélectionnez cette option uniquement s’il manque des entrées d’ID public dans le catalogue ou si les fichiers DITA utilisent uniquement les ID système relatifs au chemin d’accès au serveur à partir duquel ils sont chargés. |
   | Chemin temporaire DITA-OT | Emplacement temporaire où les fichiers DITA sont copiés pour traitement. Avant que DITA-OT ne traite les fichiers, ils sont copiés à cet emplacement temporaire. Par défaut, l’emplacement de stockage temporaire est le suivant : <br> `<*AEM-Install*>/crx-quickstart/profiles/ditamaps` <br> **Important :** Vous ne devez pas modifier le chemin par défaut. |

   >[!NOTE]
   >
   > Le programme d’installation d’AEM Guides crée deux variables d’environnement que vous pouvez utiliser pour spécifier le chemin d’accès des fichiers de module externe DITA-OT personnalisés. Ces variables d’environnement sont les suivantes : `DITAOT\_DIR`, qui contient le chemin du répertoire DITA-OT sur le système de fichiers ; et `DITAMAP\_DIR`, qui contient le chemin d’accès où le contenu de la carte DITA est extrait sur le système de fichiers.

1. Cliquez sur **Terminé** pour enregistrer le profil.


## Intégration de la spécialisation DITA {#id211MB0E00XA}

La spécialisation DITA est le processus de création de structures DITA en ajoutant de nouveaux éléments ou en supprimant des éléments existants. Pour créer un élément DITA, vous pouvez prendre un élément DITA existant comme base et le modifier selon vos besoins de création. Essentiellement, la spécialisation DITA vous permet de créer des modèles d’informations personnalisés qui répondent aux besoins de votre entreprise tout en conservant les avantages de l’architecture DITA existante.

Vous pouvez utiliser la fonction Profil pour stocker des paramètres de spécialisation DITA personnalisés. Ces paramètres peuvent ensuite être utilisés au moment de la création et de la publication de contenu DITA personnalisé. AEM Guides vous permet d’utiliser l’ID public et l’ID système dans vos DTD/XSD personnalisés.

>[!NOTE]
>
> AEM Guides Web Editor ne prend pas en charge les schémas XSD.

Effectuez les étapes suivantes pour créer un nouveau profil et le configurer afin d’utiliser des DTD et des XSD spécialisés dans vos guides d’AEM :

1. Créez sur votre ordinateur local un dossier de spécialisation contenant les DTD et les XSD spécialisés.

1. Indiquez les détails de la DTD dans la variable `catalog.xml` qui doit également être inclus dans le dossier de spécialisation.

   >[!NOTE]
   >
   > Dans le cas de DITA 1.3, l’emplacement par défaut pour DTD `catalog.xml` dans le référentiel AEM est : `/libs/fmdita/dita_resources/DITA-1.3/dtd/catalog.xml`.

1. Spécifiez les détails du schéma XSD dans la variable `catalog.xml` qui doit également être inclus dans le dossier de spécialisation.

   >[!NOTE]
   >
   > Dans le cas de DITA 1.3, l’emplacement par défaut du fichier XSD catalog.xml dans le référentiel AEM est : `/libs/fmdita/dita_resources/DITA-1.3/xsd/catalog.xml`.

1. Téléchargez le dossier à l’emplacement suivant :

   `/var/dxml/dita_resources`

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et choisissez **Outils**.

1. Sélectionner **Guides** dans la liste des outils.

1. Cliquez sur le bouton **Profils DITA** mosaïque.

1. Vous pouvez choisir de modifier le profil par défaut, de créer un nouveau profil ou de dupliquer les paramètres du profil par défaut pour créer un nouveau profil.

   >[!NOTE]
   >
   > Vous ne pouvez pas supprimer le profil par défaut. Cependant, tous les nouveaux profils que vous créez peuvent être modifiés et supprimés.

1. Dans le **Schéma** \> **Catalogue** , spécifiez le chemin d’accès des fichiers DTD et XSD personnalisés. `catalog.xml` dans votre référentiel AEM.

1. Sélectionnez la variable **Ajout d’un catalogue d’identifiants système** .

   >[!NOTE]
   >
   > Sélectionnez cette option uniquement s’il manque des entrées d’ID public dans le catalogue ou si les fichiers DITA utilisent uniquement les ID système relatifs au chemin d’accès au fichier local à partir duquel ils sont chargés.

   Pour plus d’informations sur les autres propriétés de la page Profils , voir le tableau des propriétés dans [Étape 6](#id17A9F0D075Z) de [Utilisation des modules externes DITA-OT personnalisés](#id181NH1020L7) .

1. Cliquez sur **Terminé** pour enregistrer le profil.
