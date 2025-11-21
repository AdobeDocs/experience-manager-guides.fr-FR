---
title: Configuration d’un connecteur de source de données
description: Découvrez comment configurer un connecteur de source de données
exl-id: bd1188e1-0e1d-4e70-928a-10251c3d529d
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---

# Configuration d’un connecteur de source de données

AEM Guides fournit des connecteurs prêts à l’emploi pour les bases de données JIRA et SQL (MySQL, PostgreSQL, SQL Server, SQLite). Vous pouvez également ajouter d’autres connecteurs en étendant les interfaces par défaut. La configuration suivante vous permet d’ajouter facilement les différentes sources de données. Une fois ajoutées, vous pouvez afficher les sources de données dans l’éditeur web.

Pour configurer un connecteur de source de données et l’utiliser ensuite à partir de l’éditeur web, procédez comme suit :

## Configuration d’un connecteur

Vous pouvez configurer un connecteur prêt à l’emploi en chargeant un fichier JSON. Vous pouvez utiliser les fichiers d’installation d’exemple suivants pour configurer des connecteurs pour les bases de données Jira et SQL (MySQL, PostgreSQL, SQL Server, SQLite).

Exemple de fichier de configuration pour l’authentification de base de Jira avec le nom d’utilisateur et le mot de passe :

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
    "configName": "Jira",
    "templateFolders": ["/content/dam/dita-templates/konnect/jira"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
        "configData": {
            "username": "jirausername",
            "password": "jirapassword",
            "url": "https://jira.corp.adobe.com/rest/api/latest/search"
        }
    }
}
```

Par exemple, enregistrez-le en tant que `jira.json`.

Exemple de fichier de configuration pour l’authentification de base de Jira avec un jeton :

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
    "configName": "Jira",
    "templateFolders": ["/content/dam/dita-templates/konnect/jira"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
        "configData": {
            "token": "jiraauthtoken",
            "url": "https://jira.corp.adobe.com/rest/api/latest/search"
        }
    }
}
```

Par exemple, enregistrez-le en tant que `jira.json`.

Exemple de fichier de configuration pour l’authentification de base de Jira avec le jeton contenant le mot-clé « De base » :

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
    "configName": "Jira",
    "templateFolders": ["/content/dam/dita-templates/konnect/jira"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
        "configData": {
            "token": "Basic jiraauthtoken",
            "url": "https://jira.corp.adobe.com/rest/api/latest/search"
        }
    }
}
```

Par exemple, enregistrez-le en tant que `jira.json`.

Exemple de fichier de configuration pour l’authentification de base de MySql :

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MySqlConnector",
    "configName": "MySQL",
    "templateFolders": ["/content/dam/dita-templates/konnect/sql"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
        "configData": {
            "username": "admin",
            "password": "admin",
            "driver": "com.mysql.jdbc.Driver",
            "connectionString": "jdbc:mysql://host.corp.adobe.com:3306/plm"
        }
    }
}
```

Par exemple, enregistrez-le en tant que `mysql.json`.

Exemple de fichier de configuration pour l’authentification de base de PostgreSQL :

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.PostgreSqlConnector",
    "configName": "PostgreSQL",
    "templateFolders": ["/content/dam/dita-templates/konnect/sql"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
        "configData": {
            "username": "admin",
            "password": "admin",
            "driver": "org.postgresql.Driver",
            "connectionString": "jdbc:postgresql://host:port/database"
        }
    }
}
```

Par exemple, enregistrez-le en tant que `postgres.json`.

Exemple de fichier de configuration pour l&#39;authentification de base de MS SQL Server :

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MsSqlServerConnector",
    "configName": "MSSQLServer",
    "templateFolders": ["/content/dam/dita-templates/konnect/sql"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
        "configData": {
            "username": "admin",
            "password": "admin",
            "driver": "com.microsoft.sqlserver.jdbc.SQLServerDriver",
            "connectionString": "jdbc:sqlserver://10.10.10.10\\SQLEXPRESS01:1433;database=TutorialDB;encrypt=false;trustServerCertificate=true"
        }
    }
}
```

Par exemple, enregistrez-le en tant que `mssqlserver.json`.

Exemple de fichier de configuration pour l&#39;authentification de base de SQLite :

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.SqliteConnector",
    "configName": "SQLiteServer",
    "templateFolders": ["/content/dam/dita-templates/konnect/sql"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
        "configData": {
            "username": "admin",
            "password": "admin",
            "driver": "org.sqlite.JDBC",
            "connectionString": "jdbc:sqlite:sample.db"
        }
    }
}
```

Par exemple, enregistrez-le en tant que `sqqlite.json`.

### Personnalisation d’une configuration de connecteur

AEM Guides vous permet de personnaliser certaines valeurs du fichier de configuration en fonction des besoins de l’utilisateur.

| Nom de la propriété | Description |
|---|---|
| configName | L’utilisateur peut spécifier un nom de configuration pour l’aider à identifier le connecteur |
| templateFolders | Liste des dossiers à partir desquels les modèles seront récupérés |

D’autres champs sont personnalisés en fonction de la classe de configuration sélectionnée pour exécuter le connecteur.

## Chargez le fichier vers un emplacement d’AEM

Chargez le fichier vers un emplacement d’AEM Assets.

Par exemple, `/content/dam/jira.json`

## Créer une configuration à l’aide de l’API REST

Vous pouvez enregistrer la configuration en utilisant l’API REST. Pour plus d’informations, consultez la section *API REST pour enregistrer un connecteur de source de données* dans la référence d’API pour Adobe Experience Manager Guides.

Une fois la source de données configurée, le connecteur est répertorié sous le panneau Sources de données dans l’éditeur web. Vous pouvez ensuite vous connecter à la source de données et insérer un fragment de contenu dans vos rubriques. Pour plus d’informations, consultez la section [ Insérer un fragment de contenu à partir de votre source de données ](../user-guide/web-editor-content-snippet.md).
