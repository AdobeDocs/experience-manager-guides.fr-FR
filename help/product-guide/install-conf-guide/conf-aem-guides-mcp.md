---
title: Utilisation de MCP avec Adobe Experience Manager Guides
description: Découvrez comment utiliser le protocole MCP (Model Context Protocol) avec AEM Guides pour utiliser les rubriques, cartes, lignes de base et rapports via un assistant d’IA
feature: Authoring
role: User
source-git-commit: 20e5b1099b3d9a7230a40415495ba8e77f438b2a
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 0%
---

# Utilisation du serveur MCP Adobe Experience Manager Guides

Le protocole MCP (Model Context Protocol) est un moyen standard pour les assistants d’IA de se connecter à des outils et des données externes, au lieu de changer de contexte pour utiliser ces outils vous-même.

Le serveur Adobe Experience Manager Guides MCP apporte ces informations à Experience Manager Guides. Il permet à un assistant d’IA compatible MCP, tel qu’Anthropic Claude, de se connecter à votre environnement Experience Manager Guides et d’agir en votre nom, sous vos propres autorisations AEM. Une fois la connexion établie, vous pouvez utiliser vos cartes, rubriques, lignes de base et rapports sur Experience Manager Guides as a Cloud Service en langage naturel simple.

Cet article explique l’utilité de MCP pour Experience Manager Guides, ce que couvre le serveur MCP, les applications avec lesquelles il fonctionne et comment l’utiliser.

## L’utilité de MCP pour Experience Manager Guides

Les équipes de documentation passent souvent beaucoup de temps sur des tâches répétitives et gourmandes en ressources, telles que la recherche de rubriques sur une grande carte, la vérification de l’état des documents, le suivi des liens rompus, la création de lignes de base pour une version ou l’exportation de rapports. Avec le serveur MCP Experience Manager Guides, vous pouvez demander à un assistant d’IA de les gérer directement, sans passer par l’interface utilisateur de Experience Manager Guides.

Par exemple :

- Au lieu d&#39;ouvrir une carte et de vérifier l&#39;état de chaque sujet un par un, demandez à l&#39;assistant de répertorier les sujets et leurs états.
- Au lieu de démarrer manuellement un rapport de liens rompus et d’attendre dans l’interface utilisateur de Experience Manager Guides, demandez à l’assistant d’exécuter le rapport et de vous informer lorsqu’il est terminé.
- Au lieu d’accéder à l’écran de ligne de base, demandez à l’assistant de créer une ligne de base pour une carte spécifique.

## Serveur MCP fourni par Experience Manager Guides

Experience Manager Guides offre des fonctionnalités MCP pour travailler avec le contenu Experience Manager Guides et les workflows associés. Selon vos autorisations AEM, le serveur MCP permet d’accéder aux fonctionnalités suivantes :

* **Rubriques et mappages** : utilisez les rubriques et les mappages tout au long du cycle de vie du contenu, depuis la création et l’affichage du contenu jusqu’à sa mise à jour, le contrôle de version, le verrouillage et la suppression.
* **Lignes de base** : utilisez des lignes de base en les créant, les répertoriant, les exportant, les dupliquant, les reconstruisant et les étiquetant.
  >[!NOTE]
  >
  > Pour les environnements Cloud Service et On-premise, les fonctionnalités de ligne de base ne sont disponibles que lorsque la [nouvelle ligne de base](../user-guide/web-editor-baseline-v2.md) est activée.
* **Rapports** : obtenez des informations sur votre contenu en accédant aux listes de rubriques et aux métadonnées, en identifiant les liens rompus et en examinant l’utilisation du multimédia.
* **Système** : comprendre l’état de votre système en vérifiant les versions des packages, l’intégrité des lots et les diagnostics d’environnement.

Si vous n’êtes pas autorisé à effectuer une action dans AEM, vous ne pouvez pas effectuer la même action via MCP.


## Applications prises en charge

Le serveur MCP Experience Manager Guides est un serveur MCP distant qui peut se connecter à des clients MCP compatibles. En fonction de votre environnement, connectez votre client MCP et authentifiez-le sur le serveur MCP Experience Manager Guides. Pour plus d’informations, consultez la section [Configuration du serveur MCP Experience Manager Guides](./configure-aem-guides-mcp.md).

## Utilisation du serveur Experience Manager Guides MCP

Une fois connecté, décrivez en langage clair ce que vous souhaitez. L&#39;assistant sélectionne l&#39;outil approprié et renseigne ses paramètres, tels que le chemin de mappage ou le nom de la ligne de base.

>[!IMPORTANT]
>
> Les requêtes qui impliquent plusieurs étapes ou qui prennent du temps à se terminer, telles que les exportations, les versions de base et les mises à jour en bloc, fonctionnent mieux avec un modèle de réflexion. Ils s’exécutent en arrière-plan : l’assistant démarre la tâche, puis vérifie son statut jusqu’à ce que le résultat, ou un lien de téléchargement, soit prêt.

### Exemples d’invites

Les invites suivantes illustrent des requêtes standard, chacune déclenchant un outil différent :

1. **Vérification des états de rubrique dans une carte**

   > Répertoriez toutes les rubriques de la carte à l’adresse `/content/dam/docs/user-guide.ditamap` et affichez leur titre et l’état du document.

1. **Créer une ligne de base**

   > Créez une ligne de base statique d’`/content/dam/docs/user-guide.ditamap` intitulée « Version 3.2 ».

1. **Exécution d’un rapport**

   > Exécutez le rapport sur les liens rompus pour le guide d’utilisation et donnez-moi le lien de téléchargement lorsqu’il est prêt.

## Gestion des attentes

- **Valider le résultat** - L’assistant peut faire des erreurs, comme choisir une mauvaise carte ou un mauvais sujet. Examinez un rapport ou une nouvelle ligne de base avant de l&#39;utiliser.
- **Sa qualité s&#39;améliore avec le temps** - À mesure que l&#39;assistant s&#39;améliore, les tâches qui nécessitent quelques invites aujourd&#39;hui peuvent nécessiter une invite plus tard.
- **Vous passez toujours l’appel** - L’assistant peut vous indiquer l’état d’une rubrique ou répertorier les liens rompus, mais il appartient toujours au réviseur ou à l’éditeur de décider si le contenu est prêt à être publié.
- **Faites attention avec l’approbation automatique** - Certains clients MCP, dont Claude, vous permettent d’approuver automatiquement les actions au lieu de confirmer chacune d’elles. Cela est acceptable pour les actions en lecture seule, telles que l’exécution d’un rapport. Pour les actions qui créent, modifient ou verrouillent du contenu, confirmez chacune d’elles afin de pouvoir les passer en revue avant qu’elles ne prennent effet.

Pour toute question sur Experience Manager Guides MCP, contactez votre équipe du service client Adobe.


