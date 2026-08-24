---
title: Présentation du connecteur Git dans Experience Manager Guides
description: Découvrez la fonction du connecteur Git dans Experience Manager Guides, ses fonctionnalités essentielles et la manière dont le contenu passe d’un référentiel Git à votre workflow AEM Guides.
feature: Authoring, Features of Web Editor
role: User
TQID: https://experienceleague.adobe.com/DDAXW8cUFjvHUeJIbtL6FaHYSU7NW5fkzTai-7n90ms
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: f8123b54fae2aa209efda73abb333e63cf722708
workflow-type: tm+mt
source-wordcount: 1409
ht-degree: 0%

---

# Importer du contenu à l’aide du connecteur Git

>[!NOTE]
>
> Cette fonction est désactivée par défaut. Pour l’activer dans votre environnement, contactez votre équipe du succès client.

Le connecteur Git vous permet d’[importer du contenu des référentiels Git connectés dans Experience Manager Guides](#import-content-from-the-connected-git-repository). Une fois le contenu importé, vous pouvez utiliser les fonctions de création, de révision, de traduction et de publication de Experience Manager Guides pour développer et diffuser de la documentation.

Lorsque le contenu change dans le référentiel source, vous pouvez récupérer les mises à jour, examiner les conflits et synchroniser les dernières modifications avec Experience Manager Guides.

## Fonctionnalités clés

Le connecteur Git permet aux auteurs d’extraire directement du contenu d’un référentiel Git dans Experience Manager Guides, sans transfert manuel de fichiers. Une fois configurées, les créatrices ont accès aux fonctionnalités suivantes.

**Ingestion de contenu**

- Synchronise les fichiers de n’importe quel référentiel Git (public ou privé) dans Experience Manager Guides.
- Filtre par chemin d’accès au dossier source afin d’ingérer un seul sous-répertoire au lieu d’un référentiel entier.
- Utilise un moteur de règles `gitignore-aware` pour ignorer automatiquement les fichiers exclus par des modèles de `.gitignore` ou des règles personnalisées.
- Conserve les GUID lors de la resynchronisation pour conserver les références croisées DITA existantes intactes après une mise à jour.

**Synchronisation incrémentielle (delta)**

- Effectue le suivi de la dernière validation synchronisée et récupère uniquement les fichiers qui ont été ajoutés, modifiés ou supprimés lors des synchronisations suivantes, au lieu de réimporter l’intégralité du référentiel.
- Génère un rapport delta répertoriant chaque fichier modifié et son type de modification avant l’importation.
- Maintient des temps de récupération cohérents quelle que soit la taille du référentiel. Pour obtenir des données de référence, voir [Références de performance](#performance-benchmarks).

## Fonctionnement du connecteur Git

Le diagramme suivant montre comment le connecteur Git déplace le contenu d’un référentiel source vers Experience Manager Guides.

![](./images/git-connector-arch.png)

Le connecteur Git déplace le contenu d’un référentiel Git vers Experience Manager Guides en quatre étapes :

1. **Explorer et synchroniser** : un robot d&#39;exploration se connecte à votre référentiel Git et à votre profil configurés, et synchronise le contenu dans le connecteur à la demande.
1. **Ingérer et détecter les conflits** : les fichiers entrants sont analysés et hachés par rapport à ce qui se trouve déjà dans Experience Manager Guides. Les fichiers sans modifications en conflit sont transférés automatiquement ; les fichiers avec des modifications en conflit sont marqués pour une résolution manuelle.
1. **Persistance** : le contenu résolu est traité et enregistré dans AEM, avec vos autres contenus Experience Manager Guides.
1. **Workflow Experience Manager Guides** : une fois conservé, le contenu est disponible comme tout autre contenu Experience Manager Guides pour la création, la révision, la traduction et la publication.

## Références de performances

Les références suivantes affichent des temps de synchronisation complets (non incrémentiels) **Importateur en bloc** sur Experience Manager as a Cloud Service, à une échelle de référentiel croissante.

| Échelle | Heure de récupération | Heure d’import | Durée totale | Lots | Débit |
|---|---|---|---|---|---|
| 1 000 fichiers | 1m 53s | 3m 30s | 5m 29s | 10 × 100 | ~286 fichiers/min |
| 5 000 fichiers | 1m 55s | 18m 21s | 20m 27s | 20 × 250 | ~273 fichiers/min |
| 10 000 fichiers | 1m 39s | 36 m 22 s | 37 m 24 s | 40 × 250 | ~267 fichiers/min |
| 50 000 fichiers | 1m 25s | 2h 43m | 2h 58m | 200 × 250 | ~270 fichiers/min |

## Importer du contenu à l’aide du connecteur Git

Une fois que votre administrateur a configuré le connecteur Git dans Experience Manager Guides, vous pouvez l’utiliser à partir de l’éditeur pour importer du contenu d’un référentiel Git.

## Prérequis

Avant de commencer à utiliser cette fonctionnalité, assurez-vous des points suivants :

- La fonctionnalité Connecteur Git doit être activée pour votre environnement.
- (*Si activé*) Votre administrateur a configuré le connecteur Git dans votre environnement. Pour plus d’informations, consultez la section [Créer et configurer un connecteur Git à partir de l’interface utilisateur](../install-conf-guide/conf-git-connector.md).
- Vous disposez d’un accès *lecture* au référentiel Git qui contient le contenu que vous souhaitez importer.
- Vous savez quelle branche de référentiel et quel dossier source vous souhaitez importer.
- Vous connaissez le dossier cible dans Experience Manager Guides où sera stocké le contenu importé.

## Importer du contenu à partir du référentiel Git connecté

Pour importer du contenu à partir d’un référentiel Git, procédez comme suit :

1. Dans l’éditeur, ouvrez le panneau de gauche.
1. Sélectionnez **Sources de données**.

   Les sources de données connectées s’affichent.

1. Sélectionnez la mosaïque **Connecteur Git**.

1. Sélectionnez l’icône + , puis sélectionnez **Importateur en bloc**.

   La boîte de dialogue **Importateur en bloc** s’affiche.

   ![](images/git-bulk-importer-dialog.png)

1. Dans la boîte de dialogue **Importateur en bloc**, attribuez un nom à l’importation, sélectionnez un sous-dossier dans le référentiel Git que vous avez configuré, puis sélectionnez **Enregistrer et récupérer**.  La liste des fichiers disponibles à l’importation s’affiche dans la boîte de dialogue. Passez en revue la liste et validez le contenu avant de continuer.

   ![](images/git-bulk-importer-import-all.png)

1. Après avoir examiné les fichiers, sélectionnez **Importer tout** pour importer le contenu dans Experience Manager Guides.

   >[!NOTE]
   >
   > Si vous utilisez une version de Git Connector antérieure à la version 1.0.1, l’importation d’un référentiel contenant des sous-modules Git peut échouer lors de l’opération de récupération. Effectuez la mise à niveau vers la version 1.0.1 ou une version ultérieure du connecteur Git pour éviter ce problème. À compter de la version 1.0.1, les sous-modules Git sont ignorés lors du clonage et de l’importation, et seul le contenu du référentiel principal est importé.

1. *(Facultatif)* Vous pouvez activer la fonction **Synchronisation automatique** pour synchroniser et importer automatiquement du contenu de votre référentiel Git dans Experience Manager Guides. Si des erreurs sont détectées, la synchronisation automatique n’est pas déclenchée et l’auteur doit importer manuellement le contenu en sélectionnant **Tout importer**. Une fois activée, la synchronisation automatique ne peut pas être désactivée pour l’importateur.

Une fois le contenu importé, il est stocké sous le **chemin d’accès racine Target AEM** configuré lors de la configuration du connecteur Git.

## Gérer le contenu importé par Git

Une fois le contenu importé dans Experience Manager Guides, vous pouvez utiliser les actions disponibles pour gérer le contenu et le maintenir synchronisé avec les modifications du référentiel source.

![](images/git-connector-imported-content-options.png){width="600"}

- **Aperçu** : aperçu du contenu importé. Si le référentiel source contient des mises à jour, passez en revue les différences et utilisez l’option **Récupérer à nouveau** pour importer les dernières modifications. Si les différences nécessitent une fusion, consultez la section [Résoudre les conflits du connecteur Git](#review-and-resolve-content-conflicts).
- **Supprimer** : supprimez l’importateur qui n’est plus nécessaire.
- **Renommer** : renommez l’importateur pour une identification plus facile.
- **Afficher le journal** : affichez le journal d’importation pour consulter les détails de l’opération d’importation.
- **Afficher le rapport** : affichez et téléchargez le **rapport d’importation en bloc** qui comprend des détails tels que :

  - nombre total de fichiers importés
  - nombre d’imports réussis
  - nombre d’imports ayant échoué

  ![](images/git-connector-view-report.png){width="600"}

  Vous pouvez également télécharger le rapport détaillé. Si l’importation de certains fichiers échoue, utilisez **Réessayer les importations ayant échoué** pour réessayer de les importer.

## Vérifier et résoudre les conflits de contenu

Lorsque vous récupérez à nouveau du contenu à partir d’un référentiel Git, les différences de contenu entre la version du référentiel et le contenu correspondant disponible dans Experience Manager Guides s’affichent sous la forme de conflits. Vous devez résoudre et fusionner ces conflits avant d’importer les données dans Experience Manager Guides.

Procédez comme suit pour résoudre les conflits de fusion et :

1. Ouvrez la boîte de dialogue d’importation en bloc et sélectionnez **Récupérer à nouveau**.
1. Si des conflits sont détectés, l’onglet **Fusion requise** s’affiche et répertorie les fichiers contenant des conflits. Sélectionnez l’onglet **Fusion requise**, puis sélectionnez un fichier dans la liste pour examiner et résoudre les conflits.
1. Pour les fichiers présentant des conflits, une vue de fusion à trois voies s’affiche.

   ![](images/git-connector-resolve-conflicts.png)

   Le volet de gauche (**&#x200B;**) affiche le contenu actuel du référentiel AEM, tandis que le volet de droite (**GIT**) affiche le contenu entrant en provenance du référentiel Git distant. Le volet central (**Result**) est initialement renseigné avec le contenu du référentiel AEM et sert d’éditeur de fusion, où les conflits sont résolus. Le résultat final fusionné est généré et affiché dans ce volet central.

1. Examinez les différences mises en surbrillance dans l’éditeur et résolvez les conflits à l’aide des commandes de fusion :

   - Si vous souhaitez utiliser les dernières modifications du référentiel Git, assurez-vous que la case correspondant au conflit dans la section **GIT** est cochée, puis sélectionnez le contrôle de `<<<` correspondant. Le contenu Git sélectionné remplace le contenu en conflit dans la section **Résultat**.

     ![](images/git-connector-replace-with-git.png)

   - Si vous souhaitez conserver le contenu des deux versions, décochez la case correspondant au conflit, puis utilisez le contrôle `<<<` pour ajouter le contenu requis à la section **Result** sans remplacer le contenu existant.

     ![](images/git-connector-keep-both-versions.png)

   - De même, vous pouvez utiliser la commande `>>>` dans la section AEM pour conserver la version actuellement disponible dans Experience Manager Guides.


1. Après avoir examiné le contenu fusionné, effectuez l’une des actions suivantes :

   - Utilisez **Accepter AEM** pour remplacer entièrement le contenu de la section **Résultat** par la version de la section **AEM**, en conservant vos modifications locales.
   - Utilisez **Accepter GIT** pour remplacer entièrement le contenu de la section **Résultat** par la version de la section **GIT**, en conservant les modifications du référentiel.

La **fusion complète** est requise, quelle que soit l’option utilisée ci-dessus. Sa sélection verrouille le contenu actuel de **Result** en tant que version résolue de ce fichier et marque le fichier comme fusionné.

Une fois que tous les fichiers contenant les conflits sont marqués comme fusionnés, le bouton **Tout importer** est activé. Sélectionnez **Importer tout** pour terminer le processus de résolution des conflits.

Si un fichier a été modifié dans le référentiel Git mais n’a pas été modifié dans Experience Manager Guides, aucune fusion n’est requise. Ces fichiers sont automatiquement inclus sous **Mises à jour propres** et peuvent être importés directement.

![](images/git-connector-clean-updates.png){width="600"}