---
title: Configuration du modèle de mappage DITA personnalisé
description: Découvrez comment configurer le modèle de mappage DITA personnalisé
exl-id: a0eeb43c-06e4-4922-a005-704e8929063f
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 83971ee35a19cf0146ddd034b1ae7a345f587663
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 1%

---

# Configuration du modèle de mappage DITA personnalisé {#id1774F04F05Z}

AEM Guides est fourni avec deux modèles de mappage prêts à l’emploi : carte DITA et carte des livres. Vous pouvez créer des cartes à partir de ces modèles ou définir vos propres modèles de carte qui pourront ensuite être utilisés pour créer de nouvelles cartes.

Effectuez les étapes suivantes pour ajouter vos modèles de mappage personnalisés :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Dans l’interface utilisateur d’Assets, accédez au dossier configuré pour stocker les fichiers de modèle de carte. Par défaut, tous les modèles de mappage sont stockés dans le dossier /content/dam/dita-templates/maps .

   >[!NOTE]
   >
   > Pour configurer un emplacement personnalisé pour stocker des modèles de rubrique ou de mappage, voir [&#x200B; Configuration du chemin d’accès au dossier de modèle DITA personnalisé](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1. Cliquez sur **Créer** \> **Modèle DITA**.

1. Sur la page Plan directeur, sélectionnez le type de modèle de carte que vous souhaitez créer.

   >[!NOTE]
   >
   > Vous pouvez utiliser le modèle de carte ou de carte-livre comme base de votre nouveau modèle.

1. Cliquez sur **Suivant**.

1. Sur la nouvelle page Propriétés du modèle, saisissez un **Titre** et un **Nom** pour le modèle.

   >[!NOTE]
   >
   > Le nom est automatiquement proposé en fonction du titre de votre modèle. Si vous souhaitez spécifier manuellement le nom, assurez-vous que le nom ne contient aucun espace, apostrophe ou accolades et qu’il se termine par .ditamap.

1. Cliquez sur **Créer**.

   Le message Mapper créé s’affiche.

   Vous pouvez choisir d’ouvrir le modèle à modifier dans l’éditeur de mappage ou d’enregistrer le fichier de modèle à l’emplacement de la boutique de modèles. Une fois le modèle créé, vous pouvez utiliser l’éditeur de cartes pour le personnaliser selon vos besoins de création. Une fois qu’un modèle est en place, veillez à l’associer à un profil global ou de niveau dossier.


La prochaine fois que vous créerez une carte, votre modèle s’affichera dans la page Plan directeur. Pour plus d’informations sur la création d’un mappage DITA, consultez le guide Utilisation de l’as a Cloud Service Adobe Experience Manager Guides .

>[!TIP]
>
> Voir la section *Modèles personnalisés* du guide Bonnes pratiques pour connaître les bonnes pratiques relatives à l’utilisation de modèles de mappage personnalisés.


## Personnalisation du nombre de références dans un mappage DITA

Vous pouvez configurer le seuil du traitement asynchrone en fonction du nombre de références dans la carte DITA. Par défaut, les cartes avec plus de 5 références seront créées par le biais d’opérations asynchrones, tandis que les cartes avec moins de références continueront à utiliser des opérations synchrones.


Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails (propriété) suivants pour spécifier le nombre de références dans le modèle de mappage DITA pour que le processus reste synchrone :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| com.adobe.fmdita.xmleditor.config.XmlEditorConfig | xmleditor.asyncmapcreation | > 0 <br> **Valeur par défaut** : 5 |

Lors de la création d’un mappage DITA avec des références de rubrique volumineuses à l’aide d’un modèle personnalisé, la création du mappage échoue sur le serveur cloud si le temps de traitement total dépasse 60 secondes.

Pour éviter cela, configurez la **création asynchrone de mappage dita** dans XmlEditorConfig qui permet aux tâches de s’exécuter en parallèle et de réduire les temps de traitement pour les mappages DITA plus volumineux.

**Rubrique parente :** [Configuration de modèles de rubrique et de mappage](conf-template-tags.md)
