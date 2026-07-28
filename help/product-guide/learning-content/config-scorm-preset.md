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
source-git-commit: dbb138a7804d102d1b9aa9cfbc3564e827ef199e
workflow-type: tm+mt
source-wordcount: 678
ht-degree: 0%

---

# Configuration du paramètre prédéfini de sortie SCORM

Une fois le paramètre prédéfini créé, configurez-le. Les options de configuration prédéfinies sont organisées sous les onglets Général, Contenu, Expérience de l’élève et Publication.

- **Général :** utilisé pour spécifier des paramètres de sortie de base, tels que la version prise en charge, le chemin de sortie, le nom de fichier SCORM (zip), le modèle de sortie et le workflow de post-génération pour une nouvelle liste déroulante de workflow de post-génération contenant tous les workflows configurés.

  ![](assets/scorm-general-tab-v3.png){width="650"}


- **Contenu :** permet de spécifier le filtrage conditionnel disponible (à l’aide de DITAVAL ou d’un paramètre prédéfini de condition) et le jeu de variables.

  ![](assets/scorm-content-tab.png){width="650"}

- **Expérience de l’élève :** l’onglet **Expérience de l’élève** vous permet de configurer la manière dont les élèves interagissent avec la sortie SCORM et la parcourent. Les paramètres sont organisés sous **Général**, **Navigation** et **Quiz**, ce qui vous permet de contrôler l’accessibilité du contenu, le flux de navigation et le comportement du quiz pour une expérience d’apprentissage personnalisée.

  ![](assets/learner-experience.png){width="650"}

  - **Général :** configurer des options au niveau de la sortie, telles que l’activation des téléchargements PDF pour les élèves.

    - **Autoriser les élèves à télécharger le cours PDF** : lorsqu’elle est activée, cette option ajoute une icône PDF à la sortie SCORM. Cliquez sur cette icône pour permettre à l’élève de télécharger une version PDF du contenu du cours directement depuis la sortie publiée.

      **Conditions préalables :** Avant d’activer cette option, vérifiez les points suivants :

      - Le **modèle de sortie** doit être configuré avec l’icône **Incorporer PDF** à l’emplacement souhaité et le même modèle doit être sélectionné sous l’option **modèle de sortie** de l’onglet **Général** lors de la configuration d’un paramètre prédéfini SCORM.

        ![](assets/embed-pdf.png){width="650"}

      - Le **paramètre prédéfini de PDF natif** associé doit avoir été généré au moins une fois. La sélection d’un paramètre prédéfini PDF non généré entraîne une erreur invitant l’utilisateur à publier le paramètre prédéfini.

    Une fois la sortie SCORM générée avec les paramètres ci-dessus, la sortie obtenue comprend une icône PDF, comme illustré ci-dessous, qui permet aux élèves de télécharger le cours PDF.

    ![](assets/pdf-icon.png){width="650"}

  - **Navigation :** définit la manière dont les élèves se déplacent dans le cours, y compris la progression séquentielle, les conditions d’achèvement obligatoires et les règles de déverrouillage du bouton **Suivant**.

    - **Les élèves doivent progresser dans le contenu dans un ordre séquentiel** : garantit que les élèves suivent le cours dans une séquence fixe et ne peuvent pas avancer ou passer d’un composant de cours à l’autre.
    - **Désactiver le bouton suivant si l’élève n’a pas réussi le quiz** : empêche l’élève de passer à la section/page suivante jusqu’à ce qu’il ait réussi le quiz.
    - **Les élèves doivent répondre à chaque question pour continuer** : nécessite que les élèves répondent à toutes les questions avant de pouvoir envoyer le quiz, ce qui empêche les envois incomplets.
    - **Verrouiller la progression jusqu’à la fin** : empêche la navigation dans le cours jusqu’à ce que toutes les sous-conditions configurées ci-dessous soient remplies en désactivant le bouton **Suivant** dans le cours.
      - **Tous les éléments interactifs ouverts** : nécessite que l’élève ouvre chaque élément interactif de la page.
      - **Tous les médias regardés** : nécessite que l’élève regarde tous les médias vidéo/audio de la page.
      - **Toutes les vérifications de connaissances ont été tentées** : nécessite que l’élève tente de répondre à chaque question de vérification de connaissances sur la page.
      - **Durée minimale de consultation de la page** : l’élève doit rester sur la page pendant au moins la durée spécifiée avant que le bouton Suivant ne soit activé. Une fois activé, vous devez saisir le temps nécessaire, comme indiqué ci-dessous.
        - **Durée requise (secondes)** : nombre minimum de secondes (par exemple, `30`) pendant lesquelles un élève doit rester sur la page pour que cette condition soit remplie.

  - **Quiz :** configurez le comportement lié au quiz, tel que la randomisation de l’ordre des questions et des choix de réponses pour réduire la prévisibilité entre les tentatives.

    - **Ordre aléatoire des questions pour chaque tentative** : affiche les questions du quiz dans un ordre différent pour chaque tentative, ce qui contribue à réduire la prévisibilité.
    - **Randomiser les choix de réponses pour chaque tentative** : mélange les options de réponse pour chaque question à chaque tentative, ce qui réduit les chances de deviner.

- **Publier dans LMS :** utilisez ce paramètre pour publier votre contenu directement dans Adobe Learning Manager (ALM). Dans la liste déroulante **Serveur de publication**, sélectionnez **Adobe Learning Manager**, puis choisissez le **Profil de publication** requis précédemment configuré dans les paramètres de Workspace. Le profil sélectionné est utilisé pour établir la connexion et charger le contenu généré vers AEM.

  >[!NOTE]
  >
  > Avant de publier du contenu dans ALM, vous devez configurer un profil de publication Adobe Learning Manager. Pour plus d’informations, consultez [Publication de profils](../lc-config-guide/lc-folder-profile.md).

  ![](assets/scorm-publish-lms.png){width="650"}

Une fois toutes les modifications configurées, enregistrez-les pour le paramètre prédéfini SCORM à l’aide de l’option **Enregistrer** dans le coin droit de la barre d’outils de la page du paramètre prédéfini SCORM.
