---
title: Questions fréquentes sur la nouvelle migration de base dans Adobe Experience Manager Guides
description: Découvrez les questions fréquentes sur la nouvelle migration de base dans Adobe Experience Manager Guides.
TQID: https://experienceleague.adobe.com/hsiglBlwA8KOqUkkDck1RZb307TBuHfoVFb64DKTcXk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: c38bc65b-dea9-4a6e-9de3-3daf1d2b388b
  - id: f6b497f1-f8e0-42ce-8e95-56c28d94026e
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: f3f30400f776f746427e257e2c937ff3413aa9ac
workflow-type: tm+mt
source-wordcount: 919
ht-degree: 0%

---

# FAQ sur la migration de nouvelle ligne de base

Cette FAQ aborde les questions courantes relatives à la migration vers la nouvelle ligne de base, aux changements de comportement, aux considérations relatives à la migration et aux résultats attendus lors de la mise à niveau vers le nouveau modèle de ligne de base.

## Quels sont les principaux avantages de la migration vers la nouvelle ligne de base ?

Le nouveau modèle de ligne de base offre plusieurs améliorations, notamment :

- Amélioration des performances et de l’évolutivité
- Amélioration de la cohérence de l’interface utilisateur et du serveur principal
- Modification déterministe et comportement d&#39;enregistrement
- Amélioration des fonctionnalités de filtrage et de navigation
- Aperçu de l’impact des dépendances
- Amélioration de la fiabilité lors de la création et des mises à jour de la ligne de base
- Amélioration de la prise en charge des API et de l’automatisation

## La migration des lignes de base crée-t-elle de nouvelles lignes de base pour toutes les versions d’une carte ?

Non, le processus de migration crée des lignes de base uniquement pour la **copie de travail actuelle** de la carte. Les références associées à d&#39;autres copies de travail ne sont pas incluses dans la migration.

## Que se passe-t-il lorsqu’un utilisateur revient à une version précédente d’une carte ?

Lorsqu’une version précédente d’un mappage est restaurée ou accessible, les lignes de base associées à cette version sont automatiquement migrées vers le nouveau modèle de ligne de base par un processus de migration asynchrone.

## Les références non valides sont-elles migrées vers la nouvelle ligne de base ?

Non, les références non valides sont ignorées pendant la migration pour maintenir la cohérence de la ligne de base et assurer la fiabilité de la ligne de base migrée.

## La migration de référence modifie-t-elle la référence ?

La migration de la ligne de base conserve tout le contenu et les références de la ligne de base valides tels quels. Toutefois, les références non valides ne sont pas incluses dans la ligne de base migrée. Outre la suppression des références non valides, la migration n’introduit aucun changement dans les références ou le comportement de résolution de dépendance.

Toute autre modification des références ou de la résolution de dépendance ne peut avoir lieu qu&#39;une fois la ligne de base migrée modifiée, reconstruite ou nouvellement créée à l&#39;aide du nouveau modèle de ligne de base.

Tant que l&#39;une de ces actions n&#39;est pas effectuée, la ligne de base migrée continue de refléter la définition de ligne de base d&#39;origine.

## Les références `reltable` sont-elles incluses dans le nouveau modèle de référence ?

Non, les références provenant d&#39;éléments `reltable` sont exclues de la résolution de la ligne de base, conformément au comportement du modèle de ligne de base hérité.

## Comment les références DIRECT sont-elles gérées dans la nouvelle ligne de base ?

Dans le modèle Nouvelle ligne de base, les références de mappage direct sont explicitement classées comme références **DIRECT**. Lors de la migration et de la résolution de la ligne de base, ces références ont la priorité la plus élevée et sont résolues avant tous les autres types de référence.

## Les références `scope="peer"` sont-elles incluses dans la ligne de base ?

Non, les références avec `scope="peer"` ne sont pas incluses dans le modèle de référence. L’exclusion de ces références améliore les performances de publication et évite une résolution inutile des dépendances.

## Les lignes de base peuvent-elles toujours être gérées à partir du tableau de bord des cartes ?

Non, la gestion des lignes de base n&#39;est prise en charge qu&#39;à partir de la **console Map** dans Nouvelle ligne de base. La création et la gestion de lignes de base à partir du **tableau de bord Map** ne sont pas prises en charge.

## Des précautions sont-elles nécessaires lors de la migration ?

Oui, les modifications de ligne de base doivent être évitées pendant une migration, en particulier dans les copies de travail. Apporter des modifications aux lignes de base pendant la migration peut entraîner des échecs de migration et peut laisser les lignes de base dans un état incohérent.

## Que se passe-t-il si des versions sont manquantes après la migration ?

Certaines lignes de base peuvent devoir être reconstruites après la migration si les versions référencées par ces lignes de base ne sont plus disponibles ou accessibles.


## Quel est le temps approximatif nécessaire à la migration des lignes de base pour une configuration On-Premise ?

Le temps de migration dépend de plusieurs facteurs, notamment :

- Nombre de lignes de base migrées
- Nombre total de références dans ces lignes de base
- Taille et complexité du référentiel
- Configuration matérielle
- Ressources système disponibles

D’après les tests internes et les observations des référentiels contenant environ 18 000 références, la durée de migration peut varier considérablement en fonction de la structure du référentiel et de l’environnement d’exploitation.

| Portée de la migration | Durée standard |
|-----------------|------------------|
| Ligne de base unique | Quelques secondes |
| 10-15 niveaux de référence | Quelques dizaines de secondes |
| 25-50 niveaux de référence | Environ 1-2 minutes |

>[!NOTE]
>
> Ces chiffres sont fournis à titre de référence uniquement et sont basés sur un environnement On-Premise. Les valeurs réelles peuvent varier en fonction de la complexité du référentiel, de la capacité de l’infrastructure, de la configuration matérielle et des conditions de fonctionnement globales.

## Pouvons-nous revenir aux anciennes lignes de base ?

Oui. Cependant, lorsqu’une restauration est effectuée, les anciennes lignes de base sont restaurées à l’état dans lequel elles se trouvaient au moment de la migration. Les modifications apportées alors que l&#39;ancienne configuration de ligne de base est désactivée et que la nouvelle est active ne sont pas répercutées dans les lignes de base restaurées.

Les anciens objets de référence d&#39;origine restent disponibles à leur emplacement d&#39;origine. Lorsque la nouvelle configuration de ligne de base est désactivée, le système revient automatiquement à l&#39;utilisation de ces objets d&#39;origine.

## Comment migrer vers de nouvelles lignes de base ?

Pour migrer vers une nouvelle ligne de base, suivez les étapes décrites dans [Migrer vers une nouvelle ligne de base](./web-editor-baseline-v2.md#migrate-to-new-baseline).

## Pouvons-nous migrer vers la nouvelle ligne de base à tout moment ? Y a-t-il des conditions préalables ?

Oui. Vous pouvez activer la nouvelle ligne de base à tout moment, à condition que votre environnement réponde aux exigences de version minimales.

**Conditions préalables :**

- AEM Guides (On-Premise) : version 5.2 ou ultérieure
- AEM Guides (Cloud Service) : version 2026.05.0 ou ultérieure

Une fois ces exigences remplies, vous pouvez migrer vos anciennes lignes de base existantes vers le nouveau modèle de ligne de base et commencer à utiliser ses fonctionnalités.

## Est-il nécessaire de sauvegarder l’état actuel du serveur avant de migrer vers la nouvelle ligne de base ?

Aucune sauvegarde supplémentaire n&#39;est requise spécifiquement pour la migration vers la nouvelle ligne de base.

Toutefois, les lignes de base associées à la copie de travail peuvent être perdues si un utilisateur effectue ultérieurement une opération de rétablissement de version. Ce comportement n’est pas propre au nouveau modèle de ligne de base ; le retour à une version antérieure peut également supprimer les anciens nœuds de copie de travail de ligne de base correspondants.

Si la conservation des lignes de base de la copie de travail est importante, il est recommandé de les sauvegarder avant la migration. Après la migration, les utilisateurs travaillent principalement avec de nouvelles lignes de base, mais un retour ultérieur à la version précédente peut toujours entraîner la perte des lignes de base de la copie de travail.


