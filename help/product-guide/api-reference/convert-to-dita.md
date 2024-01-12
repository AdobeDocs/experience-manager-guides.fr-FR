---
title: API REST pour le workflow de conversion
description: En savoir plus sur les API REST pour le workflow de conversion
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# API REST pour le workflow de conversion {#id175UB30E05Z}

Les API REST suivantes vous permettent de convertir des documents Word, HTML et InDesign au format DITA.

## Conversion de documents Word

Méthode de GET qui convertit les documents Word au format DITA.

**URL de la requête**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/conversion

**Paramètres**: |Nom|Type|Obligatoire|Description| |—|—|—|— |``operation``|String|Yes|Nom de l’opération en cours d’appel. La valeur de ce paramètre est ``word2dita``. <br> **Remarque :** La valeur n’est pas sensible à la casse. | |`inputFile`|Chaîne|Oui|Chemin absolu des fichiers Word source dans le référentiel AEM.| |`destPath`|String|Yes|Chemin absolu de l’emplacement de destination où les fichiers DITA convertis seront enregistrés.| |`createRev`|Booléen|Oui|Indiquez si une révision des fichiers est créée \( `true`\) à la destination spécifiée ou non \( `false`\). Cela n’est pris en compte que lorsque l’emplacement de destination contient une version existante des fichiers convertis.| |`style2tagMap`|Chaîne|Oui|Chemin absolu du fichier de mappage de style qui sera utilisé pour la conversion.|

**Valeurs de réponse**: renvoie une réponse HTTP 200 \(réussie\).

## Conversion de documents de HTML

Méthode de GET qui convertit les documents de HTML au format DITA.

**URL de la requête**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/conversion

**Paramètres**: |Nom|Type|Obligatoire|Description| |—|—|—|— |`operation`|String|Yes|Nom de l’opération en cours d’appel. La valeur de ce paramètre est ``html2dita``. <br> **Remarque :** La valeur n’est pas sensible à la casse.| |`inputFile`|String|Yes|Chemin absolu des fichiers de HTML source dans le référentiel AEM.| |`destPath`|String|Yes|Chemin absolu de l’emplacement de destination où les fichiers DITA convertis seront enregistrés.| |`createRev`|Booléen|Oui|Indiquez si une révision des fichiers est créée \( `true`\) à la destination spécifiée ou non \( `false`\). Ceci est pris en compte uniquement lorsque l’emplacement de destination contient une version existante des fichiers convertis.|

**Valeurs de réponse**: renvoie une réponse HTTP 200 \(réussie\).

## Convertir des documents d’InDesign

Méthode de GET qui convertit les documents InDesigns au format DITA.

**URL de la requête**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/conversion

**Paramètres**: |Nom|Type|Obligatoire|Description| |—|—|—|— |``operation``|String|Yes|Nom de l’opération en cours d’appel. La valeur de ce paramètre est ``idml2dita``. <br> **Remarque :** La valeur n’est pas sensible à la casse.| |`inputFile`|String|Yes|Chemin absolu des fichiers d’InDesign source dans le référentiel AEM.| |`destPath`|String|Yes|Chemin absolu de l’emplacement de destination où les fichiers DITA convertis seront enregistrés.| |`createRev`|Booléen|Oui|Indiquez si une révision des fichiers est créée \( `true`\) à la destination spécifiée ou non \( `false`\). Ceci est pris en compte uniquement lorsque l’emplacement de destination contient une version existante des fichiers convertis.|

**Valeurs de réponse**: renvoie une réponse HTTP 200 \(réussie\).
