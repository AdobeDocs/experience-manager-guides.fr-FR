---
title: Bonnes pratiques relatives à la traduction de contenu
description: connaître les bonnes pratiques relatives à la traduction de contenu dans AEM Guides ; Découvrez comment configurer le service de traduction, créer un projet de traduction et démarrer la tâche de traduction.
feature: Translation
role: User
hide: true
exl-id: 09e813fd-ec22-4d2e-9ee7-098d562ad44f
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 2%

---

# Bonnes pratiques relatives à la traduction de contenu {#id1678G0S702F}

Tenez compte du point suivant pour la traduction de contenu :

- Les noms de dossier et de fichier doivent respecter les normes de dénomination des fichiers, notamment : il ne doit y avoir ni espaces, ni apostrophes, ni accolades, ni signe égal, ni caractères spéciaux ou non ASCII.

- Si vous traduisez du contenu dans différentes langues, vous devez créer des dossiers correspondant à chaque langue. Chacun de ces dossiers de langue contient le contenu correspondant à cette langue. Par exemple, vous pouvez créer des dossiers à l’aide de l’indicateur de langue, tel que `de` pour l’allemand, `fr` pour le français, etc. Vous pouvez également créer des dossiers à l’aide des indicateurs de langue et de région, tels que `fr-FR` pour le français utilisé en France ou `fr-CA` pour le français utilisé au Canada.
- Les paramètres régionaux doivent également être sélectionnés pour la langue cible en fonction des dossiers de langue cible sur leur instance.
- La configuration cloud doit être identique à celle du dossier source et il ne doit y avoir qu’une seule configuration cloud dans un dossier. Si vous souhaitez utiliser plusieurs connecteurs de traduction, vous pouvez créer plusieurs dossiers sous /conf.
- Un dossier ne doit pas contenir plus de 1 000 fichiers.
- Assurez-vous que l’utilisateur chargé de lancer le processus de traduction dispose des autorisations de lecture, de modification, de création et de suppression sur les dossiers de langue source et cible.
- Comme la traduction du contenu nécessite la création d’un projet de traduction, l’utilisateur doit avoir accès à la création de projet dans AEM.
- Si vous souhaitez utiliser des paramètres prédéfinis conditionnels avec votre carte, vous devez les créer avant de lancer le processus de traduction. Comme les paramètres prédéfinis conditionnels sont également inclus dans la version traduite de la carte, la création des paramètres prédéfinis avant de lancer le processus de traduction garantit qu’ils sont disponibles dans la version traduite.
- Le processus de traduction de contenu doit être démarré à partir de la console de mappage DITA et non de l’interface utilisateur d’AEM Assets.
- Le workflow de traduction DITA basé sur les composants ne doit pas être utilisé si vous traduisez du contenu par traduction humaine. Toutefois, cette option doit être utilisée pour la traduction automatique.
- Le contenu et les médias utilisés globalement qui ne nécessitent pas de localisation doivent être conservés hors des copies de langue.
- Tout le contenu commun qui doit être localisé doit être conservé dans un dossier commun sous le dossier de langue.

L’illustration suivante présente un exemple de structure de dossiers dans AEM lorsque vous avez utilisé globalement du contenu et trois copies de langue.

![](images/aem-directory_structure.png){width="800" align="left"}

## Configuration du service de traduction

Effectuez les étapes suivantes pour configurer le service de traduction humaine ou automatique à utiliser :

1. Dans l’interface utilisateur d’Assets, sélectionnez le dossier de langue source.

1. Ouvrez les propriétés du dossier et accédez à l’onglet **Services cloud**.

1. Dans l’onglet **Services cloud**, configurez le service de traduction que vous souhaitez utiliser.

   Vous pouvez configurer la traduction humaine ou automatique.

   Assurez-vous qu’il n’existe qu’une seule configuration pour le connecteur de traduction dans un dossier. Plusieurs dossiers peuvent être créés sous /conf, s’il existe plusieurs connecteurs de traduction. Une configuration cloud doit être sélectionnée pour le dossier de langue source avant de démarrer le processus de traduction.

   >[!NOTE]
   >
   > Consultez [ Configuration de la structure d’intégration de traduction ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) dans la documentation d’AEM pour plus d’informations sur l’intégration à des services de traduction tiers.

1. Cliquez sur **Enregistrer et fermer** pour enregistrer les propriétés du dossier mis à jour.


>[!TIP]
>
> Voir la section *Traduction* dans le guide des bonnes pratiques pour connaître les bonnes pratiques en matière de traduction de contenu.

## Créer un projet de traduction

Pour créer un projet de traduction, procédez comme suit :

>[!NOTE]
>
> Avant d’effectuer les étapes de cette procédure, assurez-vous d’avoir créé la racine de langue et les dossiers cibles requis, comme décrit dans la section [ Bonnes pratiques pour la traduction de contenu ](#id1678G0S702F).

1. Dans l&#39;interface utilisateur d&#39;Assets, cliquez sur le fichier de mappage DITA.

1. Cliquez sur l’onglet **Traduction**.

1. Dans la liste **Langues cibles**, sélectionnez le paramètre régional vers lequel vous souhaitez traduire votre projet et cliquez sur **Terminé**.

   Un résumé et des détails sur les rubriques et les ressources associées s’affichent.

   >[!IMPORTANT]
   >
   > Le **Langues cibles** affiche uniquement les langues pour lesquelles un dossier de langue est créé parallèlement à la langue source. Un dossier de langue créé à un autre niveau, par exemple un niveau vers le bas à partir du dossier de langue source, n’est pas affiché non plus. Veillez à créer tous vos dossiers de langue cible au même niveau que votre dossier de langue source.

1. Sélectionnez les rubriques à envoyer pour traduction.

   Vous pouvez également utiliser les options de filtrage de rubrique suivantes :

   >[!NOTE]
   >
   > Après avoir appliqué le filtre requis, cliquez sur **Terminé** dans le panneau Filtre pour filtrer les rubriques en fonction de votre sélection.

   - **Statut de traduction** : choisissez de filtrer les rubriques en fonction de leur statut de traduction. Les options disponibles sont les suivantes : Désynchronisé, Copie manquante, En cours et Synchronisé.
   - **Rechercher** : saisissez un ou plusieurs termes à rechercher dans les titres des rubriques.
   - **Type Source** : choisissez de filtrer les rubriques en fonction de leurs types de fichiers. Les options disponibles sont les suivantes : Tous, DITA, Plan DITA, Ressource.
   - **Version de Source modifiée après** : choisissez de filtrer les rubriques en fonction de leur date et heure de modification. Toutes les rubriques modifiées après la date et l’heure spécifiées sont affichées dans la liste.
   - **Ligne de base** : cliquez sur Utiliser la ligne de base et choisissez une ligne de base créée sur la carte. Tous les fichiers faisant partie de la ligne de base sélectionnée sont affichés sur la page Traduction . Vous pouvez choisir les fichiers souhaités dans la ligne de base et poursuivre le processus de traduction. Une fois votre contenu traduit, vous pouvez exporter la ligne de base traduite. Pour plus d&#39;informations sur l&#39;exportation de la ligne de base traduite, voir [ Exporter la ligne de base traduite ](generate-output-use-baseline-for-publishing.md#id196SE600GHS).
1. Cliquez sur **Créer/mettre à jour des copies de langue** au bas du panneau Filtre.

1. Dans la liste **Projet**, sélectionnez **Créer un projet de traduction**.

   >[!NOTE]
   >
   > Si vous disposez déjà d’un projet de traduction, vous pouvez y ajouter des rubriques. Sélectionnez l’option **Ajouter à un projet de traduction existant** dans la liste **Projet** et choisissez un projet dans la liste **Projet de traduction existant**.

1. Dans le champ **Titre du projet**, saisissez un titre pour le projet.

1. Sélectionnez l&#39;option **Inclure le plan DITA** pour envoyer le plan pour traduction.
1. Cliquez sur **Démarrer** pour créer un projet de traduction.

   Un nouveau projet de traduction est créé avec la version sélectionnée des rubriques. À ce stade, un message pop-up s’affiche pour confirmer que le projet de traduction a été créé. Une fois que toutes les copies de langue cible sont disponibles dans le projet de traduction, vous recevez une notification dans la boîte de réception. Une fois que les copies de langue cible sont disponibles dans le projet de traduction, vous pouvez poursuivre et démarrer la tâche de traduction.

   ![](images/status-translation-uuid.png){width="800" align="left"}


L’onglet Traduction comporte les sections suivantes :

- **Résumé** : affiche le nombre de rubriques référencées et la langue source, ainsi que son code.
- **Détails** : affiche le titre de la rubrique, le type de rubrique, le code de langue de la rubrique, la langue source, la version de la rubrique source, le libellé ajouté à la rubrique et le statut de traduction.




## Démarrer la tâche de traduction {#id225IK030OE8}

Pour démarrer la tâche de traduction, procédez comme suit :

1. Dans la console **Projets**, accédez au dossier de projet que vous avez créé pour la localisation.

1. Cliquez sur le projet de localisation pour ouvrir la page de détails.

1. Cliquez sur la flèche de la mosaïque **Tâche de traduction**, puis sélectionnez **Démarrer** dans la liste pour lancer le processus de traduction.

   >[!NOTE]
   >
   > Si vous utilisez le service de traduction humaine, vous devez exporter le contenu pour le traduire. Une fois que vous disposez du contenu traduit, vous devez le réimporter dans le projet de traduction.

1. Pour afficher le statut de la tâche de traduction, cliquez sur les points de suspension en bas de la mosaïque **Tâche de traduction**.


Une fois la traduction terminée, le statut de la tâche de traduction passe à *Prêt pour la révision*. Pour terminer le processus de traduction, vous devez accepter la copie traduite et les métadonnées de la ressource à partir de la mosaïque Tâche de traduction dans la console Projet.

>[!NOTE]
>
> Si vous rejetez la traduction d’une ou de plusieurs rubriques dans une tâche de traduction, le statut de traduction **En cours** de toutes les rubriques rejetées revient à son statut d’origine. Le statut des rubriques référencées est vérifié et rétabli en fonction du dernier état de traduction. En outre, les fichiers de traduction créés dans le projet de destination ne sont pas supprimés, même si la traduction est rejetée pour eux.

**Rubrique parente :**&#x200B;[ Traduire le contenu](translation.md)
