---
title: Mesures clés SCORM pour la progression de l’élève et l’achèvement du cours
description: En savoir plus sur les mesures clés SCORM pour la progression des élèves et l’achèvement du cours
feature: Authoring
role: Admin
level: Experienced
exl-id: f25cbbbd-5d9f-47b0-9260-8062e026913d
TQID: https://experienceleague.adobe.com/ZyY9sjaqGANXlUI5l3OsP-i1Pu-es-B-iGnpPJjQYrY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 281
ht-degree: 1%

---

# Mesures clés SCORM pour la progression de l’élève et l’achèvement du cours

Cet article répertorie les paramètres clés capturés dans un package SCORM, ainsi que les champs correspondants et des exemples. Ces paramètres fournissent des informations essentielles sur la progression de l’élève, la fin du cours, les détails de l’interaction et les performances du quiz. Les administrateurs peuvent utiliser ces informations pour valider le suivi, configurer les rapports et garantir des analyses précises dans l’environnement LMS. Voici des exemples de valeurs fournies pour chaque paramètre tel qu’il apparaît dans le package SCORM.

| **Nom du paramètre** | **Description** | **Champs** | **Exemple** |
|---|---|---|---|
| **Statut d’achèvement du cours** | Indique si le cours est terminé ou non | cmi.completion_status | incomplet |
| **Nombre de tentatives** | Nombre de tentatives effectuées par l’élève | Compteur/contenu de tentative côté LMS | Tentatives : 1 |
| **Emplacement du package SCORM** | Signet ou emplacement actuel dans le cours | cmi.location | - |
| **Progression terminée** | Learner&#39;s progress | cmi.progress_measurement | 0,87 |
| **Durée totale (tentative)** | Temps total passé dans la tentative actuelle | cmi.total_time | 0000:01:09.87 |
| **Visibilité de la table des matières et nombre de rubriques** | Affiche la visibilité de la table des matières et les détails d&#39;achèvement de la rubrique | Project.HideTOC, Project.TotalTopics, Project.TopicsCompleted | - |
| **Par statut de topic** | Statut d’achèvement et de réussite pour chaque rubrique | État personnalisé par leçon | - |
| **Par état de choix de question** | Effectue le suivi des choix sélectionnés de l’élève par question | value, generate_id, vérifié. | - |
| **Score global des questions** | Score obtenu au niveau des questions et agrégat | {« score »:0,« maxScore »:1} et % | « score »:33.33,« maxScore »:100,« minScore »:0 |
| **Interactions à chaque niveau de question** | Détails de l’interaction de l’élève par question | id/type/timestamp/correct_response/learner_response/result/latency | - |
| **Etat général du cours** | Indique les réussites/échecs et la progression globale. | success_status, completion_status, score, progress_measurement | Réussite ou échec |
| **Learner details** | Identifie l’élève par ID et nom | cmi.learner_id, cmi.learner_name | Albert |
| **Paramètres du quiz** | Configurations du timing du quiz et du score de réussite | cmi.max_time_allowed, cmi.scaled_pass_score, cmi.time_limit_action | Valeurs non définies ou configurées |
