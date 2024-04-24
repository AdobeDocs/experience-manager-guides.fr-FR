---
title: Generate PDF
description: Découvrez comment créer un paramètre prédéfini de PDF à partir de l’éditeur web et du tableau de bord de mappage. Configurez le paramètre prédéfini de sortie PDF dans AEM Guides.
exl-id: f12c91fd-3f95-478e-a9cd-68d037206ee8
feature: Publishing
role: User
source-git-commit: b82f1f3b42f85cce8420d3962c69cd3bafc5728d
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 1%

---

# PDF {#id205BE600HAH}

Vous pouvez créer le paramètre prédéfini du PDF de deux manières :

**Dans l’éditeur Web :** Dans le panneau Référentiel, ouvrez le fichier de mappage DITA en mode Carte, puis, dans l’onglet Sortie, sélectionnez l’icône + pour créer un paramètre prédéfini de sortie, puis sélectionnez PDF dans la liste déroulante de type de la boîte de dialogue Ajouter un paramètre prédéfini .

>[!NOTE]
>
> Vous pouvez choisir la méthode de génération du PDF à l’aide de DITA-OT, de l’PDF natif ou de FMPS \(si votre administrateur système l’a configuré\).

Dans l&#39;éditeur Web, les paramétrages ont été organisés sous les onglets Général et Avancé :

**Général**

La variable **Général** contient les configurations suivantes :

- Chemin d’accès de sortie
- Arguments de ligne de commande DITA-OT
- Nom de la transformation
- Nom de fichier du PDF
- Appliquer les conditions à l’aide de \(si les conditions sont définies pour une carte\)
- Utiliser la ligne de base \(si une ligne de base est créée pour une carte\)
- Processus de génération de publication

**Avancé**

L&#39;onglet Avancé contient les paramétrages suivants :

- Activation des versions
- Téléchargement de fichiers temporaires

Pour plus d’informations, voir [Configuration du PDF](#id231KIM004X1).

**Depuis le tableau de bord de la carte**

Pour ouvrir les paramètres prédéfinis de sortie pour PDF, cliquez sur un fichier de mappage DITA dans l’interface utilisateur d’Assets, puis cliquez sur Paramètres prédéfinis de sortie, puis sur l’option du PDF. Dans le tableau de bord de la carte, cliquez sur **Modifier** dans la partie supérieure pour mettre à jour les différentes configurations, puis cliquez sur **Enregistrer**.

**Configuration du PDF**

Les options suivantes sont disponibles pour PDF Output :

| Options de PDF | Description |
| --- | --- |
| Type de sortie | Type de sortie à générer. Pour générer une sortie de PDF, sélectionnez l’option de PDF. |
| Nom du paramètre | Donnez un nom explicite aux paramètres de sortie du PDF que vous créez. Par exemple, vous pouvez spécifier _Sortie de clients internes_ ou _sortie utilisateurs finaux_. |
| Arguments de ligne de commande DITA-OT | Spécifiez les arguments supplémentaires que vous souhaitez que DITA-OT traite lors de la génération de la sortie. Pour plus d’informations sur les arguments de ligne de commande pris en charge dans DITA-OT, voir [Documentation DITA-OT](https://www.dita-ot.org/). |
| Appliquer les conditions à l’aide de | Sélectionnez l’une des options suivantes :<br><br>* **Aucun appliqué**: sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.<br>* **Fichier DITAVal**: sélectionnez le ou les fichiers DITAVal pour générer du contenu personnalisé. Vous pouvez sélectionner plusieurs fichiers DITAVal à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier. Pour le supprimer, utilisez l’icône croisée située à proximité du nom du fichier. Les fichiers DITAVal sont évalués dans l’ordre spécifié. Par conséquent, les conditions spécifiées dans le premier fichier sont prioritaires sur les conditions correspondantes spécifiées dans les fichiers ultérieurs. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers. Si le fichier DITAVal est déplacé vers un autre emplacement ou supprimé, il n’est pas automatiquement supprimé du tableau de bord de la carte. Vous devez mettre à jour l’emplacement au cas où des fichiers seraient déplacés ou supprimés. Vous pouvez placer le pointeur de la souris sur le nom du fichier pour afficher le chemin d’accès dans le référentiel AEM où le fichier est stocké. Vous ne pouvez sélectionner que les fichiers DITAVal et une erreur s’affiche si vous avez sélectionné un autre type de fichier. FrameMaker Publishing Server ne prend pas en charge plusieurs fichiers DITAVAL.<br>* **Paramètre prédéfini de condition**: sélectionnez un paramètre prédéfini de condition dans la liste déroulante pour appliquer une condition lors de la publication de la sortie. L’option est visible si vous avez ajouté une condition présente dans l’onglet Paramètres prédéfinis de condition de la console de mappage DITA. Pour en savoir plus sur le paramètre prédéfini de condition, voir [Utilisation des paramètres de condition prédéfinis](generate-output-use-condition-presets.md#id1825FL004PN). |
| Générer un PDF à l’aide de | Sélectionnez DITA-OT pour générer le PDF. |
| Exécuter le processus de génération de publication | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Processus de génération de publication s’affiche, contenant tous les workflows configurés dans AEM. Vous devez sélectionner un workflow à exécuter une fois le workflow de génération de sortie terminé.<br><br>**Remarque**: pour plus d’informations sur la création d’un workflow personnalisé de génération de post-sortie, voir Personnaliser le workflow de génération post-sortie dans Installation et configuration des Guides Adobe Experience Manager as a Cloud Service. |
| Nom de la transformation | Indiquez le type de sortie à générer. Cela est nécessaire si vous souhaitez générer une sortie à l’aide de votre propre module externe personnalisé, qui est intégré au module externe DITA-OT. Par exemple, si vous souhaitez générer une sortie XHTML, spécifiez `xhtml`. Pour obtenir la liste des transformations disponibles dans DITA-OT, voir [Conversions DITA-OT (formats de sortie)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) dans le guide de l’utilisateur OASIS DITA-OT. |
| Nom du fichier | Indiquez le nom de fichier avec lequel vous souhaitez enregistrer le PDF.<br><br>Vous pouvez également utiliser des variables lors de la définition du nom de fichier du PDF. Pour plus d’informations sur l’utilisation des variables, voir [Utilisez des variables pour définir le chemin de destination, le nom du site ou le nom de fichier.](generate-output-use-variables.md#id18BUG70K05Z).<br><br>**Remarque**: si vous ne fournissez pas de nom de fichier, le titre de la carte DITA est utilisé pour générer le nom de fichier du PDF final. Si le mappage ne comporte pas de titre, le nom de fichier du mappage DITA est utilisé pour nommer le PDF final. Le nom de fichier est assaini à l’aide des règles configurées dans le système pour gérer tout caractère non valide. |
| Chemin de destination | Chemin d’accès dans votre référentiel AEM où le PDF est stocké.<br><br>Vous pouvez également utiliser des variables lors de la définition du chemin de destination. Pour plus d’informations sur l’utilisation des variables, voir [Utilisez des variables pour définir le chemin de destination, le nom du site ou le nom de fichier.](generate-output-use-variables.md#id18BUG70K05Z). |
| Téléchargement de fichiers temporaires | Sélectionnez cette option pour télécharger les fichiers temporaires générés par DITA-OT. L’emplacement où DITA-OT stocke les fichiers temporaires se trouve dans le journal de génération de sortie. Si vous rencontrez des erreurs lors de la génération de la sortie via DITA-OT, sélectionnez cette option pour conserver les fichiers temporaires. Vous pouvez ensuite utiliser ces fichiers pour résoudre les erreurs de génération de sortie.<br> <br>  Après avoir généré la sortie, sélectionnez la variable **Téléchargement de fichiers temporaires** ![icône de téléchargement de fichiers temporaires](images/download-temp-files-icon.png) pour télécharger le dossier ZIP contenant les fichiers temporaires. <br><br> **Remarque**: si vous sélectionnez certaines propriétés de fichier, puis téléchargez les fichiers temporaires, vous obtenez également la variable *metadata.xml* dans le dossier ZIP. |
| Utilisation de la ligne de base | Si vous avez créé une ligne de base pour le mappage DITA sélectionné, sélectionnez cette option pour spécifier la version que vous souhaitez publier.<br><br>Voir [Utilisation de la ligne de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) pour plus de détails. |
| Propriétés du fichier | Sélectionnez les propriétés que vous souhaitez traiter en tant que métadonnées. Ces propriétés sont définies à partir de la page Propriétés du mappage DITA ou du fichier bookmap. Les propriétés que vous sélectionnez dans la liste déroulante s’affichent sous **Propriétés du fichier** champ . Sélectionnez l’icône croisée en regard de la propriété pour la supprimer. <br><br>Remarque : vous pouvez également transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT. Pour plus d’informations, voir [Transmission des métadonnées à la sortie à l’aide de DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Rubrique parente :**[ Présentation des paramètres prédéfinis de sortie](generate-output-understand-presets.md)
