---
title: Configuration de MCP pour Adobe Experience Manager Guides
description: Découvrez comment connecter un assistant d’IA au serveur MCP Experience Manager Guides pour les déploiements sur site et Cloud Service
meta-feature: Authoring
meta-product: Experience Manager, Experience Manager Guides
meta-role: User
meta-type: Documentation
source-git-commit: e234425f1e277990de25057971f3e2453c93360f
workflow-type: tm+mt
source-wordcount: '1539'
ht-degree: 1%
---

# Configuration du serveur MCP Experience Manager Guides

Cet article couvre les détails spécifiques à l’environnement pour la connexion au serveur MCP Experience Manager Guides. La configuration diffère selon que votre instance Experience Manager Guides exécute as a Cloud Service ou sur site. Sélectionnez l’onglet correspondant à votre environnement.

>[!BEGINTABS]

>[!TAB ]

## Point d’entrée du serveur MCP

Experience Manager Guides expose ses fonctionnalités MCP par le biais d’un point d’entrée HTTP unique.

| Serveur MCP | Point d’entrée | Description |
|---|---|---|
| **** | `https://mcp.adobeaemcloud.com/adobe/mcp/guides` | Utiliser des rubriques et des cartes, des [nouvelles lignes de base](../user-guide/web-editor-baseline-v2.md) et des rapports dans Experience Manager Guides. |

Pour découvrir la liste d’outils actuelle pour votre environnement, demandez à votre assistant :

```
List all Experience Manager Guides tools available from the author https://author-pXXXX-eXXXX.adobeaemcloud.com and describe what they do.
```

## Demander l’accès pour votre organisation

L’accès au serveur MCP Experience Manager Guides est **opt-in par organisation**. Avant qu’un membre de votre organisation puisse se connecter :

- Experience Manager Guides doit être activé dans votre environnement AEM as a Cloud Service.
- L’ID d’organisation IMS de votre organisation (ID d’organisation) doit être placé sur la liste autorisée par l’équipe Adobe Guides.

Pour demander l’accès, contactez votre équipe du succès client Adobe.

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

>[!TAB On-premise]

Vous pouvez connecter les clients d’IA pris en charge à une instance locale de Experience Manager Guides à l’aide du protocole MCP (Model Context Protocol). Une fois la connexion établie, le client peut accéder aux opérations Experience Manager Guides disponibles pour votre compte utilisateur AEM.

Toutes les opérations sont effectuées à l’aide de **votre identité AEM et vos autorisations**. Le client connecté peut uniquement afficher ou modifier le contenu et les ressources auxquels votre compte AEM est autorisé à accéder.

L’authentification utilise le flux de code d’autorisation OAuth 2.0 avec PKCE (Proof Key for Code Exchange). Vous vous authentifiez avec AEM lorsque vous connectez un client pour la première fois. Une fois l’authentification réussie, la connexion actualise automatiquement les jetons d’accès.

Vous pouvez connecter les clients suivants :

| Client | Méthode de connexion | Configuration requise pour les instances AEM |
| ------------------ | ----------------------------------------- | --------------------------------------------------------------------------------------------------- |
| **Bureau Claude** | Extension Desktop (`.mcpb`) | Prend en charge les points d’entrée HTTP et HTTPS, y compris les hôtes internes accessibles à partir du réseau de votre entreprise. |
| **ChatGPT (web et bureau)** | Connecteur personnalisé | Nécessite un point d’entrée HTTPS accessible au public avec un certificat TLS valide approuvé par le public. |
| **Curseur** | Configuration du MCP dans `~/.cursor/mcp.json` | Prend en charge les points d’entrée HTTP et HTTPS, y compris les hôtes internes accessibles à partir du réseau de votre entreprise. |

## Conditions préalables

Avant de connecter un client, contactez votre administrateur AEM pour vérifier la configuration suivante :

1. **Vérifiez que la fonctionnalité MCP est déployée.** : assurez-vous que la fonctionnalité MCP est déployée et en cours d’exécution sur votre instance Experience Manager Guides.

2. **Configurez l’URL de base Granite.** : dans le gestionnaire de configuration de la console web AEM (`/system/console/configMgr`), recherchez la configuration **Wrapper de jeton PKCE OAuth Experience Manager Guides** et vérifiez que l’URL de base Granite est configurée. Si l’URL de base Granite n’est pas configurée correctement, le client ne peut pas établir la connexion.

3. **Configurez l’externaliseur de liens Day CQ.** : dans le gestionnaire de configuration de la console web d’AEM, recherchez la configuration **Externaliseur de liens Day CQ** et vérifiez que l’URL de l’auteur externe pointe vers l’instance d’auteur AEM appropriée. L’URL de création externe est utilisée lors de la découverte OAuth. Une URL incorrecte peut empêcher le client d’établir la connexion.

   Pour plus d’informations, consultez [Configuration des paramètres de connexion MCP pour AEM Guides On-Premise](./configure-aem-guides-mcp-on-prem.md)

4. **Obtenir l’URL du serveur MCP.** : l’URL du serveur MCP utilise le format suivant :

   ```
   http(s)://<AEM-HOST>/bin/guides/v1/mcp/sse
   ```

   >[!NOTE]
   >
   > Utilisez le point d’entrée SSE complet lors de la configuration d’un client. N’ajoutez pas de barre oblique de fin à l’URL.

   Par exemple :

   **Instance d’auteur AEM interne :**

   ```
   http://10.42.42.20:4502/bin/guides/v1/mcp/sse
   ```

   **Instance d’auteur AEM publique :**

   ```
   https://author.example.com/bin/guides/v1/mcp/sse
   ```



5. **Vérifiez vos identifiants AEM et vos autorisations.** : vous devez disposer d’un compte valide pour l’instance AEM. Utilisez les mêmes informations d’identification que celles que vous utilisez pour vous connecter à l’interface utilisateur d’AEM. Les opérations disponibles via MCP sont déterminées par les autorisations attribuées à ce compte.

## Connecter Claude Desktop

Claude Desktop prend en charge les extensions Desktop (`.mcpb`). L’extension Experience Manager Guides MCP regroupe la configuration de connexion de sorte que vous n’ayez pas besoin de modifier manuellement une configuration JSON MCP.

1. Extrayez le fichier zip [AEM Guides .mcpb](./mcpbfile.zip) et obtenez le fichier d’extension `aem-guides-mcp.mcpb`.

2. Ouvrez **Claude Desktop** et accédez à **Paramètres > Extensions**.

3. Installez `aem-guides-mcp.mcpb` en double-cliquant sur le fichier ou en le faisant glisser dans la fenêtre Extensions .

   **Adobe Experience Manager Guides MCP** s’affiche dans la boîte de dialogue Installation.

4. Sélectionnez **Installer**.

5. Dans le champ **URL du serveur Experience Manager Guides MCP**, saisissez le point d’entrée SSE complet de votre instance AEM.

   Par exemple :

   ```
   http://<AEM-HOST>:4502/bin/guides/v1/mcp/sse
   ```

6. Sélectionnez **Enregistrer** et assurez-vous que l’extension est activée.

## Connexion à ChatGPT

Vous pouvez configurer le serveur Experience Manager Guides MCP en tant que connecteur personnalisé dans ChatGPT.

>[!IMPORTANT]
>
> ChatGPT nécessite que le serveur MCP soit disponible via un **point d’entrée HTTPS accessible au public avec un certificat TLS valide et approuvé par le public**.
>
> Les points d’entrée HTTP, `localhost`, adresses IP privées et certificats auto-signés ne sont pas pris en charge. L’instance AEM doit être exposée via un hôte HTTPS, tel qu’une répartition de charge, un proxy inverse ou un Dispatcher configuré avec TLS.
>
> L’URL de création externe configurée dans **Day CQ Link Externalizer** doit également pointer vers l’adresse HTTPS publique. Sinon, les métadonnées de découverte OAuth peuvent signaler des points d’entrée d’authentification incorrects et empêcher la connexion.

1. Vérifiez que votre serveur MCP est disponible à une URL HTTPS publique au format suivant :

   ```
   https://<PUBLIC-AEM-HOST>/bin/guides/v1/mcp/sse
   ```

   Ouvrez le point d’entrée dans un navigateur et vérifiez que vous pouvez atteindre l’hôte sans avertissement de certificat ni erreur de connexion.

2. Dans ChatGPT, ouvrez **Paramètres > Plug-ins**.

   >[!NOTE]
   >
   > La disponibilité du connecteur dépend de votre plan ChatGPT et de la configuration de votre espace de travail. L’administrateur de votre espace de travail devra peut-être activer les connecteurs personnalisés ou les connecteurs développeur.

3. Sélectionnez l’option pour ajouter ou créer un module externe.

4. Spécifiez les détails du connecteur :

   * **Nom :** saisissez `Experience Manager Guides` ou un autre nom explicite.
   * **URL du serveur MCP :** saisissez le point d’entrée HTTPS SSE public.
   * **Authentification :** sélectionnez **OAuth**.

   Vous n’avez pas besoin de fournir d’ID client OAuth ou de secret client. Le serveur MCP prend en charge l’enregistrement client automatique.

5. Créez le connecteur.

## Connecter le curseur

Configurez le serveur MCP Experience Manager Guides dans le curseur en ajoutant les détails du serveur à la configuration MCP.

1. Dans le curseur, accédez à **Personnaliser > MCP > Nouveau**.

   Le curseur ouvre le fichier de configuration `~/.cursor/mcp.json`.

2. Ajoutez la configuration du serveur Experience Manager Guides MCP.

   Par exemple :

   ```json
   {
     "mcpServers": {
       "aem-guides": {
         "url": "http://10.42.34.176:4502/bin/guides/v1/mcp/sse",
         "type": "http"
       }
     }
   }
   ```

3. Remplacez l’exemple d’URL par le point d’entrée MCP SSE pour votre instance AEM.

4. Enregistrez la configuration.

5. Activez le serveur MCP configuré.

>[!ENDTABS]

## Authentification et utilisation de Experience Manager Guides

Après avoir configuré la connexion MCP dans votre client, authentifiez-vous avec votre compte AEM.

1. Démarrez le processus d’authentification à partir de votre client.

   * **Ordinateur de bureau Claude :** le flux d’authentification commence lorsque Claude tente d’utiliser la connexion Experience Manager Guides pour la première fois.
   * **ChatGPT :** l’authentification commence après la création et la connexion du connecteur Experience Manager Guides.
   * **Curseur :** activez le serveur MCP configuré et sélectionnez **Authentifier**.

2. Lorsque la page de connexion à AEM s’ouvre dans votre navigateur, connectez-vous à l’aide de vos informations d’identification AEM.

3. Approuvez la demande d’accès lorsque vous y êtes invité.

4. Une fois l’authentification terminée, revenez à votre client.

Vous pouvez désormais utiliser les opérations Experience Manager Guides disponibles pour votre compte. Par exemple, essayez des invites telles que :

```
List the available Experience Manager Guides operations.
```

```
Get the topic list for my map in Experience Manager Guides.
```

```
Show me the broken-link report for my map.
```

>[!NOTE]
>
> Les opérations et le contenu disponibles via MCP sont déterminés par les autorisations du compte AEM utilisé pour l’authentification. La connexion MCP ne fournit pas de privilèges AEM supplémentaires.

Une fois l’authentification réussie, le client actualise automatiquement les jetons d’authentification. En règle générale, vous n’avez pas besoin de vous reconnecter, sauf si la session expire ou si l’accès est révoqué.

## Résolution des problèmes de connexion

Utilisez les informations suivantes pour résoudre les problèmes courants de connexion et d’authentification.

| Client | Problème | Cause possible et résolution |
| -------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Claude Desktop | L’extension ne peut pas être installée ou est désactivée. | Il se peut que votre version de Claude Desktop ne prenne pas en charge l&#39;extension. Mettez à jour Claude Desktop et réessayez. |
| Claude Desktop | Le navigateur ne s’ouvre pas pour permettre l’authentification ou la connexion ne se termine pas. | Vérifiez l’URL du serveur MCP. Elle doit se terminer par `/bin/guides/v1/mcp/sse` et ne doit pas contenir de barre oblique. Vérifiez également que l’instance AEM est accessible depuis votre ordinateur. |
| ChatGPT | ChatGPT ne peut pas atteindre le serveur MCP ou ne vous permet pas d&#39;ajouter le connecteur. | Vérifiez que le point d’entrée est accessible au public via HTTPS. Les points d’entrée HTTP, `localhost`, adresses IP privées et points d’entrée de réseau privé ne sont pas pris en charge. |
| ChatGPT | Un certificat ou une erreur de sécurité s’affiche. | Vérifiez que le serveur utilise un certificat valide non expiré émis par une autorité de certification approuvée publiquement. Les certificats auto-signés ne sont pas pris en charge. |
| ChatGPT | L’authentification redirige vers un hôte incorrect ou échoue lors de la découverte. | Vérifiez que l’URL de création externe dans **Day CQ Link Externalizer** pointe vers l’adresse de création publique HTTPS AEM. |
| Tous les clients | L’enregistrement échoue lors de l’authentification. | Vérifiez la configuration de l’enregistrement OAuth côté serveur auprès de votre administrateur AEM. |
| Tous les clients | Échec ou échec de l&#39;authentification. | Vérifiez l’URL de base Granite, la configuration de l’externaliseur de liens Day CQ, l’URL du serveur MCP et la connectivité à l’instance AEM. |
| Tous les clients | La connexion réussit, mais les opérations ou les résultats de Experience Manager Guides ne sont pas disponibles. | Vérifiez que le compte AEM authentifié dispose des autorisations Experience Manager Guides requises et que l’opération demandée est disponible pour le compte. |
| Tous les clients | Le client demande une authentification après le fonctionnement de la connexion précédente. | La session d’authentification a peut-être expiré ou l’accès a été révoqué. Authentifiez-vous à nouveau avec AEM. |



