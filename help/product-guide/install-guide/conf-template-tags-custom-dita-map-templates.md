---
title: Configurer un modèle de plan DITA personnalisé
description: Découvrez comment configurer un modèle de plan DITA personnalisé
exl-id: ea8a6687-1a7b-45c7-8cbc-161f9e88a8be
feature: Template Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 1%

---

# Configurer un modèle de plan DITA personnalisé {#id1774F04F05Z}

AEM Guides est fourni avec deux modèles de carte prêts à l&#39;emploi : DITA map et Bookmap. Vous pouvez créer des mappages basés sur ces modèles ou définir vos propres modèles de mappage qui peuvent ensuite être utilisés pour créer de nouveaux mappages.

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

   Le message Mappage créé s’affiche.

   Vous pouvez choisir d’ouvrir le modèle pour le modifier dans l’éditeur de cartes ou d’enregistrer le fichier de modèle à l’emplacement du magasin de modèles. Une fois le modèle créé, vous pouvez utiliser l’éditeur de cartes pour le personnaliser en fonction de vos besoins de création. Une fois qu’un modèle est en place, veillez à l’associer à un profil global ou au niveau du dossier.


La prochaine fois que vous créerez une nouvelle carte, votre modèle s’affichera dans la page Plan directeur. Pour plus d&#39;informations sur la création d&#39;un plan DITA, reportez-vous au *Utilisation d&#39;Adobe Experience Manager Guides*.

>[!TIP]
>
> Voir la section *Modèles personnalisés* dans le guide des bonnes pratiques pour connaître les bonnes pratiques relatives à l’utilisation de modèles de carte personnalisés.

**Rubrique parente :** [Configuration des modèles de rubrique et de mappage](conf-template-tags.md)
