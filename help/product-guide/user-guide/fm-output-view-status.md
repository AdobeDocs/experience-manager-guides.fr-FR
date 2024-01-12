---
title: Afficher l'état de la tâche de génération de sortie
description: Affichez la file d’attente de génération de sortie des documents de FrameMaker. Découvrez comment afficher l’état d’une tâche de génération de sortie.
exl-id: c358f747-f0a5-4d9e-a96f-20f30663101f
feature: Publishing FrameMaker Documents
role: User
source-git-commit: 462647f953895f1976af5383124129c3ee869fe9
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# Afficher l&#39;état de la tâche de génération de sortie {#viewing_output_history}

Une fois que vous avez lancé la tâche de génération de sortie pour un document de FrameMaker, AEM Guides envoie cette tâche à la file d’attente de génération de sortie. Cette file d’attente est mise à jour en temps réel, indiquant l’état de chaque tâche de génération de sortie dans la file d’attente.

Effectuez les étapes suivantes pour afficher la file d’attente de génération de sortie :

1. Dans l’interface utilisateur d’Assets, accédez au document FrameMaker pour lequel vous souhaitez vérifier l’état de génération de la sortie, puis cliquez dessus.

1. Cliquez sur Sorties.

   ![](images/output-queued-fm.png){width="800" align="left"}

1. La page Sorties est divisée en deux parties :

   - **Sorties en file d’attente :**

     Répertorie les sorties en attente de génération ou en cours de processus de génération. Vous pouvez également trouver le paramètre de génération de sortie ou le paramètre prédéfini utilisé pour la tâche en file d’attente, le type, l’utilisateur qui a lancé la tâche, le temps écoulé depuis que la tâche est en file d’attente et l’état actuel.

   - **Sorties générées**

     Répertorie les tâches de sortie terminées. Ici encore, les informations affichées sont similaires à la section Sorties en file d’attente , avec la seule différence de temps de génération de sortie.

     Dans cette liste, vous pouvez avoir des tâches qui ont été exécutées avec succès ou des tâches qui ont échoué. Pour les tâches terminées avec succès, le processus de publication crée un fichier journal \(logs.txt\) accessible en cliquant sur le lien dans la colonne Généré à.


**Rubrique parente :**[ Générer une sortie de documents de FrameMaker](fm-output-generatation.md)
