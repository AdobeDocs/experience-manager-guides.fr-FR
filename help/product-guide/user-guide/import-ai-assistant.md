---
title: Importer des documents en tant que rubriques avec l’assistant AI
description: Découvrez comment convertir des fichiers PDF, Word et Markdown en rubriques DITA et en carte à l’aide de l’assistant AI, et examinez les résultats avant de les enregistrer.
source-git-commit: f936d474c6efcea89b244ccd25e03b065a478250
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%
---

# Importer du contenu avec l’assistant d’IA

Les compétences **Import** du mode Agentic de l&#39;assistant AI vous permettent de convertir des fichiers PDF, Word ou Markdown existants en rubriques DITA structurées, avec la possibilité de générer des plans DITA en fonction des entrées de l&#39;utilisateur. Il simplifie l’ingestion de contenu à partir de formats non structurés vers des formats structurés dans Adobe Experience Manager Guides en réduisant les efforts manuels nécessaires à la recréation, la structure et l’organisation du contenu.

## Importer un fichier

Vous pouvez importer des fichiers à partir de votre appareil ou référentiel de contenu, spécifier le niveau d’en-tête qui définit le début d’une nouvelle rubrique et choisir le dossier de destination du contenu importé. Pour importer un fichier, procédez comme suit :

1. Connectez-vous à Experience Manager Guides.
1. Sur la page d’accueil, sélectionnez **Assistant AI** dans la barre de navigation. Assurez-vous que l’assistant [AI en mode Agence](../install-conf-guide/workspace-settings.md) est activé par l’administrateur.
1. Sélectionnez **Importer** dans le panneau de l’assistant d’IA. Vous pouvez également utiliser d&#39;autres invites comme *Convertir cette documentation en rubriques DITA* pour un fichier Word ou *Convertir ce markdown en rubriques DITA* pour un fichier Markdown.

   L’invite de démarrage *Aide pour importer du contenu à partir du fichier PDF joint* s’affiche dans la zone d’invite.

1. Joignez le fichier à votre invite à l’aide de l’une des méthodes suivantes :

   - **Utilisation d’un raccourci** : saisissez `/` dans le champ Invite, puis choisissez **Ajouter une référence au référentiel** pour choisir le fichier dans le référentiel (ou **Ajouter des fichiers à partir de l’appareil** pour télécharger le fichier depuis votre ordinateur).

   - **À l’aide de l’icône Joindre des fichiers ou Ajouter un contexte (+)** : permet d’ajouter des fichiers de votre système local pour fournir le contenu à importer.

   - **Glisser-déposer** : faites glisser et déposez le fichier à importer du système directement dans l&#39;espace d&#39;invite.

     ![](images/attach-import.png)

1. Sélectionnez **Envoyer**.

   L’assistant AI analyse le fichier et répertorie chaque étape qu’il effectue.

1. Sélectionnez et confirmez le dossier dans lequel vous souhaitez enregistrer les rubriques importées.

   ![](images/folder-import.png)

1. Choisissez le niveau d&#39;en-tête qui devient une rubrique. Par exemple, H2, comme illustré dans la capture d’écran.

   Répondez à toutes les questions de suivi supplémentaires qui semblent fournir les détails nécessaires au processus d’importation.

   ![](images/heading-import.png)

1. Sélectionnez **Confirmer**.

   L’assistant AI commence à convertir le fichier. La compétence Importer identifie et attribue automatiquement les types de rubrique DITA appropriés, tels que Tâche, Dépannage, etc., en fonction du contenu importé.

1. Sélectionnez **Aperçu** pour consulter les rubriques générées et la carte.

   Vérifiez que chaque rubrique commence à l’en-tête attendu et que l’ordre de mappage correspond au fichier d’origine. Vous pouvez également vérifier le code Source des données importées à l’aide de l’onglet Source .

   ![](images/preview-import.png)

1. Effectuez l’une des actions suivantes :

   - **Accepter** pour enregistrer toutes les rubriques et les mapper au dossier que vous avez confirmé.
   - **Rejeter** pour annuler l’importation sans rien enregistrer. Vous pouvez indiquer le motif du rejet de l’importation et saisir une invite spécifiant les modifications souhaitées. L’assistant AI utilise vos commentaires pour réviser l’importation.

   Les rubriques et la carte sont désormais disponibles dans votre référentiel.

   ![](images/accept-reject-import.png)

Une fois la conversion terminée, l’assistant AI ouvre un aperçu des rubriques et du mappage générés. Vous pouvez accéder à la carte et aux rubriques correspondantes directement à partir de la boîte de dialogue de l’assistant d’IA.

## Importer le contenu collé sous forme de rubriques

Coller du contenu à partir d’une page web, de Word, de Google Docs ou d’un wiki permet d’importer sans enregistrer de fichier au préalable. Le contenu formaté conserve ses en-têtes, ses listes et ses tableaux.

Pour importer du contenu collé :

1. Connectez-vous à Experience Manager Guides.
1. Sur la page d’accueil, sélectionnez **Assistant AI** dans la barre de navigation. Assurez-vous que l’assistant AI en mode Agence est activé par l’administrateur.
1. Copiez le contenu de la page web, de Word, de Google Docs ou du wiki.
1. Collez le contenu dans la zone d’invite.

   Le contenu formaté de plus de 2 000 caractères est joint en tant que Markdown, sa structure est donc transférée.

   ![](images/pasted-import.png)

1. Saisissez une invite qui spécifie le contenu souhaité.

   Par exemple, saisissez *Importer la page collée dans DITA* ou *Transformer le contenu collé en rubriques DITA et en carte*

1. Sélectionnez **Envoyer**.

L’assistant AI vous invite à sélectionner le niveau d’en-tête pour fractionner le contenu en rubriques et à spécifier le dossier de destination. Les étapes restantes sont identiques à l&#39;importation d&#39;un fichier joint, notamment la révision et la confirmation du workflow d&#39;importation pour générer des rubriques DITA et un mappage.



