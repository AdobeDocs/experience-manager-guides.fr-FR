---
title: Résolution des problèmes de base
description: Résolvez les problèmes liés au dépannage de base dans AEM Guides. Découvrez comment afficher, copier et vérifier le fichier journal dans un éditeur de texte et résoudre les erreurs de compilation JSP.
exl-id: 57b88291-b5a3-4931-b3ed-f2b2ce7a463c
feature: Publishing, Troubleshooting
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 0%

---

# Résolution des problèmes de base {#id1821I0Y0G0A}

Lorsque vous utilisez AEM Guides, vous pouvez rencontrer des erreurs lors de la publication ou de l’ouverture de votre document. Ces erreurs peuvent se trouver dans le mappage DITA, la rubrique ou dans le processus AEM Guides lui-même. Cette section fournit des informations sur la manière d’accéder aux informations et de les analyser dans le fichier journal de génération de sortie. En outre, si votre rubrique DITA est trop volumineuse, l’erreur de compilation JSP peut s’afficher. Cette section fournit également des informations sur la manière de résoudre l’erreur de compilation JSP.

## Afficher et vérifier le fichier journal {#id1822G0P0CHS}

Effectuez les étapes suivantes pour afficher et vérifier le fichier journal de génération de sortie :

1. Une fois que vous avez lancé le processus de génération de sortie, cliquez sur **Sorties** dans la console de mappage DITA.

   La colonne **Général** de la colonne **Sorties générées** affiche les icônes pour donner un indice visuel sur la réussite ou l’échec de la génération de sortie.

   ![](images/output-general-settings.png){width="300" align="left"}

   Dans la capture d’écran ci-dessus, les première et troisième icônes affichent la génération de sortie ayant échoué. La seconde icône affiche une génération de sortie réussie, mais avec des messages. La dernière est une génération de sortie réussie sans message.

1. Cliquez sur le lien de la colonne **Généré à** une fois la tâche terminée.

   Le fichier journal s’ouvre dans un nouvel onglet.

   ![](images/log-file.png){width="800" align="left"}

1. Appliquez les filtres suivants pour mettre le texte en surbrillance dans le fichier journal :
   - Fatal : met en évidence les erreurs fatales dans le fichier journal avec une couleur rose.
   - Erreur : met en surbrillance les erreurs dans le fichier journal avec une couleur orange.
   - Avertissement : met en surbrillance les avertissements dans le fichier journal avec une couleur violette.
   - Informations : met en surbrillance les messages d’informations du fichier journal avec la couleur bleue.
   - Exception : met en évidence les exceptions dans le fichier journal avec la couleur jaune.
1. Utilisez les boutons de navigation vers le haut et vers le bas pour accéder au texte en surbrillance dans le fichier journal.

   Vous pouvez également faire défiler le fichier journal et vérifier les messages.


## Copier et vérifier le fichier journal dans un éditeur de texte

Effectuez les étapes suivantes pour copier et vérifier le fichier journal de génération de sortie dans un éditeur de texte :

1. Une fois que vous avez lancé le processus de génération de sortie, cliquez sur **Sorties** dans la console de mappage DITA.

1. Cliquez sur le lien de la colonne **Généré à** une fois la tâche terminée.

   Le fichier journal s’ouvre dans un nouvel onglet.

1. Cliquez sur le bouton **Copier le journal** . Le fichier journal est copié dans le Presse-papiers.
1. Ouvrez un éditeur de texte et collez le fichier journal dans l’éditeur.

1. Faites défiler le fichier journal et recherchez les messages.

   Les informations suivantes vous aideront à déterminer si une erreur s’est produite dans le fichier DITA ou dans le processus AEM Guides :

   - *Erreur liée au fichier de mappage DITA* : en cas d’erreur trouvée dans le fichier de mappage DITA ou dans tout autre fichier contenu dans le mappage DITA, le fichier journal contiendra une chaîne &quot;BUILD FAILED&quot;. Vous pouvez vérifier les informations données dans le fichier journal pour localiser le fichier en erreur et corriger le problème.

   Dans l’exemple de fragment de code de fichier journal suivant, vous pouvez voir le message `BUILD FAILED` avec la raison de l’erreur.

   ![](images/dita-error-in-log-file.png){width="650" align="left"}

   - *Erreur liée à AEM Guides* : l’autre type d’erreur que vous pouvez identifier dans le fichier journal est lié au processus AEM Guides lui-même. Dans ce cas, le fichier de mappage DITA est analysé avec succès, mais le processus de génération de sortie échoue en raison d’une erreur interne dans AEM Guides. Pour ce type d&#39;erreurs, vous devez demander de l&#39;aide auprès de l&#39;équipe d&#39;assistance technique.

   Dans l’exemple de fragment de code de fichier journal suivant, vous pouvez voir le message `BUILD SUCCESSFUL` suivi d’une autre erreur technique.

   ![](images/process-error-in-log-file.png){width="650" align="left"}


## Résolution de l’erreur de compilation JSP

Si votre rubrique DITA est trop volumineuse, l’erreur de compilation JSP \(`org.apache.sling.api.request.TooManyCallsException`\) peut s’afficher dans votre navigateur. Cette erreur peut s’afficher lorsque vous ouvrez une rubrique à des fins de modification, de révision ou de publication.

Pour résoudre ce problème, procédez comme suit :

1. Dans la navigation globale, sélectionnez Outils, puis Opérations > Console web.

   La page de configuration de la console web Adobe Experience Manager s’affiche.

1. Recherchez et cliquez sur le composant *Apache Sling Main Servlet*.

   Les options configurables pour le servlet principal Apache Sling s’affichent.

1. Augmentez la valeur du paramètre *Nombre d’appels par requête* en fonction de vos besoins.


**Rubrique parente :**[ Génération de sortie](generate-output.md)
