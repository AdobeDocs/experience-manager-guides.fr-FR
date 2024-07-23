---
title: EPUB prédéfini
description: Découvrez comment créer un paramètre prédéfini d’EPUB à partir du tableau de bord de mappage. Configurez le paramètre prédéfini de sortie EPUB dans AEM Guides.
feature: Publishing
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 1%

---

# EPUB {#id205BED020YT}

Vous pouvez créer le paramètre prédéfini d’EPUB à partir du tableau de bord de carte.

>[!NOTE]
>
> Vous pouvez choisir la méthode pour générer HTML5 à l’aide de DITA-OT ou FMPS \(si votre administrateur système l’a configuré\).

Pour ouvrir les paramètres prédéfinis de sortie pour l’EPUB, cliquez sur un fichier de mappage DITA, puis sur Paramètres prédéfinis de sortie, puis cliquez sur l’option EPUB. Les options suivantes sont disponibles pour EPUB Output :

| Options de l’EPUB | Description |
| --- | --- |
| Type de sortie | Type de sortie à générer. Pour générer la sortie de l’EPUB, sélectionnez l’option EPUB. |
| Nom du paramètre | Donnez un nom explicite aux paramètres de sortie de l’EPUB que vous créez. Par exemple, vous pouvez spécifier _Sortie de clients internes_ ou _Sortie d’utilisateurs finaux_. |
| Arguments de ligne de commande DITA-OT | Spécifiez les arguments supplémentaires que vous souhaitez que DITA-OT traite lors de la génération de la sortie. Pour plus d’informations sur les arguments de ligne de commande pris en charge dans DITA-OT, consultez la [documentation DITA-OT](https://www.dita-ot.org/). |
| Générer un EPUB à l’aide de | Sélectionnez DITA-OT pour générer la sortie EPUB. |
| Appliquer les conditions à l’aide de | Sélectionnez l’une des options suivantes :<br><br>* **Aucun appliqué** : sélectionnez cette option si vous ne souhaitez appliquer aucune condition sur la sortie publiée.<br>* **Fichier DITAVal** : sélectionnez le ou les fichiers DITAVal pour générer du contenu personnalisé. Vous pouvez sélectionner plusieurs fichiers DITAVal à l’aide de la boîte de dialogue de navigation ou en saisissant le chemin du fichier. Pour le supprimer, utilisez l’icône croisée située à proximité du nom du fichier. Les fichiers DITAVal sont évalués dans l’ordre spécifié. Par conséquent, les conditions spécifiées dans le premier fichier sont prioritaires sur les conditions correspondantes spécifiées dans les fichiers ultérieurs. Vous pouvez conserver l’ordre des fichiers en ajoutant ou en supprimant des fichiers. Si le fichier DITAVal est déplacé vers un autre emplacement ou supprimé, il n’est pas automatiquement supprimé du tableau de bord de la carte. Vous devez mettre à jour l’emplacement au cas où des fichiers seraient déplacés ou supprimés. Vous pouvez placer le pointeur de la souris sur le nom du fichier pour afficher le chemin d’accès dans le référentiel AEM où le fichier est stocké. Vous ne pouvez sélectionner que les fichiers DITAVal et une erreur s’affiche si vous avez sélectionné un autre type de fichier. FrameMaker Publishing Server ne prend pas en charge plusieurs fichiers DITAVAL.<br>* **Paramètre prédéfini de condition** : sélectionnez un paramètre prédéfini de condition dans la liste déroulante pour appliquer une condition lors de la publication de la sortie. L’option est visible si vous avez ajouté une condition présente dans l’onglet Paramètres prédéfinis de condition de la console de mappage DITA. Pour en savoir plus sur les paramètres prédéfinis de condition, voir [Utilisation des paramètres prédéfinis de condition](generate-output-use-condition-presets.md#id1825FL004PN). |
| Chemin de destination | Chemin d’accès dans votre référentiel AEM où est stockée la sortie de l’EPUB. |
| Nom du fichier | Indiquez le nom de fichier avec lequel vous souhaitez enregistrer la sortie de l’EPUB.<br><br>**Remarque** : si vous ne fournissez pas de nom de fichier, le titre de la carte DITA est utilisé pour générer le nom de fichier de sortie EPUB final. Si la carte ne comporte pas de titre, le nom de fichier de la carte DITA est utilisé pour nommer la sortie finale de l’EPUB. Le nom de fichier est assaini à l’aide des règles configurées dans le système pour gérer tout caractère non valide. |
| Nom de la transformation | Indiquez le type de sortie à générer. Cela est nécessaire si vous souhaitez générer une sortie à l’aide de votre propre module externe personnalisé, qui est intégré au module externe DITA-OT. Par exemple, si vous souhaitez générer une sortie XHTML, spécifiez `xhtml`. Pour obtenir la liste des transformations disponibles dans DITA-OT, voir [Conversions DITA-OT (formats de sortie)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.md) dans le Guide de l’utilisateur OASIS DITA-OT. |
| Nettoyer les fichiers temporaires DITA-OT | Sélectionnez cette option pour nettoyer les fichiers temporaires générés par DITA-OT. L’emplacement où DITA-OT stocke les fichiers temporaires se trouve dans le journal de génération de sortie.<br><br>Si vous rencontrez des erreurs lors de la génération de la sortie via DITA-OT, vous pouvez désélectionner cette option pour conserver les fichiers temporaires. Vous pouvez ensuite utiliser ces fichiers pour résoudre les erreurs de génération de sortie. |
| Exécuter le processus de génération de publication | Lorsque vous sélectionnez cette option, une nouvelle liste déroulante Processus de génération de publication s’affiche, contenant tous les workflows configurés dans AEM. Vous devez sélectionner un workflow à exécuter une fois le workflow de génération de sortie terminé.<br><br>**Remarque** : Pour plus d’informations sur la création d’un workflow de génération post-sortie personnalisé, voir _Personnaliser le workflow de génération post-sortie_ dans Installer et configurer Adobe Experience Manager Guides as a Cloud Service. |
| Utilisation de la ligne de base | Si vous avez créé une ligne de base pour le mappage DITA sélectionné, sélectionnez cette option pour spécifier la version que vous souhaitez publier.<br><br>Voir [Utilisation de la ligne de base](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) pour plus de détails. |
| Propriétés | Sélectionnez les propriétés que vous souhaitez traiter en tant que métadonnées. Ces propriétés sont définies à partir de la page Propriétés du mappage DITA ou du fichier bookmap. Les propriétés que vous sélectionnez dans la liste déroulante sont répertoriées sous le champ Propriétés et sont supprimées de la liste déroulante. Une fois définies, ces propriétés sont également copiées dans les rubriques de la carte.<br><br>**Remarque** : vous pouvez également transmettre les métadonnées à la sortie à l’aide de la publication DITA-OT. Pour plus d’informations, voir [Transmission des métadonnées à la sortie à l’aide de DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Rubrique parente :**[ Comprendre les paramètres prédéfinis de sortie](generate-output-understand-presets.md)
