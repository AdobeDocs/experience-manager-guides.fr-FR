---
title: Manage content
description: Manage content and identify your roles and permissions in AEM Guides. Learn the key concepts of content management and working with the global or folder-level profiles.
feature: Content Management
role: User
hide: true
exl-id: 54b960cf-fb00-4d4a-a836-9de4738c49a8
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 12%

---

# Manage content {#id164JBG0M0T1}

Before you start with the actual content creation, you must familiarize yourself with some basic concepts of content management in AEM Guides. Then, start with creating different user groups and organizing your assets.

## Concepts clés

Some key concepts of content management in AEM are as follows:

**Asset management**

AEM Guides uses AEM&#39;s digital asset management \(DAM\) to manage your DITA files. The files that you upload or check into the DAM are stored as digital assets. You can manage and edit your assets in AEM Assets. For more information about asset management, see [Manage assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=fr).

**Link management**

Move or rename files or change folder structure in the content repository, without worrying about broken references. All references to and from the impacted content are automatically updated. Get warnings when deleting content which is referenced from elsewhere, to prevent unintentional breakages.

**Managing versions**

AEM Guides provides version management for your digital assets. You can easily enable this functionality from a DITA authoring application of choice. Allowing your writers to perform the standard version control functions such as check-in and check-out.

For more information about creating versions or reverting to a specific version, see [Branch, revert, and subsequent versioning](web-editor-preview-topics.md#id193PG0Y051X).

**Native DITA handling**

While AEM Guides maintains the structure of your DITA files, it also enables AEM to natively handle DITA using element mapping to map the DITA elements to AEM components. The native DITA handling is used in features such as topic preview, AEM Sites publishing, and the review workflows.

## Identify your role and permissions {#id181TF0K0MHT}

AEM Guides fournit trois groupes prêts à l’emploi. Ces groupes sont les suivants : *Auteurs*, *Réviseurs* et *Éditeurs*. Selon le groupe auquel vous êtes associé, vous disposez des autorisations nécessaires pour effectuer des tâches spécifiques, comme indiqué dans le tableau ci-dessous. Par exemple, une tâche de publication ne peut être effectuée que par un éditeur, mais pas par un auteur ou un réviseur. De même, un auteur peut créer une rubrique et un réviseur peut uniquement réviser une rubrique.

>[!TIP]
>
> Voir la section *Autorisations* dans le guide des bonnes pratiques pour connaître les bonnes pratiques relatives à la définition des autorisations utilisateur.

Le tableau suivant répertorie les différentes tâches et les groupes qui peuvent les effectuer :

| Tâche | Auteurs | Réviseurs | Editeurs |
|----|-------|---------|----------|
| Créer une rubrique DITA | Oui |   | Oui |
| Créer un plan DITA | Oui |   | Oui |
| Mapper les collections | Oui |   | Oui |
| Créer une tâche de révision | Oui |   | Oui |
| Rubrique [ révision 1](#fntarg_1) | Oui | Oui | Oui |
| Résolution de la clé | Oui |   | Oui |
| Extraction/enregistrement | Oui |   | Oui |
| Modifier le sujet | Oui |   | Oui |
| Déplacer rubrique | Oui |   | Oui |
| Modifier les propriétés de rubrique | Oui |   | Oui |
| Copier | Oui |   | Oui |
| Supprimer | Oui |   | Oui |
| Partager | Oui |   | Oui |
| **État du document** |  |  |  |
| Créer/modifier un profil d’état de document |   |   | Oui |
| Modifier l’état du document [2](#fntarg_2) | Oui | Oui | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(onglet Paramètres prédéfinis de sortie\)** |  |  |  |
| Générer |   |   | Oui |
| Modifier |   |   | Oui |
| Doublon |   |   | Oui |
| Créer |   |   | Oui |
| Supprimer le paramètre prédéfini |   |   | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(onglet Sorties\)** |  |  |  |
| Afficher la sortie générée | Oui |   | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(Onglet Rubriques\)** |  |  |  |
| Créer une tâche de révision | Oui |   | Oui |
| Modifier | Oui |   | Oui |
| **Fonctionnalités disponibles dans la console de plan DITA \(onglet Lignes de base\)** |  |  |  |
| Créer |   |   | Oui |
| Modifier |   |   | Oui |
| Doublon |   |   | Oui |
| Supprimer |   |   | Oui |
| Console de mappage DITA \(onglet Rapports\) | Oui |   | Oui |
| **Features available in DITA map console \(Condition Presets\)** |  |  |  |
| Create/edit condition preset |   |   | Oui |

[1](#fnsrc_1) If *Authors* and *Publishers* are invited for a review.

[2](#fnsrc_2) Depending on the rights given to the user in the document state profile.

## Pre-requisites to content authoring

**Work with global or folder-level profiles**

In an enterprise, different groups or products may use different authoring templates, output templates, conditional attribute profiles \(or subject schemes\), and Web Editor configurations. Configuring these only at an enterprise \(or global\) level can make authors experience difficult, as they will see templates or profiles that are not relevant to them.

AEM Guides allows you to configure authoring \(topic or map\) templates, output templates, conditional attribute, and Web Editor configurations at an enterprise \(global\) level as well as at a folder level. This way, you can segregate the configurations for different departments or products in your enterprise.

Also, you can delegate the folder-specific configurations to a department or product administrators to decentralize the administration.

For details on setting up global and folder-level profiles, see *Configure global or folder-level profiles* in Install and configure Adobe Experience Manager Guides as a Cloud Service.
