---
title: Configurer les paramètres de connexion MCP pour AEM Guides On-Premise
description: Découvrez comment configurer les paramètres de connexion MCP pour AEM Guides On-Premise.
meta-feature: Authoring
meta-product: Experience Manager, Experience Manager Guides
meta-role: Admin
meta-type: Documentation
source-git-commit: e234425f1e277990de25057971f3e2453c93360f
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 4%
---

# Configurer les paramètres de connexion MCP pour Experience Manager Guides (On-Premise)

Les outils d’IA tels que Claude, Cursor et Codex peuvent se connecter à Experience Manager Guides à l’aide du protocole MCP (Model Context Protocol). Vous pouvez configurer les paramètres de connexion et d’authentification MCP à partir de la page Configuration de la console web Adobe Experience Manager .

Les configurations disponibles contrôlent la gestion des jetons, les requêtes sans informations sur le référent et l’URL externe de l’instance d’auteur AEM.

## Configuration de la gestion des jetons de connexion

Pour configurer la gestion des jetons de connexion, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Recherchez et sélectionnez **Wrapper de jeton PKCE OAuth**.

3. Configurez les propriétés suivantes :

   | Propriété | Valeur par défaut | Description |
   |---|---|---|
   | URL de base Granite | `http://localhost:4502` | Indique l’URL qu’AEM utilise pour communiquer avec l’instance de création lors de l’authentification. Modifiez le port par défaut 4502 uniquement si votre instance de création utilise un autre port. |
   | Délai d’expiration Granite (ms) | `5000` | Indique la durée maximale d’attente, en millisecondes, de la fin de la demande d’authentification. |

4. Sélectionnez **Enregistrer**.

## Configuration de requêtes sans informations sur le référent

>[!NOTE]
>
> Ce paramètre doit être configuré uniquement si vous utilisez Cursor.

Certains clients MCP, notamment Cursor, peuvent envoyer des requêtes sans informations sur le référent. Pour autoriser ces requêtes, configurez le filtre de référent Apache Sling comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Recherchez et sélectionnez **Filtre de référent Apache Sling**.

3. Dans la propriété **Allow Empty**, définissez la valeur sur `true`.

   Ce paramètre autorise les requêtes qui ne contiennent pas d’informations de référent lors de l’authentification.

4. Sélectionnez **Enregistrer**.

## Configuration de l’URL externe de l’instance d’auteur

Le service **Day CQ Link Externalizer** vous permet de définir de manière centralisée les URL externes utilisées pour préfixer les chemins d’accès aux ressources, y compris l’URL de l’instance d’auteur AEM.

Pour configurer l’URL externe, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Recherchez et sélectionnez **Externaliseur de lien Day CQ**.

3. Sous **Domaines**, ajoutez ou mettez à jour le mappage `author` en utilisant le format suivant :

   ```
   author [scheme://]server[:port][/contextpath]
   ```

   Par exemple :

   ```
   author https://author.mycompany.com
   ```

4. Sélectionnez **Enregistrer**.