---
title: Rapport de mappage DITA à partir de l’éditeur web
description: Générez des rapports de mappage DITA à partir de l’éditeur web dans AEM Guides. Découvrez comment générer un fichier CSV pour une liste de rubriques, un fichier multimédia, des métadonnées et des rapports sur les liens rompus.
exl-id: 2f202b41-85d9-4a5a-aa28-e25715ce5e2e
feature: Report Generation
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '2366'
ht-degree: 0%

---

# Rapport de mappage DITA à partir de l’éditeur web {#id231HF0Z0NXA}

AEM Guides s’accompagne d’une fonctionnalité de l’éditeur web qui vous permet de vérifier l’intégrité globale de vos références et de générer des rapports à leur intention.

Vous pouvez afficher la liste des rubriques, gérer les métadonnées de toutes les références et afficher la liste multimédia de la carte actuelle à partir du **Rapports** dans l’éditeur Web.

## Génération d’un fichier CSV à partir de la vue Liste de rubriques

La variable **Liste des rubriques** La vue fournit des informations détaillées sur vos rubriques, telles que le type de référence, l’état du document et l’auteur.

Vous pouvez créer un rapport des rubriques en procédant comme suit :

1. Dans le **Référentiel** , ouvrez le fichier de mappage DITA en mode Carte.
1. Cliquez sur le bouton **Gérer** .
1. Double-cliquez **Liste des rubriques** sur la gauche. La liste des rubriques présentes dans le mappage DITA s’affiche.

   ![](images/web-editor-topiclist-panel.png){width="800" align="left"}

1. Dans la **Filtres** Vous pouvez filtrer vos rubriques en fonction du panneau **Type de référence** \(direct ou indirect\), **État du document** \(état actuel de vos rubriques. Si, par exemple, vos rubriques sont à l’état Modifier, En révision ou Révisé, elles sont répertoriées\) ou la variable **Auteur** de la rubrique.

1. Vous pouvez également utiliser les options de filtrage de rubrique suivantes pour choisir d’afficher les colonnes suivantes dans la liste :

   - **Rubrique** Le titre de la rubrique est spécifié dans le mappage DITA. Vous pouvez cliquer sur la rubrique pour la modifier.
   - **Nom du fichier** Nom du fichier.
   - **UUID** L’identifiant unique universelle \(UUID\) du fichier.
   - **Emplacement du fichier** Chemin d’accès complet de la rubrique.
   - **Type de référence** Type de référence : directe ou indirecte.
   - **État du document** État actuel du sujet.
   - **Auteur** L’utilisateur qui a travaillé en dernier sur le sujet.
   - **Carte parente** Liste de toutes les cartes dans lesquelles la rubrique est directement référencée.
   >[!NOTE]
   >
   > Cliquez sur **Actualiser** pour obtenir une nouvelle liste des rubriques et afficher toute modification dans votre fichier map ou si une référence dans votre fichier de rubrique est mise à jour.

1. Cliquez sur **Téléchargement de fichier CSV** pour télécharger l’instantané actuel des rubriques dans le mappage DITA. Le fichier CSV contient les colonnes sélectionnées et les rubriques filtrées dans la variable **Liste des rubriques** vue. Vous pouvez ensuite ouvrir ce fichier CSV de liste de rubriques dans n’importe quel éditeur CSV.

**Gestion des métadonnées en bloc à partir du rapport Métadonnées**

AEM Guides vous permet de baliser le contenu DITA à partir de l’éditeur web. Vous pouvez appliquer des balises sur une rubrique individuelle ou utiliser la fonction de balisage en masse pour appliquer plusieurs balises sur plusieurs rubriques, un mappage DITA ou sur une sous-map. Vous pouvez également remplacer l’état du document de toutes les rubriques sélectionnées par l’état suivant du document commun.

## Affichage des métadonnées

Pour afficher les métadonnées de vos références dans le mappage DITA actuel, procédez comme suit :

1. Dans le panneau Repository, ouvrez le fichier de mappage DITA en mode Carte.
1. Cliquez sur le bouton **Gérer** .
1. Double-cliquez **Métadonnées** sur la gauche. La liste des métadonnées de toutes les références du mappage DITA s’affiche. Cela inclut également les références aux médias.

   ![](images/web-editor-metadata-panel.png){width="800" align="left"}

1. Dans la **Filtres** vous pouvez filtrer vos rubriques en fonction des **État du document** \(état actuel de vos rubriques. Par exemple, si vos rubriques sont à l’état Modifier, En révision ou Révisé, elles sont répertoriées\), **Références** \(direct ou indirect\), **Type de fichier** \(Carte, Rubrique et Image\) de la référence.
1. Vous pouvez également choisir de n’afficher que le **Fichiers sans balise** ou sélectionnez également des balises spécifiques dans la **Balises** filtre pour afficher les fichiers qui y sont associés.
   1. Vous pouvez également utiliser les options de filtrage de rubrique suivantes pour choisir d’afficher les colonnes suivantes dans la liste des métadonnées :
      - **Titre** \(sélectionné par défaut\) Le titre du fichier référencé est spécifié dans le mappage DITA. Vous pouvez cliquer sur le fichier pour le modifier. Vous pouvez également cliquer sur un fichier audio ou vidéo et le lire dans l’éditeur Web. Vous pouvez modifier le volume ou l’affichage de la vidéo. Dans le menu contextuel, vous disposez également des options de téléchargement, de modification de la vitesse de lecture ou d’affichage de l’image.

        >[!NOTE]
        >
        > Une icône d’extraction s’affiche également près du titre d’un fichier extrait. Vous pouvez placer le pointeur de la souris sur l’icône pour afficher le nom de l’utilisateur.

      - **Nom du fichier** Nom du fichier.
      - **Emplacement du fichier** Chemin d’accès complet au fichier.
      - **Balises** \(sélectionné par défaut\) Balises appliquées au fichier.

        >[!NOTE]
        >
        > Par défaut, vous pouvez afficher deux balises pour un fichier. Pour afficher d’autres balises, cliquez sur **Afficher plus**. Cliquez sur **Afficher moins** pour contracter à nouveau la liste.

      - **Type de référence** Type de référence : directe ou indirecte
      - **État du document** \(sélectionné par défaut\) État actuel du fichier de référence.
      - **Type de fichier** \(sélectionné par défaut\) Type du fichier source. Les options disponibles sont Carte, Rubrique et Image.
      - **Extraits par** L’utilisateur qui a extrait le fichier.
1. Cliquez sur **Téléchargement de fichier CSV** pour télécharger l’instantané actuel des références dans le mappage DITA. Le fichier CSV contient les colonnes sélectionnées et les références filtrées en mode Liste des rubriques. Vous pouvez ensuite ouvrir ce fichier CSV de métadonnées dans n’importe quel éditeur CSV.

**Mise à jour les métadonnées**

1. Pour mettre à jour les métadonnées, sélectionnez les fichiers pour lesquels vous souhaitez effectuer la mise à jour.

   >[!NOTE]
   >
   > Vous ne pouvez pas sélectionner de fichiers extraits. Une icône d’extraction s’affiche également près du titre d’un fichier extrait. Vous pouvez placer le pointeur de la souris sur l’icône pour afficher le nom de l’utilisateur.

1. Sélectionner **Gérer** dans la partie supérieure.

   ![](images/web-editor-manage-metadata.png){width="350" align="left"}

1. Si vous souhaitez ajouter de nouvelles balises, sélectionnez-les dans la liste déroulante pour les appliquer à toutes les rubriques sélectionnées. Vous pouvez également supprimer une balise en cliquant sur l’icône croisée située près de la balise .

   >[!NOTE]
   >
   > Les balises courantes appliquées à toutes les rubriques sélectionnées sont répertoriées.

1. Sélectionnez un nouvel état de document si vous souhaitez modifier l’état du document de toutes les références sélectionnées. La liste déroulante affiche l’état possible commun pour toutes les rubriques sélectionnées. Par exemple, si l’état actuel de vos rubriques est En révision, vous pouvez afficher l’état Version préliminaire, Approuvé ou Révisé.
1. Cliquez sur **Mettre à jour** pour mettre à jour les métadonnées. Un message de confirmation s’affiche pour les métadonnées, qu’elles aient été mises à jour avec succès ou qu’elles aient échoué. Cliquez également sur **Télécharger le rapport** pour télécharger le fichier CSV de métadonnées à partir de la boîte de dialogue de confirmation. Ce fichier CSV contient les détails de l’état de mise à jour des références sélectionnées.

## Génération d’un rapport multimédia

La variable **Multimédia** Le rapport fournit des informations détaillées sur le contenu multimédia utilisé dans votre carte, telles que le titre, le type \(audio, vidéo et images\), les fichiers dans lesquels le contenu multimédia est utilisé, ainsi que le type de référence des fichiers dans lesquels ils ont été utilisés. Vous pouvez également afficher l’UUID et l’emplacement du fichier multimédia dans le référentiel. Vous pouvez créer un rapport du fichier multimédia en procédant comme suit :

1. Dans le **Référentiel** , ouvrez le fichier de mappage DITA en mode Carte.
1. Cliquez sur le bouton **Gérer** .
1. Double-cliquez **Multimédia** sur la gauche. La liste des fichiers multimédia présents dans la carte DITA s’affiche.
1. Dans la **Filtres** vous pouvez classer la liste par contenu multimédia ou par nom d’utilisation dans les références.

   - Lorsque vous commandez par **Multimédia**, le****nom du fichier multimédia s&#39;affiche dans la première colonne, puis le nom de toutes les références dans lesquelles il a été utilisé, s&#39;affiche dans une autre colonne sur la même ligne. Par exemple, la capture d’écran suivante montre le fichier multimédia WarmCoolForC.gif dans la première colonne et trois références dans lesquelles il est utilisé sont affichées dans la troisième colonne de la même ligne.

     ![](images/multimedia-report-file-order.png){width="650" align="left"}

   - Si vous commandez par **Utilisé dans** , vous verrez la vue transposée dans laquelle les noms des références dans lesquelles des éléments multimédias ont été utilisés sont répertoriés dans la première colonne tandis que les noms multimédias sont répertoriés dans une autre colonne sur des lignes distinctes. Par exemple, la capture d’écran suivante montre les noms de trois références \(Ajuster la température du siège, Modifier l’affichage de la température du siège et Zone d’équipage\) dans la première colonne et le fichier multimédia WarmCoolForC.gif est affiché dans la troisième colonne sur trois lignes distinctes.

     ![](images/multimedia-report-used-in-order.png){width="650" align="left"}

1. Vous pouvez filtrer votre contenu multimédia en fonction des **Type de média multimédia**, et **Type de référence**. La liste des fichiers multimédia s’affiche en fonction de la sélection que vous avez effectuée dans la liste déroulante. Par exemple, vous pouvez choisir d’afficher uniquement les références audio dans votre carte DITA, et un fichier n’affiche que les références audio utilisées.

   >[!NOTE]
   >
   > Selon le type de fichier multimédia utilisé dans votre carte, Image, Vidéo et Audio sont répertoriés dans la variable **Type de média multimédia** et Direct ou Indirect sont répertoriés dans le **Type de référence** menu déroulant.

1. Vous pouvez également utiliser les options de filtrage suivantes pour choisir d&#39;afficher les colonnes suivantes dans la liste :

   - **Multimédia** \(sélectionné par défaut\) Le titre du fichier multimédia est spécifié dans le mappage DITA. Vous pouvez cliquer sur le fichier multimédia pour le modifier.
   - **Emplacement multimédia** Chemin d’accès complet au fichier multimédia.
   - **UUID multimédia** L’identifiant unique universelle \(UUID\) du fichier.
   - **Type de média multimédia** \(sélectionné par défaut\) Type du fichier multimédia. Les options disponibles sont Audio, Vidéo ou Image.
   - **Utilisé dans** \(sélectionné par défaut\) Références dans lesquelles le fichier multimédia a été utilisé. Vous pouvez cliquer sur la référence pour la modifier.
   - **Type de référence** \(sélectionné par défaut\) Type de référence : directe ou indirecte.
   >[!NOTE]
   >
   > Cliquez sur **Actualiser** pour obtenir une nouvelle liste de fichiers multimédias et afficher toute modification dans votre fichier de carte ou si un fichier multimédia de votre carte DITA est mis à jour.

1. Vous pouvez également cliquer et lire un fichier audio ou vidéo dans l’éditeur web. Vous pouvez modifier le volume ou l’affichage de la vidéo. Dans le menu contextuel, vous disposez également des options de téléchargement, de modification de la vitesse de lecture ou d’affichage de l’image.

   ![](images/video-web-editor.png){width="800" align="left"}

1. Cliquez sur **Téléchargement de fichier CSV** pour télécharger l’instantané actuel du fichier multimédia dans la carte DITA. Le fichier CSV contient les colonnes sélectionnées et le fichier multimédia filtré dans la variable **Multimédia** vue. Vous pouvez ensuite ouvrir ce fichier CSV multimédia dans n’importe quel éditeur CSV.


## Afficher et corriger les liens rompus{#report-broken-links}

La variable **Liens rompus** est un rapport utile qui vous fournit les détails des liens rompus présents dans votre carte actuelle. Vous pouvez afficher les liens rompus, qui peuvent être destinés aux rubriques DITA, aux références de fichiers multimédia, aux références de clés de contenu, etc. Vous avez aussi la possibilité de les réparer ici même.
Le rapport fournit des informations détaillées telles que le lien rompu, le type de lien, les fichiers dans lesquels une référence est utilisée et le type de fichiers dans lesquels ils ont été utilisés.
Vous pouvez afficher le rapport pour les liens rompus en procédant comme suit :
1. Dans le **Référentiel** , ouvrez le fichier de mappage DITA en mode Carte.
1. Cliquez sur le bouton **Gérer** .
1. Double-cliquez **Liens rompus** sur la gauche. La liste des liens ou références rompus présents dans le mappage DITA s’affiche.
1. Dans la **Filtres** vous pouvez classer la liste par liens ou par noms d’éléments utilisés dans les références.

   - Lorsque vous commandez par **Lien rompu**, les chemins d’accès des liens rompus sont affichés dans la première colonne, puis les noms de toutes les références dans lesquelles ils ont été utilisés sont affichés dans une autre colonne sur des lignes distinctes. Si le même lien rompu est utilisé dans plusieurs fichiers, il s’affiche sur une ligne et s’affiche sous la forme de sous-lignes ou de groupes. Par exemple, la capture d&#39;écran suivante montre trois liens rompus dans la première colonne et la référence dans laquelle ils sont utilisés, `TestMap.ditamap` s’affiche dans la troisième colonne sur trois lignes distinctes.
   ![](images/broken-link-report.png){width="800" align="left"}

   - Si vous commandez par **Utilisé dans** , vous verrez la vue transposée dans laquelle les noms des références dans lesquelles les liens rompus ont été utilisés sont répertoriés dans la première colonne tandis que les liens rompus sont répertoriés dans une autre colonne sur la même ligne. Par exemple, la capture d’écran suivante montre la référence (dans laquelle le lien rompu est utilisé). `TestMap.ditamap` dans la première colonne et les liens rompus sont affichés dans la troisième colonne de la même ligne.
   ![](images/broken-link-filter-usedin.png){width="800" align="left"}
1. Vous pouvez filtrer vos liens rompus en fonction des **Type de fichier** et **Type de lien**. La liste des liens rompus s’affiche en fonction de votre sélection dans la liste déroulante. Par exemple, vous pouvez choisir d’afficher uniquement les références de contenu dans votre mappage DITA, et un fichier n’affiche que les références de contenu utilisées dans celui-ci.

   Selon le type de références utilisé dans votre carte, la référence de fichier, la référence de clé, la référence de contenu, la référence de clé de contenu, la référence d’image et la référence de fichier multimédia sont répertoriées dans la liste **Type de lien** et **rubrique DITA** ou **Carte DITA** sont répertoriées dans la variable **Type de fichier** menu déroulant.
1. Vous pouvez également utiliser les options de filtrage suivantes pour choisir d&#39;afficher les colonnes suivantes dans la liste :

   - **Lien rompu** (sélectionné par défaut) Le chemin d’accès du lien rompu est spécifié dans le mappage DITA.

   - **Type de lien** (sélectionné par défaut) Type des liens. Les options disponibles sont Référence de clé de contenu, Référence de contenu, Rubrique DITA, Référence de fichier, Référence d’image, Référence de clé et Référence de fichier multimédia.

   - **Utilisé dans** (sélectionné par défaut) Références dans lesquelles le lien rompu a été utilisé. Vous pouvez cliquer sur la référence pour l’afficher en mode création.

   - **Type de fichier** (sélectionné par défaut) Type de référence : carte DITA ou rubrique DITA.
Cliquez sur **Actualiser** pour obtenir une nouvelle liste des liens rompus et afficher toute modification dans votre fichier de mappage ou si un lien rompu dans votre mappage DITA est mis à jour.
1. Vous pouvez cliquer sur le bouton **Lien de correction** icône (![](images/fix-broken-link.svg)) pour corriger le lien rompu.

   >[!NOTE]
   >
   > Passez la souris sur le chemin du lien rompu sous la colonne Lien rompu pour afficher le lien Correctif (![](images/fix-broken-link.svg)).

   Vous pouvez corriger un lien dans les deux vues (lorsque vous avez ordonné la commande **Liens rompus** ou par **Utilisé dans**.

   >[!NOTE]
   >
   > Lorsque vous corrigez un lien rompu alors que vous avez trié par Liens rompus, le lien est corrigé dans tous les fichiers dans lesquels il est utilisé (qui sont regroupés dans une seule ligne).

1. Vous devez mettre à jour les détails de référence requis dans la variable **Mettre à jour le lien** boîte de dialogue. Les détails requis dans **Mettre à jour le lien** La boîte de dialogue dépend du type de référence.\
   Une fois un lien corrigé, il ne s’affiche pas sous la liste des liens rompus. Vous pouvez plutôt l’afficher sous Liste de rubriques ou Métadonnées.

1. Cliquez sur **Téléchargement de fichier CSV** pour télécharger l’instantané actuel des liens rompus dans le mappage DITA. Le fichier CSV contient les colonnes sélectionnées et les liens rompus filtrés dans la vue Liens rompus. Vous pouvez ensuite ouvrir et afficher ce fichier CSV dans n’importe quel éditeur CSV.


**Rubrique parente :**[ Rapports](reports-intro.md)
