---
title: Configuration d’un connecteur de source de données
description: Découvrez comment configurer un connecteur de source de données
exl-id: bd1188e1-0e1d-4e70-928a-10251c3d529d
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---

# Configuration d’un connecteur de source de données

AEM Guides fournit des connecteurs prêts à l’emploi pour les bases de données JIRA et SQL (MySQL, PostgreSQL, SQL Server, SQLite). Vous pouvez également ajouter d’autres connecteurs en étendant les interfaces par défaut. La configuration suivante vous permet d’ajouter facilement les différentes sources de données. Une fois ajoutées, vous pouvez afficher les sources de données dans l’éditeur web.

Effectuez les étapes suivantes pour configurer un connecteur de source de données, puis utilisez-le à partir de l’éditeur web :

## Configurer un connecteur

Vous pouvez configurer un connecteur d’usine en chargeant un fichier JSON. Vous pouvez utiliser les exemples de fichiers de configuration suivants pour configurer les connecteurs pour les bases de données Jira et SQL (MySQL, PostgreSQL, SQL Server, SQLite).

Exemple de fichier de configuration pour l’authentification de base de Jira avec nom d’utilisateur et mot de passe :

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

Par exemple, enregistrez sous `jira.json`.

Exemple de fichier de configuration pour l’authentification de base de Jira avec jeton :

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

Par exemple, enregistrez sous `jira.json`.

Exemple de fichier de configuration pour l’authentification de base de Jira avec le jeton qui contient le mot-clé &quot;De base&quot; :

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

Par exemple, enregistrez sous `jira.json`.

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

Par exemple, enregistrez sous `mysql.json`.

Exemple de fichier de configuration pour l&#39;authentification de base de PostgreSQL :

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

Par exemple, enregistrez sous `postgres.json`.

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

Par exemple, enregistrez sous `mssqlserver.json`.

Exemple de fichier de configuration pour l’authentification de base de SQLite :

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

Par exemple, enregistrez sous `sqqlite.json`.

### Personnalisation de la configuration d’un connecteur

AEM Guides vous permet de personnaliser certaines valeurs du fichier de configuration en fonction des besoins de l’utilisateur.

| Nom de la propriété | Description |
|---|---|
| configName | L’utilisateur peut spécifier un nom de configuration pour identifier le connecteur. |
| templateFolders | Liste des dossiers à partir desquels les modèles seront récupérés |

Les autres champs sont personnalisés en fonction de la classe de configuration sélectionnée pour exécuter le connecteur.

## Téléchargez le fichier vers un emplacement dans AEM

Téléchargez le fichier vers un emplacement spécifique dans AEM Assets.

Par exemple :  `/content/dam/jira.json`

## Créer une configuration à l’aide de l’API REST

Vous pouvez enregistrer la configuration à l’aide de l’API REST. Pour plus d’informations, voir la *API REST pour enregistrer un connecteur de source de données* dans la section Référence d’API pour les guides Adobe Experience Manager.

Une fois la source de données configurée, le connecteur est répertorié sous le panneau Sources de données dans l’éditeur web. Vous pouvez ensuite vous connecter à la source de données et insérer un fragment de contenu dans vos rubriques. Pour plus d’informations, voir [Insertion d’un fragment de contenu à partir de votre source de données](../user-guide/web-editor-content-snippet.md).
