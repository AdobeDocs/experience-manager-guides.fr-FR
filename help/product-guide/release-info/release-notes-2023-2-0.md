---
title: Notes de mise à jour | Adobe Experience Manager Guides as a Cloud Service, version de février 2023
description: Version de février d’Adobe Experience Manager Guides as a Cloud Service
exl-id: c639b136-11ed-4a8b-a595-4bb5da879747
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 1%

---

# Version de février 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cette note de mise à jour couvre les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans la version de février 2023 d’Adobe Experience Manager Guides (plus tard appelée *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version de février 2023 d’AEM Guides as a Cloud Service](whats-new-2023-2-0.md).

## Mise à niveau vers la version de février 2023

Mettez à niveau votre configuration AEM Guides as a Cloud Service actuelle en procédant comme suit :
1. Consultez le code Git des services cloud et passez à la branche configurée dans le pipeline des services cloud correspondant à l’environnement à mettre à niveau.
2. Mettez à jour `<dox.version>` propriété dans `/dox/dox.installer/pom.xml` fichier de votre code Git Cloud Services vers la version 2023.2.235.
3. Validez les modifications et exécutez le pipeline Cloud Services pour effectuer la mise à niveau vers la version de février 2023 d’AEM Guides as a Cloud Service.

## Procédure à suivre pour indexer le contenu existant (uniquement si vous utilisez une version antérieure à la version de septembre d’AEM Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte de recherche et de remplacement au niveau du mappage :

* Exécutez une requête POST au serveur (avec l’authentification correcte) - `http://<server:port>/bin/guides/map-find/indexing`.
(Facultatif) Vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés || Exemple : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée : `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Par exemple : http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Une fois la tâche terminée, la requête GET ci-dessus répond avec succès et mentionne si des mappages ont échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version de février 2023 d’AEM Guides as a Cloud Service.

### FrameMaker et FrameMaker Publishing Server

| Version d’AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.02.0 | Non compatible | 2022 ou version ultérieure |
| | | |

*La ligne de base et les conditions créées dans AEM sont prises en charge dans les versions FMPS à compter de 2020.2.

### Connecteur D&#39;Oxygène

| Version d’AEM Guides as a Cloud | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.02.0 | 2.8-uuid-8 | 2.8-uuid-8 | 2,3 | 2,3 |
|  |  |  |  |  |

## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :

### Création

* Les modifications apportées au code HTML de l’éditeur web entraînent des problèmes avec `<dl>` et `<dlentry>`. (11024)
* Certains attributs ne sont pas traités comme conditionnels, ce qui entraîne des problèmes. (10895)
* Trois niveaux ou plus de `<indexterm>` imbriqués ne sont pas imbriqués dans l’exportation native de PDF. (10799)
* Le contenu disparaît dans le corps d’une tâche lors du passage de la vue Auteur à la vue Source. (10735)
* Les commentaires de révision sont déplacés dans une tâche de révision. (10625)
* Les options **Annuler** ou **Rétablir** ne fonctionnent pas correctement sur certains fichiers. (10373)
* Les métadonnées personnalisées ne sont pas conservées lors de l’action de copier-coller. (10367)
* L’option Annuler dans l’éditeur XML redirige l’utilisateur en haut de la page. (10091)
* Les propriétés de nœud sont supprimées après l’opération de copier-coller d’une ressource. (10053)
* mimeType est codé en dur pour la création et la mise à jour de ressources DITA. (8979)
* Le nom du créateur de la version dans l’historique des versions est « fmdita-serviceuser » pour les fichiers chargés via l’interface utilisateur d’Assets. (8910)
* Les fragments de contenu ne peuvent pas être copiés et collés lorsqu’AEM Guides est installé sur le cloud. (11315)
* Le navigateur (éditeur web) se fige lors du chargement du contenu avec le schéma personnalisé. (11211)

### Gestion

* La copie d&#39;une ressource de plan DITA (à partir de l&#39;interface utilisateur des ressources ) entraîne des références erronées dans la ressource copiée. (11218)
* Un message d&#39;avertissement ne s&#39;affiche pas lors du téléchargement d&#39;un fichier dont la taille est supérieure à la limite autorisée dans AEM (2 Go par défaut). (10817)
* Ligne de base de l’éditeur web | Le comportement de la dernière colonne est différent dans le nouveau tableau de bord de ligne de base de l’éditeur web. (10808)
* Traduction | La tâche de traduction ne démarre pas en raison d’une /libs/fmdita/i18n/ja.json non valide. (10543)
* Traduction | Une erreur se produit dans un projet de traduction de la portée créé à partir du tableau de bord de traduction (traduction humaine). (10526)
* Traduction | Le post-traitement est bloqué pour l’ensemble du dossier de langue dont les ressources sont présentes dans un projet de traduction actif. (10332)
* Plusieurs pop-ups s’affichent pour une ressource si la version est modifiée et enregistrée dans l’éditeur Ligne de base. (10399)
* La fuite de session se produit à `com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210)`. (10279)

### Publication

* La régénération de rubrique ne fonctionne pas pour certains scénarios. (10635)
* Publishlistener n&#39;affiche pas les données demandées dans les journaux d&#39;informations et contient également certains journaux indésirables.( 10567)
* PDF natif | Lors de la création d’un paramètre prédéfini de sortie avec l’option « Ajouter au profil de dossier », la génération PDF échoue avec une exception de pointeur Null. (10950)
* PDF natif | Des problèmes surviennent lors de la rotation de l’en-tête du tableau. (10555)
* PDF natif | Les `<indexterm>` imbriqués ne sont pas imbriqués dans l’exportation PDF native. (10521)
* PDF natif | Les rubriques imbriquées dans les annexes sont toutes transformées en h1 dans l’HTML temporaire. (10454)
* La publication de référence échoue pour PDF généré à l’aide de FrameMaker Publishing Server 2020. (10551)
* PDF natif | L’ajout de `xref` à une image n’effectue pas le rendu de l’image sur le PDF généré. (11346)
* PDF natif | La balise d’image ajoute un attribut display-inline à toutes les images. (10653)
* PDF natif | Les commentaires de brouillon sont masqués par défaut dans la sortie générée. (10560)
* PDF natif | navtitle n’est pas honoré pour topichead. (10509)
