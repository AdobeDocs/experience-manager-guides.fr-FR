---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans Adobe Experience Manager Guides, version de juin 2023
description: Découvrez les correctifs et comment effectuer la mise à niveau vers la version de juin 2023 d’Adobe Experience Manager Guides as a Cloud Service
exl-id: df17ee33-9f50-4223-ab9f-a57a31097d22
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/LIY9wVDmvusGD-K-kyjK-lmzpyxJELj0mWzn9YoP0vw
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 1169
ht-degree: 3%

---

# Version de juin 2023 d’Adobe Experience Manager Guides as a Cloud Service

Cette note de mise à jour couvre les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans la version de juin 2023 d’Adobe Experience Manager Guides (plus tard appelée *AEM Guides as a Cloud Service*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version de juin 2023 d’AEM Guides as a Cloud Service](whats-new-2023-6-0.md).

## Mise à niveau vers la version de juin 2023

Mettez à niveau votre configuration AEM Guides as a Cloud Service actuelle en procédant comme suit :

1. Consultez le code Git des services cloud et passez à la branche configurée dans le pipeline des services cloud correspondant à l’environnement à mettre à niveau.
2. Mettez à jour `<dox.version>` propriété dans `/dox/dox.installer/pom.xml` fichier de votre code Git Cloud Services vers la version 2023.6.297.
3. Validez les modifications et exécutez le pipeline Cloud Services pour effectuer la mise à niveau vers la version de juin 2023 d’AEM Guides as a Cloud Service.

## Procédure d’activation du déclenchement d’un script via une servlet

Une fois l’installation terminée, vous pouvez choisir d’APPUYER sur le déclencheur pour démarrer la tâche de traduction :

PUBLICATION :

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

Dans la réponse précédente JSON, la clé `lockNodePath` contient le chemin d’accès au nœud créé dans le référentiel pointant vers la tâche envoyée. Elle sera automatiquement supprimée une fois le traitement terminé. En attendant, vous pouvez vous référer à ce nœud pour connaître le statut actuel du traitement.

Patientez jusqu’à ce que ce traitement soit terminé avant de passer aux étapes suivantes.

>[!NOTE]
>
> Vous devez vérifier si le nœud est toujours présent, ainsi que le statut de la tâche.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Étapes de post-traitement du contenu existant pour utiliser le rapport de lien rompu

(Uniquement si vous utilisez une version d’AEM Guides as a Cloud Service antérieure à la version de juin 2023)

Effectuez les étapes suivantes pour post-traiter le contenu existant et utiliser le nouveau rapport de lien rompu :

1. (Facultatif) S’il existe plus de 100 000 fichiers dita dans le système, mettez à jour le `queryLimitReads` sous `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` avec une valeur plus élevée (toute valeur supérieure au nombre de ressources présentes, par exemple 200 000), puis redéployez.

   - Suivez les instructions de la section *Remplacements de configuration* dans Installation et configuration d’Adobe Experience Manager Guides.
as a Cloud Service, pour créer le fichier de configuration.
   - Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer l’option queryLimitReads :

     | PID | Clé de la propriété | Valeur de la propriété |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valeur : 200000 Valeur par défaut : 100000 |

1. Exécutez une requête POST au serveur (avec l’authentification correcte) - `http://<server:port>//bin/guides/reports/upgrade`.

1. L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Une fois le traitement terminé, la requête GET précédente répond avec succès. Si le traitement échoue pour une raison quelconque, l’échec est visible dans les journaux du serveur.

1. Revenez à la valeur par défaut ou à la valeur existante précédente de `queryLimitReads` si vous l’avez modifiée à l’étape 1.

## Procédure à suivre pour indexer le contenu existant afin d’utiliser la nouvelle liste de recherche et de remplacement et de rubriques sous l’onglet Rapports :

(Uniquement si vous utilisez une version antérieure à la version de septembre 2022 d’AEM Guides as a Cloud Service)

Effectuez les étapes suivantes pour indexer le contenu existant et utiliser le nouveau texte rechercher et remplacer au niveau du mappage et de la liste de rubriques sous l’onglet rapports :

1. Exécutez une requête POST au serveur \(avec l’authentification correcte\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facultatif : vous pouvez transmettre des chemins spécifiques des mappages pour les indexer. Par défaut, tous les mappages sont indexés \|\| Par exemple : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Vous pouvez également transmettre un dossier racine pour indexer les plans DITA d&#39;un dossier spécifique (et de ses sous-dossiers). Par exemple, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Notez que si le paramètre de chemins d’accès et le paramètre racine sont transmis, seul le paramètre de chemins d’accès est pris en compte.

1. L’API renvoie un jobId. Pour vérifier le statut de la tâche, vous pouvez envoyer une requête GET avec l’ID de tâche au même point d’entrée : `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(par exemple : `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\).


1. Une fois la tâche terminée, la requête GET précédente répond avec succès et mentionne si des mappages ont échoué. Les mappages indexés avec succès peuvent être confirmés à partir des journaux du serveur.

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version de juin 2023 d’AEM Guides as a Cloud Service.

### FrameMaker et FrameMaker Publishing Server

| Version d’AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.06.0 | Non compatible | 2022 ou version ultérieure |
| | | |


### Connecteur D&#39;Oxygène

| Version d’AEM Guides as a Cloud | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.06.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |  |


## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :

### Création

- Navtitle est supprimé du contenu33 lors du passage de la vue de mise en page à la vue de création ou source. (12174)
- Parfois, une erreur d&#39;application se produit lorsque vous cliquez sur un plan DITA. (11842)
- Éditeur web | Un espace insécable est ajouté dans l’éditeur XML lors de l’édition d’une rubrique. (11786)
- Interface utilisateur d’Assets | Dans la vue Liste, les colonnes disponibles superposées ne peuvent pas être fusionnées. (11528)
- Keyref n’est pas résolu en mode Carte. (11490)
- Le menu supérieur n’apparaît pas lors de la navigation dans l’éditeur XML. (10868)
- `conref` dans la balise ph | La boîte de dialogue de navigation affichée est incorrecte. (9481)
- Les liens locaux vers d’autres éléments ne sont pas résolus dans l’éditeur web. (8790)
- La fonction Matches() ne fonctionne pas dans la fonction schematron. (11224)


### Gestion

- L&#39;onglet Rapports de l&#39;interface utilisateur de l&#39;éditeur Web n&#39;affiche pas la liste de rubriques des anciens plans DITA créés avant la mise à niveau vers la version 4.2. (11708)

- La fonctionnalité du bouton Charger des fichiers dans l’interface utilisateur d’Assets interrompt la version 4.2. (11633)

### Publication

- La publication sur le site AEM échoue lors de la lecture des fichiers temporaires du pod qui peuvent avoir été actualisés ou redémarrés. (12113)
- Native PDF | La publication de contenu ayant une classe de sortie avec des crochets() entraîne un gel de la publication. (11936)
- Sortie JSON | Mappez des métadonnées dont la valeur de propriété est `"value in spaces and double quotes"` pour générer une erreur de publication. (11933)
- Éditeur web | Le chemin de sortie et le modèle ne peuvent pas être sélectionnés dans le paramètre prédéfini AEM. (11530)
- PDF natif | Les attributs personnalisés ne sont pas propagés au moteur temporaire HTML ou PDF. (DXML-12005)
- Native PDF | Java OutOfMemoryError se produit lors de la publication de contenu volumineux. (11789)
- Sortie JSON | La propriété `fmUuid` du nœud jcr:content de JSON est différente de l’« id » dans le fichier JSON. (11564)
- Sortie JSON | Si le mappage et la rubrique portant le même nom de fichier sont présents, le JSON du mappage est supprimé. (11524)
- Native PDF | Xref imprime le contenu du titre de la rubrique href au lieu du libellé Xref. (11322)
- PDF natif | Impossible d’enregistrer les paramètres du modèle PDF. (10751)
- PDF natif | Le texte s’étend au-delà de la largeur de colonne lors de l’inclusion de plusieurs xréfs. (10876)
- L’élément Native PDF | `<note>` `</note>` ne génère pas de titre d’étendue supplémentaire de son type. (10549)
- PDF natif | Les métadonnées de langue ne peuvent pas être définies dans le PDF généré pour se conformer au WCAG 2.0. (12296)



### Traduction

- Après la version cloud de février (2302), tout le contenu de traduction s’affiche Désynchronisé ou Copie manquante. (11834)

### Révision

- Nouvelle interface utilisateur de révision | Les conditions mettent en surbrillance et affichent le travail de masquage différemment de leur fonctionnement dans l’éditeur web. (11628)
