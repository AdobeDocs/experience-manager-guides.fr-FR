---
title: Afficher le statut de la tâche de génération de sortie
description: Affichez la file d’attente de génération de sortie des documents FrameMaker. Découvrez comment afficher le statut d’une tâche de génération de sortie.
exl-id: c358f747-f0a5-4d9e-a96f-20f30663101f
feature: Publishing FrameMaker Documents
role: User
source-git-commit: b78a34430476c15cadacb23d65bd978b3c25bd23
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---

# Afficher le statut de la tâche de génération de sortie {#viewing_output_history}

Une fois que vous avez lancé la tâche de génération de sortie pour un document FrameMaker, Adobe Experience Manager Guides envoie cette tâche à la file d’attente de génération de sortie. Cette file d’attente est mise à jour en temps réel, affichant le statut de chaque tâche de génération de sortie dans la file d’attente.

Pour afficher la file d’attente de génération de sortie, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez au document FrameMaker pour lequel vous souhaitez vérifier le statut de génération de sortie et sélectionnez-le.

1. Sélectionnez Sorties.

   ![](images/output-queued-fm.png){align="left"}

1. La page Sorties est divisée en deux parties :

   - **Sorties mises en file d’attente :**

     Répertorie les sorties qui sont en attente de génération ou qui sont en cours de génération. Vous pouvez également trouver le paramètre ou le préréglage de génération de sortie utilisé pour la tâche mise en file d’attente, le type, l’utilisateur qui a initié la tâche, la durée écoulée depuis la mise en file d’attente de la tâche et le statut actuel.

   - **Sorties générées**

     Répertorie les tâches de sortie qui ont été terminées. Là encore, les informations affichées dans cette section sont similaires à celles de la section Sorties mises en file d’attente, à la seule différence du temps de génération de sortie.

     Dans cette liste, il peut y avoir des tâches exécutées avec succès ou des tâches ayant échoué. Pour les tâches terminées avec succès, le processus de publication crée un fichier journal \(logs.txt\) accessible en sélectionnant le lien dans la colonne Généré à .


**Rubrique parente :**&#x200B;[&#x200B; générer la sortie des documents FrameMaker](fm-output-generatation.md)
