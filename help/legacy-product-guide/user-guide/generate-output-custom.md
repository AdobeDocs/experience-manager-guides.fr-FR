---
title: Personnalisé
description: Découvrez comment créer un paramètre prédéfini personnalisé à partir de l’éditeur web et du tableau de bord de mappage. Configurez un paramètre prédéfini de sortie personnalisé dans AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: b96e6599-f8f3-491a-8b8f-fcb1e0f58aae
source-git-commit: 26fa1e52920c1f1abd5655b9ca7341600a9bca67
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 1%

---

# Personnalisé {#id205BEF00PX0}

Les paramètres prédéfinis de sortie personnalisés sont disponibles pour les modules externes DITA-OT personnalisés. Vous pouvez créer un paramètre prédéfini de sortie DITA-OT personnalisé pour publier la sortie à l&#39;aide de votre plug-in DITA-OT personnalisé.

Vous pouvez créer le paramètre prédéfini personnalisé de deux manières :

**Dans l’éditeur Web :** dans le panneau Référentiel, ouvrez le fichier DITA map en mode Carte, puis dans l’onglet Sortie, sélectionnez l’icône + pour créer un paramètre prédéfini de sortie, puis sélectionnez Personnalisé dans la liste déroulante Type de la boîte de dialogue Ajouter un paramètre prédéfini.

Dans l’éditeur web, les configurations ont été organisées sous les onglets Général et Avancé :

**Général**

L&#39;onglet **Général** contient les paramétrages suivants :

- Arguments de ligne de commande DITA-OT
- Nom de la transformation
- Nom du fichier
- Chemin d’accès de sortie
- Appliquer des conditions à l’aide de l’opérateur \(si les conditions sont définies pour un mappage\)
- Utiliser la ligne de base \(si une ligne de base est créée pour un mappage\)
- Workflow de post-génération

**Avancé**

L’onglet Avancé contient les configurations suivantes :

- Conserver les fichiers temporaires
- Propriétés du fichier

Pour plus d&#39;informations, consultez la section [Configuration personnalisée](#id231KJA00REJ).

**Depuis le tableau de bord de la carte**

Pour afficher les paramètres prédéfinis de sortie pour PDF, cliquez sur un fichier de mappage DITA dans l’interface utilisateur d’Assets, puis cliquez sur Paramètres prédéfinis de sortie, puis sur l’option HTML5. Dans le tableau de bord des cartes, cliquez sur **Modifier** dans la partie supérieure pour mettre à jour les différentes configurations, puis cliquez sur **Enregistrer**.

**Configuration personnalisée**

Les options suivantes sont disponibles pour le paramètre prédéfini de sortie personnalisé :

| Options de sortie personnalisées | Description |
| --- | --- |
| Type de sortie | Type de sortie que vous souhaitez générer. Pour générer une sortie à l’aide du plug-in DITA-OT personnalisé, sélectionnez l’option Personnalisé . |
| Nom du paramètre | Attribuez un nom explicite aux paramètres de sortie que vous êtes en train de créer. Par exemple, vous pouvez spécifier _sortie des clients internes_ ou _sortie des utilisateurs finaux_. |
| Arguments de ligne de commande DITA-OT | Spécifiez les arguments supplémentaires que DITA-OT doit traiter lors de la génération de la sortie. Pour plus d&#39;informations sur les arguments de ligne de commande pris en charge dans DITA-OT, consultez la [documentation DITA-OT](https://www.dita-ot.org/). |
| Nom de la transformation | Indiquez le type de sortie que vous souhaitez générer. Cela est nécessaire si vous souhaitez générer une sortie à l’aide de votre propre plug-in personnalisé, qui est intégré au plug-in DITA-OT. Par exemple, si vous souhaitez générer une sortie XHTML, spécifiez `xhtml`. Pour obtenir la liste des transformations disponibles dans DITA-OT, consultez [Transformations DITA-OT (formats de sortie)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) dans le guide d&#39;utilisation OASIS DITA-OT. |
| Nom du fichier | Indiquez le nom du fichier avec lequel vous souhaitez enregistrer la sortie.<br><br>**Remarque** : si vous ne fournissez pas de nom de fichier, le titre du plan DITA est utilisé pour générer le nom de fichier de sortie final. Si le mappage n&#39;a pas de titre, le nom de fichier du mappage DITA est utilisé comme nom de sortie finale. Le nom du fichier est assaini à l’aide des règles configurées dans le système pour gérer tout caractère non valide. |
| Application de conditions à l’aide de | Sélectionnez l’une des options suivantes :<br><br>* **Aucune appliquée** : sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.<br>* **fichier DITAVal** : sélectionnez le ou les fichiers DITAVal pour générer du contenu personnalisé. Vous pouvez sélectionner plusieurs fichiers DITAVal à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier. Utilisez la croix près du nom du fichier pour le supprimer. Les fichiers DITAVal sont évalués dans l&#39;ordre spécifié. De ce fait, les conditions spécifiées dans le premier fichier sont prioritaires sur les conditions correspondantes spécifiées dans les fichiers ultérieurs. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers. Si le fichier DITAVal est déplacé vers un autre emplacement ou est supprimé, il n&#39;est pas automatiquement supprimé du tableau de bord de mappage. Vous devez mettre à jour l’emplacement au cas où les fichiers seraient déplacés ou supprimés. Vous pouvez pointer sur le nom du fichier pour afficher le chemin d’accès dans le référentiel AEM où le fichier est stocké. Vous ne pouvez sélectionner que les fichiers DITAVal et une erreur s&#39;affiche si vous avez sélectionné un autre type de fichier.<br>* **Paramètre prédéfini de condition** : sélectionnez un paramètre prédéfini de condition dans la liste déroulante pour appliquer une condition lors de la publication de la sortie. Cette option est visible si vous avez ajouté une condition présente dans l&#39;onglet Paramètres prédéfinis de condition de la console de mappage DITA. Pour en savoir plus sur les paramètres prédéfinis de condition, voir [ Utilisation de paramètres prédéfinis de condition ](generate-output-use-condition-presets.md#id1825FL004PN). |
| Chemin de destination | Chemin d’accès dans votre référentiel AEM où est stockée la sortie EPUB. |
| Conserver les fichiers temporaires | Sélectionnez cette option pour conserver les fichiers temporaires générés par DITA-OT. Si vous rencontrez des erreurs lors de la génération de la sortie via DITA-OT, sélectionnez cette option pour conserver les fichiers temporaires. Vous pouvez ensuite utiliser ces fichiers pour résoudre les erreurs de génération de sortie.<br> <br> Après avoir généré la sortie, sélectionnez l’icône **Télécharger les fichiers temporaires** ![Télécharger les fichiers temporaires](images/download-temp-files-icon.png) pour télécharger le dossier ZIP contenant les fichiers temporaires. <br><br> **Remarque** : si des propriétés de fichier sont ajoutées pendant la génération, les fichiers temporaires de sortie incluent également un fichier *metadata.xml* contenant ces propriétés. |
| Exécuter le workflow de post-génération | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Workflow de post-génération s’affiche, contenant tous les workflows configurés dans AEM. Vous devez sélectionner un workflow à exécuter une fois le workflow de génération de sortie terminé.<br><br>**Remarque** : pour plus d’informations sur la création d’un workflow personnalisé de génération post-sortie, voir _Personnaliser le workflow de génération post-sortie_ dans Installation et configuration d’Adobe Experience Manager Guides as a Cloud Service. |
| Utiliser niveau de référence | Si vous avez créé une ligne de base pour le plan DITA sélectionné, sélectionnez cette option pour spécifier la version que vous souhaitez publier.<br><br>Voir [Utilisation de la ligne de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) pour plus d’informations. |
| Propriétés du fichier | Sélectionnez les propriétés à traiter en tant que métadonnées. Ces propriétés sont définies à partir de la page Propriétés du fichier DITA map ou bookmap. Les propriétés que vous sélectionnez dans la liste déroulante s’affichent sous le champ **Propriétés du fichier**. Sélectionnez l’icône croisée en regard de la propriété pour la supprimer. <br><br>**Remarque** : vous pouvez également transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT. Pour plus d&#39;informations, reportez-vous à la section [Transmission des métadonnées à la sortie à l&#39;aide de DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Rubrique parente :**&#x200B;[ Présentation des paramètres prédéfinis de sortie](generate-output-understand-presets.md)
