---
title: Configuration du modèle de mappage DITA personnalisé
description: Découvrez comment configurer le modèle de mappage DITA personnalisé
exl-id: ea8a6687-1a7b-45c7-8cbc-161f9e88a8be
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 1%

---

# Configuration du modèle de mappage DITA personnalisé {#id1774F04F05Z}

AEM Guides est fourni avec deux modèles de mappage prêts à l’emploi — carte DITA et carte des livres. Vous pouvez créer des cartes à partir de ces modèles ou définir vos propres modèles de carte qui pourront ensuite être utilisés pour créer de nouvelles cartes.

Effectuez les étapes suivantes pour ajouter vos modèles de mappage personnalisés :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Dans l’interface utilisateur d’Assets, accédez au dossier configuré pour stocker les fichiers de modèle de carte. Par défaut, tous les modèles de mappage sont stockés dans le dossier /content/dam/dita-templates/maps .

   >[!NOTE]
   >
   > Pour configurer un emplacement personnalisé pour stocker des modèles de rubrique ou de mappage, voir [Configuration du chemin d’accès au dossier de modèle DITA personnalisé](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1. Cliquez sur **Créer** \> **Modèle DITA**.

1. Sur la page Plan directeur, sélectionnez le type de modèle de carte que vous souhaitez créer.

   >[!NOTE]
   >
   > Vous pouvez utiliser le modèle de carte ou de carte-livre comme base de votre nouveau modèle.

1. Cliquez sur **Suivant**.

1. Sur la nouvelle page Propriétés du modèle, saisissez une **Titre** et **Nom** pour le modèle.

   >[!NOTE]
   >
   > Le nom est automatiquement proposé en fonction du titre de votre modèle. Si vous souhaitez spécifier manuellement le nom, assurez-vous que le nom ne contient aucun espace, apostrophe ou accolades et qu’il se termine par .ditamap.

1. Cliquez sur **Créer**.

   Le message Mapper créé s’affiche.

   Vous pouvez choisir d’ouvrir le modèle à modifier dans l’éditeur de mappage ou d’enregistrer le fichier de modèle à l’emplacement de la boutique de modèles. Une fois le modèle créé, vous pouvez utiliser l’éditeur de cartes pour le personnaliser selon vos besoins de création. Une fois qu’un modèle est en place, veillez à l’associer à un profil global ou de niveau dossier.


La prochaine fois que vous créerez une carte, votre modèle s’affichera dans la page Plan directeur. Pour plus d’informations sur la création d’un mappage DITA, voir *Utilisation des guides Adobe Experience Manager*.

>[!TIP]
>
> Voir *Modèles personnalisés* section du guide Bonnes pratiques pour connaître les bonnes pratiques relatives à l’utilisation de modèles de mappage personnalisés.

**Rubrique parente :** [Configuration des modèles de rubrique et de mappage](conf-template-tags.md)
