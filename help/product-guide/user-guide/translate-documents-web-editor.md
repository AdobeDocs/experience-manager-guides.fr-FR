---
title: Traduire des documents à partir de la console de mappage
description: Traduisez votre contenu dans plusieurs langues à partir de l’éditeur web. Découvrez comment créer un projet de traduction, ajouter des règles, afficher des versions et ignorer les fichiers non synchronisés dans AEM Guides.
exl-id: 321c5442-92eb-4662-ab61-d4d4f05eeb39
feature: Authoring, Features of Web Editor, Translation
role: User
source-git-commit: 4165535976082c1e8f28bf15f16999b6bfe5bf9a
workflow-type: tm+mt
source-wordcount: '2446'
ht-degree: 1%

---

# Traduire des documents à partir de la console de mappage {#id21BKF0Z0YZF}

>[!TIP]
>
> Il est recommandé d’utiliser cette fonctionnalité de traduction à partir de l’éditeur si vous avez effectué une mise à niveau vers Adobe Experience Manager Guides as a Cloud Service version de février 2022 ou ultérieure.

Experience Manager Guides s’accompagne d’une puissante fonctionnalité dans l’éditeur, qui vous permet de traduire votre contenu dans plusieurs langues. Vous pouvez créer un projet de traduction et ajouter ultérieurement les tâches de traduction au projet de traduction existant. Vous pouvez également créer un projet de traduction multilingue qui comprend des tâches de traduction pour toutes les langues sélectionnées.

>[!NOTE]
>
> Votre administrateur peut configurer l’onglet Gérer \(utilisé pour la traduction\) dans l’éditeur. Pour plus d’informations, consultez la section *Configuration de la fonction de traduction dans l’éditeur* dans la section Installation et configuration d’Adobe Experience Manager Guides as a Cloud Service.

## Avant de commencer

Avant d’effectuer les étapes de cette procédure, assurez-vous d’avoir créé les dossiers racine de langue et cible requis

1. Créez un dossier racine pour stocker votre contenu source. Le dossier racine doit être créé avec le nom de langue \(tel que l’anglais\) ou le code de langue \(en\).
1. Créez les dossiers de destination vers lesquels vous souhaitez traduire votre contenu. Par exemple, pour traduire votre contenu en allemand ou en français, vous devez créer un dossier nommé -de \(pour l’allemand\) ou -fr \(pour le français\).

>[!NOTE]
>
> Le dossier racine et les dossiers de destination doivent être créés au même niveau.

## Créer un projet de traduction

1. Dans le panneau **Référentiel**, ouvrez le fichier DITA map en mode Carte.
1. Sélectionnez l’icône **Ouvrir dans la console de mappage**.
1. Sur la page de la console Mappage , accédez à l’onglet **Traduction**. Le **panneau Traduction** affiche les groupes de langues disponibles.

1. En tant qu’utilisateur, vous pouvez afficher les groupes linguistiques configurés sur votre profil de dossier. Les groupes de langues affichent les dossiers de langue ainsi que leurs codes de langue. Par exemple, le groupe de langues G1 contient les dossiers de langues Italien \(it\), Allemand \(de\), Français \(fr\) et Anglais \(en\).

   ![Panneau de traduction](images/translation-languages.png){width="300" align="left"}

   *Sélectionnez les groupes linguistiques ou les langues dans lesquelles vous souhaitez traduire vos documents.*


   >[!IMPORTANT]
   >
   > Vous pouvez uniquement sélectionner et traduire vers les langues pour lesquelles vous avez créé le dossier cible parallèlement à la langue source. Un dossier de langue créé à un autre niveau, par exemple un niveau vers le bas à partir du dossier de langue source, n’est pas affiché non plus. Veillez à créer tous vos dossiers de langue cible au même niveau que votre dossier de langue source.



1. Vous pouvez sélectionner n’importe quel groupe de langues en tant que cible pour la traduction. Si vous **Tout sélectionner**, les fichiers sélectionnés sont traduits dans toutes les langues disponibles dans les groupes de langues existants.

   L’option Dossier de langue est grisée et affiche un signe d’avertissement :

   - Si le dossier cible d’une langue est manquant.
   - Si la langue cible est la même que la langue source.


   >[!NOTE]
   >
   > Si vous créez le dossier cible pour une langue après avoir créé le groupe de langues, actualisez le navigateur pour activer la langue dans les groupes de langues.

1. Si vous choisissez une langue particulière, elle apparaît comme sélectionnée sous tous les groupes linguistiques que vous avez sélectionnés. Donc, quand vous traduisez dans n&#39;importe quelle langue, c&#39;est traduit en une seule fois pour tous les groupes linguistiques. Par exemple, si l’allemand est présent dans les deux groupes linguistiques G1 et G2, il est sélectionné pour les deux.

1. Dans la section **Autres langues**, vous pouvez choisir n’importe quelle langue pour laquelle vous avez créé le dossier cible, mais qui ne fait partie d’aucun groupe de langues.

1. Vous pouvez également sélectionner l’une des options suivantes pour traduire votre projet :

   **Aucun** sélectionnez cette option pour traduire les versions par défaut des fichiers. Cette option est sélectionnée par défaut.

   **Utiliser la ligne de base :** vous pouvez sélectionner une ligne de base pour traduire votre projet. Sélectionnez **Utiliser la ligne de base** et choisissez une ligne de base créée sur la carte. Tous les fichiers faisant partie de la ligne de base sélectionnée sont affichés sur la page Traduction . Une fois votre contenu traduit, vous pouvez exporter la ligne de base traduite. Pour plus d&#39;informations sur l&#39;exportation de la ligne de base traduite, voir [ Exporter la ligne de base traduite ](generate-output-use-baseline-for-publishing.md#id196SE600GHS).

   **Utiliser la dernière version comme activée** : choisissez de filtrer la version des rubriques en fonction de leur date et heure de création. Lorsque vous sélectionnez une date et une heure, seules la dernière version des fichiers créés le ou avant la date et l’heure sélectionnées s’affichent.

1. Sélectionnez **Appliquer**. Une liste comportant des détails sur les rubriques et les ressources associées s’affiche.
1. Sélectionnez les rubriques à envoyer pour traduction. Vous pouvez également utiliser les options de filtrage par rubrique pour les colonnes suivantes :

   - **Title** : titre du fichier source.  Passez la souris sur le titre du fichier source pour afficher le titre du fichier cible ou traduit.
   - **Nom de fichier** : nom du fichier source
   - **Type de fichier** : type du fichier source. Les options disponibles sont Carte, Rubrique et Image.
   - **Type de référence** : références directes ou indirectes.
   - **Version** : numéro de version du fichier source.

     Si un fichier contient des modifications qui n’ont pas encore de version (c’est-à-dire qui ne sont pas enregistrées en tant que nouvelle version dans votre mappage), une icône d’information s’affiche en regard du fichier, indiquant la présence de modifications sans version.

     ![](images/unversioned-changes-translation.png){width="650" align="left"}

     >
     >
     > Pour afficher uniquement les fichiers contenant des modifications sans version, activez le paramètre **Afficher uniquement les ressources contenant des modifications sans version** dans le panneau Filtres. En outre, l’indicateur sans version n’est visible que lors de la traduction de fichiers en fonction de leur dernière version.
   - **Libellé de la version** : libellé de la version sélectionnée du fichier source
   - **Version cible** : numéro de version du fichier cible
   - **Document State** : état du fichier source. Les options disponibles sont Brouillon, En cours de révision et Révisé.
   - **Langue cible** : langue vers laquelle vous souhaitez traduire le fichier source
   - **Statut de traduction** : les options disponibles sont les suivantes : Désynchronisé, Copie manquante, En cours et Synchronisé.
   - **Libellé cible** : libellé de la version sélectionnée du fichier cible
1. Sélectionnez **Envoyer pour traduction** dans le coin supérieur droit.

   ![](images/translation-send.png){align="left"}

1. Dans la liste déroulante, sélectionnez **Créer un projet de traduction**.

   ![](images/translation-project-types.png){width="350" align="left"}

   Outre un nouveau projet de traduction, vous pouvez également choisir parmi les options suivantes :

   - Vous pouvez choisir de **Créer uniquement la structure** pour le projet de traduction.
   - Vous pouvez choisir de **Créer un projet de traduction XLIFF** pour convertir le contenu XML au format XLIFF (XML Localization Interchange File Format). XLIFF est un format XML ouvert utilisé pour normaliser le transfert de données entre différents outils utilisés dans le processus de traduction de contenu. Experience Manager Guides prend en charge XLIFF version 1.2.
Dans un projet XLIFF, le contenu est exporté au format XLIFF standard du secteur, qui peut être fourni aux fournisseurs de services de traduction. Le format XLIFF permet la réutilisation potentielle des segments que vous avez déjà traduits lors de la phase de traduction.\
     Une fois le contenu XLIFF traduit, il peut être importé dans Experience Manager Guides, créant une version traduite du projet DITA d&#39;origine.

   >[!NOTE]
   >
   > L’exportation XLIFF ne fonctionne qu’avec la configuration de traduction humaine.

   - Vous pouvez sélectionner **Créer un projet de traduction multilingue** qui inclura les tâches de traduction pour toutes les langues que vous avez sélectionnées pour la traduction. Par exemple, si vous avez sélectionné le français, l’allemand et l’espagnol, un projet contenant des tâches de traduction pour les trois langues sera créé.
   - Si vous disposez déjà d’un projet de traduction, vous pouvez y ajouter des rubriques. Sélectionnez l’option **Ajouter à un projet de traduction existant** dans la liste Projet et choisissez un projet dans la liste Projet de traduction existant . Vous pouvez trier ces projets par ordre le plus récent, croissant ou décroissant.

   - Si vous sélectionnez **Ajouter à un projet de traduction existant**, cette opération met à jour l’entrée de ressource existante dans le projet si la ressource est déjà ajoutée et que le statut de la tâche de traduction associée est à l’état *Brouillon*.
      - Si la langue de destination n’est pas présente dans le projet, un nouveau projet est créé pour le projet de traduction unilingue et une nouvelle tâche est créée pour le projet de traduction multilingue.

      - Si la tâche est déjà présente pour la langue de destination et que le statut de la tâche n’est pas à l’état *Brouillon*, une nouvelle tâche est créée dans le même projet pour ajouter les ressources à traduire.

   >[!NOTE]
   >
   > Si votre projet existant est un projet de définition de la portée, son nom comporte le suffixe « \(Définition de la portée\) ».

   - Si vous devez créer la portée d’un projet à traduire, vous pouvez sélectionner **Créer un nouveau projet de traduction de la portée**. Les copies ne seront pas envoyées pour traduction et l’état de traduction original des fichiers sera conservé. Il n’y a aucun impact sur la copie de langue de destination des rubriques mentionnées envoyées pour la définition de la portée.

1. Dans le champ **Titre du projet**, saisissez un titre pour le projet.
1. Sélectionnez **Envoyer** pour créer un projet de traduction.

Un nouveau projet de traduction est créé avec la version sélectionnée des rubriques. À ce stade, un message pop-up s’affiche pour confirmer que le projet de traduction a été créé. Une fois que toutes les copies de langue cible sont disponibles dans le projet de traduction, vous recevez une notification dans la boîte de réception. Une fois que les copies de langue cible sont disponibles dans le projet de traduction, vous pouvez poursuivre et démarrer la tâche de traduction. Pour plus d’informations, [Démarrez la tâche de traduction](translation-first-time.md#id225IK030OE8).

>[!NOTE]
>
> Si vous rejetez la traduction d’une ou de plusieurs rubriques dans une tâche de traduction, le statut de traduction **En cours** de toutes les rubriques rejetées revient à son statut d’origine. Le statut des rubriques référencées est vérifié et rétabli en fonction du dernier état de traduction. En outre, les fichiers de traduction créés dans le projet de destination ne sont pas supprimés, même si la traduction est rejetée pour eux.

## Ajouter les règles de traduction

Experience Manager Guides permet à vos administrateurs de configurer les règles de traduction. Le format SRX (Segmentation Rules eXchange) est une norme pour échanger des règles de segmentation entre différents utilisateurs et différents environnements de traduction. Vous pouvez créer un dossier et y ajouter vos fichiers SRX personnalisés.

Les fichiers SRX doivent être nommés comme `<language-code>.srx`. Par exemple, en-US ou ar-AE.

>[!NOTE]
> 
> Le titre n’est pas sensible à la casse. Vous pouvez donc avoir « en-US », « en-us » ou « EN-us ». En outre, Experience Manager Guides peut résoudre « - » (trait d’union) ou « _ » (trait de soulignement). Vous pouvez donc avoir « en-US » ou « en_US ».

En outre, vous pouvez placer ces fichiers dans n’importe quel dossier sous la racine Adobe Experience Manager Assets `./content/dam`.

Une fois que vous avez créé le dossier contenant les fichiers SRX, vous pouvez ajouter le chemin du dossier dans la configuration de l’emplacement SRX de traduction au sein de votre profil de dossier.

Pour de meilleures performances, il est recommandé de ne conserver que les fichiers SRX dans le dossier configuré dans le profil du dossier.

Experience Manager Guides sélectionne les règles SRX en fonction de la langue source du projet de traduction. Il recherche un fichier SRX personnalisé pour une langue, et si vous ne définissez pas de fichier SRX personnalisé, il sélectionne les règles selon les règles de traduction prêtes à l’emploi.

Pour plus d’informations sur la configuration des profils globaux et au niveau du dossier, consultez la section *Configurer des modèles de création* dans Installation et configuration d’Adobe Experience Manager Guides as a Cloud Service.

## Transmettez le libellé de version à la version cible

Experience Manager Guides permet de transmettre le libellé du fichier source au fichier cible. Cela vous aidera à identifier facilement la version source du fichier traduit.

Pour ajouter le libellé de version source dans la copie cible, votre administrateur système doit activer l’option **Propager les libellés de version source à la version cible** dans l’onglet **Traduction** des paramètres **Workspace** (apparaissant sous la forme **Paramètres** pour **On-Prem**).

Par exemple, si vous avez des fichiers source auxquels est appliqué le libellé de version `Release 1.0`, vous pouvez également transmettre le libellé source \(`Release 1.0`\) au fichier traduit.

![](images/translation-pass-source-label.png){width="650" align="left"}

>[!NOTE]
>
> Le libellé source n’est attaché qu’à une seule version cible. Si vous déplacez le libellé source vers une autre version, il est automatiquement répercuté dans le dernier libellé cible.

## Afficher la différence de version pour les fichiers désynchronisés 

Experience Manager Guides permet de vérifier les différences entre la version sélectionnée et la dernière version source traduite des rubriques. Vous pouvez choisir de traduire les fichiers **Désynchronisés** en fonction des modifications apportées.

![](images/translation-version-diff.png){width="650" align="left"}

Sélectionnez l’icône **Afficher la différence** icône \(![](images/show-difference-icon.svg)\) d’une rubrique pour afficher les différences entre la dernière version traduite et la version actuelle du fichier sélectionné.

>[!NOTE]
>
> **Afficher la différence** l&#39;icône \(![](images/show-difference-icon.svg)\) s&#39;affiche uniquement pour les fichiers DITA dont le statut de traduction est **Désynchronisé**.

La boîte de dialogue **Différence de version** s’affiche. Il affiche le numéro **Dernière version traduite** et le numéro **Version sélectionnée** sur la gauche. La fenêtre d&#39;aperçu affiche les différences entre la dernière version traduite et la version sélectionnée de la rubrique.

![](images/version-diff.png){width="650" align="left"}

## Ignorer les ressources désynchronisées

Si vous apportez des modifications à certaines ressources, celles-ci ne sont plus synchronisées. Vous pouvez soit retraduire les ressources modifiées, soit ignorer le statut Désynchronisé . Par exemple, si vous avez apporté des modifications très mineures qui n’ont pas vraiment besoin d’être traduites, vous pouvez marquer leur statut sur Synchronisé.

Pour ignorer le statut Désynchronisé , procédez comme suit :

1. Sélectionnez les ressources non synchronisées dont vous souhaitez modifier le statut.
1. Sélectionnez le bouton **Marquer comme synchronisé** \(![](images/translation-mark-in-sync-icon.svg)\) en haut. La boîte de dialogue **Marquer comme synchronisé** s’affiche.

   ![](images/translation-mark-in-sync.png){width="550" align="left"}

1. Sélectionnez **Forcer la synchronisation**. Il définit le statut sur Synchronisé pour les ressources désynchronisées sélectionnées.

>[!NOTE]
>
> Le bouton **Marquer comme synchronisé** \(![](images/translation-mark-in-sync-icon.svg)\) s’affiche uniquement pour les ressources dont le statut de traduction est Désynchronisé.

## Affichage des projets de traduction en cours pour une carte ou une rubrique

Certaines des références de votre tableau de bord de traduction peuvent avoir le statut En cours . Ces références comportent un lien **En cours** dans la colonne **Statut de la traduction**. Lorsque vous sélectionnez le lien, la boîte de dialogue **Projets en cours** s’ouvre. Dans la boîte de dialogue, vous pouvez afficher la liste de tous les projets de traduction en cours \(ainsi que la langue cible\) qui contiennent la référence sélectionnée.

>[!NOTE]
>
> Vous pouvez afficher le lien En cours pour les projets traduits créés dans Adobe Experience Manager Guides as a Cloud Service version de février 2023 ou ultérieure.

Sélectionnez le nom de la référence dans la boîte de dialogue pour l’ouvrir en mode Aperçu. Vous pouvez également sélectionner le projet de traduction pour commencer la traduction.

![](images/translation-in-progress.png){width="550" align="left"}


## Supprimer ou désactiver automatiquement un projet de traduction terminé

>[!NOTE]
> 
>Cette fonctionnalité est disponible pour les nouveaux projets de traduction que vous créez à l’aide de la version Experience Manager Guides 2404 ou ultérieure.  Cela n’aura aucune incidence sur les projets existants.

Votre administrateur peut configurer l’option **Nettoyage du projet de traduction après l’achèvement** sous l’onglet **Traduction** dans les paramètres de **Workspace** (apparaissant sous la forme **Paramètres** pour **On-Prem**) pour désactiver ou supprimer automatiquement les projets de traduction.

Pour effectuer la gestion des documents, Experience Manager Guides permet de supprimer les projets de traduction une fois que vous avez terminé la traduction.

Vous pouvez également désactiver les projets de traduction si vous souhaitez les utiliser ultérieurement. La suppression d’un projet supprime tous les fichiers et dossiers présents dans le projet. La désactivation d’un projet ne le supprime pas, mais le conserve dans le référentiel. Cependant, vous ne pouvez pas mettre à jour ni modifier un projet désactivé.  La suppression ou la désactivation d’un projet n’aura aucune incidence sur le statut de traduction des références.


**Rubrique parente :**[ Présentation de l’éditeur](web-editor.md)
