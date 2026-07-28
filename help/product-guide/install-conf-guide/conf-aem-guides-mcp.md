---
title: Utilisation de MCP avec Adobe Experience Manager Guides
description: Découvrez comment utiliser le protocole MCP (Model Context Protocol) avec AEM Guides pour utiliser les rubriques, cartes, lignes de base et rapports via un assistant d’IA
feature: Authoring, Publishing
role: User
source-git-commit: c724946a3426e28a1270ba01cdf2646bbf5f2a0d
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 0%

---


# Utilisation du serveur MCP Adobe Experience Manager Guides

Le protocole MCP (Model Context Protocol) est un moyen standard pour les assistants d’IA de se connecter à des outils et des données externes, au lieu de changer de contexte pour utiliser ces outils vous-même.

Le serveur Adobe Experience Manager Guides MCP apporte ces informations à Experience Manager Guides. Il permet à un assistant d’IA compatible MCP, tel qu’Anthropic Claude, de se connecter à votre environnement Experience Manager Guides et d’agir en votre nom, sous vos propres autorisations AEM. Une fois la connexion établie, vous pouvez utiliser vos cartes, rubriques, lignes de base et rapports sur Experience Manager Guides as a Cloud Service en langage naturel simple.

Cet article explique pourquoi MCP est utile pour Experience Manager Guides, ce que couvre le serveur MCP, les applications avec lesquelles il fonctionne, comment le configurer et comment l’utiliser.

## L’utilité de MCP pour Experience Manager Guides

Les équipes de documentation passent souvent beaucoup de temps sur des tâches répétitives et gourmandes en ressources, telles que la recherche de rubriques sur une grande carte, la vérification de l’état des documents, le suivi des liens rompus, la création de lignes de base pour une version ou l’exportation de rapports. Avec le serveur MCP Experience Manager Guides, vous pouvez demander à un assistant d’IA de les gérer directement, sans passer par l’interface utilisateur de Experience Manager Guides.

Par exemple :

- Au lieu d&#39;ouvrir une carte et de vérifier l&#39;état de chaque sujet un par un, demandez à l&#39;assistant de répertorier les sujets et leurs états.
- Au lieu de démarrer manuellement un rapport de liens rompus et d’attendre dans l’interface utilisateur de Experience Manager Guides, demandez à l’assistant d’exécuter le rapport et de vous informer lorsqu’il est terminé.
- Au lieu d’accéder à l’écran de ligne de base, demandez à l’assistant de créer une ligne de base pour une carte spécifique.

## Serveur MCP fourni par Experience Manager Guides

Experience Manager Guides expose ses fonctionnalités MCP par le biais d’un point d’entrée HTTP unique.

| Serveur MCP | Point d’entrée | Description |
| --- | --- | --- |
| **** | `https://mcp.adobeaemcloud.com/adobe/mcp/guides` | Utiliser des rubriques et des cartes, des lignes de base et des rapports dans Experience Manager Guides. |

Ce point d’entrée couvre quatre domaines :

- **Rubriques et mappages** - Créez, lisez, mettez à jour, supprimez, modifiez et verrouillez les rubriques et les mappages.
- **Lignes de base** - Créez, répertoriez, exportez, dupliquez, recréez et étiquetez des lignes de base.
- **Rapports** - Listes de sujets, métadonnées, liens rompus et utilisation multimédia.
- **Système** - Diagnostics de version de package, d’intégrité de lot et d’environnement.

Les outils précis disponibles peuvent changer au fil du temps. Au lieu de vous fier à une liste fixe, demandez à votre assistant de vous montrer les éléments disponibles :

```
List all Experience Manager Guides tools available from the author https://author-pXXXX-eXXXX.adobeaemcloud.com and describe what they do.
```

## Demander l’accès pour votre organisation

L’accès au serveur MCP Experience Manager Guides est **opt-in par organisation**. Avant qu’un membre de votre organisation puisse se connecter :

- Experience Manager Guides doit être activé dans votre environnement AEM as a Cloud Service.
- L’ID d’organisation IMS de votre organisation (ID d’organisation) doit être placé sur la liste autorisée par l’équipe Adobe Guides.

Pour demander l’accès, contactez votre équipe du succès client Adobe.

## Applications prises en charge

Le serveur Experience Manager Guides MCP est un serveur **distant**. Il fonctionne avec n’importe quel client MCP prenant en charge les serveurs distants, notamment :

### Applications de conversation

- Anthropic Claude (web et bureau)

### Outils de développement

- Curseur
- Visual Studio Code
- Autres IDE compatibles avec MCP

## Configuration

Vous n’installez rien localement. Vous pointez votre client vers l’URL du serveur et vous l’authentifiez par le biais du flux de connexion Adobe IMS.

### Claude Anthropique

Suivez la présentation officielle : [Configurer Claude pour AEM MCP](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/ai-in-aem/mcp-support/chat-applications/setup-claude). Lors de l’ajout du connecteur personnalisé, utilisez le point d’entrée Experience Manager Guides :

```
https://mcp.adobeaemcloud.com/adobe/mcp/guides
```

### Curseur/Visual Studio Code

Ajoutez le serveur à votre configuration MCP. Pour Cursor, ajoutez-le à `.cursor/mcp.json` :

```json
{
  "mcpServers": {
    "aem-guides": {
      "url": "https://mcp.adobeaemcloud.com/adobe/mcp/guides"
    }
  }
}
```

Pour les clients qui prennent uniquement en charge les serveurs locaux (stdio), faites le pont vers le point d’entrée distant avec [`mcp-remote`](https://www.npmjs.com/package/mcp-remote) :

```json
{
  "mcpServers": {
    "aem-guides": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://mcp.adobeaemcloud.com/adobe/mcp/guides"]
    }
  }
}
```

## Authentification

Le serveur Experience Manager Guides MCP utilise **Adobe IMS** pour l’authentification.

- Lors de la première connexion, votre client ouvre une fenêtre de connexion au navigateur. Connectez-vous avec votre Adobe ID pour établir la connexion.
- Une fois que vous êtes connecté, chaque action s’exécute avec vos autorisations AEM existantes. Si vous n’avez pas l’autorisation d’effectuer une action dans AEM, la même action échoue dans MCP.

## Utilisation du serveur Experience Manager Guides MCP

Une fois connecté, décrivez en langage clair ce que vous souhaitez. L&#39;assistant sélectionne l&#39;outil approprié et renseigne ses paramètres, tels que le chemin de mappage ou le nom de la ligne de base.

>[!IMPORTANT]
>
>Les requêtes qui impliquent plusieurs étapes ou qui prennent du temps à se terminer, telles que les exportations, les versions de base et les mises à jour en bloc, fonctionnent mieux avec un modèle de réflexion. Ils s’exécutent en arrière-plan : l’assistant démarre la tâche, puis vérifie son statut jusqu’à ce que le résultat, ou un lien de téléchargement, soit prêt.

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


