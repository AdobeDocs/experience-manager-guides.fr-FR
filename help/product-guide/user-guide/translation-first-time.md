---
title: Bonnes pratiques relatives à la traduction de contenu
description: Découvrez les bonnes pratiques en matière de traduction de contenu dans AEM Guides. Découvrez comment configurer le service de traduction, créer un projet de traduction et lancer la tâche de traduction.
exl-id: f2a4df86-bba7-434c-b7f9-3587b8a4f9bc
feature: Translation
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 2%

---

# Bonnes pratiques relatives à la traduction de contenu {#id1678G0S702F}

Tenez compte du point suivant pour traduire du contenu :

- Les noms de dossier et de fichier doivent respecter les normes d’attribution de noms de fichier, telles que : il ne doit pas y avoir d’espaces, d’apostrophe, d’accolades, de signe égal, de caractères spéciaux ou non ASCII.

- Si vous traduisez du contenu dans différentes langues, vous devez créer des dossiers correspondant à chaque langue. Chacun de ces dossiers de langue contiendra le contenu correspondant à cette langue. Par exemple, vous pouvez créer des dossiers à l’aide du concepteur de langue, comme `de` pour l&#39;allemand, `fr` pour le français, etc. Vous pouvez également créer des dossiers à l’aide des indicateurs de langue et de région, tels que `fr-FR` pour le français utilisé en France ou `fr-CA` pour le français utilisé au Canada.
- Les paramètres régionaux de la langue cible doivent également être sélectionnés en fonction des dossiers de langue cible sur leur instance.
- La configuration du cloud doit être identique à celle du dossier source et il ne doit y avoir qu’une seule configuration du cloud dans un dossier. Vous pouvez créer plusieurs dossiers sous /conf si vous souhaitez utiliser plusieurs connecteurs de traduction.
- Un dossier ne doit pas contenir plus de 1 000 fichiers.
- Assurez-vous que l’utilisateur chargé de lancer le processus de traduction dispose des autorisations de lecture, de modification, de création et de suppression sur les dossiers de langue source et cible.
- Comme la traduction de contenu nécessite la création d’un projet de traduction, l’utilisateur doit avoir accès à la création d’un projet dans AEM.
- Si vous souhaitez utiliser des paramètres prédéfinis conditionnels avec votre carte, vous devez les créer avant de lancer le processus de traduction. Comme les paramètres prédéfinis conditionnels sont également regroupés dans la version traduite de la carte, la création des paramètres prédéfinis avant de lancer le processus de traduction permet de s’assurer qu’ils sont disponibles dans la version traduite.
- Le processus de traduction du contenu doit être démarré à partir de la console de mappage DITA et non de l’interface utilisateur d’AEM Assets.
- Le processus de traduction DITA basé sur des composants ne doit pas être utilisé si vous traduisez du contenu par le biais d’une traduction humaine. Toutefois, cette option doit être utilisée pour la traduction automatique.
- Le contenu et le média utilisés globalement qui ne nécessitent pas de localisation doivent être conservés en dehors des copies de langue.
- Tout le contenu commun à localiser doit être conservé dans un dossier commun sous le dossier de langue.

L’illustration suivante présente un exemple de structure de dossiers dans AEM lorsque vous avez utilisé du contenu global et trois copies de langue.

![](images/aem-directory_structure.png){width="800" align="left"}

## Configuration du service de traduction

Effectuez les étapes suivantes pour configurer le service de traduction humaine ou automatique à utiliser :

1. Dans l’interface utilisateur d’Assets, sélectionnez le dossier de langue source.

1. Ouvrez les propriétés du dossier, puis accédez à **Cloud Service** .

1. Dans le **Cloud Service** , configurez le service de traduction à utiliser.

   Vous pouvez configurer la traduction automatique ou humaine.

   Assurez-vous qu’il n’existe qu’une seule configuration pour le connecteur de traduction dans un dossier. Plusieurs dossiers peuvent être créés sous /conf, s’il existe plusieurs connecteurs de traduction. Une configuration cloud doit être sélectionnée pour le dossier de langue source avant de démarrer le processus de traduction.

   >[!NOTE]
   >
   > Voir [Configuration de la structure d’intégration de traduction](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) dans la documentation d’AEM pour plus d’informations sur l’intégration à des services de traduction tiers.

1. Cliquez sur **Enregistrer et fermer** pour enregistrer les propriétés du dossier mises à jour.


>[!TIP]
>
> Voir *Traduction* dans le guide des bonnes pratiques pour connaître les bonnes pratiques en matière de traduction de contenu.

## Créer un projet de traduction

Effectuez les étapes suivantes pour créer un projet de traduction :

>[!NOTE]
>
> Avant d’exécuter les étapes de cette procédure, assurez-vous d’avoir créé la racine de langue et les dossiers cible requis, comme décrit dans la section [Bonnes pratiques relatives à la traduction de contenu](#id1678G0S702F).

1. Dans l’interface utilisateur d’Assets, cliquez sur le fichier de mappage DITA.

1. Cliquez sur le bouton **Traduction** .

1. Dans la **Langues cibles** sélectionnez la liste des paramètres régionaux dans lesquels vous souhaitez traduire votre projet, puis cliquez sur **Terminé**.

   Un résumé et des détails des rubriques et des ressources associées s’affichent.

   >[!IMPORTANT]
   >
   > La variable **Langues cibles** afficher uniquement les langues pour lesquelles un dossier de langues est créé parallèlement à la langue source. Un dossier de langue créé à un autre niveau, tel qu’un niveau inférieur du dossier de langue source, n’est pas non plus affiché. Veillez à créer tous vos dossiers de langue cible au même niveau que votre dossier de langue source.

1. Sélectionnez les rubriques que vous souhaitez envoyer pour traduction.

   Vous pouvez également utiliser les options de filtrage de rubrique suivantes :

   >[!NOTE]
   >
   > Après avoir appliqué le filtre requis, cliquez sur **Terminé** dans le panneau Filtre pour filtrer les rubriques en fonction de votre sélection.

   - **État de traduction**: choisissez de filtrer les rubriques en fonction de leur état de traduction. Les options disponibles sont : Désynchronisé, Copie manquante, En cours et Synchronisé.
   - **Rechercher**: saisissez un ou plusieurs termes à rechercher dans les titres de rubrique.
   - **Type de source**: choisissez de filtrer les rubriques en fonction de leurs types de fichiers. Les options disponibles sont les suivantes : Tous, DITA, Carte DITA, Ressource.
   - **Version source modifiée après**: choisissez de filtrer les rubriques en fonction de leur date et heure de modification. Toutes les rubriques modifiées après la date et l’heure spécifiées s’affichent dans la liste.
   - **Ligne de base**: cliquez sur Utiliser la ligne de base et choisissez une ligne de base créée sur la carte. Tous les fichiers qui font partie de la ligne de base sélectionnée sont affichés dans la page Traduction. Vous pouvez choisir les fichiers de votre choix à partir de la ligne de base et poursuivre le processus de traduction. Une fois votre contenu traduit, vous pouvez exporter la ligne de base traduite. Pour plus d’informations sur l’exportation de la ligne de base traduite, voir [Exporter la ligne de base traduite](generate-output-use-baseline-for-publishing.md#id196SE600GHS).
1. Cliquez sur **Créer/mettre à jour des copies de langue** au bas du panneau Filtre.

1. Dans la **Projet** list, select **Création d’un projet de traduction**.

   >[!NOTE]
   >
   > Si vous disposez déjà d’un projet de traduction, vous pouvez ajouter des rubriques à ce projet. Sélectionner **Ajouter à un projet de traduction existant** de l’option **Projet** et sélectionnez un projet dans la liste **Projet de traduction existant** liste.

1. Dans le champ **Titre du projet**, saisissez un titre pour le projet.

1. Sélectionnez la variable **Inclure la carte DITA** pour envoyer la carte à traduire.
1. Cliquez sur **Début** pour créer un projet de traduction.

   Un nouveau projet de traduction est créé avec la version sélectionnée des rubriques. À l’heure actuelle, un message contextuel s’affiche, confirmant que le projet de traduction a été créé. Une fois que toutes les copies de langue cible sont disponibles dans le projet de traduction, vous recevez une notification dans la boîte de réception. Une fois la zone des copies de langue cible disponible dans le projet de traduction, vous pouvez poursuivre et lancer la tâche de traduction.

   ![](images/status-translation-uuid.png){width="800" align="left"}


L’onglet Traduction comporte les sections suivantes :

- **Résumé**: indique le nombre de rubriques référencées et la langue source, ainsi que son code.
- **Détails**: affiche le titre de la rubrique, le type de rubrique, le code de langue de la rubrique, la langue source, la version de la rubrique source, le libellé ajouté à la rubrique et l’état de traduction.




## Démarrage de la tâche de traduction {#id225IK030OE8}

Effectuez les étapes suivantes pour démarrer la tâche de traduction :

1. Dans le **Projets** , accédez au dossier de projet que vous avez créé pour la localisation.

1. Cliquez sur le projet de localisation pour ouvrir la page de détails.

1. Cliquez sur la flèche du **Tâche de traduction** et sélectionnez **Début** de la liste pour lancer le workflow de traduction.

   >[!NOTE]
   >
   > Si vous utilisez le service de traduction humaine, vous devez exporter le contenu en vue de la traduction. Une fois que vous avez le contenu traduit, vous devez le réimporter dans le projet de traduction.

1. Pour afficher le statut de la tâche de traduction, cliquez sur les points de suspension en bas de la mosaïque **Tâche de traduction**.


Une fois la traduction terminée, l’état de la tâche de traduction devient *Prêt pour révision*. Pour terminer le processus de traduction, vous devez accepter la copie traduite et les métadonnées de ressource de la mosaïque Tâche de traduction dans la console Projet.

>[!NOTE]
>
> Si vous rejetez la traduction d’une ou de plusieurs rubriques dans une tâche de traduction, la variable **En cours** l’état de traduction de toutes les rubriques rejetées revient à leur état d’origine. L’état des rubriques référencées est vérifié et rétabli en fonction de l’état de traduction le plus récent. En outre, les fichiers de traduction créés dans le projet de destination ne sont pas supprimés même si la traduction est refusée pour eux.

**Rubrique parente :**[ Traduire le contenu](translation.md)
