---
title: Utilisation de la spécialisation DITA-OT et DITA personnalisée
description: Découvrez comment utiliser la spécialisation DITA-OT et DITA personnalisée
exl-id: 4d3e0fc1-b684-44f9-ab0d-411033024019
feature: DITA-OT Configuration
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1700'
ht-degree: 0%

---

# Utilisation de la spécialisation DITA-OT et DITA personnalisée {#id181GAJ0005Z}

DITA Open Toolkit \(DITA-OT\) est un ensemble d&#39;outils open source basés sur Java qui assurent le traitement des cartes DITA et du contenu des rubriques. AEM Guides vous permet d’importer et d’utiliser facilement des modules externes DITA-OT personnalisés. Une fois importé, AEM Guides peut être configuré pour utiliser le plug-in DITA-OT personnalisé afin de générer une sortie dans n’importe quel format. Au moment de générer la sortie, sélectionnez simplement l’option DITA-OT pour que l’AEM Guides utilise le plug-in DITA-OT personnalisé pour générer la sortie requise.

Si vous souhaitez traiter des paramètres Ant lors de la publication d’une sortie, AEM Guides vous offre un moyen facile de le faire. Vous pouvez spécifier les paramètres Ant à utiliser, et ceux-ci sont ensuite traités par le processus de publication.

>[!NOTE]
>
> AEM Guides est fourni avec la version 3.3.2 de DITA-OT, mais il prend en charge un large éventail de versions, de DITA-OT 1.7 à DITA-OT 4.x. Pour obtenir la liste complète des versions DITA-OT, voir [versions DITA-OT](http://www.dita-ot.org/download).

>[!TIP]
>
> Voir les sections *Configuration des profils DITA-OT* et *Utilisation de DITA-OT* personnalisés dans le guide des bonnes pratiques pour connaître les bonnes pratiques relatives à l&#39;utilisation de plug-ins DITA-OT personnalisés.

## Utilisation de modules externes DITA-OT personnalisés {#id181NH1020L7}

Vous pouvez utiliser le plug-in DITA-OT personnalisé pour la publication en chargeant le plug-in DITA-OT personnalisé dans le référentiel AEM. Par défaut, AEM Guides s’accompagne d’un profil préconfiguré qui contient les configurations des modèles par défaut à utiliser pour la modification et la publication de contenu. Vous pouvez créer des profils personnalisés avec des modèles personnalisés à utiliser lors de l&#39;édition de documents et des plug-ins DITA-OT personnalisés pour publier du contenu.

Le package DITA-OT par défaut disponible avec AEM Guides est fourni avec le processeur Apache FOP XSL-FO, qui ne prend pas en charge le rendu des équations de MathML. Si vous utilisez des équations MathML dans votre contenu, assurez-vous d’avoir intégré un module externe de moteur de rendu MathML pour Apache FOP ou utilisez un autre processeur XSL-FO.

Pour charger le plug-in DITA-OT personnalisé dans le référentiel AEM, procédez comme suit :

1. Téléchargez le fichier DITA-OT.zip à partir du lien partagé dans l’e-mail de bienvenue.

1. Extrayez le contenu du fichier zip sur votre système.

1. Utilisez un mécanisme d&#39;intégration de module externe DITA-OT pour intégrer la nouvelle version de DITA-OT à votre module externe DITA-OT personnalisé.

1. Créez à nouveau le fichier ZIP en conservant le même nom \(`DITA-OT.ZIP`\) et la structure de dossiers.

1. Chargez à nouveau le fichier ZIP mis à jour dans le référentiel AEM.

   Vérifiez les points suivants avant de charger le fichier ZIP :

   - Exécutez l’intégrateur \(pour installer le plug-in personnalisé\) sur un système d’exploitation Mac/Linux afin d’éviter tout problème lié aux séparateurs de fichiers. Étant donné que les systèmes d’exploitation Windows et Linux ont des séparateurs de fichiers différents, le plug-in intégré sur le système d’exploitation Mac/Linux est compatible avec les configurations Windows et Linux.
   - Assurez-vous que le fichier `DITA-OT.ZIP` contient un dossier nommé « DITA-OT » qui contient tous les modules externes et fichiers appropriés.
   - Vérifiez que `DITA-OT.ZIP` fichier que vous créez est de type mime : « nt:file » \(cela correspond au type principal du fichier ZIP lors du téléchargement sur AEM\). Utilisez un outil WebDAV ou un déploiement de code pour charger ce fichier ZIP vers le chemin d’accès souhaité dans AEM. \(N’utilisez pas le gestionnaire de packages AEM pour déployer ce fichier ZIP, car ce fichier ZIP n’est pas un package de contenu AEM, mais simplement un fichier d’archive.\)

   >[!NOTE]
   >
   > Il est recommandé de ne pas remplacer le package DITA-OT par défaut. Vous devez charger votre package DITA-OT personnalisé contenant votre dossier /var/dxml/dita\_resources/dita-ot de plug-in. Vous pouvez également le faire à l’aide du pipeline Cloud Manager. Voir [Déploiement vers AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=fr) dans la documentation d’AEM pour plus d’informations.

1. Vous pouvez choisir de modifier le profil par défaut, de créer un nouveau profil ou de dupliquer les paramètres du profil par défaut pour créer un nouveau profil.

   >[!NOTE]
   >
   > Vous pouvez mettre à jour le profil par défaut, mais vous ne pouvez pas le supprimer. Cependant, tous les nouveaux profils que vous créez peuvent être modifiés et supprimés.

1. Configurez les propriétés suivantes pour utiliser le plug-in DITA-OT personnalisé :

   | Nom de la propriété | Description |
   |-------------|-----------|
   | **Propriétés du profil** |  |
   | Nom du profil | Attribuez un nom unique à ce profil. |
   | Réutiliser la sortie | *\(Facultatif\)* Si votre profil est basé sur un profil existant, sélectionnez cette option. La sélection de cette option garantit qu&#39;AEM Guides n&#39;extrait pas à nouveau le contenu du package DITA-OT et réutilise le package DITA-OT existant. |
   | Chemin d’extraction du profil | *\(Facultatif\)* spécifiez le chemin d’accès où DITA-OT est conservé sur le disque. Par défaut, AEM Guides regroupe un package DITA-OT dans son référentiel et il est extrait sur le disque à cet emplacement. <br> **REMARQUE** vous pouvez définir ce chemin à l’aide de n’importe quelle variable ou propriété système existante. Pour plus d’informations, voir la description de la propriété [Variables d’environnement DITA-OT](#id181NH0YN0AX). |
   | Chemin affecté | \(*Facultatif*\) Spécifiez le chemin d’accès dans votre référentiel de contenu auquel ce profil s’applique. Vous pouvez spécifier plusieurs emplacements. |
   | **Propriétés DITA-OT** |  |
   | Délai DITA-OT | \(*Facultatif*\) Spécifiez la durée \(en secondes\) pendant laquelle AEM Guides attend une réponse du plug-in DITA-OT. Si aucune réponse n’est reçue dans le délai spécifié, AEM Guides met fin à la tâche de publication et celle-ci est marquée comme ayant échoué. En outre, les journaux d’échec sont disponibles dans le fichier journal de génération de sortie. <br> Valeur par défaut : 300 secondes \(5 minutes\) |
   | Arguments PDF DITA-OT | Spécifiez les arguments de ligne de commande qui sont traités par le plug-in DITA-OT personnalisé pour générer la sortie PDF. Pour tous les profils DITA-OT personnalisés, spécifiez l&#39;argument de ligne de commande suivant :`-lib plugins/org.dita.pdf2.fop/lib/` |
   | Arguments AEM DITA-OT | \(*Facultatif*\) Spécifiez les arguments de ligne de commande personnalisés qui sont traités par le plug-in DITA-OT personnalisé pour générer la sortie du site AEM. |
   | Chemins d&#39;accès à la bibliothèque DITA-OT | \(*Facultatif*\) Spécifiez les chemins de bibliothèque supplémentaires du module externe DITA-OT. |
   | DITA-TO Build XML | \(*Facultatif*\) Spécifiez le chemin d’accès du script de build Ant personnalisé fourni avec le plug-in DITA-OT personnalisé. Ce chemin d&#39;accès est relatif au répertoire DITA-OT de votre système de fichiers. |
   | Dossier de script Ant DITA-OT | \(Facultatif\) Spécifiez le chemin d’accès du dossier de script Ant DITA-OT. Ce chemin d&#39;accès est relatif au répertoire DITA-OT de votre système de fichiers. |
   | Variables d&#39;environnement DITA-OT | *\(Facultatif\)* Spécifiez les variables d&#39;environnement à transmettre au processus DITA-OT. Par défaut, AEM Guides ajoute quatre variables : `ANT_OPTS`, `ANT_HOME`, `PATH` et `CLASSPATH`. <br> Vous pouvez réutiliser n’importe quelle variable ou propriété d’environnement système existante pour créer de nouvelles variables d’environnement. Par exemple, si `JAVA_HOME` variable système est définie dans votre système et que vous souhaitez définir une nouvelle variable d’environnement appelée `JAVA_BIN` qui est créée à l’aide de `JAVA_HOME`. Vous pouvez ensuite ajouter la définition de `JAVA_BIN` en tant que :`JAVA_BIN= ${JAVA_HOME}/bin` <br> **Remarque :** vous pouvez également utiliser les propriétés système Java pour créer des variables d’environnement. Par exemple, si le script de démarrage AEM définit une propriété système Java `java.io.tmpdir` à un répertoire temporaire, vous pouvez utiliser cette propriété pour définir une nouvelle variable en tant que : `${java.io.tmpdir}/fmdita/dita_ot`. <br> **Important :** pour réutiliser une variable ou une propriété système existante, celle-ci doit être placée entre `${}`. |
   | Remplacer la sortie DITA-OT | Choisissez si la sortie DITA-OT doit être remplacée. Gardez cette option sélectionnée. |
   | Chemin d’accès ZIP DITA-OT AEM | Indiquez le chemin d’accès complet où le fichier DITA-OT.zip personnalisé est stocké dans votre référentiel AEM. |
   | Chemin d&#39;accès du module externe DITA-OT | Chemin d’accès du plug-in personnalisé. Ce plug-in est automatiquement intégré au package DITA-OT principal. |
   | Intégration de catalogues | \(*Facultatif*\) Chemin d’accès aux fichiers Catalogue.xml DTD et XSD personnalisés dans le référentiel AEM. Cela ne doit être fourni que lorsque les catalogues sont absents du package DITA-OT. Ces catalogues sont automatiquement intégrés au DITA-OT principal sous la forme d&#39;un plug-in. |
   | Ajouter un catalogue d’ID système | \(*Facultatif*\) Sélectionnez cette option uniquement s’il manque des entrées d’ID public dans le catalogue ou si les fichiers DITA utilisent uniquement les ID système relatifs au chemin d’accès au serveur à partir duquel ils sont chargés. |
   | Chemin temporaire DITA-OT | Emplacement temporaire où les fichiers DITA sont copiés pour traitement. Avant que DITA-OT traite les fichiers, ils sont copiés à cet emplacement temporaire. Par défaut, l’emplacement de stockage temporaire est : <br> `<*AEM-Install*>/crx-quickstart/profiles/ditamaps` <br> **Important :** vous ne devez pas modifier le chemin d’accès par défaut. |

   >[!NOTE]
   >
   > Le programme d’installation d’AEM Guides crée deux variables d’environnement que vous pouvez utiliser pour spécifier le chemin d’accès des fichiers du plug-in DITA-OT personnalisés. Ces variables d&#39;environnement sont les suivantes : `DITAOT\_DIR`, qui contient le chemin du répertoire DITA-OT sur le système de fichiers, et `DITAMAP\_DIR`, qui contient le chemin d&#39;extraction du contenu du plan DITA sur le système de fichiers.

1. Cliquez sur **Terminé** pour enregistrer le profil.


## Intégrer la spécialisation DITA {#id211MB0E00XA}

La spécialisation DITA est le processus de création de nouvelles structures DITA par l&#39;ajout de nouveaux éléments ou la suppression d&#39;éléments existants. Pour créer un élément DITA, vous pouvez prendre un élément DITA existant comme base et le modifier en fonction de vos besoins de création. En substance, la spécialisation DITA vous permet de créer des modèles d&#39;informations personnalisés qui répondent aux besoins de votre entreprise tout en conservant les avantages de l&#39;architecture DITA existante.

Vous pouvez utiliser la fonction Profil pour stocker les paramètres personnalisés de spécialisation DITA. Ces paramètres peuvent ensuite être utilisés au moment de la création et de la publication de contenu DITA personnalisé. AEM Guides vous permet d’utiliser l’ID public et l’ID système dans vos DTD/XSD personnalisés.

>[!NOTE]
>
> L’éditeur web d’AEM Guides ne prend pas en charge les schémas XSD.

Pour créer un profil et le configurer afin d’utiliser des DTD et des fichiers XSD spécialisés dans votre AEM Guides, procédez comme suit :

1. Créez un dossier de spécialisation sur votre ordinateur local qui contient les DTD et les fichiers XSD spécialisés.

1. Spécifiez les détails de la DTD dans le fichier `catalog.xml` qui doivent également être inclus dans le dossier de spécialisation.

   >[!NOTE]
   >
   > Dans le cas de DITA 1.3, l&#39;emplacement par défaut du fichier DTD `catalog.xml` dans le référentiel AEM est : `/libs/fmdita/dita_resources/DITA-1.3/dtd/catalog.xml`.

1. Spécifiez les détails du schéma XSD dans le fichier `catalog.xml` qui doivent également être inclus dans le dossier de spécialisation.

   >[!NOTE]
   >
   > Dans le cas de DITA 1.3, l’emplacement par défaut du fichier XSD catalog.xml dans le référentiel AEM est : `/libs/fmdita/dita_resources/DITA-1.3/xsd/catalog.xml`.

1. Chargez le dossier à l’emplacement suivant :

   `/var/dxml/dita_resources`

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils.

1. Cliquez sur la mosaïque **Profils DITA**.

1. Vous pouvez choisir de modifier le profil par défaut, de créer un nouveau profil ou de dupliquer les paramètres du profil par défaut pour créer un nouveau profil.

   >[!NOTE]
   >
   > Vous ne pouvez pas supprimer le profil par défaut. Cependant, tous les nouveaux profils que vous créez peuvent être modifiés et supprimés.

1. Dans les paramètres **Schéma** \> **Catalogue**, spécifiez le chemin d’accès aux fichiers `catalog.xml` DTD et XSD personnalisés dans votre référentiel AEM.

1. Sélectionnez l’option **Ajouter un catalogue d’identifiants système**.

   >[!NOTE]
   >
   > Sélectionnez cette option uniquement s&#39;il manque des entrées d&#39;ID public dans le catalogue ou si les fichiers DITA utilisent uniquement les ID système relatifs au chemin d&#39;accès local du fichier à partir duquel ils sont chargés.

   Pour plus d&#39;informations sur les autres propriétés de la page Profils, reportez-vous au tableau des propriétés à l&#39;[étape 6](#id17A9F0D075Z) de la section [Utilisation de modules externes DITA-OT personnalisés](#id181NH1020L7).

1. Cliquez sur **Terminé** pour enregistrer le profil.
