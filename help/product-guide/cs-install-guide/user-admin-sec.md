---
title: Administration et sécurité des utilisateurs
description: Découvrez comment fonctionne l’administration et la sécurité des utilisateurs
exl-id: 10ab0f3c-97dc-4293-ab73-75b438c03d99
feature: User Management
role: Admin
level: Experienced
source-git-commit: 462647f953895f1976af5383124129c3ee869fe9
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 10%

---

# Administration et sécurité des utilisateurs {#id181AED00G5Z}

Pour accéder aux fonctionnalités et les configurer dans AEM Guides, vous devez créer des utilisateurs. Ces utilisateurs peuvent alors se voir attribuer des autorisations d’accès à l’ensemble des fonctionnalités ou à certaines fonctionnalités d’AEM Guides. Découvrez comment configurer et gérer l’autorisation utilisateur et comprendre également la théorie sous-jacente au fonctionnement de l’authentification et de l’autorisation dans AEM.

Les rubriques suivantes de la documentation d’AEM vous aideront à comprendre les concepts et fonctionnalités relatifs à l’administration des utilisateurs et à la sécurité :

- [AEM utilisateurs, groupes et autorisations](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/accessing/aem-users-groups-and-permissions.html)

- [Administration et sécurité des utilisateurs](https://experienceleague.adobe.com/docs/experience-manager-65/administering/security/security.html?lang=fr)


## Groupes d’utilisateurs créés par AEM Guides {#id181TF0K0MHT}

AEM Guides fournit trois groupes prêts à l’emploi pour gérer différentes tâches dans un projet DITA. Ces groupes sont les suivants : *Auteurs*, *Réviseurs* et *Éditeurs*. Selon le groupe auquel un utilisateur est associé, il est autorisé à effectuer des tâches spécifiques. Par exemple, la tâche de publication peut être effectuée uniquement par un éditeur, mais pas par un auteur ou un réviseur. De même, un auteur peut créer une rubrique et un réviseur ne peut consulter qu’une rubrique.

>[!TIP]
>
> Consultez la section *Autorisations* du guide Bonnes pratiques pour connaître les bonnes pratiques relatives à la définition des autorisations d’utilisateur.

Le tableau suivant répertorie les différentes tâches et les groupes pouvant effectuer ces tâches :

| Tâche | Auteurs | Réviseurs | Éditeurs |
|----|-------|---------|----------|
| Création d’une rubrique DITA | Oui |   | Oui |
| Création d’une carte DITA | Oui |   | Oui |
| Mappage de collections | Oui |   | Oui |
| Créer une tâche de révision | Oui |   | Oui |
| Rubrique de révision[1](#fntarg_1) | Oui | Oui | Oui |
| Résolution des clés | Oui |   | Oui |
| Extraction/archivage | Oui |   | Oui |
| Modifier le sujet | Oui |   | Oui |
| Déplacer la rubrique | Oui |   | Oui |
| Modification des propriétés de rubrique | Oui |   | Oui |
| Copier | Oui |   | Oui |
| Supprimer | Oui |   | Oui |
| Partager | Oui |   | Oui |
| **État du document** |
| Création/modification d’un profil d’état de document |   |   | Oui |
| Modifier l’état du document[2](#fntarg_2) | Oui | Oui | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(onglet Paramètres prédéfinis de sortie\)** |
| Générer |   |   | Oui |
| Modifier |   |   | Oui |
| Dupliquer |   |   | Oui |
| Créer |   |   | Oui |
| Supprimer le paramètre prédéfini |   |   | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(onglet Sorties\){1** |
| Afficher la sortie générée | Oui |   | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(onglet Rubriques\){1** |
| Créer une tâche de révision | Oui |   | Oui |
| Modifier | Oui |   | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(onglet Lignes de base\){1** |
| Créer |   |   | Oui |
| Modifier |   |   | Oui |
| Dupliquer |   |   | Oui |
| Supprimez |   |   | Oui |
| Console de mappage DITA \(onglet Rapports\) | Oui |   | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(Paramètres prédéfinis de condition\)** |
| Créer/modifier un paramètre prédéfini de condition |   |   | Oui |

## Remarques supplémentaires sur les groupes d’utilisateurs

La liste suivante contient des recommandations et des points relatifs aux groupes d’utilisateurs et aux autorisations correspondantes :

- Si vous souhaitez qu’un utilisateur démarre le processus de traduction ou de révision, assurez-vous qu’il est membre du *groupe d’éditeurs* et du *groupe projects-administrateurs*.

- Les utilisateurs doivent disposer des autorisations de lecture, de création, de suppression et de modification disponibles dans les dossiers de langue source et cible sur lesquels ils doivent travailler.

- Si vous créez un projet, vous êtes le propriétaire du projet avec les autorisations *Publishers*. Pour que les autres utilisateurs d’un projet puissent voir les membres de leur équipe, créer des tâches ou créer des workflows, ils doivent disposer d’un accès en lecture aux noeuds `/home/users` et `/home/groups`. Une façon de donner un accès en lecture aux noeuds `/home/users` et `/home/groups` est de donner un accès en lecture au groupe `projects-users`.

- *Les réviseurs* peuvent accéder et ajouter des commentaires de révision sur une rubrique en cours de révision à partir de la console Projet ou à partir du lien de notification de boîte de réception. En outre, cet accès n’est disponible que jusqu’à l’ouverture de la tâche de révision.

- Par défaut, les *éditeurs* se voient accorder l’accès et les autorisations sur les dossiers suivants dans la gestion des ressources numériques :

   - `/content/fmdita` -\> Lecture et écriture

   - `/content/dam/fmdita-outputs` -\> Lecture et écriture

   - `/content/output/sites` -\> Lecture et écriture

  Vous devez accorder des autorisations de lecture et d’écriture explicites à votre éditeur si vous utilisez un autre emplacement que les emplacements de publication par défaut mentionnés ci-dessus.

- Tous les utilisateurs des groupes *Auteurs*, *Réviseurs* et *Éditeurs* ont un accès en lecture à tout le contenu dans la gestion des ressources numériques.

- Les autorisations au niveau du dossier doivent être attribuées aux utilisateurs via la page d’administration des utilisateurs.

- Si vous souhaitez que vos utilisateurs puissent effectuer des opérations de recherche sur DAM, faites de vos utilisateurs un membre du groupe *dam-users*.

- Si vous souhaitez accorder des droits d’administrateur à n’importe quel utilisateur, vous pouvez le faire en lui donnant accès par le biais AEM groupes standard tels que *administrateurs*, *projects-administrateurs* ou la configuration OSGI \(console Felix\).

- Pour accorder à un utilisateur les droits de modifier l’état d’un document, veillez à ajouter l’utilisateur dans la section de transition d’état du profil d’état du document.

[1](#fnsrc_1) Si *Auteurs* et *Éditeurs* sont invités pour une révision.[2](#fnsrc_2) Selon les droits accordés à l’utilisateur dans le profil d’état du document.
