---
title: JSON
description: Découvrez comment créer un paramètre prédéfini JSON à partir de l’éditeur web et du tableau de bord de mappage. Configurez le paramètre prédéfini de sortie JSON dans AEM Guides.
feature: Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 0%

---

# JSON {#id231KK0180T4}

Vous pouvez créer le paramètre prédéfini JSON à partir de l’éditeur web :

Dans le panneau Repository, ouvrez le fichier de mappage DITA en mode Carte, puis, dans l’onglet Output, sélectionnez l’icône + pour créer un paramètre prédéfini de sortie, puis sélectionnez JSON dans la liste déroulante type de la boîte de dialogue Add preset.

Dans l&#39;éditeur Web, les configurations suivantes ont été organisées sous l&#39;onglet **Général** :

- Chemin d’accès de sortie
- Fichier d’index
- Appliquer les conditions à l’aide de \(si les conditions sont définies pour une carte\)
- Utiliser la ligne de base \(si une ligne de base est créée pour une carte\)
- Conserver les fichiers temporaires
- Propriétés à propager dans la sortie
- Processus de génération de publication

Pour plus d’informations, reportez-vous à la section [Configuration JSON](#id231KJA00REJ).


**Configuration JSON**

Les options suivantes sont disponibles pour le paramètre prédéfini JSON :

>[!NOTE]
>
> Vous pouvez également modifier le fichier JSON dans l’éditeur web.

| Options JSON | Description |
| --- | --- |
| Chemin d’accès de sortie | Chemin d’accès dans votre référentiel AEM où est stockée la sortie JSON. |
| Fichier d’index | Vous pouvez attribuer un nom au fichier d’index que vous créez pour la sortie JSON. Par défaut, il sélectionne le nom de fichier de la carte DITA et ajoute un suffixe (comme `map_filename_index.json`).<br><br>Vous pouvez également utiliser des variables lors de la définition du fichier d’index. Pour plus d’informations sur l’utilisation des variables, voir [Utilisation de variables pour définir le chemin de destination, le nom du site ou les options de nom de fichier](generate-output-use-variables.md#id18BUG70K05Z). |
| Appliquer les conditions à l’aide de | Sélectionnez l’une des options suivantes :<br><br>* **Aucun appliqué** : sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.<br>* **Fichier DITAVAL** : sélectionnez le ou les fichiers DITAVAL pour générer du contenu personnalisé. Vous pouvez sélectionner plusieurs fichiers DITAVAL à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier. Pour le supprimer, utilisez l’icône croisée située à proximité du nom du fichier. Les fichiers DITAVAL sont évalués dans l’ordre spécifié. Par conséquent, les conditions spécifiées dans le premier fichier sont prioritaires sur les conditions correspondantes spécifiées dans les fichiers ultérieurs. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers. Si le fichier DITAVAL est déplacé vers un autre emplacement ou supprimé, il n’est pas automatiquement supprimé du tableau de bord de carte. Vous devez mettre à jour l’emplacement au cas où des fichiers seraient déplacés ou supprimés. Vous pouvez placer le pointeur de la souris sur le nom du fichier pour afficher le chemin d’accès dans le référentiel AEM où le fichier est stocké. Vous ne pouvez sélectionner que les fichiers DITAVAL et une erreur s’affiche si vous avez sélectionné un autre type de fichier.<br>* **Paramètre prédéfini de condition** : sélectionnez un paramètre prédéfini de condition dans la liste déroulante pour appliquer une condition lors de la publication de la sortie. L’option est visible si vous avez ajouté une condition présente dans l’onglet Paramètres prédéfinis de condition de la console de mappage DITA. Pour en savoir plus sur les paramètres prédéfinis de condition, voir [Utilisation des paramètres prédéfinis de condition](generate-output-use-condition-presets.md#id1825FL004PN). |
| Utilisation de la ligne de base | Si vous avez créé une ligne de base pour le mappage DITA sélectionné, sélectionnez cette option pour spécifier la version que vous souhaitez publier.<br><br>Voir [Utilisation de la ligne de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) pour plus de détails. |
| Conserver les fichiers temporaires | Sélectionnez cette option pour conserver les fichiers temporaires générés par DITA-OT. Si vous rencontrez des erreurs lors de la génération de la sortie via DITA-OT, sélectionnez cette option pour conserver les fichiers temporaires. Vous pouvez ensuite utiliser ces fichiers pour résoudre les erreurs de génération de sortie.<br> <br> Après avoir généré la sortie, sélectionnez l’icône **Télécharger les fichiers temporaires** ![ ](images/download-temp-files-icon.png) pour télécharger le dossier ZIP contenant les fichiers temporaires. <br><br> **Remarque** : Si des propriétés de fichier sont ajoutées pendant la génération, les fichiers temporaires de sortie incluent également un fichier *metadata.xml* contenant ces propriétés. |
| Propriétés à propager dans la sortie | Sélectionnez les propriétés que vous souhaitez traiter en tant que métadonnées. Ces propriétés sont définies à partir de la page Propriétés du mappage DITA ou du fichier bookmap. Les propriétés que vous sélectionnez dans la liste déroulante sont répertoriées sous le champ Propriétés .<br><br>**Remarque** : vous pouvez également définir des propriétés personnalisées et transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT. Pour plus d’informations, voir [Utilisation des métadonnées](metadata-dita.md#id21BJ00QD0XA). |
| Processus de génération de publication | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Processus de génération de publication s’affiche, contenant tous les workflows configurés dans AEM. Vous devez sélectionner un workflow à exécuter une fois le workflow de génération de sortie terminé.<br><br>**Remarque** : Pour plus d’informations sur la création d’un workflow personnalisé de génération post-sortie, voir _Personnaliser le workflow de génération post-sortie_ dans le guide as a Cloud Service Installer et configurer Adobe Experience Manager Guides. |

**Rubrique parente :**[ Comprendre les paramètres prédéfinis de sortie](generate-output-understand-presets.md)
