---
title: Workflow de post-génération
description: Présentation du workflow de post-génération avec un exemple
exl-id: e19fdc0b-0ec6-46ce-81ed-e9490d12c029
feature: Workflow Configuration
role: User, Admin
TQID: https://experienceleague.adobe.com/GmpUvIwR5aDOIQ4RNUXoeOeQB3MrueRuxpvYBwYev4I
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b455a250-64c4-4598-b015-7b6b6dc528b1id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 327
ht-degree: 2%

---

# Publication AEM Guides - Workflow de post-génération

AEM Guides vous offre la possibilité de spécifier un workflow de génération post-sortie. Vous pouvez effectuer certaines tâches de post-traitement sur la sortie générée à l’aide d’AEM Guides.
Par exemple, vous pouvez définir certaines propriétés sur la sortie PDF ou envoyer un e-mail à un ensemble d’utilisateurs une fois la sortie générée.


## Quelles sont les étapes nécessaires pour utiliser les workflows de post-génération ?

### Création d’un processus de workflow

Créez un processus de workflow basé sur Java ou ECMA qui effectue l’opération sur la sortie générée. Par exemple, la copie de métadonnées de la source vers le contenu généré ou la manipulation des métadonnées de la sortie générée.
- Nous allons prendre un exemple de création d’un tel processus à l’aide d’un script ECMA (vous pouvez vous référer au package joint)
- Pour le processus de workflow basé sur Java, reportez-vous à la section « *Personnaliser le workflow de génération post-sortie* » du [Guide d’installation et de configuration](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_Installation-Configuration-Guide_EN.pdf#page=119)


### Créer un modèle de processus

Avec le processus de workflow personnalisé que vous avez créé à l’étape précédente, créez un modèle de workflow et ajoutez-y cette étape de processus.
- Vous devez également ajouter une étape de processus obligatoire « *Finaliser la post-génération* » comme dernière étape du workflow.

Consultez l’exemple de modèle de workflow illustré ci-dessous :

![ Modèle de workflow de post-génération ](../assets/workflows/pgwf-workflow-model.png)


### Utiliser ce workflow de post-génération sur une carte

Le workflow de post-génération est une propriété qui peut être configurée sur n’importe quel paramètre prédéfini de sortie dans le mécanisme de publication d’AEM Guides. Exemple :

![Workflow de post-génération sur le paramètre prédéfini de sortie](../assets/workflows/pgwf-preset-settings.png)


En supposant que le modèle sélectionné soit déjà créé.


### Tests

Vous pouvez maintenant exécuter la publication à l’aide de ce paramètre prédéfini et valider la sortie de l’étape de processus


## Échantillon

À titre de référence, vous pouvez utiliser le package ci-dessous et l’installer via le gestionnaire de packages pour tester l’exemple de workflow de post-génération (*comme indiqué dans les captures d’écran ci-dessus*)

[Exemple de modèle de workflow de post-génération basé sur ECMA](../assets/workflows/sample-pgwf-ecma-test-wfmetadata.zip)
