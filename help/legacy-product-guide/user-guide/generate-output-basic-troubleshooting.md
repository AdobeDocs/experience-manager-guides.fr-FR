---
title: Résolution des problèmes de base
description: Résolvez les problèmes grâce au dépannage de base dans AEM Guides. Découvrez comment afficher, copier et vérifier le fichier journal dans un éditeur de texte et résoudre les erreurs de compilation JSP.
feature: Publishing, Troubleshooting
role: User
hide: true
exl-id: f85fee0f-30d1-453f-8700-781e0be8f616
source-git-commit: 26fa1e52920c1f1abd5655b9ca7341600a9bca67
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 0%

---

# Résolution des problèmes de base {#id1821I0Y0G0A}

Lorsque vous utilisez AEM Guides, vous pouvez rencontrer des erreurs lors de la publication ou de l’ouverture de votre document. Ces erreurs peuvent se trouver dans le plan DITA, la rubrique ou dans le processus AEM Guides lui-même. Cette section fournit des informations sur la manière d’accéder aux informations et de les analyser dans le fichier journal de génération de sortie. En outre, si votre rubrique DITA est trop volumineuse, il se peut que l&#39;erreur de compilation JSP s&#39;affiche. Cette section fournit également des informations sur la façon de résoudre l’erreur de compilation JSP.

## Afficher et vérifier le fichier journal {#id1822G0P0CHS}

Pour afficher et vérifier le fichier journal de génération de sortie, procédez comme suit :

1. Une fois que vous avez lancé le processus de génération de sortie, cliquez sur **Sorties** dans la console de mappage DITA.

   La colonne **Général** des **Sorties générées** affiche les icônes pour donner un indice visuel sur le succès ou l’échec de la génération de la sortie.

   ![](images/output-general-settings.png){width="300" align="left"}

   Dans la capture d’écran ci-dessus, les première et troisième icônes indiquent l’échec de la génération de sortie. La deuxième icône affiche une génération de sortie réussie, mais avec des messages. La dernière est une génération de sortie réussie sans aucun message.

1. Une fois la tâche terminée, cliquez sur le lien de la colonne **Date de génération**.

   Le fichier journal s’ouvre dans un nouvel onglet.

   ![](images/log-file.png){width="800" align="left"}

1. Appliquez les filtres suivants pour mettre en surbrillance le texte dans le fichier journal :
   - Fatal : met en évidence les erreurs fatales dans le fichier journal avec la couleur rose.
   - Erreur : met en surbrillance les erreurs dans le fichier journal avec la couleur orange.
   - Avertissement : met en surbrillance les avertissements dans le fichier journal avec la couleur violette.
   - Infos : met en surbrillance les messages d’information dans le fichier journal avec la couleur bleue.
   - Exception : met en surbrillance les exceptions dans le fichier journal, en jaune.
1. Utilisez les boutons de navigation vers le haut et vers le bas pour accéder au texte en surbrillance dans le fichier journal.

   Vous pouvez également faire défiler le fichier journal et vérifier les messages.


## Copier et vérifier le fichier journal dans un éditeur de texte

Effectuez les étapes suivantes pour copier et vérifier le fichier journal de génération de sortie dans un éditeur de texte :

1. Une fois que vous avez lancé le processus de génération de sortie, cliquez sur **Sorties** dans la console de mappage DITA.

1. Une fois la tâche terminée, cliquez sur le lien de la colonne **Date de génération**.

   Le fichier journal s’ouvre dans un nouvel onglet.

1. Cliquez sur le bouton **Copier le journal**. Le fichier journal est copié dans le presse-papiers.
1. Ouvrez un éditeur de texte et collez le fichier journal dans l’éditeur.

1. Parcourez le fichier journal et recherchez des messages.

   Les informations suivantes vous aideront à déterminer s&#39;il existe une erreur dans le fichier DITA ou dans le processus AEM Guides :

   - *Erreur liée au fichier de plan DITA* : si une erreur est trouvée dans le fichier de plan DITA ou dans tout autre fichier contenu dans le plan DITA, le fichier journal contiendra une chaîne « BUILD FAILED ». Vous pouvez vérifier les informations fournies dans le fichier journal pour localiser le fichier erroné et résoudre le problème.

   Dans l’exemple de fragment de code suivant de fichier journal, vous pouvez voir le message `BUILD FAILED` ainsi que la raison de l’erreur.

   ![](images/dita-error-in-log-file.png){width="650" align="left"}

   - *Erreur liée à AEM Guides* : l&#39;autre type d&#39;erreur que vous pouvez identifier dans le fichier journal est lié au processus AEM Guides lui-même. Dans ce cas, le fichier de mappage DITA est analysé avec succès, mais le processus de génération de sortie échoue en raison d&#39;une erreur interne dans AEM Guides. Pour ce type d’erreur, vous devez demander de l’aide à l’équipe d’assistance technique.

   Dans l’exemple d’extrait de fichier journal suivant, le message `BUILD SUCCESSFUL` s’affiche, suivi d’une autre erreur technique.

   ![](images/process-error-in-log-file.png){width="650" align="left"}


## Résoudre l’erreur de compilation JSP

Si votre rubrique DITA est trop volumineuse, il se peut que l&#39;erreur de compilation JSP \(`org.apache.sling.api.request.TooManyCallsException`\) s&#39;affiche dans votre navigateur. Cette erreur peut apparaître lorsque vous ouvrez une rubrique pour la modifier, la réviser ou la publier.

Pour résoudre ce problème, procédez comme suit :

1. Dans la navigation globale, sélectionnez Outils et choisissez Opérations \> Console web.

   La page de configuration de la console web Adobe Experience Manager s’affiche.

1. Recherchez le composant *Servlet principal Apache Sling* et cliquez dessus.

   Les options configurables pour le servlet principal Apache Sling s’affichent.

1. Augmentez la valeur du paramètre *Nombre d’appels par requête* en fonction de vos besoins.


**Rubrique parente :**&#x200B;[ Génération de sortie](generate-output.md)
