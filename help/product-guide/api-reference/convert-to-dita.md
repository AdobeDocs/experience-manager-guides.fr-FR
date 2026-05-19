---
title: API REST pour le workflow de conversion
description: En savoir plus sur les API REST pour le workflow de conversion
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/EG-ugDPVpviaEI1SXHOaFLPfChkzqQ8tSkPV-LZ-X3o
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 402
ht-degree: 9%

---

# API REST pour le workflow de conversion {#id175UB30E05Z}

Les API REST suivantes vous permettent de convertir des documents Word, HTML et InDesign au format DITA.

## Convertir des documents Word

Méthode GET qui convertit des documents Word au format DITA.

**URL de la requête** :
*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/fmdita/conversion

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| ``operation`` | Chaîne | Oui | Nom de l’opération appelée. La valeur de ce paramètre est ``word2dita``. <br> **Remarque :** la valeur ne respecte pas la casse. |
| `inputFile` | Chaîne | Oui | Chemin d’accès absolu aux fichiers Word sources dans le référentiel AEM. |
| `destPath` | Chaîne | Oui | Chemin d&#39;accès absolu à l&#39;emplacement de destination où les fichiers DITA convertis seront enregistrés. |
| `createRev` | Booléen | Oui | Indiquez si une révision des fichiers est créée \( `true`\) à la destination spécifiée ou non \( `false`\). Cela n’est pris en compte que lorsque l’emplacement de destination contient une version existante des fichiers convertis. |
| `style2tagMap` | Chaîne | Oui | Chemin d’accès absolu au fichier de mappage de style qui sera utilisé pour la conversion. |

**Valeurs de réponse** :
Renvoie une réponse HTTP 200 \(Successful\).

## Convertir des documents HTML

Méthode GET qui convertit des documents HTML au format DITA.

**URL de la requête** :

*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/fmdita/conversion

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| `operation` | Chaîne | Oui | Nom de l’opération appelée. La valeur de ce paramètre est ``html2dita``. <br> **Remarque :** la valeur ne respecte pas la casse. |
| `inputFile` | Chaîne | Oui | Chemin d’accès absolu aux fichiers HTML sources dans le référentiel AEM. |
| `destPath` | Chaîne | Oui | Chemin d&#39;accès absolu à l&#39;emplacement de destination où les fichiers DITA convertis seront enregistrés. |
| `createRev` | Booléen | Oui | Indiquez si une révision des fichiers est créée \( `true`\) à la destination spécifiée ou non \( `false`\). Cela n’est pris en compte que lorsque l’emplacement de destination contient une version existante des fichiers convertis. |

**Valeurs de réponse** :

Renvoie une réponse HTTP 200 \(Successful\).

## Convertir des documents InDesign

Méthode GET qui convertit des documents InDesign au format DITA.

**URL de la requête** :
*&lt;aem-guides-server\>* : *&lt;port-number\>*/bin/fmdita/conversion

**Paramètres** :

| Nom | Type | Requis | Description |
|----|----|--------|-----------|
| ``operation`` | Chaîne | Oui | Nom de l’opération appelée. La valeur de ce paramètre est ``idml2dita``. <br> **Remarque :** la valeur ne respecte pas la casse. |
| `inputFile` | Chaîne | Oui | Chemin d’accès absolu aux fichiers InDesign sources dans le référentiel AEM. |
| `destPath` | Chaîne | Oui | Chemin d&#39;accès absolu à l&#39;emplacement de destination où les fichiers DITA convertis seront enregistrés. |
| `createRev` | Booléen | Oui | Indiquez si une révision des fichiers est créée \( `true`\) à la destination spécifiée ou non \( `false`\). Cela n’est pris en compte que lorsque l’emplacement de destination contient une version existante des fichiers convertis. |

**Valeurs de réponse** :
Renvoie une réponse HTTP 200 \(Successful\).
