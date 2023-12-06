---
title: PDF
description: Générez et configurez la sortie PDF pour les documents de FrameMaker dans AEM Guides.
exl-id: df3d3cd8-2aa1-4d82-8756-c3f5555cb904
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 3%

---

# PDF {#id205BB0T20RH}

Les options suivantes sont disponibles pour PDF Output :

>[!NOTE]
>
> Pour ouvrir les paramètres prédéfinis de sortie pour PDF, cliquez sur un FrameMaker \(`.fm` ou `.book`\), puis cliquez sur Paramètres prédéfinis de sortie, puis sur l’option Sortie du PDF.

| Options de PDF | Description |
|-----------|-----------|
| Type de sortie | Type de sortie à générer. Pour générer une sortie de PDF, sélectionnez l’option de PDF. |
| Nom du paramètre | Donnez un nom explicite aux paramètres de sortie du PDF que vous créez. Par exemple, vous pouvez spécifier *Sortie de clients internes* ou *sortie utilisateurs finaux*. |
| **Paramètres de tâche** |
| Options | Sélectionnez le paramètre prédéfini du PDF à utiliser pour générer la sortie du PDF. |
| Générer un PDF balisé | Sélectionnez cette option pour générer des PDF balisés qui contiendront des informations sur le contenu et la structure du document. Ces informations sont utilisées par les lecteurs à l’écran. |
| Générer un PDF pour chaque fichier du livre | Si vous générez une sortie pour un fichier livre, sélectionnez cette option pour générer un PDF distinct pour chaque fichier du livre. |
| Générer un PDF pour révision uniquement | Sélectionnez cette option pour générer un PDF avec la fonction de commentaire activée. |
| Création d’une destination nommée pour tous les éléments et paragraphes | Sélectionnez cette option pour créer des destinations nommées basées sur des éléments et des paragraphes. |
| **Paramètres d’affichage** |
| Ouvrir le document sur la page | Spécifiez le numéro de page qui doit s’afficher à l’ouverture du PDF. |
| Niveau de zoom initial | Sélectionnez le niveau de zoom du document. |
| Marque d’enregistrement | Pour imprimer un document avec des marques de recadrage et d’enregistrement, sélectionnez une option dans la liste déroulante Marques d’enregistrement . |
| Largeur de page et hauteur de page | Indiquez la largeur et la hauteur de la page. |
| Plage de pages | Choisissez si vous souhaitez publier toutes les pages du livre ou une série de pages. Si vous choisissez Plage, vous devez spécifier les plages De et À. |
| Convertir CYMK en RGB | Sélectionnez cette option pour convertir les couleurs CYMK en RGB dans le PDF généré. |
| Génération de signets de PDF | Créez un PDF accessible qui contient des signets. |
| Chemin de destination | Chemin d’accès dans votre référentiel AEM où est stockée la sortie du PDF. |
| Exécuter le processus de génération de publication | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Processus de génération de publication s’affiche, contenant tous les workflows configurés dans AEM. Vous devez sélectionner un workflow à exécuter une fois le workflow de génération de sortie terminé. |

**Rubrique parente :**[ Générer une sortie de documents de FrameMaker](fm-output-generatation.md)
