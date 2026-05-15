---
title: API REST pour utiliser les plans DITA
description: En savoir plus sur l'API REST pour utiliser les plans DITA
exl-id: 6277e52d-1b05-4dd7-8d2b-4b94f329e2d7
feature: Rest API DITA Map
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/GT4JRw1nFV7M18tJX-0t0Gx-g0I9tA8XfXLGnnhvif0
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: c6d09140-3c91-45d3-b7ed-b681af752f43
subfeature_v2: id: b7cb7f25-3b6d-4e58-beab-fe9279275fe4
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 626
ht-degree: 4%

---

# API REST pour utiliser les plans DITA {#id175UB30E05Z}

L&#39;API REST suivante vous permet d&#39;utiliser des plans DITA dans AEM Guides.

## Télécharger le plan DITA avec les personnes à charge

Méthode GET qui télécharge un plan DITA avec toutes ses dépendances telles que les rubriques référencées, les sous-plans, les images et les DTD utilisés dans le plan et les rubriques.

**URL de la requête** :
*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/fmdita/exportditamap

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `ditamap` | Chaîne | Oui | Chemin d&#39;accès absolu au fichier de mappage DITA dans le référentiel AEM. |
| `baseline` | Chaîne | Non | Titre de la ligne de base utilisée pour récupérer le contenu avec version. <br> **Remarque :** la valeur respecte la casse. |

**Valeurs de réponse** :
Fichier .zip dont le contenu est écrit dans le flux de sortie de la réponse.

## Lancement de l&#39;export pour un plan DITA avec des dépendances

Méthode POST qui lance une exportation pour un plan DITA avec toutes ses dépendances telles que les rubriques référencées, les sous-plans, les images et les DTD utilisés dans le plan et les rubriques. Le statut peut ensuite être interrogé et l’URL de téléchargement peut être récupérée une fois l’opération terminée.

**URL de la requête** :
http:*//&lt;aem-guides-server\>: &lt;port-number\>/bin/dxml/async-export*

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `ditamap` | Chaîne | Oui | Chemin d&#39;accès absolu au fichier de mappage DITA dans le référentiel AEM. |
| `baseline` | Chaîne | Non | Titre de la ligne de base utilisée pour récupérer le contenu avec version. <br> **Remarque :** la valeur respecte la casse. |
| `flatFS` | Booléen | Non | \(Facultatif\) Si cet attribut est défini sur true, une structure plate de fichiers est renvoyée dans le fichier ZIP. Par exemple, si votre plan DITA fait référence à du contenu situé dans plusieurs dossiers, tous les fichiers référencés sont extraits dans un seul dossier. Si des fichiers portent le même nom, ils sont renommés en ajoutant un suffixe numérique. Toutes les références \(dans plan DITA et rubriques\) sont gérées automatiquement, car elles sont mises à jour en fonction du nouvel emplacement des fichiers dans la structure de dossiers plate. Si cette valeur est définie sur false, la structure de dossiers est conservée telle quelle dans le fichier ZIP. Si le plan DITA fait référence à des fichiers provenant de plusieurs emplacements, tous ces emplacements sont également créés dans le fichier ZIP. Lorsque vous restaurez le fichier ZIP, la structure de dossiers exacte est créée à l’emplacement de destination. <br> La valeur par défaut de ce paramètre est false. |

**Valeurs de réponse** :

| Elément | Description |
|-------|-----------|
| `status` | Statut de retour de l’opération effectuée. Les options possibles sont : DÉMARRÉ, ÉCHEC, EN COURS, RÉUSSI, MANQUANT, SUPPRIMÉ |
| `jobId` | Identifiant unique de la tâche. Peut être utilisé ultérieurement pour interroger le statut. |
| errorMessage | Message d’erreur de la tâche en cas d’échec \(si le statut est sur ÉCHEC, MANQUANT ou SUPPRIMÉ\). |
| `filePath` | Chemin d’accès au fichier ZIP. Il n’est présent que lorsque la tâche est terminée et que le statut est SUCCÈS. Vous pouvez l’utiliser pour télécharger le fichier ZIP. |

## Demander le statut du mappage DITA d&#39;exportation

Méthode GET qui récupère le statut d&#39;exportation d&#39;un plan DITA avec toutes ses dépendances. Il peut être interrogé à intervalles réguliers si l’état est DÉMARRÉ ou EN COURS jusqu’à ce qu’il soit terminé \(avec succès ou avec une erreur\).

**URL de la requête** :
http:*//&lt;aem-guides-server\>: &lt;port-number\>/bin/dxml/async-export*

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `jobId` | Chaîne | Oui | La tâche est récupérée lorsque la tâche d’exportation est lancée. |

**Valeurs de réponse** :

| Elément | Description |
|-------|-----------|
| `status` | Statut de la tâche d’exportation. Les options possibles sont : DÉMARRÉ, ÉCHEC, EN COURS, RÉUSSI, MANQUANT, SUPPRIMÉ |
| `jobId` | Identifiant unique de la tâche. Peut être utilisé ultérieurement pour interroger le statut. |
| `errorMessage` | Message d’erreur de la tâche en cas d’échec \(si le statut est sur ÉCHEC, MANQUANT ou SUPPRIMÉ\). |
| `filePath` | Chemin d’accès au fichier ZIP. Il n’est présent que lorsque la tâche est terminée et que le statut est SUCCÈS. Vous pouvez l’utiliser pour télécharger le fichier ZIP. |
