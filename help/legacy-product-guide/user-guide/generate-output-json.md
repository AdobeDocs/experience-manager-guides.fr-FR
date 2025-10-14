---
title: JSON
description: Découvrez comment créer un paramètre prédéfini JSON à partir de l’éditeur web et du tableau de bord de mappage. Configurez le paramètre prédéfini de sortie JSON dans AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: dbc082e9-e75e-414d-a1d1-41f919b345af
source-git-commit: 1426cdaecdd358f06e76908b09330e65997e8452
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 0%

---

# JSON {#id231KK0180T4}

Vous pouvez créer le paramètre prédéfini JSON à partir de l’éditeur web :

Dans le panneau Référentiel, ouvrez le fichier DITA map en mode Carte, puis dans l’onglet Sortie, sélectionnez l’icône + pour créer un paramètre prédéfini de sortie, puis sélectionnez JSON dans la liste déroulante Type de la boîte de dialogue Ajouter un paramètre prédéfini.

Dans l&#39;éditeur Web, les paramétrages suivants ont été organisés sous l&#39;onglet **Général** :

- Chemin d’accès de sortie
- Fichier d’index
- Appliquer des conditions à l’aide de l’opérateur \(si les conditions sont définies pour un mappage\)
- Utiliser la ligne de base \(si une ligne de base est créée pour un mappage\)
- Conserver les fichiers temporaires
- Propriétés à propager dans la sortie
- Workflow de post-génération

Pour plus d’informations, consultez la section [Configuration JSON](#id231KJA00REJ).


**Configuration JSON**

Les options suivantes sont disponibles pour le paramètre prédéfini JSON :

>[!NOTE]
>
> Vous pouvez également modifier le fichier JSON dans l’éditeur web.

| Options JSON | Description |
| --- | --- |
| Chemin d’accès de sortie | Chemin d’accès dans votre référentiel AEM où est stockée la sortie JSON. |
| Fichier d’index | Vous pouvez donner un nom au fichier d’index que vous créez pour la sortie JSON. Par défaut, il sélectionne le nom de fichier du plan DITA et ajoute un suffixe (comme `map_filename_index.json`).<br><br>Vous pouvez également utiliser des variables lors de la définition du fichier d’index. Pour plus d’informations sur l’utilisation des variables, voir [Utiliser des variables pour définir les options Chemin de destination, Nom du site ou Nom de fichier](generate-output-use-variables.md#id18BUG70K05Z). |
| Application de conditions à l’aide de | Sélectionnez l’une des options suivantes :<br><br>* **Aucune appliquée** : sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.<br>* **Fichier DITAVAL** : Sélectionnez le ou les fichiers DITAVAL pour générer du contenu personnalisé. Vous pouvez sélectionner plusieurs fichiers DITAVAL à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier. Utilisez la croix près du nom du fichier pour le supprimer. Les fichiers DITAVAL sont évalués dans l&#39;ordre spécifié. Les conditions spécifiées dans le premier fichier sont donc prioritaires sur les conditions correspondantes spécifiées dans les fichiers ultérieurs. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers. Si le fichier DITAVAL est déplacé vers un autre emplacement ou est supprimé, il n&#39;est pas automatiquement supprimé du tableau de bord de carte. Vous devez mettre à jour l’emplacement au cas où les fichiers seraient déplacés ou supprimés. Vous pouvez pointer sur le nom du fichier pour afficher le chemin d’accès dans le référentiel AEM où le fichier est stocké. Vous ne pouvez sélectionner que des fichiers DITAVAL et une erreur s&#39;affiche si vous avez sélectionné un autre type de fichier.<br>* **Paramètre prédéfini de condition** : sélectionnez un paramètre prédéfini de condition dans la liste déroulante pour appliquer une condition lors de la publication de la sortie. Cette option est visible si vous avez ajouté une condition présente dans l&#39;onglet Paramètres prédéfinis de condition de la console de mappage DITA. Pour en savoir plus sur les paramètres prédéfinis de condition, voir [&#x200B; Utilisation de paramètres prédéfinis de condition &#x200B;](generate-output-use-condition-presets.md#id1825FL004PN). |
| Utiliser niveau de référence | Si vous avez créé une ligne de base pour le plan DITA sélectionné, sélectionnez cette option pour spécifier la version que vous souhaitez publier.<br><br>Voir [Utilisation de la ligne de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) pour plus d’informations. |
| Conserver les fichiers temporaires | Sélectionnez cette option pour conserver les fichiers temporaires générés par DITA-OT. Si vous rencontrez des erreurs lors de la génération de la sortie via DITA-OT, sélectionnez cette option pour conserver les fichiers temporaires. Vous pouvez ensuite utiliser ces fichiers pour résoudre les erreurs de génération de sortie.<br> <br> Après avoir généré la sortie, sélectionnez l’icône **Télécharger les fichiers temporaires** ![Télécharger les fichiers temporaires](images/download-temp-files-icon.png) pour télécharger le dossier ZIP contenant les fichiers temporaires. <br><br> **Remarque** : si des propriétés de fichier sont ajoutées pendant la génération, les fichiers temporaires de sortie incluent également un fichier *metadata.xml* contenant ces propriétés. |
| Propriétés à propager dans la sortie | Sélectionnez les propriétés à traiter en tant que métadonnées. Ces propriétés sont définies à partir de la page Propriétés du fichier DITA map ou bookmap. Les propriétés que vous sélectionnez dans la liste déroulante sont répertoriées sous le champ Propriétés .<br><br>**Remarque** : vous pouvez également définir des propriétés personnalisées et transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT. Pour plus d’informations, consultez [&#x200B; Utilisation des métadonnées &#x200B;](metadata-dita.md#id21BJ00QD0XA). |
| Workflow de post-génération | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Workflow de post-génération s’affiche, contenant tous les workflows configurés dans AEM. Vous devez sélectionner un workflow à exécuter une fois le workflow de génération de sortie terminé.<br><br>**Remarque** : pour plus d’informations sur la création d’un workflow personnalisé de génération post-sortie, voir _Personnaliser le workflow de génération post-sortie_ dans le guide Installation et configuration d’Adobe Experience Manager Guides as a Cloud Service . |

**Rubrique parente :**&#x200B;[&#x200B; Présentation des paramètres prédéfinis de sortie](generate-output-understand-presets.md)
