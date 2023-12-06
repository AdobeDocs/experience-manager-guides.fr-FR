---
title: Traduire des documents à partir de l’éditeur Web
description: Traduisez votre contenu dans plusieurs langues à partir de l’éditeur web. Découvrez comment créer un projet de traduction, ajouter des règles, afficher des versions et ignorer les fichiers désynchronisés dans les Guides d’AEM.
exl-id: 321c5442-92eb-4662-ab61-d4d4f05eeb39
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1907'
ht-degree: 0%

---

# Traduire des documents à partir de l’éditeur Web {#id21BKF0Z0YZF}

>[!TIP]
>
> Il est recommandé d’utiliser cette fonction de traduction de l’éditeur Web si vous avez effectué la mise à niveau vers AEM Guides version as a Cloud Service de février 2022 ou ultérieure.

AEM Guides s’accompagne d’une puissante fonctionnalité de l’éditeur web qui vous permet de traduire votre contenu dans plusieurs langues. Vous pouvez créer un projet de traduction, puis ajouter les tâches de traduction au projet de traduction existant. Vous pouvez également créer un projet de traduction multilingue qui comprend des tâches de traduction pour toutes les langues sélectionnées.

>[!NOTE]
>
> Votre administrateur peut configurer l’onglet Gérer \(utilisé pour la traduction\) dans l’éditeur web. Pour plus d’informations, voir *Configuration de la fonction de traduction dans l’éditeur web* dans la section Installation et configuration de Adobe Experience Manager Guides as a Cloud Service.

## Avant de commencer

Avant d’exécuter les étapes de cette procédure, assurez-vous d’avoir créé la racine de langue et les dossiers cibles requis.

1. Créez un dossier racine pour stocker le contenu source. Le dossier racine doit être créé avec le nom de langue \(par exemple, Anglais\) ou le code de langue \(en\).
1. Créez les dossiers de destination vers lesquels vous souhaitez traduire votre contenu. Par exemple, si vous souhaitez traduire votre contenu en allemand ou en français, vous devez créer un dossier nommé -de \(pour allemand\) ou -fr \(pour français\).

>[!NOTE]
>
> Le dossier racine et les dossiers de destination doivent être créés au même niveau.

## Créer un projet de traduction

1. Dans le panneau Référentiel, ouvrez le fichier de mappage DITA en mode Carte.
1. Cliquez sur le bouton **Gérer** . Le panneau Traduction affiche le titre hypertexte du mappage DITA avec le **Langues** liste.
1. Dans la **Langues** sélectionnez les paramètres régionaux dans lesquels vous souhaitez traduire votre projet. Vous pouvez sélectionner **Tous** pour traduire votre projet dans toutes les langues disponibles.

   >[!NOTE]
   >
   > La liste contient les dossiers de langue ainsi que leurs codes de langue. Par exemple, Français \(fr\) et Allemand \(de\).

   >[!IMPORTANT]
   >
   > La langue affiche uniquement les langues pour lesquelles un dossier de langues est créé parallèlement à la langue source. Un dossier de langue créé à un autre niveau, tel qu’un niveau inférieur du dossier de langue source, n’est pas non plus affiché. Veillez à créer tous vos dossiers de langue cible au même niveau que votre dossier de langue source.

   ![](images/translation-languages.png){width="350" align="left"}

1. Vous pouvez également utiliser les options suivantes :

   **Utiliser la ligne de base :** Vous pouvez sélectionner une référence pour traduire votre projet. Cliquez sur Utiliser la ligne de base et choisissez une ligne de base créée sur la carte. Tous les fichiers qui font partie de la ligne de base sélectionnée sont affichés dans la page Traduction. Une fois votre contenu traduit, vous pouvez exporter la ligne de base traduite. Pour plus d’informations sur l’exportation de la ligne de base traduite, voir [Exporter la ligne de base traduite](generate-output-use-baseline-for-publishing.md#id196SE600GHS).

   **Utiliser la dernière version telle quelle**: choisissez de filtrer la version des rubriques en fonction de leur date et heure de création. Lorsque vous sélectionnez une date et une heure, seule la dernière version des fichiers créés avant ou après la date et l’heure sélectionnées s’affiche.

1. Cliquez sur **Appliquer**. Une liste contenant les détails des rubriques et des ressources associées s’affiche.
1. Sélectionnez les rubriques que vous souhaitez envoyer pour traduction. Vous pouvez également utiliser les options de filtrage des rubriques pour les colonnes suivantes :

   - **Titre**: titre du fichier source.  Passez la souris sur le titre du fichier source pour afficher le titre du fichier cible ou du fichier traduit.
   - **Nom du fichier**: nom du fichier source
   - **Type de fichier**: type du fichier source. Les options disponibles sont Carte, Rubrique et Image.
   - **Type de référence**: références directes ou indirectes
   - **Version**: numéro de version du fichier source
   - **Libellé de version**: libellé de la version sélectionnée du fichier source.
   - **Version cible**: numéro de version du fichier cible
   - **État du document**: état du fichier source. Les options disponibles sont Version préliminaire, In-Review et Review.
   - **Langue cible**: la langue dans laquelle vous souhaitez traduire le fichier source
   - **État de traduction**: les options disponibles sont : Désynchronisé, Copie manquante, En cours et Synchronisé.
   - **Libellé de la cible**: libellé de la version sélectionnée du fichier cible.
1. Cliquez sur **Envoyer pour traduction** dans le coin supérieur droit.

   ![](images/translation-send.png){width="800" align="left"}

1. Dans la liste déroulante, sélectionnez **Création d’un projet de traduction**.

   ![](images/translation-project-types.png){width="350" align="left"}

   Outre un nouveau projet de traduction, vous pouvez également sélectionner l’une des options suivantes :

   - Vous pouvez choisir de **Création d’une structure** uniquement pour le projet de traduction.
   - Vous pouvez choisir de **Créer un projet de traduction XLIFF** pour convertir le contenu XML au format XLIFF (XML Localization Interchange File Format). XLIFF est un format XML ouvert utilisé pour normaliser le transfert de données entre différents outils utilisés dans le processus de traduction de contenu. AEM Guides prend en charge XLIFF version 1.2. Dans un projet XLIFF, le contenu est exporté au format XLIFF standard du secteur, qui peut être fourni aux fournisseurs de traduction. Le format XLIFF permet la réutilisation potentielle des segments que vous avez déjà traduits lors de la phase de traduction.\
     Une fois le contenu XLIFF traduit, il peut être importé dans AEM Guides, créant ainsi une version traduite du projet DITA d’origine.

     >[!NOTE]
     >
     > L’exportation XLIFF fonctionne uniquement avec la configuration de traduction humaine.

   - Vous pouvez sélectionner **Créer un projet de traduction multilingue** qui inclut les tâches de traduction pour toutes les langues que vous avez sélectionnées pour la traduction. Par exemple, si vous avez sélectionné le français, l’allemand et l’espagnol, un projet contenant des tâches de traduction pour les trois langues sera créé.
   - Si vous disposez déjà d’un projet de traduction, vous pouvez ajouter des rubriques à ce projet. Sélectionnez Ajouter à **Projet de traduction existant** dans la liste Projet , puis choisissez un projet dans la liste Projet de traduction existant . Vous pouvez trier ces projets par ordre croissant ou décroissant le plus récent.

     >[!NOTE]
     >
     > Si votre projet existant est un projet de définition de la portée, &quot;\(Portée\)&quot; est ajouté dans son nom.

   - Si vous devez créer la portée d’un projet à traduire, vous pouvez sélectionner **Création d’un projet de traduction d’étendue**. Cela n’enverra pas les copies à traduire et l’état de traduction d’origine des fichiers est conservé. Il n’y a aucun impact sur la copie de langue de destination des rubriques référencées qui sont envoyées pour la définition de la portée.
1. Dans le champ **Titre du projet**, saisissez un titre pour le projet.
1. Cliquez sur **Créer** pour créer un projet de traduction.

   Un nouveau projet de traduction est créé avec la version sélectionnée des rubriques. À l’heure actuelle, un message contextuel s’affiche, confirmant que le projet de traduction a été créé. Une fois que toutes les copies de langue cible sont disponibles dans le projet de traduction, vous recevez une notification dans la boîte de réception. Une fois que les copies de langue cible sont disponibles dans le projet de traduction, vous pouvez poursuivre et lancer la tâche de traduction. Pour plus d’informations, voir [Démarrage de la tâche de traduction](translation-first-time.md#id225IK030OE8).

   >[!NOTE]
   >
   > Si vous rejetez la traduction d’une ou de plusieurs rubriques dans une tâche de traduction, la variable **En cours** l’état de traduction de toutes les rubriques rejetées revient à leur état d’origine. L’état des rubriques référencées est vérifié et rétabli en fonction de l’état de traduction le plus récent. En outre, les fichiers de traduction créés dans le projet de destination ne sont pas supprimés même si la traduction est refusée pour eux.

## Ajout de règles de traduction

AEM Guides permet à vos administrateurs de configurer les règles de traduction. Le format SRX (Segmentation Rules eXchange) est une norme permettant d’échanger des règles de segmentation entre différents utilisateurs et différents environnements de traduction. Vous pouvez créer un dossier et y ajouter vos fichiers SRX personnalisés.

Les fichiers SRX doivent être nommés comme `<language-code>.srx`. Par exemple, en-US ou ar-AE.

>[Remarque]
>Le titre n’est pas sensible à la casse. Vous pouvez donc avoir &quot;en-US&quot;, &quot;en-us&quot; ou &quot;EN-us&quot;. En outre, AEM guides peuvent résoudre &quot;-&quot; (trait d’union) ou &quot;_&quot; (trait de soulignement). Vous pouvez donc avoir &quot;en-US&quot; ou &quot;en_US&quot;.

En outre, vous pouvez placer ces fichiers dans n’importe quel dossier sous AEM racine de ressources qui est `./content/dam`.



Une fois que vous avez créé le dossier contenant les fichiers SRX, vous pouvez ajouter le chemin d’accès au dossier dans la configuration de l’emplacement de Traduction SRX dans votre profil de dossiers.

Pour de meilleures performances, il est recommandé de ne conserver que les fichiers SRX dans le dossier configuré dans le profil de dossiers.


AEM Guides sélectionne les règles SRX en fonction de la langue source du projet de traduction. Il recherche un fichier SRX personnalisé pour une langue. Si vous ne définissez pas de fichier SRX personnalisé, il sélectionne les règles conformément aux règles de traduction prêtes à l’emploi.


Pour plus d’informations sur la configuration des profils globaux et au niveau du dossier, voir *Configuration de modèles de création* dans la section Installation et configuration de Adobe Experience Manager Guides as a Cloud Service.

## Transmettre le libellé de la version à la version cible

AEM Guides vous permet de transmettre le libellé du fichier source au fichier cible. Vous pourrez ainsi identifier facilement la version source du fichier traduit.

Pour ajouter le libellé de la version source dans la copie cible, votre administrateur système doit sélectionner l’option . **Propager les libellés de version source à la version cible** sous le **Traduction** dans **Paramètres de l’éditeur**.

Par exemple, si vous disposez de fichiers source avec le libellé de version `Release 1.0` qui leur sont appliquées, vous pouvez également transmettre l’étiquette source \(`Release 1.0`\) au fichier traduit.

![](images/translation-pass-source-label.png){width="650" align="left"}

>[!NOTE]
>
> Le libellé source n&#39;est joint qu&#39;à une seule version cible. Si vous déplacez le libellé source vers une autre version, il est automatiquement repris dans le dernier libellé cible.

## Afficher la différence de version pour les fichiers de désynchronisation 

AEM Guides permet de vérifier les différences entre la version sélectionnée et la dernière version source traduite des rubriques. Vous pouvez choisir de traduire le **Désynchronisé** en fonction des modifications apportées.

![](images/translation-version-diff.png){width="800" align="left"}

Sélectionnez la variable **Afficher la différence** icon \(![](images/show-difference-icon.svg)\) pour une rubrique afin d’afficher les différences entre la dernière version traduite et la version actuelle du fichier sélectionné.

>[!NOTE]
>
> **Afficher la différence** icon \(![](images/show-difference-icon.svg)\) apparaît uniquement pour les fichiers DITA dont l’état de traduction est **Désynchronisé**.

La variable **Différence entre les versions** s’affiche. Elle affiche la variable **Dernière version traduite** et la variable **Version sélectionnée** numéro à gauche. La fenêtre d’aperçu affiche les différences entre la dernière version traduite et la version sélectionnée de la rubrique.

![](images/version-diff.png){width="650" align="left"}

## Ignorer les ressources désynchronisées

Si vous apportez des modifications à certaines ressources, celles-ci deviennent désynchronisées. Vous pouvez soit retraduire les ressources modifiées, soit choisir d’ignorer l’état Désynchronisé . Par exemple, si vous avez apporté des modifications très mineures qui n’ont vraiment pas besoin de traduction, vous pouvez marquer leur état sur Synchronisé.

Pour ignorer l’état de désynchronisation, procédez comme suit :

1. Sélectionnez les ressources désynchronisées pour lesquelles vous souhaitez modifier l’état.
1. Sélectionnez la variable **Marquer comme synchronisé** bouton \(![](images/translation-mark-in-sync-icon.svg)\) en haut. La variable **Marquer comme synchronisé** s’affiche.

   ![](images/translation-mark-in-sync.png){width="550" align="left"}

1. Cliquez sur **Synchronisation des forces**. Elle définit l’état sur En synchronisation pour les ressources désynchronisées sélectionnées.

>[!NOTE]
>
> **Marquer comme synchronisé** bouton \(![](images/translation-mark-in-sync-icon.svg)\) s’affiche uniquement pour les ressources dont l’état de traduction est Désynchronisé.

## Projets de traduction Afficher en cours pour une carte ou une rubrique

Certaines des références de votre tableau de bord de traduction peuvent être à l’état en cours. Ces références comportent une **En cours** lien sous **État de traduction** colonne . Lorsque vous cliquez sur le lien, la variable **Projets en cours** s’ouvre. Dans la boîte de dialogue, vous pouvez voir la liste de tous les projets de traduction en cours \(avec la langue cible\) qui contiennent la référence sélectionnée.

>[!NOTE]
>
> Vous pouvez voir le lien En cours pour les projets traduits créés dans AEM Guides as a Cloud Service de février 2023 ou version ultérieure.

Cliquez sur le nom de la référence dans la boîte de dialogue pour l’ouvrir en mode aperçu. Vous pouvez également cliquer sur le projet de traduction pour commencer la traduction.

![](images/translation-in-progress.png){width="550" align="left"}

**Rubrique parente :**[ Utilisation de l’éditeur web](web-editor.md)
