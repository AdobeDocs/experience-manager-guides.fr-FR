---
title: Mesures clés SCORM pour la progression de l’élève et l’achèvement du cours
description: En savoir plus sur les mesures clés SCORM pour la progression des élèves et l’achèvement du cours
feature: Authoring
role: Admin
level: Experienced
source-git-commit: 0dff380131dadc971f257eb464700392328164e5
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 1%

---

# Mesures clés SCORM pour la progression de l’élève et l’achèvement du cours

Cet article répertorie les paramètres clés capturés dans un package SCORM, ainsi que les champs correspondants et des exemples. Ces paramètres fournissent des informations essentielles sur la progression de l’élève, la fin du cours, les détails de l’interaction et les performances du quiz. Les administrateurs peuvent utiliser ces informations pour valider le suivi, configurer les rapports et garantir des analyses précises dans l’environnement LMS. Voici des exemples de valeurs fournies pour chaque paramètre tel qu’il apparaît dans le package SCORM.

| **Nom du paramètre** | **Description** | **Champs** | **Exemple** |
|---|---|---|---|
| **Statut d’achèvement du cours** | Indique si le cours est terminé ou non | cmi.completion_status | incomplet |
| **Nombre de tentatives** | Nombre de tentatives effectuées par l’élève | Compteur/contenu de tentative côté LMS | Tentatives : 1 |
| **Emplacement du package SCORM** | Signet ou emplacement actuel dans le cours | cmi.location | - |
| **Progression terminée** | Learner&#39;s progress | cmi.progress_measure | 0,87 |
| **Durée totale (tentative)** | Temps total passé dans la tentative actuelle | cmi.total_time | 0000:01:09,87 |
| **Visibilité de la table des matières et nombre de rubriques** | Affiche la visibilité de la table des matières et les détails d&#39;achèvement de la rubrique | Project.HideTOC, Project.TotalTopics, Project.TopicsCompleted | - |
| **Par statut de topic** | Statut d’achèvement et de réussite pour chaque rubrique | État personnalisé par leçon | - |
| **Par état de choix de question** | Effectue le suivi des choix sélectionnés de l’élève par question | value, generate_id, vérifié. | - |
| **Score global des questions** | Score obtenu au niveau des questions et agrégat | {« score »:0,« maxScore »:1} et % | « score »:33.33,« maxScore »:100,« minScore »:0 |
| **Interactions à chaque niveau de question** | Détails de l’interaction de l’élève par question | id/type/timestamp/correct_response/learner_response/result/latency | - |
| **Etat général du cours** | Indique les réussites/échecs et la progression globale. | success_status, completion_status, score, progress_measurement | Réussite ou échec |
| **Learner details** | Identifie l’élève par ID et nom | cmi.learner_id, cmi.learner_name | Albert |
| **Paramètres du quiz** | Configurations du timing du quiz et du score de réussite | cmi.max_time_allowed, cmi.scaled_pass_score, cmi.time_limit_action | Valeurs non définies ou configurées |