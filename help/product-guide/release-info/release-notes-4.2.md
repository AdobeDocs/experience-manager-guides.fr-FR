---
title: Notes de mise à jour | Version 4.2 de Adobe Experience Manager Guides
description: Découvrez les correctifs de bogues et comment mettre à niveau vers les versions 4.2 des Guides Adobe Experience Manager.
exl-id: 8a7fef77-63af-462f-89c5-054ab31e079b
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1391'
ht-degree: 1%

---

# Version 4.2 des guides Adobe Experience Manager (février 2023)

Cette note de mise à jour traite des instructions de mise à niveau, de la matrice de compatibilité et des problèmes résolus dans la version 4.2 des Guides Adobe Experience Manager (appelés ultérieurement *Guides d’AEM*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version 4.2 des guides Adobe Experience Manager](whats-new-4.2-release.md).

## Mise à niveau vers la version 4.2 des Guides AEM

Vous pouvez facilement mettre à niveau votre version actuelle des AEM Guides vers la version 4.2. Avant de procéder à la mise à niveau vers la version 4.2 des Guides d’AEM, vous devez tenir compte des points suivants :
* Si vous utilisez la version 4.0, 4.1 ou 4.1.x, vous pouvez directement effectuer la mise à niveau vers la version 4.2.
* Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
* Si vous utilisez une version antérieure à 3.8.5, reportez-vous à la section *Mise à niveau AEM guides* dans le guide d’installation spécifique au produit.

>[!NOTE]
>
>Vous devez installer AEM Service Pack avant de mettre à niveau AEM version de Guides.

Pour plus d’informations, voir [Instructions de mise à niveau](assets/Adobe-Experience-Manager-Guides-Upgrade-Instructions-EN.pdf).

## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par AEM Guides 4.2.

### Adobe Experience Manager

**Non UUID**
Version 6.5 Service Pack 15, 14, 13 ou 12

**UUID**
Version 6.5 Service Pack 15, 14, 13 ou 12

Pour plus d’informations, voir *Exigences techniques* dans le guide d’installation et de configuration de Adobe Experience Manager Guides.

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.2 (non UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.3 ou version ultérieure |
| 4.2 (UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.4 ou version ultérieure |
| | | | |

*Les conditions de base et créées dans AEM sont prises en charge dans les versions FMPS à partir de 2020.2.

### Connecteur Oxygen

| Version | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.2 (non UUID) | 2.1-normal-4 | 2.1-normal-4 | 1,6 | 1,6 |
| 4.2 (UUID) | 2.8-uuid-8 | 2.8-uuid-8 | 2,3 | 2,3 |
|  |  |   |

## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

### Création

* Le panneau de gauche se casse lors de l’ajout d’un onglet. (11126)
* Les modifications dans le code HTML de l’éditeur Web entraînent des problèmes avec `<dl>` et `<dlentry>`. (11024)
* Certains attributs ne sont pas traités comme conditionnels et posent des problèmes. (10895)
* Trois niveaux ou plus imbriqués `<indexterm>` ne sont pas imbriqués dans l’exportation de PDF natif. (10799)
* Le contenu disparaît dans le corps d’une tâche lors du passage de la vue Auteur à la vue Source. (10735)
* Les commentaires de révision sont déplacés dans une tâche de révision. (10625)
* `<conref>` remarque à l’intérieur d’une balise para ne s’affiche pas en mode aperçu. (10559)
* Lorsque vous appuyez sur Retour arrière à la fin d’un élément de liste, toute la liste est supprimée. (10540)
* L’écran s’affiche comme vide dans Chrome v106 lors du glisser-déposer d’un élément de l’interface utilisateur (par exemple, dans le panneau Conditions ). 10524)
* Le bouton Retrait automatique est manquant dans la barre d’outils de la **Source** vue. 10448
* Le premier caractère d’un élément de liste est parfois perdu lorsque la liste est en cours de création dans l’éditeur.(10447)
* **Annuler** ou **Rétablir** ne fonctionne pas correctement sur certains fichiers. 10373)
* Les métadonnées personnalisées ne sont pas conservées lors de l’action copier-coller. (10367)
* Une erreur se produit lors de la copie (ctrl+c) et du collage (ctrl+v) du contenu. 10304
* Le panneau Plan n’affiche pas de contenu lorsqu’il est passé du mode Auteur au mode Source. (10296)
* Le sous-mappage n’est pas créé lorsqu’il fait référence à un mappage principal dans les modèles DITA. (10231)
* Les problèmes de navigation se produisent dans l’éditeur web après la mise à niveau vers la version 4.0. 10159
* L’option Annuler de l’éditeur XML permet à l’utilisateur d’accéder au haut de la page. 10091
* Les propriétés de noeud sont supprimées après l’opération de copier-coller d’une ressource. (10053)
* Les fichiers de SVG ajoutés aux rubriques DITA ne s’affichent pas en mode aperçu de l’éditeur. (10010)
* Les résultats de recherche pour rechercher et remplacer dans l’éditeur web ne sont pas lisibles en mode sombre. (9978)
* Il n’existe aucun chargeur lors de la création d’une carte à partir du modèle de carte. (9891)
* La référence dans le modèle de rubrique ne fonctionne pas et l’ID de hachage copié n’est pas mis à jour dans la copie de contenu. (9890)
* Aucune option n’est affichée pour parcourir les rubriques ou le modèle de mappage dans les sous-dossiers du dossier de rubrique ou de mappage. (9889)
* Aucune option pour créer un modèle sur les sous-dossiers de rubriques ou de mappages. (9888)
* XML Editor ne met pas à jour les images sur les rubriques. (9500)
* mimeType est codé en dur pour la création et la mise à jour de ressources DITA. (8979)
* Un trait d’union normal est inséré lors de la sélection d’un trait d’union insécable dans le **Insérer un caractère spécial** boîte de dialogue. (8919)
* Le nom du créateur de versions dans l’historique de versions est &quot;fmdita-serviceuser&quot; pour les fichiers chargés via l’interface utilisateur d’Assets. (8910)
* L’option Modifier ne fonctionne pas pour les images lorsque vous utilisez le mode Colonnes de l’interface utilisateur d’Assets. (8758)
* La rubrique DITA n’est pas mise à jour automatiquement avec les modifications effectuées sur **Propriétés** page. (8745)
* Lors du déplacement d’éléments dans la rubrique dans l’éditeur web, les identifiants attribués aux éléments sont remplacés par des identifiants attribués automatiquement. (7895)

### Gestion

* La copie d’une ressource de mappage DITA (à partir de l’interface utilisateur d’Asset ) entraîne des lignes de base erronées dans la ressource copiée. (11218)
* Le message d’avertissement ne s’affiche pas lors du téléchargement d’un fichier qui est supérieur à la limite autorisée dans AEM (2 Go par défaut). (10817)
* Ligne de base de l’éditeur web | Le comportement de la colonne Dernière colonne est différent dans le nouveau tableau de bord de ligne de base de l’éditeur web. 10808
* Traduction | La tâche de traduction ne démarre pas en raison d’un /libs/fmdita/i18n/ja.json non valide. 10543
* Traduction | Une erreur se produit dans un projet de traduction de portée créé à partir du tableau de bord de traduction (traduction humaine). 10526
* Traduction | Le post-traitement est bloqué pour l’ensemble du dossier linguistique dont les ressources sont présentes dans un projet de traduction actif. (10332)
* Traduction| Les métadonnées et les balises ne sont pas propagées aux copies traduites. (4696)
* Plusieurs fenêtres contextuelles s’affichent pour n’importe quelle ressource si la version est modifiée et enregistrée dans l’éditeur de ligne de base. 10399)
* La fuite de session se produit à l’adresse com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210). (10279)
* Le fichier vidéo est absent de la ligne de base si le dossier parent contient de l’espace dans le nom. (10031)

### Publication

* La régénération de rubrique ne fonctionne pas dans certains scénarios. (10635)
* La publication du PDF échoue lors de la génération de la sortie pour un paramètre prédéfini en double (d’un paramètre prédéfini existant). 10584
* Le bouton Afficher le journal ne fonctionne pas si la génération du PDF échoue pour un paramètre prédéfini. 10576
* L’écouteur de publication n’affiche pas les données demandées dans les journaux d’informations et contient également des journaux indésirables.(10567)
* PDF natif | La génération du PDF échoue avec une exception Null Pointer . (10950)
* PDF natif | conkeyref n’est pas résolu dans la sortie générée. 10564
* PDF natif | Des problèmes se produisent avec les métadonnées d’un mappage qui doit être référencé dans la sortie du PDF.(10556)
* PDF natif | Des problèmes se produisent lors de la rotation de l’en-tête du tableau. (10555)
* PDF natif | Des problèmes se produisent lors de la suppression des rubriques qui ont un rôle de traitement=&#39;resource-only&#39;. (10554)
* PDF natif | Les clés vides s’affichent en sortie PDF. 10553)
* PDF natif | Imbriqué `<indexterm>` ne sont pas imbriqués dans l’exportation de PDF natif. (10521)
* PDF natif | Le PDF natif utilise le style intégré au lieu du nom de classe pour les balises générées. (10498)
* PDF natif | La référence de topicref imbriquée dans les appendices est toutes transformée en h1 dans le HTML temporaire.(10454)
* PDF natif | Impossible de masquer les rubriques de première ligne de la table des matières. 10355
* PDF natif | L’attribut de cadre de tableau n’est pas propagé au HTML temporaire (en tant que classe). (10353)
* PDF natif | Les fichiers de HTML temporaires ajoutent les classes colsep et rowsep à <td> et <th> même si leur valeur est 0 dans le DITA source. 10352)
* PDF natif | Le redémarrage des numéros de page dans la mise en page de chapitre commence aléatoirement la numérotation à partir de la fin du chapitre précédent. 10154
* PDF natif | Les références clés des clés avec des liens d’image ou externes ne sont pas résolues. (10063)
* PDF natif | L’annexe s’affiche sous la forme d’un chapitre dans le PDF généré. (9829)
* L’onglet Modèle de l’éditeur xml n’est pas affiché pour les administrateurs de profil de dossier. (10266)
* La publication de ligne de base échoue pour le PDF généré à l’aide de FrameMaker Publishing Server 2020. (10551)
* Une erreur d’application se produit lorsque vous cliquez sur le bouton Modifier après avoir sélectionné tous les paramètres prédéfinis via la case Paramètres prédéfinis de sortie dans la fenêtre contextuelle Génération rapide . 10388
* Si l’onglet Sortie de l’éditeur web comporte davantage de paramètres prédéfinis, la section Paramètres prédéfinis ne peut pas être défilée verticalement et n’affiche pas tous les paramètres prédéfinis disponibles. (9787)
* Impossible de supprimer les paramètres prédéfinis du workflow de sortie lors de la publication via l’éditeur. (9100)
* Le lien d’homologue est rendu sous forme de texte normal au lieu d’un lien sur la page générée. (7774)

## Problème connu

Adobe a identifié le problème connu suivant pour la version 4.2 d’AEM Guides :

* Les utilisateurs peuvent effectuer des opérations de révision même une fois la tâche de révision terminée.
