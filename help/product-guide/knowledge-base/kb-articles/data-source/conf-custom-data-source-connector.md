---
title: Configuration d’un connecteur personnalisé pour les sources de données
description: Découvrez comment configurer un connecteur personnalisé pour les sources de données.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: fdd19363c6768860ffa2f70c934b6f71c811c08b
workflow-type: tm+mt
source-wordcount: '1521'
ht-degree: 0%

---

# Configuration des connecteurs de source de données personnalisés

Experience Manager Guides vous permet de personnaliser les connecteurs en fonction de vos besoins, puis de les utiliser avec les différentes sources de données. Pour personnaliser un connecteur, vous devez mettre en oeuvre l&#39;interface du connecteur et ses fonctions importantes, puis configurer l&#39;interface. Vous pouvez également fournir les ressources avec les connecteurs personnalisés.


- [Personnaliser un connecteur pour Experience Manager Guides](#customize-connector)
- [Implémentation de l’interface du connecteur](#implement-interface)
- [Fonctions importantes](#important-functions)
- [Types d’implémentation des connecteurs par défaut](#default-connectors)
   - [Interface de configuration](#config-interface)
   - [Types de mise en oeuvre des configurations par défaut](#default-config-types)
   - [Implémentations de configuration concrètes](#concrete-config-implementation)
   - [Ressources supplémentaires](#resources)



## Personnaliser un connecteur pour Experience Manager Guides {#customize-connector}

Vous pouvez personnaliser ou configurer un connecteur pour une source de données à l’aide des interfaces prédéfinies et des classes abstraites. Le code source complet est disponible à l&#39;adresse [https://github.com/adobe/guides-data-source-connectors/tree/main/konnect-definitions](https://github.com/adobe/guides-data-source-connectors/tree/main/konnect-definitions).


Reportez-vous à [![javadoc](https://javadoc.io/badge2/com.adobe.aem.addon.guides/konnect-definitions/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem.addon.guides/konnect-definitions) pour connaître les définitions de mot-clé.

## Implémentation de l’interface du connecteur {#implement-interface}

Effectuez les étapes suivantes pour implémenter l’interface et ses fonctions selon vos besoins :

1. Définissez une méthode normalisée pour que les connecteurs s’intègrent à un système, ce qui permet l’exécution des requêtes, la validation des connexions et la récupération des métadonnées.
1. Facilitez l’intégration de l’interface utilisateur en fournissant les méthodes par défaut pour configurer des modèles, des logos, des requêtes et d’autres paramètres.
1. Assurez-vous que les connecteurs sont correctement validés et peuvent gérer les erreurs (`KonnectException`) lors de l’interaction avec les sources de données.

L’interface sert de plan directeur pour la mise en oeuvre de divers types de connecteurs de données, en veillant à ce que ces derniers répondent à toutes les exigences d’intégration et d’exploitation spécifiques au sein d’un écosystème logiciel plus vaste.

## Fonctions importantes {#important-functions}

Implémentez les fonctions importantes suivantes :

| Méthode | Obligatoire | Description |
|---|---|---|
| getLogoUrl |  | <ul><li> Cette méthode renvoie l’URL utilisée comme logo du connecteur. <li> Par défaut, elle renvoie une chaîne vide, indiquant qu’aucune URL de logo n’est fournie, sauf si elle est remplacée. <br><b> Remarques supplémentaires</b> : <br> <ul><li> Si vous fournissez à la fois une URL de logo et un nom de classe de logo, l’URL du logo est utilisée pour afficher le logo dans l’interface utilisateur. <li> Si vous spécifiez l’URL du logo via les paramètres de configuration, elle remplace l’URL définie dans la mise en oeuvre de la méthode . |
| validateConnection | Oui | <ul><li> Utilisez cette méthode pour vérifier si le connecteur peut établir une connexion à sa source de données. <li> Il prend un objet `ConfigDto` comme paramètre, qui contient les paramètres de configuration tels que les informations d’identification de connexion et les URL de point d’entrée. <li> La méthode renvoie true si la validation (test de connexion) est réussie, ce qui indique que le connecteur peut se connecter à sa source de données. |
| execute | Oui | <ul><li>Utilisez cette méthode pour exécuter une seule requête pour le connecteur, en interagissant avec une source de données. <li> Les connecteurs prenant en charge cette opération gèrent l’exécution de la requête, analysent la réponse et la convertissent en chaîne JSON si nécessaire. <li> Encapsulez la requête à exécuter dans cette méthode au sein d’un objet `QueryInfoDto`, qui contient des détails tels que la chaîne de requête et des paramètres. <li> La méthode renvoie une chaîne JSON qui représente la réponse de l’exécution de la requête. <br><b> Remarques supplémentaires</b> : <li>Les mises en oeuvre de cette méthode varient en fonction du connecteur spécifique et de son interaction avec la source de données. <li> Utilisez le `KonnectException` pour gérer les exceptions ou erreurs qui se produisent pendant l’exécution ou la connexion à la source de données. |
| executeWithLimit | Oui | <ul><li> Utilisez cette méthode dans le même objectif que `execute()`, mais avec la fonctionnalité supplémentaire d’application d’une requête de limitation, généralement pour afficher les aperçus dans les composants de l’interface utilisateur. <li> Les connecteurs prenant en charge cette opération gèrent l’exécution de la requête, analysent la réponse et la convertissent en chaîne JSON si nécessaire. <li> Encapsulez la requête à exécuter dans cette méthode dans un objet `QueryInfoDto`, comme la méthode précédente. <br><b> Remarques supplémentaires</b> : <ul><li> `QueryResultDto` est une classe personnalisée ou un objet de transfert de données qui encapsule le résultat de l’exécution de la requête, y compris les métadonnées sur la requête et son état d’exécution. |
| getSampleQuery | | <ul><li>Cette méthode renvoie un exemple de chaîne de requête qui peut être affiché dans l’interface utilisateur, par exemple, dans la boîte de dialogue où les utilisateurs peuvent insérer ou modifier des requêtes. <li>Par défaut, elle renvoie une chaîne vide, indiquant qu’aucun exemple de requête n’est fourni, sauf s’il est remplacé. <br><b> Remarques supplémentaires</b> : <ul> <li> Si vous ne définissez pas d’exemple de requête et que la méthode renvoie une chaîne vide, aucun exemple de requête n’est affiché dans la boîte de dialogue de requête d’insertion de l’interface utilisateur. |
| getTemplates | | <ul> <li> Cette méthode renvoie une liste de modèles associés au connecteur. <li> Par défaut, elle renvoie une liste vide indiquant qu’aucun modèle n’est fourni à moins qu’il ne soit remplacé. |
| getLogoClassName | | <ul> <li> Cette méthode renvoie le nom de classe en tant que logo du connecteur. Par défaut, elle renvoie une chaîne vide, indiquant qu’aucun nom de classe logo n’est fourni, sauf s’il est remplacé. <br><b> Remarques supplémentaires</b> : <ul><li> Si vous fournissez à la fois une URL de logo et un nom de classe de logo, l’URL du logo est utilisée pour afficher le logo dans l’interface utilisateur. <li> Si vous spécifiez le nom de classe logo via les paramètres de configuration, il remplace le nom de classe défini dans l’implémentation de la méthode. |
| enabled | Oui | <ul><li> Cette méthode vérifie si un `connector` est activé. <li> Par défaut, la méthode renvoie false, ce qui signifie que le connecteur n’est pas activé, sauf s’il est remplacé par une classe mettant en oeuvre cette méthode. |
| getDescription | | <ul><li>Utilisez cette méthode pour renvoyer une chaîne de description qui peut être affichée dans l’interface utilisateur. <li> Par défaut, elle renvoie une chaîne vide, indiquant qu’aucune description n’est fournie, sauf si elle est remplacée. |
| getAuthor | | <ul><li> Cette méthode permet de récupérer le nom de l’auteur qui a créé ou est responsable du connecteur. <li> Il permet généralement d’identifier et de reconnaître le créateur ou le responsable du connecteur dans un système ou une structure. |
| getName | Oui | <ul><li>Cette méthode permet de récupérer le nom unique attribué à un connecteur. <li>Le nom renvoyé est essentiel pour identifier le connecteur dans un contexte d’interface utilisateur, en particulier si les paramètres de configuration du connecteur ne spécifient pas explicitement de nom. <li>Ce nom est utilisé dans divers composants de l’interface utilisateur pour afficher ou gérer les connecteurs de manière conviviale. |
| getGroup | Oui | <ul> <li>Cette méthode permet de récupérer le nom du groupe associé à un connecteur. <li>Les noms de groupe sont généralement utilisés pour organiser ou classer les connecteurs en groupes logiques en fonction de leur fonctionnalité, de leur objectif ou de leur type. <li> Cela permet une gestion et une présentation plus simples des connecteurs dans l’interface utilisateur de configuration. |
| getDefaultTemplatePath |  | <ul><li> Cette méthode renvoie le chemin par défaut des modèles associés à ce connecteur. <li> Par défaut, elle renvoie une chaîne vide, indiquant qu’aucun chemin par défaut n’est défini, sauf s’il est remplacé. |
| getLogoSvg |  | <ul><li>Utilisez cette méthode pour renvoyer la représentation SVG du logo du connecteur. <li> Par défaut, elle renvoie une chaîne vide, indiquant qu’aucune donnée de SVG n’est fournie, sauf si elle est remplacée. |
| getMaxNoRowsForPreviewQuery | | <ul><li>Cette méthode renvoie le nombre maximal de lignes interrogées ou affichées dans l’aperçu de l’interface utilisateur. <li> Par défaut, elle renvoie la valeur de DEFAULT_LIMIT_PREVIEW, une constante représentant la limite par défaut pour les lignes d’aperçu. |
| getConfigClass | Oui | <ul><li>Cette méthode fournit des informations sur les classes qui implémentent l’interface de configuration et sont prises en charge par ce connecteur. <li> Il permet à l’application ou à la structure de découvrir et d’utiliser dynamiquement des configurations compatibles avec le connecteur. |

## Types d’implémentation des connecteurs par défaut {#default-connectors}

La bibliothèque *konnect-definitions* fournit des implémentations de connecteurs abstraits et des fonctions prédéfinies pour exécuter des requêtes. Ces implémentations de connecteur agissent comme des modèles qui peuvent être directement étendus et utilisés en l’état. Si une implémentation personnalisée est requise, ses fonctions peuvent être remplacées.

Outre l’implémentation des connecteurs par défaut, vous pouvez également implémenter l’une des classes abstraites par défaut suivantes :

- Rest Connector
- Connecteur de fichiers
- Connecteur GraphQL
- Connecteur SQL
- Connecteur NoSQL


Si un connecteur correspond à l’un de ces types, étendez-le à la classe de base correspondante. Sinon, créez-le entièrement en implémentant l’interface du connecteur.

## Interface de configuration {#config-interface}

L’interface `Config` est conçue pour configurer une source de données avec une méthode d’authentification spécifique, ce qui vous permet de contrôler précisément la manière dont vous créez la connexion.

L’interface `Config` offre une certaine souplesse dans la gestion et la mise en oeuvre des détails d’authentification. Différentes mises en oeuvre peuvent proposer différentes manières d’authentifier les sources de données. Un connecteur utilise une instance de configuration pour exécuter et valider des requêtes sur une source de données, formant ainsi un workflow complet.
Un connecteur utilise une instance `Config` pour exécuter et valider des requêtes sur une source de données, formant un workflow complet.

Une mise en oeuvre de configuration définit la manière dont l’authentification est gérée pour se connecter à une source de données. Cette configuration est ensuite utilisée par une implémentation du connecteur pour interagir avec la source de données, en s’assurant que les requêtes sont exécutées et validées correctement.

Dans l’ensemble, l’interface `Config` est une partie essentielle du workflow pour se connecter aux sources de données, en se concentrant spécifiquement sur la configuration de l’authentification.

### Types de mise en oeuvre des configurations par défaut {#default-config-types}

Il existe trois types de mises en oeuvre de configuration abstraite par défaut pour l’authentification :

- RestConfig
- SqlConfig
- NoSqlConfig

Si une configuration s’aligne sur l’un de ces types, elle peut étendre la classe de base correspondante. Sinon, il peut être créé entièrement en implémentant l’interface de configuration.

### Implémentations de configuration concrètes {#concrete-config-implementation}

La bibliothèque *konnect-definitions* est fournie avec des implémentations prédéfinies de l’interface de configuration pour certaines configurations d’authentification largement utilisées. Vous pouvez utiliser ces configurations directement dans le connecteur ou définir de nouvelles configurations à l’aide de l’interface de configuration. Ces mises en oeuvre incluent :

- Configuration de l’authentification de la clé API
- Configuration de base basée sur les jetons d’authentification
- Configuration d’authentification de base
- Configuration du jeton porteur
- Configuration du mot de passe du nom d’utilisateur pour SQL
- Chaîne de connexion configuration auth pour NoSQL

### Ressources supplémentaires{#resources}

Experience Manager Guides vous permet également de fournir des ressources personnalisées pour les logos et les modèles, ainsi que pour l’implémentation. Vous pouvez conserver ces ressources dans le dossier `resources`.
Pour les rendre utilisables par le connecteur, il est obligatoire de mettre en oeuvre ces fonctions de connecteur :


- `getLogoSvg` - Renvoie le SVG du logo sous la forme d’une chaîne.

- `getTemplates` - Renvoie la liste des modèles au format donné.