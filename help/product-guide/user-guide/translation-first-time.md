---
title: Bonnes pratiques relatives à la traduction de contenu
description: connaître les bonnes pratiques relatives à la traduction de contenu dans AEM Guides ; Découvrez comment configurer le service de traduction, créer un projet de traduction et démarrer la tâche de traduction.
exl-id: f2a4df86-bba7-434c-b7f9-3587b8a4f9bc
feature: Translation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 0%

---

# Bonnes pratiques relatives à la traduction de contenu {#id1678G0S702F}

Tenez compte du point suivant pour la traduction de contenu :

- Les noms de dossier et de fichier doivent respecter les normes de dénomination des fichiers, notamment : il ne doit y avoir ni espaces, ni apostrophes, ni accolades, ni signe égal, ni caractères spéciaux ou non ASCII.

- Si vous traduisez du contenu dans différentes langues, vous devez créer des dossiers correspondant à chaque langue. Chacun de ces dossiers de langue contient le contenu correspondant à cette langue. Par exemple, vous pouvez créer des dossiers à l’aide de l’indicateur de langue, tel que `de` pour l’allemand, `fr` pour le français, etc. Vous pouvez également créer des dossiers à l’aide des indicateurs de langue et de région, tels que `fr-FR` pour le français utilisé en France ou `fr-CA` pour le français utilisé au Canada.
- Les paramètres régionaux doivent également être sélectionnés pour la langue cible en fonction des dossiers de langue cible sur leur instance.
- La configuration cloud doit être identique à celle du dossier source et il ne doit y avoir qu’une seule configuration cloud dans un dossier. Si vous souhaitez utiliser plusieurs connecteurs de traduction, vous pouvez créer plusieurs dossiers sous /conf.
- Un dossier ne doit pas contenir plus de 1 000 fichiers.
- Assurez-vous que l’utilisateur chargé de lancer le processus de traduction dispose des autorisations de lecture, de modification, de création et de suppression sur les dossiers de langue source et cible.
- Comme la traduction du contenu nécessite la création d’un projet de traduction, l’utilisateur doit avoir accès à la création de projet dans Adobe Experience Manager.
- Si vous souhaitez utiliser des paramètres prédéfinis conditionnels avec votre carte, vous devez les créer avant de lancer le processus de traduction. Comme les paramètres prédéfinis conditionnels sont également inclus dans la version traduite de la carte, la création des paramètres prédéfinis avant de lancer le processus de traduction garantit qu’ils sont disponibles dans la version traduite.
- Le processus de traduction de contenu doit être démarré à partir de la console de mappage DITA et non de l’interface utilisateur d’Adobe Experience Manager Assets.
- Le workflow de traduction DITA basé sur les composants ne doit pas être utilisé si vous traduisez du contenu par traduction humaine. Toutefois, cette option doit être utilisée pour la traduction automatique.
- Le contenu et les médias utilisés globalement qui ne nécessitent pas de localisation doivent être conservés hors des copies de langue.
- Tout le contenu commun qui doit être localisé doit être conservé dans un dossier commun sous le dossier de langue.

L’illustration suivante présente un exemple de structure de dossiers dans Adobe Experience Manager lorsque vous avez utilisé globalement du contenu et trois copies de langue.

![](images/aem-directory_structure.png){align="left"}

## Configuration du service de traduction

Effectuez les étapes suivantes pour configurer le service de traduction humaine ou automatique à utiliser :

1. Dans l’interface utilisateur d’Assets, sélectionnez le dossier de langue source.

1. Ouvrez les propriétés du dossier et accédez à l’onglet **Services cloud**.

1. Dans l’onglet **Services cloud**, configurez le service de traduction que vous souhaitez utiliser.

   Vous pouvez configurer la traduction humaine ou automatique.

   Assurez-vous qu’il n’existe qu’une seule configuration pour le connecteur de traduction dans un dossier. Plusieurs dossiers peuvent être créés sous /conf, s’il existe plusieurs connecteurs de traduction. Une configuration cloud doit être sélectionnée pour le dossier de langue source avant de démarrer le processus de traduction.

   >[!NOTE]
   >
   > Consultez la documentation [Configuration de la structure d’intégration de traduction](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) dans Adobe Experience Manager pour plus d’informations sur l’intégration à des services de traduction tiers.

1. Sélectionnez **Enregistrer et fermer** pour enregistrer les propriétés du dossier mis à jour.


## Démarrer la tâche de traduction {#id225IK030OE8}

Pour démarrer la tâche de traduction, procédez comme suit :

1. Dans la console **Projets**, accédez au dossier de projet que vous avez créé pour la localisation.

1. Sélectionnez le projet de localisation pour ouvrir la page de détails.

1. Sélectionnez la flèche sur la mosaïque **Tâche de traduction**, puis sélectionnez **Démarrer** dans la liste pour démarrer le processus de traduction.

   >[!NOTE]
   >
   > Si vous utilisez le service de traduction humaine, vous devez exporter le contenu pour le traduire. Une fois que vous disposez du contenu traduit, vous devez le réimporter dans le projet de traduction.

1. Pour afficher le statut de la tâche de traduction, sélectionnez les points de suspension en bas de la mosaïque **Tâche de traduction**.


Une fois la traduction terminée, le statut de la tâche de traduction passe à *Prêt pour la révision*. Pour terminer le processus de traduction, vous devez accepter la copie traduite et les métadonnées de la ressource à partir de la mosaïque Tâche de traduction dans la console Projet. Si vous souhaitez démarrer un nouveau projet de traduction, consultez [Créer un projet de traduction](translate-documents-web-editor.md#create-a-translation-project).

>[!NOTE]
>
>- Si vous rejetez la traduction d’une ou de plusieurs rubriques dans une tâche de traduction, le statut de traduction **En cours** de toutes les rubriques rejetées revient à son statut d’origine. Le statut des rubriques référencées est vérifié et rétabli en fonction du dernier état de traduction. En outre, les fichiers de traduction créés dans le dossier de langue de destination ne sont pas supprimés, même si la traduction est rejetée pour eux.
>- Si vous rejetez, supprimez ou annulez la tâche de traduction pour une rubrique présente dans plusieurs projets (pour l’un des projets), le statut de traduction **En cours** de la rubrique n’est pas rétabli, mais ce projet est supprimé de la liste de projets **En cours** pour cette ressource donnée.
>- En outre, si vous annulez ou supprimez la tâche de traduction ou supprimez l’ensemble du projet, le statut de traduction **En cours** revient à son statut d’origine.

**Rubrique parente :**&#x200B;[ Présentation de la traduction de contenu](translation.md)
