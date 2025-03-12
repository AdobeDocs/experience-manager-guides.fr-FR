---
title: Administration et sécurité des utilisateurs
description: Découvrez comment fonctionnent l’administration et la sécurité des utilisateurs et utilisatrices
exl-id: 10ab0f3c-97dc-4293-ab73-75b438c03d99
feature: User Management
role: Admin
level: Experienced
source-git-commit: 6aaa5c1eeb9b74ababc7ebf427babfff101acc70
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 10%

---

# Administration et sécurité des utilisateurs {#id181AED00G5Z}

Pour accéder aux fonctionnalités d’AEM Guides et les configurer, vous devez créer des utilisateurs. Ces utilisateurs peuvent ensuite se voir attribuer des autorisations pour accéder à toutes les fonctionnalités d’AEM Guides ou à certaines d’entre elles. Découvrez comment configurer et gérer l’autorisation utilisateur, mais aussi la théorie du fonctionnement de l’authentification et de l’autorisation dans AEM.

Les rubriques suivantes de la documentation d’AEM vous aideront à mieux comprendre les concepts et fonctionnalités liés à l’administration des utilisateurs et à la sécurité :

- [utilisateurs, groupes et autorisations AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/accessing/aem-users-groups-and-permissions.html)

- [ Administration et sécurité des utilisateurs ](https://experienceleague.adobe.com/docs/experience-manager-65/administering/security/security.html?lang=fr)


## Groupes d’utilisateurs créés par AEM Guides {#id181TF0K0MHT}

AEM Guides fournit trois groupes prêts à l’emploi. Ces groupes sont les suivants : *Auteurs*, *Réviseurs* et *Éditeurs*. Selon le groupe auquel un utilisateur est associé, il est autorisé à effectuer des tâches spécifiques. Par exemple, une tâche de publication ne peut être effectuée que par un éditeur, mais pas par un auteur ou un réviseur. De même, un auteur peut créer une rubrique et un réviseur peut uniquement réviser une rubrique.

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
| **État du document** |
| Créer/modifier un profil d’état de document |   |   | Oui |
| Modifier l’état du document [2](#fntarg_2) | Oui | Oui | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(onglet Paramètres prédéfinis de sortie\)** |
| Générer |   |   | Oui |
| Modifier |   |   | Oui |
| Doublon |   |   | Oui |
| Créer |   |   | Oui |
| Supprimer le paramètre prédéfini |   |   | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(onglet Sorties\)** |
| Afficher la sortie générée | Oui |   | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(Onglet Rubriques\)** |
| Créer une tâche de révision | Oui |   | Oui |
| Modifier | Oui |   | Oui |
| **Fonctionnalités disponibles dans la console de plan DITA \(onglet Lignes de base\)** |
| Créer |   |   | Oui |
| Modifier |   |   | Oui |
| Doublon |   |   | Oui |
| Supprimez |   |   | Oui |
| Console de mappage DITA \(onglet Rapports\) | Oui |   | Oui |
| **Fonctionnalités disponibles dans la console de mappage DITA \(Paramètres prédéfinis de condition\)** |
| Créer/modifier un paramètre prédéfini de condition |   |   | Oui |

## Remarques supplémentaires sur les groupes d’utilisateurs

La liste suivante contient des recommandations et des points liés aux groupes d’utilisateurs et aux autorisations correspondantes :

- Si vous souhaitez qu’un utilisateur lance le workflow de traduction ou de révision, assurez-vous qu’il est membre du groupe *Éditeurs* et *projets-administrateurs*.

- Les utilisateurs doivent disposer des autorisations de lecture, de création, de suppression et de modification disponibles sur les dossiers de langue source et cible sur lesquels ils doivent travailler.

- Si vous créez un projet, vous en êtes le propriétaire disposant des autorisations *Éditeurs*. Pour que d’autres utilisateurs d’un projet puissent voir les membres de leur équipe, créer des tâches ou créer des workflows, ils doivent disposer d’un accès en lecture sur les nœuds `/home/users` et `/home/groups`. Une façon de donner un accès en lecture sur des nœuds `/home/users` et `/home/groups` consiste à donner un accès en lecture au groupe `projects-users` .

- *Les réviseurs* peuvent accéder à un sujet en cours de révision et y ajouter des commentaires à partir de la console Projet ou à partir du lien de notification de la boîte de réception. En outre, cet accès n’est disponible que lorsque la tâche de révision est ouverte.

- Par défaut, les *éditeurs* se voient accorder l’accès et les autorisations sur les dossiers suivants dans la gestion des ressources numériques :

   - `/content/fmdita` -\> Lecture et écriture

   - `/content/dam/fmdita-outputs` -\> Lecture et écriture

   - `/content/output/sites` -\> Lecture et écriture

  Vous devez accorder des autorisations explicites en lecture et écriture à votre éditeur si vous utilisez un autre emplacement que les emplacements de publication par défaut mentionnés ci-dessus.

- Tous les utilisateurs appartenant aux groupes *Auteurs*, *Réviseurs* et *Éditeurs* ont un accès en lecture à tout le contenu de la gestion des ressources numériques.

- Les autorisations au niveau des dossiers doivent être attribuées aux utilisateurs via la page d’administration des utilisateurs.

- Si vous souhaitez que vos utilisateurs puissent effectuer des opérations de recherche sur la gestion des ressources numériques, faites de vos utilisateurs des membres du groupe *dam-users*.

- Si vous souhaitez accorder des droits d’administrateur à n’importe quel utilisateur, vous pouvez le faire en lui donnant accès par le biais de groupes standard d’AEM tels que *administrateurs*, *projets-administrateurs* ou configuration OSGI \(console Felix\).

- Pour donner à un utilisateur les droits de modifier l’état d’un document, veillez à l’ajouter dans la section Transition d’état du profil d’état du document.

[1](#fnsrc_1) Si *Auteurs* et *Éditeurs* sont invités pour une révision.[2](#fnsrc_2) selon les droits accordés à l’utilisateur dans le profil d’état du document.
