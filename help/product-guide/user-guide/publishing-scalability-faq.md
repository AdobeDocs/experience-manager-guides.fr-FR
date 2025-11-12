---
title: FAQ sur les performances et l’évolutivité de la publication dans Adobe Experience Manager Guides
description: Découvrez les questions fréquentes sur les performances et l’évolutivité de la publication dans Adobe Experience Manager Guides.
source-git-commit: d128860bdff78c100ba348b54a237b237171635f
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 0%

---

# Questions fréquentes

Vous trouverez ci-dessous une liste de réponses aux questions fréquentes qui fournit des informations détaillées sur la manière dont Adobe Experience Manager Guides gère les workflows de publication, le comportement de mise à l’échelle et les performances de l’infrastructure. Il est destiné aux utilisateurs de l’entreprise, aux administrateurs et aux équipes de documentation qui utilisent Experience Manager Guides pour une publication à grande échelle. Le diagramme décrit le workflow global de l’architecture de publication Experience Manager Guides.

![](images/IO_runtime.drawio.png){align="left"}


## Combien de requêtes de publication Experience Manager Guides peut-il exécuter par jour ?

Le nombre de requêtes de publication que Experience Manager Guides peut traiter par jour dépend de la taille et du type de contenu. Selon la configuration, le système autorise une tâche de publication par cœur de processeur. Dans la configuration actuelle, 20 tâches de publication peuvent s’exécuter en parallèle (2 pods × 10 cœurs chacun).

Lorsque l’environnement de production se met à l’échelle automatiquement, ce nombre peut passer à 40 tâches de publication simultanées lorsque les capsules se mettent à l’échelle jusqu’à 4.

## Combien de requêtes de publication peuvent s’exécuter simultanément avant d’être mises en file d’attente ?

- Minimum (par défaut) : 20 traitements de publication (2 capsules)
- Maximum (à l’échelle) : 40 tâches de publication (4 capsules)

Ce nombre peut varier en fonction de la charge globale du serveur. Si d’autres tâches Sling en arrière-plan sont en cours d’exécution, elles partagent des cœurs de traitement, ce qui peut réduire la simultanéité à moins de 20.

## L’exécution de plusieurs requêtes de publication a-t-elle une incidence sur d’autres fonctionnalités d’application telles que la modification des fichiers .dita ?

Il peut y avoir un impact sur les performances, mais il est généralement minimal. La plupart des traitements importants sont effectués sur l’exécution d’E/S (service de publication sans serveur), tandis que l’instance AEM effectue principalement des opérations d’E/S pour la génération de dépendances et l’interrogation de statut. Par conséquent, l’utilisation de CPU dans AEM reste faible et les expériences de création/modification ne sont généralement pas affectées.

## Comment Experience Manager Guides gère-t-il les fichiers volumineux et les graphiques tels que les fichiers SVG ou .dita de plus de 500 Ko ?

Tous les fichiers volumineux sont compressés et stockés dans le JCR (Java Content Repository). L’exécution d’E/S récupère le package ZIP complet avant de lancer la publication. Même lors de la gestion de plusieurs fichiers volumineux (par exemple, 500 Ko chacun), cela n’affecte pas considérablement la vitesse de téléchargement ou de transfert en raison de l’optimisation du conditionnement et de la gestion des E/S parallèles.

## Quelle est l’infrastructure et la configuration de publication utilisées par Experience Manager Guides ?

Experience Manager Guides utilise des microservices conteneurisés et sans serveur pour la publication. Chaque nouvelle version du service de publication est publiée en tant qu’image Docker, automatiquement déployée dans l’environnement cloud d’Adobe. Cette conception permet d’assurer les éléments suivants :

- Pas de maintenance d’infrastructure dédiée pour les clients
- Mise à l’échelle automatique pour gérer la demande de publication
- Mises à jour rapides et temps d’arrêt minimal

## Si la file d’attente de publication ou le système de gestion se bloque en raison d’une surcharge, d’autres fonctionnalités AEM seront-elles affectées ?

Non, le Experience Manager Guides est doté d&#39;une architecture tolérante aux pannes. Si la file d’attente de publication est surchargée, les requêtes sont automatiquement relancées et les capsules sont automatiquement redimensionnées pour gérer la charge supplémentaire. Au-delà d’un certain seuil, la limitation de charge est appliquée pour maintenir la stabilité. Les autres domaines d’application (création, révision et gestion des ressources) ne sont pas affectés.

## Existe-t-il un outil de surveillance ou un accès au journal disponible pour identifier le moment où Experience Manager Guides est soumis à une charge importante (similaire à la surveillance Jenkins) ?

Non, vous n’avez actuellement pas accès aux outils de surveillance interne. Pour les équipes internes d’Adobe, la surveillance peut être effectuée à l’aide des méthodes suivantes :

- Splunk pour le suivi des journaux et des erreurs
- Interface de ligne de commande Kubernetes (K8s) pour vérifier les performances au niveau des capsules et le comportement de mise à l’échelle

Si une dégradation des performances est constatée, les clients doivent contacter l’assistance Adobe pour lancer une enquête et une analyse.

## Quel traitement est effectué avant d’envoyer une requête de publication au microservice ?

Lorsque vous déclenchez une requête de publication à partir de l’onglet Paramètres prédéfinis dans la console Mappage , les étapes suivantes se produisent :

1. Le système accepte la demande et valide les paramètres prédéfinis de base et conditionnels.
2. AEM agrège toutes les ressources et dépendances DITA éligibles.
3. Ces ressources sont regroupées dans un package zip.
4. Le service de publication sans serveur génère un conteneur Docker, télécharge les ressources, exécute l’opération de publication et replace les artefacts de sortie générés dans Experience Manager Guides.

Ce workflow garantit une exécution de publication fiable, isolée et évolutive.

## Combien de temps une carte prend-elle avant de commencer à publier sur le conteneur de microservices et quels sont les facteurs qui définissent cette heure ?

Une requête de publication prend généralement quelques minutes avant d’être envoyée au conteneur de microservices. Cette heure initiale est utilisée pour l’agrégation des dépendances dans AEM.

Une fois la requête reçue sur le service de publication sans serveur, la durée totale de publication dépend des éléments suivants :

- Taille du plan DITA
- Nombre de sujets et de ressources multimédias
- Complexité du contenu conditionnel et des règles de mise en forme

La publication de cartes plus grandes ou plus complexes peut prendre proportionnellement plus de temps.

## Experience Manager Guides peut-il donner la priorité aux demandes de publication dans la file d’attente (au lieu de premier arrivé, premier servi) ?

Actuellement, tous les travaux de publication sont traités de la même manière et suivent un modèle de premier arrivé, premier servi (FCFS). Il n’existe actuellement aucun mécanisme de hiérarchisation.

Cependant, dans les prochaines versions, la logique de hiérarchisation (par exemple, en fonction de la taille de la tâche ou de l’importance commerciale) pourrait être introduite dans le cadre des améliorations de l’optimisation des files d’attente.

## Comment Experience Manager Guides gère-t-il la mise à l’échelle automatique pour les requêtes de publication ?

L’infrastructure de publication Experience Manager Guides prend en charge la mise à l’échelle automatique en fonction de la charge. Lorsque la demande de publication augmente :

- Des capsules supplémentaires (conteneurs) sont automatiquement émulées.
- Chaque pod peut traiter plusieurs tâches de publication en parallèle.
- Une fois la charge réduite, les capsules sont réduites pour optimiser les coûts et les performances.

Cela garantit une haute disponibilité, des performances cohérentes et un temps d’attente minimal pendant la charge maximale.

## Que se passe-t-il si une tâche de publication échoue ou expire ?

Si une demande de publication échoue en raison d’un problème transitoire (par exemple, une interruption du réseau, un délai d’expiration du service) :

- une nouvelle tentative est automatiquement effectuée en fonction de la logique de reprise configurée dans le service de publication.
- les journaux et les messages d’erreur sont capturés dans le serveur principal à des fins de diagnostic.
- vous pouvez afficher le statut d’échec et réessayer de publier manuellement à partir de la console Mappage si nécessaire.

## Pouvez-vous surveiller ou suivre la progression d’une tâche de publication ?

Oui, Experience Manager Guides fournit des mises à jour en temps réel de l’état des tâches dans l’onglet Paramètres prédéfinis de la console Carte, notamment :

- Heure de début et d’achèvement de la tâche
- Étape actuelle (compression, répartition, publication ou chargement des résultats)
- Notifications d&#39;erreur (le cas échéant)

Cela vous aide à comprendre la progression du travail et à identifier les retards potentiels.

## Quelles sont les bonnes pratiques permettant d’améliorer les performances de publication dans Experience Manager Guides ?

Pour garantir une vitesse de publication optimale, suivez ces bonnes pratiques :

- Évitez les fichiers image volumineux inutiles ou les rubriques non référencées
- Utiliser des lignes de base pour limiter la portée de la publication
- Gardez les hiérarchies de plan DITA gérables et bien organisées
- Planifier une publication importante en dehors des heures de pointe
- Utilisation efficace des filtres conditionnels pour réduire la charge de traitement




