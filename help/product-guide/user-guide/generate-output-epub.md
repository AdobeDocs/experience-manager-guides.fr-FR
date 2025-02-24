---
title: Paramètre prédéfini EPUB
description: Découvrez comment créer un paramètre prédéfini EPUB à partir du tableau de bord de carte. Configurez le paramètre prédéfini de sortie EPUB dans Experience Manager Guides.
exl-id: b6fb5483-064e-4552-84c7-b6723b79d8c5
feature: Publishing
role: User
source-git-commit: 558cc1a724a483353eb5d912354e1ab37dab348a
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 1%

---

# EPUB {#id205BED020YT}

Vous pouvez créer le paramètre prédéfini EPUB à partir du tableau de bord de mappage.

>[!NOTE]
>
> Vous pouvez choisir la méthode pour générer EPUB à l’aide de la commande DITA-OT ou FMPS \(si votre administrateur système l’a configurée\).

Pour créer le paramètre prédéfini EPUB à partir du tableau de bord de mappage, procédez comme suit :

1. Dans l’interface utilisateur d’Assets, accédez à et sélectionnez le plan DITA pour l’ouvrir dans le tableau de bord des plans.
1. Assurez-vous que l’onglet **Paramètres prédéfinis de sortie** est sélectionné.
1. Sélectionnez **Créer** dans la barre d’outils.

   Un nouveau formulaire de création de paramètre prédéfini de sortie s’affiche.

1. Saisissez les détails de configuration requis pour le paramètre prédéfini EPUB.
1. Sélectionnez **Terminé** pour enregistrer les paramètres prédéfinis.

Les options de configuration suivantes sont disponibles pour le paramètre prédéfini EPUB :

| Options d’EPUB | Description |
| --- | --- |
| Type de sortie | Type de sortie que vous souhaitez générer. Pour générer une sortie EPUB, choisissez l’option EPUB . |
| Nom du paramètre | Attribuez un nom explicite aux paramètres de sortie EPUB que vous êtes en train de créer. Par exemple, vous pouvez spécifier _sortie des clients internes_ ou _sortie des utilisateurs finaux_. |
| Arguments de ligne de commande DITA-OT | Spécifiez les arguments supplémentaires que DITA-OT doit traiter lors de la génération de la sortie. Pour plus d&#39;informations sur les arguments de ligne de commande pris en charge dans DITA-OT, consultez la [documentation DITA-OT](https://www.dita-ot.org/). |
| Générer EPUB à l’aide de | Sélectionnez DITA-OT pour générer la sortie EPUB. |
| Application de conditions à l’aide de | Sélectionnez l’une des options suivantes :<br><br>* **Aucune appliquée** : sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.<br>* **fichier DITAVal** : sélectionnez le ou les fichiers DITAVal pour générer du contenu personnalisé. Vous pouvez sélectionner plusieurs fichiers DITAVal à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier. Utilisez la croix près du nom du fichier pour le supprimer. Les fichiers DITAVal sont évalués dans l&#39;ordre spécifié. De ce fait, les conditions spécifiées dans le premier fichier sont prioritaires sur les conditions correspondantes spécifiées dans les fichiers ultérieurs. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers. Si le fichier DITAVal est déplacé vers un autre emplacement ou est supprimé, il n&#39;est pas automatiquement supprimé du tableau de bord de mappage. Vous devez mettre à jour l’emplacement au cas où les fichiers seraient déplacés ou supprimés. Vous pouvez pointer sur le nom du fichier pour afficher le chemin d’accès dans le référentiel AEM où le fichier est stocké. Vous ne pouvez sélectionner que les fichiers DITAVal et une erreur s&#39;affiche si vous avez sélectionné un autre type de fichier. FrameMaker Publishing Server ne prend pas en charge les fichiers DITAVAL multiples.<br>* **Paramètre prédéfini de condition** : sélectionnez un paramètre prédéfini de condition dans la liste déroulante pour appliquer une condition lors de la publication de la sortie. Cette option est visible si vous avez ajouté une condition présente dans l&#39;onglet Paramètres prédéfinis de condition de la console de mappage DITA. Pour en savoir plus sur les paramètres prédéfinis de condition, consultez [Utilisation des paramètres prédéfinis de condition](generate-output-use-condition-presets.md#id1825FL004PN). |
| Chemin de destination | Chemin d’accès dans votre référentiel AEM où est stockée la sortie EPUB. |
| Nom du fichier | Indiquez le nom du fichier avec lequel vous souhaitez enregistrer la sortie EPUB.<br><br>**Remarque** : si vous ne fournissez pas de nom de fichier, le titre du plan DITA est utilisé pour générer le nom de fichier de sortie EPUB final. Si le mappage n&#39;a pas de titre, le nom de fichier du mappage DITA est utilisé pour désigner la sortie EPUB finale. Le nom du fichier est assaini à l’aide des règles configurées dans le système pour gérer tout caractère non valide. |
| Nom de la transformation | Indiquez le type de sortie que vous souhaitez générer. Cela est nécessaire si vous souhaitez générer une sortie à l’aide de votre propre plug-in personnalisé, qui est intégré au plug-in DITA-OT. Par exemple, si vous souhaitez générer une sortie XHTML, spécifiez `xhtml`. Pour obtenir la liste des transformations disponibles dans DITA-OT, consultez [Transformations DITA-OT (formats de sortie)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.md) dans le guide d&#39;utilisation OASIS DITA-OT. |
| Nettoyer les fichiers temporaires DITA-OT | Sélectionnez cette option pour nettoyer les fichiers temporaires générés par DITA-OT. L&#39;emplacement où DITA-OT stocke les fichiers temporaires se trouve dans le journal de génération de sortie.<br><br>Si vous rencontrez des erreurs lors de la génération de la sortie via DITA-OT, vous pouvez désélectionner cette option pour conserver les fichiers temporaires. Vous pouvez ensuite utiliser ces fichiers pour résoudre les erreurs de génération de sortie. |
| Exécuter le workflow de post-génération | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Workflow de post-génération s’affiche, contenant tous les workflows configurés dans AEM. Vous devez sélectionner un workflow à exécuter une fois le workflow de génération de sortie terminé.<br><br>**Remarque** : pour plus d’informations sur la création d’un workflow de génération post-sortie personnalisé, consultez _Personnaliser le workflow de génération post-sortie_ dans Installation et configuration d’Adobe Experience Manager Guides as a Cloud Service. |
| Utiliser niveau de référence | Si vous avez créé une ligne de base pour le plan DITA sélectionné, sélectionnez cette option pour spécifier la version que vous souhaitez publier.<br><br>Affichage [Utilisation de la ligne de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) pour plus d’informations. |
| Propriétés | Sélectionnez les propriétés à traiter en tant que métadonnées. Ces propriétés sont définies à partir de la page Propriétés du fichier DITA map ou bookmap. Les propriétés que vous sélectionnez dans la liste déroulante sont répertoriées sous le champ Propriétés et sont supprimées de la liste déroulante. Une fois définies, ces propriétés sont également copiées dans les rubriques de la carte.<br><br>**Remarque** : vous pouvez également transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT. Pour plus de détails, [Transmettez les métadonnées à la sortie à l’aide de DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Rubrique parente :**[ Présentation des paramètres prédéfinis de sortie](generate-output-understand-presets.md)
