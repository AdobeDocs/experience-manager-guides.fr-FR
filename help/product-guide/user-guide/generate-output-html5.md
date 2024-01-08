---
title: Utilisation de HTML5
description: Découvrez comment créer un paramètre prédéfini HTML5 à partir de l’éditeur web et du tableau de bord de mappage. Configurez le paramètre prédéfini de sortie HTML5 dans AEM Guides.
exl-id: b54bf3a0-7a13-41a0-ae72-cdf2caf8d974
source-git-commit: b8c90eb8d1acfe6777a615bd71367027cd8d1c3b
workflow-type: tm+mt
source-wordcount: '1142'
ht-degree: 1%

---

# HTML5 {#id205BE700XO1}

La sortie HTML5 est générée dans une hiérarchie de dossiers plate. Cela signifie que la structure de dossiers utilisée par le contenu dans le référentiel n’est pas répliquée dans la sortie HTML5. L’ensemble du contenu est publié au format de sortie HTML5 et enregistré dans un seul dossier. Les noms de fichier sont également remplacés par les UUID des fichiers dans la sortie générée. Le seul fichier qui ne comporte pas de nom basé sur l’UUID est le fichier index.html.

Vous pouvez créer le paramètre prédéfini de HTML de deux manières :

**Dans l’éditeur Web :** Dans le panneau Référentiel, ouvrez le fichier de mappage DITA en mode Carte, puis, dans l’onglet Sortie, sélectionnez l’icône + pour créer un paramètre prédéfini de sortie, puis sélectionnez HTML5 dans la liste déroulante de type de la boîte de dialogue Ajouter un paramètre prédéfini .

>[!NOTE]
>
> Vous pouvez choisir la méthode pour générer HTML5 à l’aide de DITA-OT ou FMPS \(si votre administrateur système l’a configuré\).

Dans l&#39;éditeur Web, les paramétrages ont été organisés sous les onglets Général et Avancé :

**Général**

La variable **Général** contient les configurations suivantes :

- Chemin d’accès de sortie
- Arguments de ligne de commande DITA-OT
- Nom du fichier
- Appliquer les conditions à l’aide de \(si les conditions sont définies pour une carte\)
- Utiliser la ligne de base \(si une ligne de base est créée pour une carte\)
- Processus de génération de publication

**Avancé**

L&#39;onglet Avancé contient les paramétrages suivants :

- Nom de la transformation
- Nettoyer les fichiers temporaires DITA-OT
- Propriétés

Pour plus d’informations, voir [Configuration de HTML5](#id231KJA00REJ).

**Depuis le tableau de bord de la carte**

Pour ouvrir les paramètres prédéfinis de sortie pour PDF, cliquez sur un fichier de mappage DITA dans l’interface utilisateur d’Assets, puis cliquez sur Paramètres prédéfinis de sortie, puis sur l’option HTML5. Dans le tableau de bord de la carte, cliquez sur **Modifier** dans la partie supérieure pour mettre à jour les différentes configurations, puis cliquez sur **Enregistrer**.

**Configuration de HTML5**

Les options suivantes sont disponibles pour la sortie HTML5 :

| Options HTML5 | Description |
| --- | --- |
| Type de sortie | Type de sortie à générer. Pour générer la sortie HTML5, choisissez l&#39;option HTML5. |
| Nom du paramètre | Donnez un nom explicite aux paramètres de sortie HTML5 que vous créez. Par exemple, vous pouvez spécifier _Sortie de clients internes_ ou _sortie utilisateurs finaux_. |
| Arguments de ligne de commande DITA-OT | Spécifiez les arguments supplémentaires que vous souhaitez que DITA-OT traite lors de la génération de la sortie. Pour plus d’informations sur les arguments de ligne de commande pris en charge dans DITA-OT, voir [Documentation DITA-OT](https://www.dita-ot.org/). |
| Générer une réponse à l’aide de | Sélectionnez DITA-OT pour générer la sortie HTML5. |
| Appliquer les conditions à l’aide de | Sélectionnez l’une des options suivantes :<br><br>* **Aucun appliqué**: sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.<br>* **Fichier DITAVal**: sélectionnez le ou les fichiers DITAVal pour générer du contenu personnalisé. Vous pouvez sélectionner plusieurs fichiers DITAVal à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier. Pour le supprimer, utilisez l’icône croisée située à proximité du nom du fichier. Les fichiers DITAVal sont évalués dans l’ordre spécifié. Par conséquent, les conditions spécifiées dans le premier fichier sont prioritaires sur les conditions correspondantes spécifiées dans les fichiers ultérieurs. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers. Si le fichier DITAVal est déplacé vers un autre emplacement ou supprimé, il n’est pas automatiquement supprimé du tableau de bord de la carte. Vous devez mettre à jour l’emplacement au cas où des fichiers seraient déplacés ou supprimés. Vous pouvez placer le pointeur de la souris sur le nom du fichier pour afficher le chemin d’accès dans le référentiel AEM où le fichier est stocké. Vous ne pouvez sélectionner que les fichiers DITAVal et une erreur s’affiche si vous avez sélectionné un autre type de fichier. FrameMaker Publishing Server ne prend pas en charge plusieurs fichiers DITAVAL.<br>* **Paramètre prédéfini de condition**: sélectionnez un paramètre prédéfini de condition dans la liste déroulante pour appliquer une condition lors de la publication de la sortie. L’option est visible si vous avez ajouté une condition présente dans l’onglet Paramètres prédéfinis de condition de la console de mappage DITA. Pour en savoir plus sur le paramètre prédéfini de condition, voir [Utilisation des paramètres de condition prédéfinis](generate-output-use-condition-presets.md#id1825FL004PN).<br><br>Vous pouvez sélectionner plusieurs fichiers DITAVAL à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier. Pour le supprimer, utilisez l’icône croisée située à proximité du nom du fichier. Les fichiers DITAVAL sont évalués dans l’ordre spécifié. Par conséquent, les conditions spécifiées dans le premier fichier sont prioritaires sur les conditions correspondantes spécifiées dans les fichiers ultérieurs. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers. Vous devez mettre à jour l’emplacement au cas où des fichiers seraient déplacés ou supprimés. Vous pouvez placer le pointeur de la souris sur le nom du fichier pour afficher le chemin d’accès dans le référentiel AEM où le fichier est stocké. Vous ne pouvez enregistrer que les fichiers DITAVAL. Une erreur s’affiche si vous avez sélectionné un autre fichier.<br><br>**Remarque**: le FrameMaker Publishing Server ne prend pas en charge plusieurs fichiers DITAVAL. |
| Nom de la transformation | Indiquez le type de sortie à générer. Cela est nécessaire si vous souhaitez générer une sortie à l’aide de votre propre module externe personnalisé, qui est intégré au module externe DITA-OT. Par exemple, si vous souhaitez générer une sortie XHTML, spécifiez `xhtml`. Pour obtenir la liste des transformations disponibles dans DITA-OT, voir [Conversions DITA-OT (formats de sortie)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) dans le guide de l’utilisateur OASIS DITA-OT. |
| Nom du fichier | Indiquez le nom de fichier avec lequel vous souhaitez enregistrer la sortie HTML5.<br><br>**Remarque**: si vous ne fournissez pas de nom de fichier, le titre de la carte DITA est utilisé pour générer le nom de fichier de sortie HTML5 final. Si le mappage ne comporte pas de titre, le nom de fichier du mappage DITA est utilisé pour nommer la sortie HTML5 finale. Le nom de fichier est assaini à l’aide des règles configurées dans le système pour gérer tout caractère non valide. |
| Exécuter le processus de génération de publication | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Processus de génération de publication s’affiche, contenant tous les workflows configurés dans AEM. Vous devez sélectionner un workflow à exécuter une fois le workflow de génération de sortie terminé.<br><br>**Remarque**:Pour plus d’informations sur la création d’un workflow de génération de post-sortie personnalisé, voir _Personnaliser le workflow de génération après la sortie_ dans Installation et configuration de Adobe Experience Manager Guides as a Cloud Service. |
| Chemin de destination | Chemin d’accès dans votre référentiel AEM où est stockée la sortie HTML5. |
| Nettoyer les fichiers temporaires DITA-OT | Sélectionnez cette option pour nettoyer les fichiers temporaires générés par DITA-OT. L’emplacement où DITA-OT stocke les fichiers temporaires se trouve dans le journal de génération de sortie.<br><br>Si vous rencontrez des erreurs lors de la génération de la sortie via DITA-OT, vous pouvez désélectionner cette option pour conserver les fichiers temporaires. Vous pouvez ensuite utiliser ces fichiers pour résoudre les erreurs de génération de sortie. |
| Utilisation de la ligne de base | Si vous avez créé une ligne de base pour le mappage DITA sélectionné, sélectionnez cette option pour spécifier la version que vous souhaitez publier.<br><br>Voir [Utilisation de la ligne de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) pour plus de détails. |
| Propriétés | Sélectionnez les propriétés que vous souhaitez traiter en tant que métadonnées. Ces propriétés sont définies à partir de la page Propriétés du mappage DITA ou du fichier bookmap. Les propriétés que vous sélectionnez dans la liste déroulante s’affichent sous **Propriétés** champ . Sélectionnez l’icône croisée en regard de la propriété pour la supprimer. <br><br>**Remarque**: vous pouvez également transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT. Pour plus d’informations, voir [Transmission des métadonnées à la sortie à l’aide de DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Rubrique parente :**[ Présentation des paramètres prédéfinis de sortie](generate-output-understand-presets.md)
