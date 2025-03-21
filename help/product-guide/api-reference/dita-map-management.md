---
title: API REST pour travailler avec des mappages DITA
description: En savoir plus sur l’API REST pour utiliser les mappages DITA
exl-id: 6277e52d-1b05-4dd7-8d2b-4b94f329e2d7
feature: Rest API DITA Map
role: Developer
level: Experienced
source-git-commit: 1843cae11aac38053abc3c50fa2d00c050520470
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 4%

---

# API REST pour travailler avec des mappages DITA {#id175UB30E05Z}

L’API REST suivante vous permet d’utiliser des mappages DITA dans AEM Guides.

## Téléchargement du mappage DITA avec des dépendances

Méthode de GET qui télécharge un mappage DITA avec toutes ses dépendances, telles que les rubriques référencées, les sous-cartes, les images et les DTD utilisées dans le mappage et les rubriques.

**Demander l’URL** :
http://*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/fmdita/exportditamap

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `ditamap` | Chaîne | Oui | Chemin d’accès absolu au fichier de mappage DITA dans AEM référentiel. |
| `baseline` | Chaîne | Non | Titre de la ligne de base utilisée pour récupérer le contenu versionné. <br> **Remarque :** La valeur est sensible à la casse. |

**Valeurs de réponse** :
Un fichier .zip dont le contenu est écrit dans le flux de sortie de la réponse.

## Lancement de l’exportation pour le mappage DITA avec les dépendances

Méthode de POST qui initie une exportation pour un mappage DITA avec toutes ses dépendances telles que les rubriques référencées, les sous-cartes, les images et les DTD utilisées dans la carte et les rubriques. L’état peut ensuite être interrogé et l’URL de téléchargement peut être récupérée une fois l’opération terminée.

**Demander l’URL** :
http:*//&lt;aem-guides-server\>: &lt;port-number\>/bin/dxml/async-export*

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `ditamap` | Chaîne | Oui | Chemin d’accès absolu au fichier de mappage DITA dans AEM référentiel. |
| `baseline` | Chaîne | Non | Titre de la ligne de base utilisée pour récupérer le contenu versionné. <br> **Remarque :** La valeur est sensible à la casse. |
| `flatFS` | Booléen | Non | \(Facultatif\) Si la valeur est définie sur true, une structure plate des fichiers est renvoyée dans le fichier ZIP. Par exemple, si votre mappage DITA fait référence au contenu de plusieurs dossiers, tous les fichiers référencés sont extraits dans un seul dossier. S’il existe des fichiers portant le même nom, ces fichiers sont renommés en ajoutant un suffixe numérique. Toutes les références \(dans le mappage DITA et les rubriques\) sont gérées automatiquement, car elles sont mises à jour en fonction du nouvel emplacement des fichiers dans la structure de dossiers plate. S’il est défini sur false, la structure de dossiers est conservée telle quelle dans le fichier ZIP. Si le mappage DITA fait référence à des fichiers provenant de plusieurs emplacements, tous ces emplacements sont également créés dans le fichier ZIP. Lorsque vous restaurez le fichier ZIP, la structure exacte des dossiers est créée à l’emplacement de destination. <br> La valeur par défaut de ce paramètre est false. |

**Valeurs de réponse** :

| Elément | Description |
|-------|-----------|
| `status` | État de retour de l’opération effectuée. Les options possibles sont : DÉMARRER, ÉCHEC, INPROGRESSER, SUCCÈS, MANQUANT, SUPPRIMÉ. |
| `jobId` | Identifiant unique de la tâche. Peut être utilisé ultérieurement pour interroger l’état. |
| errorMessage | Message d’erreur de la tâche en cas d’échec \(si l’état est EN ÉCHEC, MANQUANT ou SUPPRIMÉ\). |
| `filePath` | Chemin d’accès au fichier du fichier ZIP. Il est présent uniquement lorsque la tâche est terminée et que l’état est SUCCEED. Vous pouvez l’utiliser pour télécharger le fichier ZIP. |

## Statut du mappage DITA d’export de requête

Méthode de GET qui récupère l’état de l’exportation pour un mappage DITA avec tous ses dépendances. Il peut être interrogé à un intervalle si l’état est DÉMARRÉ ou INPROGRESSÉ jusqu’à ce qu’il soit terminé \(avec succès ou avec une erreur\).

**Demander l’URL** :
http:*//&lt;aem-guides-server\>: &lt;port-number\>/bin/dxml/async-export*

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `jobId` | Chaîne | Oui | Identifiant de tâche récupéré lors du lancement de la tâche d’exportation. |

**Valeurs de réponse** :

| Elément | Description |
|-------|-----------|
| `status` | État de la tâche d’exportation. Les options possibles sont : DÉMARRER, ÉCHEC, INPROGRESSER, SUCCÈS, MANQUANT, SUPPRIMÉ. |
| `jobId` | Identifiant unique de la tâche. Peut être utilisé ultérieurement pour interroger l’état. |
| `errorMessage` | Message d’erreur de la tâche en cas d’échec \(si l’état est EN ÉCHEC, MANQUANT ou SUPPRIMÉ\). |
| `filePath` | Chemin d’accès au fichier du fichier ZIP. Il est présent uniquement lorsque la tâche est terminée et que l’état est SUCCEED. Vous pouvez l’utiliser pour télécharger le fichier ZIP. |
