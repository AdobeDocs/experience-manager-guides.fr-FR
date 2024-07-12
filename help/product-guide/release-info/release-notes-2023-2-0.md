---
title: Notes de mise à jour | Adobe Experience Manager Guides as a Cloud Service, version de février 2023
description: Version de février d’Adobe Experience Manager Guides as a Cloud Service
exl-id: c639b136-11ed-4a8b-a595-4bb5da879747
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '870'
ht-degree: 1%

---

# Version de février 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cette note de mise à jour traite des instructions de mise à niveau, de la matrice de compatibilité et des problèmes résolus dans la version de février 2023 d’Adobe Experience Manager Guides (appelée ultérieurement *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de février 2023 de la version AEM Guides as a Cloud Service](whats-new-2023-2-0.md).

## Mise à niveau vers la version de février 2023

Mettez à niveau votre configuration AEM Guides as a Cloud Service actuelle en procédant comme suit :
1. Extrayez le code Git des Cloud Service et passez à la branche configurée dans le pipeline Cloud Service correspondant à l’environnement que vous souhaitez mettre à niveau.
2. Mettez à jour la propriété `<dox.version>` dans le fichier `/dox/dox.installer/pom.xml` de votre code Git Cloud Service vers 2023.2.235.
3. Validez les modifications et exécutez le pipeline Cloud Service pour effectuer la mise à niveau vers la version de février 2023 d’AEM Guides as a Cloud Service.

## Procédure d’indexation du contenu existant (uniquement si vous utilisez une version antérieure à la version de septembre d’AEM Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte :

* Exécutez une requête de POST sur le serveur (avec l’authentification correcte) - `http://<server:port>/bin/guides/map-find/indexing`.
(Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées. || Exemple : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Par exemple : http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Une fois la tâche terminée, la requête de GET ci-dessus répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par la version de février 2023 d’AEM Guides as a Cloud Service.

### FrameMaker et FrameMaker Publishing Server

| Version AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.02.0 | Non compatible | 2022 ou version ultérieure |
| | | |

*Les conditions de base et créées dans AEM sont prises en charge dans les versions FMPS à partir de 2020.2.

### Connecteur Oxygen

| Version AEM Guides as a Cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.02.0 | 2.8-uuid-8 | 2.8-uuid-8 | 2,3 | 2,3 |
|  |  |  |  |

## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

### Création

* Les modifications dans le code HTML de l’éditeur web provoquent des problèmes avec `<dl>` et `<dlentry>`. (11024)
* Certains attributs ne sont pas traités comme conditionnels et posent des problèmes. (10895)
* Trois niveaux ou plus imbriqués `<indexterm>` ne sont pas imbriqués dans l’exportation native de PDF. (10799)
* Le contenu disparaît dans le corps d’une tâche lors du passage de la vue Auteur à la vue Source. (10735)
* Les commentaires de révision sont déplacés dans une tâche de révision. (10625)
* **Annuler** ou **Rétablir** ne fonctionne pas correctement sur certains fichiers. 10373)
* Les métadonnées personnalisées ne sont pas conservées lors de l’action copier-coller. (10367)
* L’option Annuler de l’éditeur XML permet à l’utilisateur d’accéder au haut de la page. 10091
* Les propriétés de noeud sont supprimées après l’opération de copier-coller d’une ressource. (10053)
* mimeType est codé en dur pour la création et la mise à jour de ressources DITA. (8979)
* Le nom du créateur de versions dans l’historique de version est &quot;fmdita-serviceuser&quot; pour les fichiers chargés via l’interface utilisateur d’Assets. (8910)
* Les fragments de contenu ne peuvent pas être copiés et collés lorsqu’AEM Guides est installé sur le cloud. (11315)
* Le navigateur (éditeur web) se bloque lors du chargement de contenu avec un schéma personnalisé. (11211)

### Gestion

* La copie d’une ressource de mappage DITA (à partir de l’interface utilisateur d’Asset ) entraîne des lignes de base erronées dans la ressource copiée. (11218)
* Le message d’avertissement ne s’affiche pas lors du téléchargement d’un fichier qui est supérieur à la limite autorisée dans AEM (2 Go par défaut). (10817)
* Ligne de base de l’éditeur web | Le comportement de la colonne Dernière colonne est différent dans le nouveau tableau de bord de ligne de base de l’éditeur web. 10808
* Traduction | La tâche de traduction ne démarre pas en raison d’un /libs/fmdita/i18n/ja.json non valide. 10543
* Traduction | Une erreur se produit dans un projet de traduction de portée créé à partir du tableau de bord de traduction (Traduction humaine). 10526
* Traduction | Le traitement Post est bloqué pour l’ensemble du dossier de langue dont les ressources sont présentes dans un projet de traduction actif. (10332)
* Plusieurs fenêtres contextuelles s’affichent pour n’importe quelle ressource si la version est modifiée et enregistrée dans l’éditeur de ligne de base. 10399)
* La fuite de session se produit à `com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210)`. (10279)

### Publication

* La régénération de rubrique ne fonctionne pas dans certains scénarios. (10635)
* L’écouteur de publication n’affiche pas les données demandées dans les journaux d’informations et contient également des journaux indésirables.(10567)
* PDF natif | Lors de la création d’un paramètre prédéfini de sortie avec l’option &quot;Ajouter au profil de dossier&quot;, la génération du PDF échoue avec une exception de pointeur de valeur NULL. (10950)
* PDF natif | Les problèmes se produisent lors de la rotation de l’en-tête du tableau. (10555)
* PDF natif | Les `<indexterm>` imbriqués ne sont pas imbriqués dans l’exportation native de PDF. (10521)
* PDF natif | Les topicref imbriqués dans les appendices sont tous transformés en h1 dans l’HTML temporaire. (10454)
* La publication de ligne de base échoue pour le PDF généré à l’aide de FrameMaker Publishing Server 2020. (10551)
* PDF natif | L’ajout de `xref` à une image n’effectue pas le rendu de l’image sur le PDF généré. (11346)
* PDF natif | La balise d’image ajoute un attribut display-inline à toutes les images. 10653)
* PDF natif | Les commentaires en version préliminaire sont masqués par défaut dans la sortie générée. (10560)
* PDF natif | navtitle n’est pas honoré pour topichead. 10509)
