---
title: Notes de mise à jour | Adobe Experience Manager Guides version 4.2
description: Découvrez les correctifs et comment effectuer une mise à niveau vers la version 4.2 d’Adobe Experience Manager Guides
exl-id: 8a7fef77-63af-462f-89c5-054ab31e079b
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/NYtiFRSNt197F9PWTh8q-CyhpZz4F8pSFIQgph0twKk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 1409
ht-degree: 5%

---

# Version 4.2 d’Adobe Experience Manager Guides (février 2023)

Cette note de mise à jour couvre les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans la version 4.2 d’Adobe Experience Manager Guides (plus tard appelée *AEM Guides*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version 4.2 d’Adobe Experience Manager Guides](whats-new-4-2-release.md).

## Mise à niveau vers la version 4.2 d’AEM Guides

Vous pouvez facilement mettre à niveau votre version actuelle d’AEM Guides vers la version 4.2. Avant de procéder à la mise à niveau vers la version 4.2 d’AEM Guides, vous devez tenir compte des points suivants :
* Si vous utilisez la version 4.0, 4.1 ou 4.1.x, vous pouvez directement effectuer la mise à niveau vers la version 4.2.
* Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
* Si vous utilisez une version antérieure à la version 3.8.5, reportez-vous à la section *Mise à niveau d’AEM Guides* du guide d’installation spécifique au produit.

>[!NOTE]
>
>Vous devez installer le pack de services AEM avant de mettre à niveau la version d’AEM Guides.

Pour plus d’informations, voir [Instructions de mise à niveau](assets/Adobe-Experience-Manager-Guides-Upgrade-Instructions-EN.pdf).

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version 4.2 d’AEM Guides.

### Adobe Experience Manager

**Non-UUID**
Version 6.5 Service Pack 15, 14, 13 ou 12

**UUID**
Version 6.5 Service Pack 15, 14, 13 ou 12

Pour plus d’informations, consultez la section *Exigences techniques* du guide Installation et configuration d’Adobe Experience Manager Guides .

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.2 (non-UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.3 ou version ultérieure |
| 4.2 (UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.4 ou version ultérieure |
| | | | | |

*La ligne de base et les conditions créées dans AEM sont prises en charge dans les versions FMPS à compter de 2020.2.

### Connecteur D&#39;Oxygène

| Version | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.2 (non-UUID) | 2.1-standard-4 | 2.1-standard-4 | 1,6 | 1,6 |
| 4.2 (UUID) | 2.8-uuid-8 | 2.8-uuid-8 | 2,3 | 2,3 |
|  |  |   |  |  |

## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :

### Création

* Le panneau de gauche s’interrompt lors de l’ajout d’un onglet. (11126)
* Les modifications apportées au code HTML de l’éditeur web entraînent des problèmes avec `<dl>` et `<dlentry>`. (11024)
* Certains attributs ne sont pas traités comme conditionnels, ce qui entraîne des problèmes. (10895)
* Trois niveaux ou plus de `<indexterm>` imbriqués ne sont pas imbriqués dans l’exportation native de PDF. (10799)
* Le contenu disparaît dans le corps d’une tâche lors du passage de la vue Auteur à la vue Source. (10735)
* Les commentaires de révision sont déplacés dans une tâche de révision. (10625)
* `<conref>` note à l’intérieur d’une balise para ne s’affiche pas en mode aperçu. (10559)
* Appuyer sur la touche Retour arrière à la fin d’un élément de liste supprime la liste entière. (10540)
* Dans Chrome v106, l’écran s’affiche comme vide lorsque vous effectuez un glisser-déposer d’un élément de l’interface utilisateur (depuis le panneau Conditions, par exemple). (10524)
* Le bouton Retrait automatique est absent de la barre d&#39;outils dans la vue **&#x200B;**. (10448)
* Le premier caractère d’un élément de liste est parfois perdu lorsque la liste est en cours de création dans l’éditeur.( 10447)
* Les options **Annuler** ou **Rétablir** ne fonctionnent pas correctement sur certains fichiers. (10373)
* Les métadonnées personnalisées ne sont pas conservées lors de l’action de copier-coller. (10367)
* Une erreur se produit lors de la copie (ctrl+c) et du collage (ctrl+v) du contenu. (10304)
* Le panneau Plan n’affiche pas le contenu lors du passage du mode Auteur au mode Source. (10296)
* Un sous-mappage n&#39;est pas créé lorsqu&#39;il fait référence à un mappage principal dans les modèles DITA. (10231)
* Des problèmes de navigation se produisent dans l’éditeur web après la mise à niveau vers la version 4.0. (10159)
* L’option Annuler dans l’éditeur XML redirige l’utilisateur en haut de la page. (10091)
* Les propriétés de nœud sont supprimées après l’opération de copier-coller d’une ressource. (10053)
* Les fichiers SVG ajoutés aux rubriques DITA ne sont pas affichés en mode Aperçu de l&#39;éditeur. (10010)
* Les résultats de recherche pour la recherche et le remplacement dans l’éditeur web ne sont pas lisibles en mode sombre. (9978)
* Aucun chargeur n’existe lors de la création d’un mappage à partir du modèle de mappage. (9891)
* La référence dans le modèle de rubrique ne fonctionne pas et l’ID de hachage copié n’est pas mis à jour dans la copie de contenu. (9890)
* Aucune option ne s’affiche pour parcourir les rubriques ou le modèle de mappage à l’intérieur des sous-dossiers de la rubrique ou du dossier de mappage. (9889)
* Pas d&#39;option pour créer un nouveau modèle sur les sous-dossiers des rubriques ou des cartes. (9888)
* L’éditeur XML ne met pas à jour les images sur les rubriques. (9500)
* mimeType est codé en dur pour la création et la mise à jour de ressources DITA. (8979)
* Un trait d&#39;union normal est inséré lors de la sélection du trait d&#39;union insécable dans la boîte de dialogue **Insérer un caractère spécial**. (8919)
* Le nom du créateur de la version dans l’historique des versions est « fmdita-serviceuser » pour les fichiers chargés via l’interface utilisateur d’Assets. (8910)
* L’option Modifier ne fonctionne pas pour les images lorsque vous travaillez en mode Colonnes de l’interface utilisateur d’Assets. (8758)
* La rubrique DITA n&#39;est pas mise à jour automatiquement avec les modifications effectuées sur la page **Propriétés**. (8745)
* Lors du déplacement d’éléments dans la rubrique dans l’éditeur web, les identifiants affectés aux éléments sont remplacés par des identifiants affectés automatiquement. (7895)

### Gestion

* La copie d&#39;une ressource de plan DITA (à partir de l&#39;interface utilisateur des ressources ) entraîne des références erronées dans la ressource copiée. (11218)
* Un message d&#39;avertissement ne s&#39;affiche pas lors du téléchargement d&#39;un fichier dont la taille est supérieure à la limite autorisée dans AEM (2 Go par défaut). (10817)
* Ligne de base de l’éditeur web | Le comportement de la colonne Dernière est différent dans le nouveau tableau de bord de ligne de base de l’éditeur web. (10808)
* La tâche de traduction | Traduction ne démarre pas en raison d’une /libs/fmdita/i18n/ja.json non valide. (10543)
* Traduction | Une erreur se produit dans un projet de traduction de portée créé à partir du tableau de bord de traduction (traduction humaine). (10526)
* Traduction | Le post-traitement est bloqué pour l’ensemble du dossier de langue dont les ressources sont présentes dans un projet de traduction actif. (10332)
* Traduction| Les métadonnées et les balises ne sont pas propagées aux copies traduites. (4696)
* Plusieurs pop-ups s’affichent pour une ressource si la version est modifiée et enregistrée dans l’éditeur Ligne de base. (10399)
* Une fuite de session se produit à l’adresse com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210). (10279)
* Le fichier vidéo est absent de la ligne de base si le nom du dossier parent contient de l’espace. (10031)

### Publication

* La régénération de rubrique ne fonctionne pas pour certains scénarios. (10635)
* La publication PDF échoue lors de la génération de la sortie d’un paramètre prédéfini en double (d’un paramètre prédéfini existant). (10584)
* Le bouton Afficher le journal ne fonctionne pas si la génération PDF échoue pour un préréglage. (10576)
* Publishlistener n&#39;affiche pas les données demandées dans les journaux d&#39;informations et contient également des journaux inutiles.( 10567)
* La génération native de PDF | PDF échoue avec une exception de pointeur nul. (10950)
* Native PDF | conkeyref n’est pas résolu dans la sortie générée. (10564)
* Native PDF | Des problèmes se produisent avec les métadonnées d’un mappage qui doit être référencé dans la sortie PDF.( 10556)
* Native PDF | Des problèmes se produisent lors de la rotation de l’en-tête du tableau. (10555)
* Native PDF | Des problèmes se produisent lors de la suppression des rubriques ayant le rôle de traitement=&#39;resource-only&#39;. (10554)
* PDF natif | Les clés vides sont affichées dans la sortie PDF. (10553)
* PDF natif | Les `<indexterm>` imbriqués ne sont pas imbriqués dans l’exportation PDF native. (10521)
* Native PDF | Native PDF utilise un style intégré au lieu du nom de classe pour les balises générées. (10498)
* Native PDF | Les rubriques imbriquées dans les annexes sont toutes transformées en h1 dans l’HTML temporaire.( 10454)
* Native PDF | Impossible de masquer les rubriques de front-office de la table des matières. (10355)
* PDF natif | Attribut de cadre de table non propagé à l’HTML temporaire (en tant que classe). (10353)
* Native PDF | Fichiers HTML temporaires ajoutez les classes colsep et rowsep à . <td> et <th> même si leur valeur est 0 dans la DITA source. (10352)
* PDF natif | Le redémarrage des numéros de page dans la disposition des chapitres lance la numérotation de manière aléatoire à partir de la fin du chapitre précédent. (10154)
* PDF natif | Les références clés pour les keydefs avec image ou liens externes ne sont pas résolues. (10063)
* PDF natif | L’annexe s’affiche sous la forme d’un chapitre dans le PDF généré. (9829)
* L’onglet Modèle dans l’éditeur xml n’est pas affiché pour les administrateurs de profil de dossier. (10266)
* La publication de référence échoue pour PDF généré à l’aide de FrameMaker Publishing Server 2020. (10551)
* Une erreur d’application se produit en cliquant sur le bouton Modifier après avoir sélectionné tous les paramètres prédéfinis via la case à cocher Paramètres prédéfinis de sortie dans le pop-up de génération rapide. (10388)
* Si l’onglet Sortie dans l’éditeur web comporte d’autres paramètres prédéfinis, la section Paramètres prédéfinis ne peut pas défiler verticalement et n’affiche pas tous les paramètres prédéfinis disponibles. (9787)
* Impossible de supprimer les paramètres prédéfinis du workflow de sortie lors de la publication via l’éditeur. (9100)
* Le lien d’homologue est rendu en tant que texte normal au lieu d’un lien sur la page générée. (7774)

## Problème connu

Adobe a identifié le problème connu suivant pour la version AEM Guides 4.2 :

* Les utilisateurs et utilisatrices peuvent effectuer des opérations de révision même une fois la tâche de révision terminée.
