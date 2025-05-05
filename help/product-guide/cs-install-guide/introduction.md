---
title: À propos de ce guide
description: En savoir plus sur ce guide
exl-id: cdd40267-3f0c-40d2-acbc-2ebe43633c2f
feature: Introduction
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 3%

---

# À propos de ce guide {#id175MC0P0S5Z}

Adobe Experience Manager Guides \(plus tard appelé *AEM Guides*\) est une puissante solution de gestion de contenu de composants cloud de niveau entreprise \(CCMS\). Il active la prise en charge native de DITA dans Adobe Experience Manager, ce qui permet à AEM de gérer la création et la diffusion de contenu basé sur DITA. Il permet aux auteurs de créer du contenu à l’aide de l’éditeur web intégré et de le publier dans divers formats de sortie.

Ce guide fournit des instructions pour télécharger, installer et configurer AEM Guides. Dans ce guide, vous trouverez des instructions détaillées pour configurer AEM Guides en fonction de vos besoins de création et de publication au sein de votre organisation.

Ce guide s’adresse aux types d’audiences suivants :

- Les administrateurs qui installent et gèrent AEM Guides.

- Les éditeurs qui exécutent la tâche de publication pour générer une sortie dans divers formats.


## Structure du contenu

Les informations contenues dans ce guide sont organisées comme suit :

- [À propos de ce guide](#id175MC0P0S5Z) : cette rubrique présente ce guide, l’audience prévue et la manière dont les informations sont organisées dans ce guide.

- [Télécharger et installer](download-install.md#) : cette rubrique décrit comment télécharger, installer ou mettre à niveau AEM Guides.

- [Administration et sécurité des utilisateurs](user-admin-sec.md#) : cette rubrique décrit le concept de base des utilisateurs et de l’authentification dans AEM et les groupes d’utilisateurs par défaut créés par AEM Guides.

- [Utiliser la spécialisation DITA-OT et DITA personnalisée](dita-ot-specialization.md#) : cette rubrique explique comment configurer des modules externes DITA-OT personnalisés et utiliser la spécialisation DITA.

- [Configurer des états de document](customize-doc-state.md#) : cette rubrique explique comment configurer des états personnalisés pour vos documents DITA.

- [Migrer le contenu existant](migrate-content.md#) : cette rubrique décrit comment embarquer votre contenu existant sur le référentiel AEM.

- [Configurer les noms de fichier](conf-file-names.md#) : cette rubrique explique comment configurer le paramètre pour attribuer automatiquement des noms de fichier et définir une expression régulière pour les caractères de nom de fichier valides.

- [Configurer des modèles de rubrique et de mappage](conf-template-tags.md#) : cette rubrique décrit comment configurer des modèles de rubrique et de mappage pour répondre à vos besoins de création. Découvrez le système de balisage dans AEM et comment configurer des balises pour qu’elles fonctionnent avec AEM Guides.

- [Personnaliser l’éditeur web](conf-web-editor.md#) : cette rubrique explique les différentes personnalisations que vous pouvez effectuer dans l’éditeur web pour améliorer ses fonctionnalités.

- [Inclure l’attribut @navtitle par défaut](auto-add-navtitle.md#) : cette rubrique explique comment ajouter l’attribut `@navtitle` à un fichier de référence dans une carte par défaut.

- [Configurer des profils globaux ou au niveau du dossier](conf-folder-level.md#) : cette rubrique explique le processus de création de profils de dossier et de délivrance d’autorisations à des utilisateurs spécifiques.

- [Gestion de version](version-management.md#) : cette rubrique décrit comment configurer l’extraction automatique de fichiers pour les fichiers ouverts en vue de leur modification dans l’éditeur web.

- [Configurer les paramètres de génération de sortie](conf-output-generation.md#) : cette rubrique décrit les différentes configurations que vous pouvez effectuer pour personnaliser le processus de génération de sortie par défaut.

- [Configurer et personnaliser des workflows](customize-workflows.md#) : cette rubrique décrit diverses configurations pour personnaliser les workflows par défaut fournis dans AEM Guides.

- [Traduire le contenu](translation.md#) : cette rubrique fournit des liens vers les articles d’aide pertinents dans AEM documentation pour vous aider à comprendre et configurer la structure de traduction. Découvrez également comment activer le processus de traduction basé sur les composants.

- [Configurer la recherche pour l’interface utilisateur d’AEM Assets](conf-dita-search.md#) : cette rubrique décrit comment configurer la recherche de contenu DITA dans l’interface utilisateur d’Assets et ajouter vos attributs personnalisés dans la recherche.


## Présentation de Adobe Experience Manager \(AEM\)

[Adobe Experience Manager \(AEM\)](https://business.adobe.com/fr/products/experience-manager/adobe-experience-manager.html) est une solution de gestion de contenu complète permettant de créer des sites web, des applications mobiles et des formulaires. AEM vous aide à gérer le contenu et les ressources marketing. AEM est disponible en as a Cloud Service. AEM as a Cloud Service vous permet de proposer à vos clients des expériences personnalisées basées sur le contenu, en combinant la puissance du système de gestion de contenu AEM à la gestion des ressources numériques d’AEM. Voici quelques-unes des ressources clés pouvant vous aider à démarrer et à effectuer un déploiement sur AEM as a Cloud Service :

- [Aperçu as a Cloud Service Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=fr)
- [Prise en main du Parcours de migration vers AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/migration-journey/getting-started.html?lang=fr)
- [Commencer l’intégration à l’as a Cloud Service Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/onboarding/home.html?lang=frhttps://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/home.html?lang=en)
- [Implémentation d’applications pour AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/home.html?lang=fr)
- [Déploiement sur AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/deploying/overview.html?lang=fr)
- [Assets as a Cloud Service Guide](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/home.html?lang=fr)

## Ressources supplémentaires

Vous trouverez ci-dessous une liste d’autres ressources utiles d’AEM Guides, disponibles sur la page [Formation et assistance](https://helpx.adobe.com/fr/support/xml-documentation-for-experience-manager.html) :

- Guide de l’utilisateur
- Guide de référence d’API
