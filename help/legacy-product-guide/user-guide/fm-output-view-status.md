---
title: Afficher le statut de la tâche de génération de sortie
description: Affichez la file d’attente de génération de sortie des documents FrameMaker. Découvrez comment afficher le statut d’une tâche de génération de sortie.
feature: Publishing FrameMaker Documents
role: User
hide: true
exl-id: bf5a4365-0183-43d5-a39a-b9eb8a34b27d
TQID: https://experienceleague.adobe.com/FP5RxNtyWcdS-xpw2Atttt3x6DHx73Ljv-Ym91IxY5s
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: bf79f6d3-0ad0-4d82-99e4-42ce98324d60
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 2e0c04c623ad0fc59d962c3b7c9f2c82d4ff70e0
workflow-type: tm+mt
source-wordcount: 245
ht-degree: 0%

---

# Afficher le statut de la tâche de génération de sortie {#viewing_output_history}

Une fois que vous avez lancé la tâche de génération de sortie pour un document FrameMaker, AEM Guides envoie cette tâche à la file d’attente de génération de sortie. Cette file d’attente est mise à jour en temps réel, affichant le statut de chaque tâche de génération de sortie dans la file d’attente.

Pour afficher la file d’attente de génération de sortie, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez au document FrameMaker pour lequel vous souhaitez vérifier le statut de génération de sortie et cliquez dessus.

1. Cliquez sur Sorties.

   ![](images/output-queued-fm.png){width="800"}

1. La page Sorties est divisée en deux parties :

   - **Sorties mises en file d’attente :**

     Répertorie les sorties qui sont en attente de génération ou qui sont en cours de génération. Vous pouvez également trouver le paramètre ou le préréglage de génération de sortie utilisé pour la tâche mise en file d’attente, le type, l’utilisateur qui a initié la tâche, la durée écoulée depuis la mise en file d’attente de la tâche et le statut actuel.

   - **Sorties générées**

     Répertorie les tâches de sortie qui ont été terminées. Là encore, les informations affichées dans cette section sont similaires à celles de la section Sorties mises en file d’attente, à la seule différence du temps de génération de sortie.

     Dans cette liste, il peut y avoir des tâches exécutées avec succès ou des tâches ayant échoué. Pour les tâches qui se sont terminées avec succès, le processus de publication crée un fichier journal \(logs.txt\) accessible en cliquant sur le lien dans la colonne Généré à .


**Rubrique parente :**&#x200B;[&#x200B; générer la sortie des documents FrameMaker](fm-output-generatation.md)

