---
title: Configuration des filtres pour la boîte de dialogue de navigation dans les fichiers
description: Découvrez comment configurer des filtres pour la boîte de dialogue de navigation dans les fichiers
exl-id: 1ef09820-3b18-4762-b177-4d40926e21f0
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---

# Configuration des filtres pour la boîte de dialogue de navigation dans les fichiers {#id20CIL7009GN}

Lorsque vous travaillez dans l’éditeur Web, vous devez utiliser la boîte de dialogue de navigation des fichiers pour insérer des éléments tels qu’une image, une référence ou une référence de clé. La boîte de dialogue de navigation par défaut ne propose aucune option de filtrage de fichier. Vous pouvez ajouter vos propres filtres pour accéder facilement et rapidement aux fichiers requis.

Procédez comme suit pour ajouter vos options de filtrage de fichier personnalisées à la boîte de dialogue de navigation des fichiers :

1. Connectez-vous à AEM et ouvrez le mode CRXDE Lite.

1. Accédez au fichier de configuration par défaut disponible à l’emplacement suivant :

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Créez une copie du fichier de configuration par défaut à l’emplacement suivant :

   `/apps/fmdita/xmleditor/ui_config.json`

1. Accédez à et ouvrez le `ui_config.json` dans le fichier `apps` pour la modification.

1. Dans le `ui_config.json` ajoutez la définition des filtres que vous souhaitez ajouter.

   Le fragment de code suivant montre comment ajouter deux options de filtrage : Fichiers DITA et Fichiers image.

   ```json
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

   - **title:**   Nom d’affichage du filtre. Ce titre apparaît comme option de filtrage dans la boîte de dialogue de navigation des fichiers.

   - **property:**   Propriété à faire correspondre dans les métadonnées du fichier. Par exemple, pour n’autoriser que les fichiers qui ont la variable `dita_class` métadonnées dans leur propriété, le filtre de propriété utilise &quot;`jcr:content/metadata/dita_class`&quot; comme valeur.

   - **operation :**   Spécifiez &quot;`exists`&quot; pour correspondre à l’existence de la valeur spécifiée dans le paramètre de propriété.

   Le second filtre concerne les fichiers image. Les paramètres sont similaires au premier filtre, à l’exception du filtre `value` . La variable `value` prend comme valeur un tableau de types d’image. Tous les types de fichiers spécifiés dans le paramètre de valeur sont recherchés et affichés dans la boîte de dialogue de navigation des fichiers ; tous les autres types de fichiers sont ignorés.

1. Enregistrez le *ui\_config.json* et rechargez l’éditeur Web.

   Lorsque vous lancez la boîte de dialogue de navigation des fichiers, les options de filtrage configurées dans le fichier ui\_config.json s’affichent.

   ![](assets/file-browse-custom-filters.png){width="300" align="left"}
