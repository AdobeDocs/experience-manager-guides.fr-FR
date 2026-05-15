---
title: Amélioration des performances de traduction de vos fichiers DITA dans les guides AEM
description: Bonnes pratiques, conseils et astuces pour améliorer les performances des projets de traduction DITA dans AEM Guides
feature: Translation
role: User, Admin
author: Pulkit Nagpal (punagpal)
exl-id: d7e4f3ae-2143-4767-b7ab-c89f5e5eef59
TQID: https://experienceleague.adobe.com/n6-b3-ZsOIueVYWgcm1NkDLKRAOwQhWxctbgj7Q6P1U
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 324
ht-degree: 0%

---

# Bonnes pratiques à suivre pour la traduction dans AEM Guides

Les performances de votre projet de traduction peuvent diminuer à mesure que l’activité de traduction sur le système augmente.

Chaque projet de traduction génère plusieurs groupes d’utilisateurs pour l’accès, ce qui entraîne une augmentation du nombre de groupes d’utilisateurs dans le système. À mesure que le nombre de groupes d’utilisateurs augmente, cela peut progressivement ralentir les opérations CRUD liées aux autorisations d’utilisateur, ce qui peut avoir un impact sur les performances globales d’AEM. En outre, si les projets de traduction restent actifs une fois terminés, cela peut avoir un impact négatif sur les performances de la synchronisation de traduction entre AEM et le fournisseur de traduction.

**Le respect des bonnes pratiques décrites ci-dessous contribue au maintien d’un environnement efficace.**

## Si vous utilisez une version antérieure à 4.6 (on-prem) ou 2404 (cloud) :

- Marquez tous les projets comme « Inactifs » une fois la traduction terminée et approuvée.Le projet reste disponible pour examen et est simplement marqué comme inactif.
   - Suivre ces étapes vous aidera à maintenir les performances globales de traduction en bonne santé.
     ![Projet de traduction inactif &#x200B;](../assets/translation/translation-project-image1.png)

- Pour les projets plus anciens, le dossier marqué comme inactif, approuvé et révisé doit être supprimé
   - Le fait de suivre ces étapes permet de maintenir les performances globales de traduction en bon état en nettoyant les fichiers de traduction temporaires et les groupes d’utilisateurs associés à ce dossier de projet.
     ![Suppression de projets de traduction et de &#x200B;](../assets/translation/translation-project-image2.png) de dossiers


## Si vous êtes sur , créez la version 4.6 ou 2404 ou une version ultérieure :

Vous pouvez continuer à suivre les mêmes étapes que celles mentionnées ci-dessus. À partir de la version 4.6/2404, AEM Guides introduit un paramètre d’éditeur permettant aux administrateurs de désactiver la suppression automatisée des projets de traduction.

Référencer : [supprimer ou désactiver automatiquement un projet de traduction terminé](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/user-guide/author-content/create-preview-topics/author-content-aem-guides/work-with-web-editor/translate-documents-web-editor#automatically-delete-or-disable-a-completed-translation-project)

![Paramètres automatisés pour supprimer et désactiver un projet de traduction dans AEM Guides &#x200B;](../assets/translation/translation-project-image3.png)
