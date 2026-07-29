---
title: Mises à jour des API dans les versions de Experience Manager Guides
description: Découvrez les différentes mises à jour des API dans les versions de Experience Manager Guides
source-git-commit: 24637376024107ae575620e5491c0150da6cc956
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 7%

---


# Mises à jour des API dans les versions de Experience Manager Guides

Cet article fournit des détails sur les API nouvellement ajoutées dans la documentation Swagger pour les versions d’Adobe Experience Manager Guides. Vous pouvez accéder à la documentation Swagger via l’interface d’AEM en accédant à **Outils** > **Guides** > **API Swagger**.

<table style="border: 1; border-collapse: collapse; table-layout:fixed">
    <tr>
        <td colspan="5"><strong>Version 2026.08.0</strong></td>
    </tr>
    <tr>
        <td>Fonctionnalité</td>
        <td>Sous-fonctionnalité</td>
        <td>Méthode</td>
        <td>API</td>
        <td>Description</td>
    </tr>
    <tr>
        <td rowspan="7"><b>Ressources</b></td>
        <td rowspan="7"></td>
        <td>POST</td>
        <td>`/bin/guides/v1/asset/import`</td>
        <td>Importe une ou plusieurs ressources dans un dossier cible ; prend en charge le chargement multipartie et la résolution des conflits.</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/asset/list`</td>
        <td>Renvoie la liste paginée des ressources sous un chemin d’accès de dossier</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/asset/validatexml`</td>
        <td>Valide le code XML DITA pour assurer la qualité de formatage, la validité du schéma et l'intégrité de la consigne</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/asset/version/revert`</td>
        <td>Rétablit une version spécifiée d’une ressource</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/asset/currentversion/detail`</td>
        <td>Renvoie les détails de la version actuelle (nom de version, statut d’intégrité, libellés, etc.)</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/assets/status`</td>
        <td>Démarre une tâche asynchrone pour vérifier le statut des guides des ressources sous un ou plusieurs chemins d’accès donnés.</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/assets/status`</td>
        <td>Récupère le statut/les résultats d’une tâche de statut de ressource par ID de tâche</td>
    </tr>
    <tr>
        <td rowspan="3"><b>Publication</b></td>
        <td rowspan="3"></td>
        <td>POST</td>
        <td>`/bin/guides/v1/output/generate`</td>
        <td>Démarre l’exécution du paramètre prédéfini afin de générer la sortie d’une carte</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/output/status`</td>
        <td>Renvoie l’état d’une génération de sortie unique par chemin de mappage et ID de génération</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/output/status/list`</td>
        <td>Renvoie l’état de tous les paramètres prédéfinis générés pour un chemin de mappage</td>
    </tr>
    <tr>
        <td rowspan="18"><b>Traduction</b></td>
        <td rowspan="6">Langue</td>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/copies`</td>
        <td>Copies de langue d’une ressource par chemin d’accès ou UUID</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/groups`</td>
        <td>Groupes linguistiques pour un profil de dossier</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/list`</td>
        <td>Prend en charge les langues de traduction (filtrées)</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/root`</td>
        <td>Langues racine disponibles pour un chemin d’accès à la ressource</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/variable`</td>
        <td>Variables de langue par type et code de langue</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/language/variable`</td>
        <td>Crée, met à jour ou supprime des variables de langue</td>
    </tr>
    <tr>
        <td rowspan="7">Projet</td>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/project/create`</td>
        <td>Créer/mettre à jour un projet de traduction pour un plan DITA</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/project/sync`</td>
        <td>Crée/met à jour un projet de traduction (flux de synchronisation)</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/project/creationstatus`</td>
        <td>Statut de synchronisation de traduction pour un projet par chemin d’accès</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/project/existing`</td>
        <td>Projets de traduction existants pour l’utilisateur actuel</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/project/inprogress`</td>
        <td>Projets en cours pour une ressource donnée</td>
    </tr>
    <tr>
        <td>SUPPRIMER</td>
        <td>`/bin/guides/v1/translation/project/delete`</td>
        <td>Mise à jour avant suppression des statuts/propriétés de traduction des ressources</td>
    </tr>
    <tr>
        <td>SUPPRIMER</td>
        <td>`/bin/guides/v1/translation/project/job/delete`</td>
        <td>Mise à jour de la pré-suppression des statuts de ressource avant la suppression de la tâche</td>
    </tr>
    <tr>
        <td rowspan="5">Référence</td>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/accept`</td>
        <td>Accepter le contenu traduit des pages enfants de la tâche</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/deny`</td>
        <td>Rejeter le contenu traduit des pages enfants de la tâche</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/sync`</td>
        <td>Création de copies de langue dans des dossiers de destination</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/baseline/export`</td>
        <td>Exporter la ligne de base de traduction vers les langues de destination</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/status/forcesync`</td>
        <td>Forcer la mise à jour des ressources non synchronisées vers la synchronisation</td>
    </tr>
</table>
