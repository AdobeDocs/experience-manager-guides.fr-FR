---
title: PDF
description: Générez et configurez la sortie PDF pour les documents FrameMaker dans AEM Guides.
exl-id: df3d3cd8-2aa1-4d82-8756-c3f5555cb904
feature: Publishing FrameMaker Documents
role: User
TQID: https://experienceleague.adobe.com/O6dJF9YPsK7quGU1k6QDzxqGcxSD9RC1Rgrw3GxhkXo
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: bf79f6d3-0ad0-4d82-99e4-42ce98324d60
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 381
ht-degree: 3%

---

# PDF {#id205BB0T20RH}

Les options suivantes sont disponibles pour la sortie PDF :

>[!NOTE]
>
> Pour ouvrir les paramètres prédéfinis de sortie pour PDF, sélectionnez un fichier FrameMaker \(`.fm` ou `.book`\), puis sélectionnez les paramètres prédéfinis de sortie et choisissez l’option Sortie PDF .

| Options de PDF | Description |
|-----------|-----------|
| Type de sortie | Type de sortie que vous souhaitez générer. Pour générer une sortie PDF, choisissez l’option PDF . |
| Nom du paramètre | Attribuez un nom explicite aux paramètres de sortie PDF que vous êtes en train de créer. Par exemple, vous pouvez spécifier *sortie des clients internes* ou *sortie des utilisateurs finaux*. |
| **Paramètres de la tâche** |  |
| Options | Choisissez le paramètre prédéfini PDF à utiliser pour générer la sortie PDF. |
| Générer un PDF balisé | Sélectionnez cette option pour générer des fichiers PDF balisés qui contiendront des informations sur le contenu et la structure du document. Ces informations sont utilisées par les lecteurs à l’écran. |
| Générer un PDF pour chaque fichier du livre | Si vous générez une sortie pour un fichier de livre, sélectionnez cette option pour générer un PDF distinct pour chaque fichier du livre. |
| Générer le PDF pour révision uniquement | Sélectionnez cette option pour générer PDF avec la fonction de commentaire activée. |
| Créer une destination nommée pour tous les éléments et paragraphes | Sélectionnez cette option pour créer des destinations nommées en fonction des éléments et des paragraphes. |
| **Paramètres d’affichage** |  |
| Ouvrir le document sur la page | Spécifiez le numéro de page à afficher à l’ouverture du PDF. |
| Niveau de zoom initial | Choisissez le niveau de zoom du document. |
| Marque D&#39;Enregistrement | Pour imprimer un document avec des traits de coupe et des repères de montage, choisissez une option dans la liste déroulante des repères de montage. |
| Largeur et hauteur de page | Spécifiez la largeur et la hauteur de la page. |
| Plage de pages | Choisissez si vous souhaitez publier toutes les pages de la liasse ou une plage de pages. Si vous choisissez Plage, vous devez spécifier la plage de pages De et À. |
| Convertir CYMK en RGB | Sélectionnez cette option pour convertir les couleurs CYMK en RGB dans le PDF généré. |
| Générer des signets PDF | Créez un PDF accessible contenant des signets. |
| Chemin de destination | Chemin d’accès dans votre référentiel AEM où est stockée la sortie PDF. |
| Exécuter le workflow de post-génération | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Workflow de post-génération s’affiche, contenant tous les workflows configurés dans AEM. Vous devez sélectionner un workflow à exécuter une fois le workflow de génération de sortie terminé. |

**Rubrique parente :**[ générer la sortie des documents FrameMaker](fm-output-generatation.md)
