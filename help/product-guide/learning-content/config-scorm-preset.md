---
title: Configuration du préréglage SCORM
description: Découvrez les différentes configurations de paramètres prédéfinis SCORM dans la section Formation et apprentissage du produit
feature: Authoring
role: User
exl-id: b3000708-6120-4725-bea1-0b8e58048948
TQID: https://experienceleague.adobe.com/9WSwgksrX0fahrniOalbizWFXCqcW0QlGAHn707vm-k
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 275
ht-degree: 0%

---

# Configuration du paramètre prédéfini de sortie SCORM

Une fois le paramètre prédéfini créé, configurez-le. Les options de configuration des paramètres prédéfinis sont organisées sous les onglets Général, Contenu et Publication .

- **Général :** utilisé pour spécifier des paramètres de sortie de base, tels que la version prise en charge, le chemin de sortie, le nom de fichier ZIP, le modèle de sortie et d’autres options liées à l’expérience de l’élève.

  ![](assets/scorm-general-tab-v3.png){width="650"}

  **Expérience de l’élève**

   - **Les élèves doivent progresser dans le contenu dans un ordre séquentiel** : garantit que les élèves passent par le quiz dans une séquence fixe et ne peuvent pas sauter d’une question à l’autre.
   - **Les élèves doivent répondre à chaque question pour continuer** : nécessite que les élèves répondent à toutes les questions avant de pouvoir envoyer le quiz, ce qui empêche les envois incomplets.
   - **Ordre aléatoire des questions pour chaque tentative** : affiche les questions du quiz dans un ordre différent pour chaque tentative, ce qui contribue à réduire la prévisibilité.
   - **Randomiser les choix de réponses pour chaque tentative** : mélange les options de réponse pour chaque question à chaque tentative, ce qui réduit les risques de suppositions en fonction de la position.
   - **Utiliser l’ID de question dans les rapports de quiz** : inclut l’ID de question unique dans les rapports de quiz, ce qui facilite le suivi, l’analyse et le mappage des résultats à des questions spécifiques.
   - **Workflow de post-génération** : lorsque vous sélectionnez cette option, une nouvelle liste déroulante Workflow de post-génération contenant tous les workflows configurés s’affiche.

- **Contenu :** permet de spécifier le filtrage conditionnel disponible (à l’aide de DITAVAL ou d’un paramètre prédéfini de condition) et le jeu de variables.

  ![](assets/scorm-content-tab.png){width="650"}

- **Publier :** utilisez ce paramètre uniquement si vous souhaitez publier la sortie dans SCORM Cloud pour un accès direct.

  ![](assets/scorm-publish-tab.png){width="650"}

Une fois toutes les modifications configurées, enregistrez-les pour le paramètre prédéfini SCORM à l’aide de l’option **Enregistrer** dans le coin droit de la barre d’outils de la page du paramètre prédéfini SCORM.
