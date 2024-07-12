---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans la version de juin 2023 d’Adobe Experience Manager Guides
description: Découvrez les correctifs et comment mettre à niveau vers la version de juin 2023 d’Adobe Experience Manager Guides as a Cloud Service
exl-id: df17ee33-9f50-4223-ab9f-a57a31097d22
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 1%

---

# Version de juin 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cette note de mise à jour traite des instructions de mise à niveau, de la matrice de compatibilité et des problèmes résolus dans la version de juin 2023 d’Adobe Experience Manager Guides (appelée ultérieurement *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de juin 2023 de la version AEM Guides as a Cloud Service](whats-new-2023-6-0.md).

## Mise à niveau vers la version de juin 2023

Mettez à niveau votre configuration AEM Guides as a Cloud Service actuelle en procédant comme suit :

1. Extrayez le code Git des Cloud Service et passez à la branche configurée dans le pipeline Cloud Service correspondant à l’environnement que vous souhaitez mettre à niveau.
2. Mettez à jour la propriété `<dox.version>` dans le fichier `/dox/dox.installer/pom.xml` de votre code Git Cloud Service vers 2023.6.297.
3. Validez les modifications et exécutez le pipeline Cloud Service pour effectuer la mise à niveau vers la version de juin 2023 d’AEM Guides as a Cloud Service.

## Procédure d’activation du déclencheur d’un script via un servlet

Une fois l’installation terminée, vous pouvez choisir d’ACCÉDER au déclencheur pour lancer la tâche de traduction :

POST :

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Réponse :

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

Dans la réponse précédente JSON, la clé `lockNodePath` contient le chemin d’accès au noeud créé dans le référentiel pointant vers la tâche envoyée. Il sera automatiquement supprimé une fois la tâche terminée. Vous pourrez alors vous référer à ce noeud pour connaître l’état actuel de la tâche.

Patientez jusqu’à ce que cette tâche soit terminée avant de passer aux étapes suivantes.

>[!NOTE]
>
> Vérifiez si le noeud est toujours présent et l’état de la tâche.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu

(Uniquement si vous utilisez une version antérieure à la version de juin 2023 d’AEM Guides as a Cloud Service)

Effectuez les étapes suivantes pour le post-traitement du contenu existant et l’utilisation du nouveau rapport de lien rompu :

1. (Facultatif) S’il existe plus de 100 000 fichiers dita dans le système, mettez à jour la valeur `queryLimitReads` sous `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` vers une valeur plus grande (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

   - Suivez les instructions de la section *Remplacements de configuration* dans Installer et configurer Adobe Experience Manager Guides
as a Cloud Service, pour créer le fichier de configuration.
   - Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer l’option queryLimitReads :

     | PID | Clé de propriété | Valeur de la propriété |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 Valeur par défaut : 100000 |

1. Exécutez une requête de POST sur le serveur (avec l’authentification correcte) - `http://<server:port>//bin/guides/reports/upgrade`.

1. L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Une fois la tâche terminée, la requête de GET précédente répond avec succès. Si la tâche échoue pour une raison quelconque, l’échec peut être visible à partir des journaux du serveur.

1. Revenez à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifiée à l’étape 1.

## Étapes pour indexer le contenu existant afin d’utiliser la nouvelle liste de rubrique et de recherche sous l’onglet Rapports :

(Uniquement si vous utilisez une version antérieure à la version de septembre 2022 d’AEM Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utilisez le nouveau texte de recherche et de remplacement au niveau de la carte et de la liste des rubriques sous l’onglet rapports :

1. Exécutez une requête de POST sur le serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des cartes pour les indexer ; par défaut, toutes les cartes seront indexées \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Vous pouvez également transmettre un dossier racine pour indexer les mappages DITA d’un dossier spécifique (et de ses sous-dossiers). Par exemple, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Notez que si les paramètres paths et root sont transmis, seul le paramètre paths est pris en compte.

1. L’API renvoie un jobId. Pour vérifier l’état de la tâche, vous pouvez envoyer une demande de GET avec l’ID de la tâche au même point de terminaison - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Une fois la tâche terminée, la requête de GET précédente répond avec succès et indique si une correspondance a échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par la version de juin 2023 d’AEM Guides as a Cloud Service.

### FrameMaker et FrameMaker Publishing Server

| Version AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.06.0 | Non compatible | 2022 ou version ultérieure |
| | | |


### Connecteur Oxygen

| Version AEM Guides as a Cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.06.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |


## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

### Création

- Navtitle est supprimé du contenu33 lors du passage de la vue de mise en page à la vue de création ou source. (12174)
- Parfois, une erreur d’application se produit lorsque vous cliquez sur un mappage DITA. (11842)
- Éditeur web | Un espace insécable est ajouté dans l’éditeur XML lors de la modification d’une rubrique. (11786)
- Interface utilisateur des ressources | En mode Liste, les colonnes disponibles superposées ne sont pas fusionnables. (11528)
- Keyref n’est pas résolu dans la vue map. (11490)
- Le menu supérieur n’apparaît pas lors de la navigation dans l’éditeur XML. 10868
- `conref` dans la balise ph | La boîte de dialogue de navigation affichée est incorrecte. (9481)
- Les liens locaux vers d’autres éléments ne sont pas résolus dans l’éditeur web. (8790)
- La fonction Matches() ne fonctionne pas dans la fonction de schéma. (11224)


### Gestion

- L’onglet Rapports de l’interface utilisateur de l’éditeur web n’affiche pas la liste des rubriques des anciens mappages DITA créés avant la mise à niveau 4.2. (11708)

- La fonctionnalité de bouton Télécharger les fichiers de l’interface utilisateur d’Assets est coupée dans la version 4.2. (11633)

### Publication

- La publication sur AEM site échoue lors de la lecture de fichiers temporaires à partir d’une capsule qui peuvent avoir été actualisés ou redémarrés. (12113)
- PDF natif | La publication de contenu comportant une classe de sortie avec crochets () entraîne un gel de publication. (11936)
- Sortie JSON | Les métadonnées de mappage dont la valeur de propriété est `"value in spaces and double quotes"` entraînent une erreur de publication. (11933)
- Éditeur web | Le chemin de sortie et le modèle ne peuvent pas être sélectionnés dans le paramètre prédéfini AEM. (11530)
- PDF natif | Les attributs personnalisés ne sont pas propagés à un moteur d’HTML ou de PDF temporaire. (DXML-12005)
- PDF natif |  Java OutOfMemoryError survient lors de la publication de contenu volumineux. (11789)
- Sortie JSON | La propriété `fmUuid` sur le noeud jcr:content de JSON est différente de &quot;id&quot; dans le JSON. (11564)
- Sortie JSON | Si la carte et la rubrique portant le même nom de fichier sont présentes, JSON de la carte est supprimé. (11524)
- PDF natif | Xref imprime le contenu du titre de la rubrique href au lieu de l’étiquette Xref. (11322)
- PDF natif | Impossible d’enregistrer les paramètres du modèle de PDF. (10751)
- PDF natif | Le texte s’étend au-delà de la largeur de colonne sur l’inclusion de plusieurs xrefs. (10876)
- PDF natif | L’élément `<note>``</note>` ne génère pas de titre d’étendue supplémentaire de son type. (10549)
- PDF natif | Les métadonnées de langue ne peuvent pas être définies dans le PDF généré pour être conformes à WCAG 2.0. (12296)



### Traduction

- Version cloud de février de Post (2302), tout le contenu de traduction affiche Désynchronisé ou Copie manquante. (11834)

### Révision

- Nouvelle interface utilisateur de révision | Les conditions de mise en évidence et d’affichage du masquage fonctionnent différemment de leur fonctionnement dans l’éditeur web. (11628)
