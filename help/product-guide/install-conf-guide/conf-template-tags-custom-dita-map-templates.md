---
title: Configurer un modèle de plan DITA personnalisé
description: Découvrez comment configurer un modèle de plan DITA personnalisé
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 1%

---

# Configurer un modèle de plan DITA personnalisé {#id1774F04F05Z}

AEM Guides est fourni avec deux modèles de carte prêts à l&#39;emploi : DITA map et Bookmap. Vous pouvez créer des mappages basés sur ces modèles ou définir vos propres modèles de mappage qui peuvent ensuite être utilisés pour créer de nouveaux mappages.

Les onglets suivants fournissent des instructions pour configurer un modèle de plan DITA personnalisé en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.


>[!BEGINTABS]

>[!TAB Tab]

Pour ajouter vos modèles de carte personnalisés, procédez comme suit :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Dans l’interface utilisateur d’Assets, accédez au dossier configuré pour stocker les fichiers de modèle de mappage. Par défaut, tous les modèles de mappage sont stockés dans le dossier /content/dam/dita-templates/maps.

   >[!NOTE]
   >
   > Pour configurer un emplacement personnalisé afin de stocker des modèles de rubrique ou de mappage, consultez [Configurer le chemin d&#39;accès au dossier de modèles DITA personnalisés](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1. Cliquez sur **Créer** \> **Modèle DITA**.

1. Sur la page Plan directeur, sélectionnez le type de modèle de carte que vous souhaitez créer.

   >[!NOTE]
   >
   > Vous pouvez utiliser le modèle Carte ou Carte des signets comme base de votre nouveau modèle.

1. Cliquez sur **Suivant**.

1. Sur la nouvelle page Propriétés du modèle, saisissez un **Titre** et un **Nom** pour le modèle.

   >[!NOTE]
   >
   > Le nom est automatiquement suggéré en fonction du Titre de votre modèle. Si vous souhaitez spécifier le nom manuellement, assurez-vous que le Nom ne contient pas d&#39;espaces, d&#39;apostrophe ou de crochets et se termine par .ditamap.

1. Cliquez sur **Créer**.

>[!TAB  On-Premise ]

Pour ajouter vos modèles de carte personnalisés, procédez comme suit :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Dans l’interface utilisateur d’Assets, accédez au dossier configuré pour stocker les fichiers de modèle de mappage. Par défaut, tous les modèles de mappage sont stockés dans le dossier /content/dam/dita-templates/maps.

   >[!NOTE]
   >
   > Pour configurer un emplacement personnalisé afin de stocker des modèles de rubrique ou de mappage, consultez [Configurer le chemin d&#39;accès au dossier de modèles DITA personnalisés](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1. Cliquez sur **Créer** \> **Modèle DITA**.

1. Sur la page Plan directeur, sélectionnez le type de modèle de carte que vous souhaitez créer.

   >[!NOTE]
   >
   > Vous pouvez utiliser le modèle Carte ou Carte des signets comme base de votre nouveau modèle.

1. Cliquez sur **Suivant**.

1. Sur la nouvelle page Propriétés du modèle, saisissez un **Titre** et un **Nom** pour le modèle.

   >[!NOTE]
   >
   > Le nom est automatiquement suggéré en fonction du Titre de votre modèle. Si vous souhaitez spécifier le nom manuellement, assurez-vous que le Nom ne contient pas d&#39;espaces, d&#39;apostrophe ou de crochets et se termine par .ditamap.

1. Cliquez sur **Créer**.

>[!ENDTABS]

Le message Mappage créé s’affiche.

    Vous pouvez choisir d’ouvrir le modèle pour le modifier dans l’éditeur de cartes ou d’enregistrer le fichier de modèle à l’emplacement du magasin de modèles. Une fois le modèle créé, vous pouvez utiliser l’éditeur de cartes pour le personnaliser en fonction de vos besoins de création. Une fois qu’un modèle est en place, veillez à l’associer à un profil global ou au niveau du dossier.


La prochaine fois que vous créerez une nouvelle carte, votre modèle s’affichera dans la page Plan directeur. Pour plus d&#39;informations sur la création d&#39;un plan DITA, reportez-vous au *Utilisation d&#39;Adobe Experience Manager Guides*.

>[!TIP]
>
> Voir la section *Modèles personnalisés* dans le guide des bonnes pratiques pour connaître les bonnes pratiques relatives à l’utilisation de modèles de carte personnalisés.


## Personnaliser le nombre de références dans un plan DITA (uniquement pour Cloud Service)

Vous pouvez configurer le seuil du traitement asynchrone en fonction du nombre de références dans le plan DITA. Par défaut, les mappages comportant plus de 5 références seront créés par le biais d&#39;opérations asynchrones, tandis que les mappages comportant moins de références continueront à utiliser des opérations synchrones.

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les informations suivantes (propriété) pour spécifier le nombre de références dans le modèle de mappage DITA afin de maintenir le processus synchrone :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| com.adobe.fmdita.xmleditor.config.XmlEditorConfig | xmleditor.asyncmapcreation | > 0 <br> **Valeur par défaut** : 5 |

Lors de la création d&#39;un plan DITA avec des références de sujet volumineuses à l&#39;aide d&#39;un modèle personnalisé, la création du plan échoue sur le serveur cloud si le temps de traitement total dépasse 60 secondes.

Pour éviter cela, configurez **création asynchrone de plan DITA** dans XmlEditorConfig qui permet aux tâches de s&#39;exécuter en parallèle et de réduire les temps de traitement pour les plans DITA plus volumineux.


**Rubrique parente :** [Configuration des modèles de rubrique et de mappage](conf-template-tags.md)
