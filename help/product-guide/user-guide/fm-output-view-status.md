---
title: Afficher le statut de la tâche de génération de sortie
description: Affichez la file d’attente de génération de sortie des documents FrameMaker. Découvrez comment afficher le statut d’une tâche de génération de sortie.
exl-id: c358f747-f0a5-4d9e-a96f-20f30663101f
feature: Publishing FrameMaker Documents
role: User
TQID: https://experienceleague.adobe.com/YL5ug0bhsYa-00J2fGQ-K-Cp6VE46KpC4Ss7hG64yRk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ec4263d9-bf7c-44c7-b3f1-3e664861c8f2
subfeature_v2:
  - id: bf79f6d3-0ad0-4d82-99e4-42ce98324d60
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 248
ht-degree: 0%

---

# Afficher le statut de la tâche de génération de sortie {#viewing_output_history}

Une fois que vous avez lancé la tâche de génération de sortie pour un document FrameMaker, Adobe Experience Manager Guides envoie cette tâche à la file d’attente de génération de sortie. Cette file d’attente est mise à jour en temps réel, affichant le statut de chaque tâche de génération de sortie dans la file d’attente.

Pour afficher la file d’attente de génération de sortie, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez au document FrameMaker pour lequel vous souhaitez vérifier le statut de génération de sortie et sélectionnez-le.

1. Sélectionnez Sorties.

   ![](images/output-queued-fm.png)

1. La page Sorties est divisée en deux parties :

   - **Sorties mises en file d’attente :**

     Répertorie les sorties qui sont en attente de génération ou qui sont en cours de génération. Vous pouvez également trouver le paramètre ou le préréglage de génération de sortie utilisé pour la tâche mise en file d’attente, le type, l’utilisateur qui a initié la tâche, la durée écoulée depuis la mise en file d’attente de la tâche et le statut actuel.

   - **Sorties générées**

     Répertorie les tâches de sortie qui ont été terminées. Là encore, les informations affichées dans cette section sont similaires à celles de la section Sorties mises en file d’attente, à la seule différence du temps de génération de sortie.

     Dans cette liste, il peut y avoir des tâches exécutées avec succès ou des tâches ayant échoué. Pour les tâches terminées avec succès, le processus de publication crée un fichier journal \(logs.txt\) accessible en sélectionnant le lien dans la colonne Généré à .


**Rubrique parente :**&#x200B;[&#x200B; générer la sortie des documents FrameMaker](fm-output-generatation.md)
