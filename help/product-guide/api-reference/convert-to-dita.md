---
title: API REST pour le workflow de conversion
description: En savoir plus sur les API REST pour le workflow de conversion
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: 45ae1471fe0f0586764ede9dd96530b7f75f69ee
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 9%

---

# API REST pour le workflow de conversion {#id175UB30E05Z}

Les API REST suivantes vous permettent de convertir des documents Word, HTML et InDesign au format DITA.

## Conversion de documents Word

Méthode de GET qui convertit les documents Word au format DITA.

**Demander l’URL** :
http://*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/fmdita/conversion

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| ``operation`` | Chaîne | Oui | Nom de l’opération en cours d’appel. La valeur de ce paramètre est ``word2dita``. <br> **Remarque :** La valeur n’est pas sensible à la casse. |
| `inputFile` | Chaîne | Oui | Chemin d’accès absolu aux fichiers Word source dans AEM référentiel. |
| `destPath` | Chaîne | Oui | Chemin absolu de l’emplacement de destination où les fichiers DITA convertis seront enregistrés. |
| `createRev` | Booléen | Oui | Indiquez si une révision des fichiers est créée \( `true`\) à la destination spécifiée ou non \( `false`\). Cela n’est pris en compte que lorsque l’emplacement de destination contient une version existante des fichiers convertis. |
| `style2tagMap` | Chaîne | Oui | Chemin d’accès absolu au fichier de mappage de style qui sera utilisé pour la conversion. |

**Valeurs de réponse** :
Renvoie une réponse HTTP 200 \(Succès\).

## Convertir des documents d’HTML

Méthode de GET qui convertit les documents HTMLS au format DITA.

**Demander l’URL** :

http://*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/fmdita/conversion

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `operation` | Chaîne | Oui | Nom de l’opération en cours d’appel. La valeur de ce paramètre est ``html2dita``. <br> **Remarque :** La valeur n’est pas sensible à la casse. |
| `inputFile` | Chaîne | Oui | Chemin d’accès absolu aux fichiers d’HTML source dans le référentiel AEM. |
| `destPath` | Chaîne | Oui | Chemin absolu de l’emplacement de destination où les fichiers DITA convertis seront enregistrés. |
| `createRev` | Booléen | Oui | Indiquez si une révision des fichiers est créée \( `true`\) à la destination spécifiée ou non \( `false`\). Cela n’est pris en compte que lorsque l’emplacement de destination contient une version existante des fichiers convertis. |

**Valeurs de réponse** :

Renvoie une réponse HTTP 200 \(Succès\).

## Convertir des documents d’InDesign

Méthode de GET qui convertit les documents InDesigns au format DITA.

**Demander l’URL** :
http://*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/fmdita/conversion

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| ``operation`` | Chaîne | Oui | Nom de l’opération en cours d’appel. La valeur de ce paramètre est ``idml2dita``. <br> **Remarque :** La valeur n’est pas sensible à la casse. |
| `inputFile` | Chaîne | Oui | Chemin d’accès absolu aux fichiers d’InDesign source dans le référentiel AEM. |
| `destPath` | Chaîne | Oui | Chemin absolu de l’emplacement de destination où les fichiers DITA convertis seront enregistrés. |
| `createRev` | Booléen | Oui | Indiquez si une révision des fichiers est créée \( `true`\) à la destination spécifiée ou non \( `false`\). Cela n’est pris en compte que lorsque l’emplacement de destination contient une version existante des fichiers convertis. |

**Valeurs de réponse** :
Renvoie une réponse HTTP 200 \(Succès\).
