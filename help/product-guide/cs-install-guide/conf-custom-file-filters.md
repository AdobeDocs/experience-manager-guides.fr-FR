---
title: Configuration des filtres pour la boîte de dialogue de navigation dans les fichiers
description: Découvrez comment configurer des filtres pour la boîte de dialogue de navigation dans les fichiers
exl-id: 1ef2cec8-2e77-40c1-9ed2-324048bf65fb
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 0%

---

# Configuration des filtres pour la boîte de dialogue de navigation dans les fichiers {#id20CIL7009GN}

Lorsque vous travaillez dans l’éditeur Web, vous devez utiliser la boîte de dialogue de navigation des fichiers pour insérer des éléments tels qu’une image, une référence ou une référence de clé. La boîte de dialogue de navigation par défaut ne propose aucune option de filtrage de fichier. Vous pouvez ajouter vos propres filtres pour accéder facilement et rapidement aux fichiers requis.

Procédez comme suit pour ajouter vos options de filtrage de fichier personnalisées à la boîte de dialogue de navigation des fichiers :

1. Pour télécharger le fichier de configuration de l’interface utilisateur, connectez-vous à Adobe Experience Manager en tant qu’administrateur.

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et sélectionnez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils et cliquez sur le bouton **Profils de dossier**.
1. Cliquez sur la mosaïque **Profil global** .
1. Sélectionnez l’onglet **Configuration de l’éditeur XML** et cliquez sur l’icône **Modifier** en haut
1. Cliquez sur l’icône **Télécharger** pour télécharger le fichier ui\_config.json sur votre système local. Vous pouvez ensuite apporter des modifications au fichier, puis charger le même fichier.
1. Dans le fichier `ui_config.json`, ajoutez la définition des filtres que vous souhaitez ajouter.

   Le fragment de code suivant montre comment ajouter deux options de filtrage : Fichiers DITA et Fichiers image.

   ```
   "browseFilters": [
                       {
                       "title": "DITA Files",
                       "property": "jcr:content/metadata/dita_class",
                       "operation": "exists"
                       },
                       {
                       "title": "Image Files",
                       "property": "jcr:content/metadata/dc:format",
                       "value": [
                       "image/jpeg",
                       "image/gif",
                       "image/png"
                       ]
                       }
                       ]
   ```

   Dans le fragment de code ci-dessus, le premier filtre concerne les fichiers DITA. La définition de filtre utilise les paramètres suivants :

   title
:   Nom d’affichage du filtre. Ce titre apparaît comme option de filtrage dans la boîte de dialogue de navigation des fichiers.

   property
:   Propriété à faire correspondre dans les métadonnées du fichier. Par exemple, pour n’autoriser que les fichiers dont la propriété contient les métadonnées `dita_class`, le filtre de propriété prend &quot; `jcr:content/metadata/dita_class`&quot; comme valeur.

   operation
:   Spécifiez &quot; `exists`&quot; pour correspondre à l’existence de la valeur spécifiée dans le paramètre de propriété.

   Le second filtre concerne les fichiers image. Les paramètres sont similaires au premier filtre, à l’exception du paramètre `value` . Le paramètre `value` utilise un tableau de types d’image comme valeur. Tous les types de fichiers spécifiés dans le paramètre de valeur sont recherchés et affichés dans la boîte de dialogue de navigation des fichiers ; tous les autres types de fichiers sont ignorés.

1. Enregistrez le fichier *ui\_config.json* et téléchargez-le. Ensuite, rechargez l’éditeur Web.

   Lorsque vous lancez la boîte de dialogue de navigation des fichiers, les options de filtrage configurées dans le fichier ui\_config.json s’affichent.

   ![](assets/file-browse-custom-filters.png)


**Rubrique parente :**&#x200B;[ Personnaliser l’éditeur web](conf-web-editor.md)
