---
title: Configuration des filtres de texte
description: Découvrez comment configurer des filtres de texte
exl-id: 180e4ab5-5259-4a00-ac3c-bb1d6814ce0d
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 0%

---

# Configuration des filtres de texte {#id21BPD0FK0XA}

AEM Guides permet de rechercher du texte dans les fichiers présents sur le chemin d’accès sélectionné du référentiel AEM. Vous pouvez utiliser la recherche de filtre pour rechercher des fichiers à partir du panneau du référentiel ou pour parcourir les fichiers. Lorsque vous travaillez dans l’éditeur Web, vous devez utiliser la boîte de dialogue de navigation des fichiers pour insérer des éléments tels qu’une image, une référence ou une référence de clé.

Par défaut, vous pouvez utiliser des filtres améliorés pour rechercher les fichiers dans le référentiel AEM. Vous pouvez filtrer tous les fichiers DITA ou non présents sur le chemin d’accès sélectionné. Vous pouvez également rechercher des valeurs spécifiques dans les attributs des éléments DITA. Vous pouvez également rechercher les fichiers extraits par l’utilisateur spécifié.

>[!NOTE]
>
> Vous pouvez également configurer le profil global et ajouter d’autres filtres pour la recherche.

Effectuez les étapes suivantes pour configurer les filtres de texte :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.
1. Cliquez sur le lien **Adobe Experience Manager** dans la partie supérieure et sélectionnez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils et cliquez sur le bouton **Profils de dossier**.
1. Cliquez sur la mosaïque **Profil global** .
1. Cliquez sur **Configuration de l’éditeur XML**.
1. Cliquez sur l’icône **Modifier** en haut de l’écran.
1. Téléchargez le fichier ui\_config.json.
1. Configurez les filtres dans le fichier . Vous pouvez également ajouter des filtres personnalisés comme illustré dans l’exemple ci-dessous :

   Le fragment de code suivant montre comment ajouter des options de filtrage Fichiers DITA, Non DITA, Éléments DITA et Extraits par fichiers. Il contient également un filtre personnalisé -Balises.

   ```json
   [
     {
       "title": "DITA files",
       "property": "jcr:content/metadata/dita_class",
       "operation": "like",
       "children": [
         {
           "title": "DITA Topics",
           "value": "- topic/topic",
           "checked": true
         },
         {
           "title": "DITA Maps",
           "value": "- map/map",
           "checked": true
         }
       ]
     },
     {
       "title": "DITA elements",
       "property": "jcr:content/ditameta",
       "widgetId": "dita_filter",
       "operation": "like"
     },
     {
       "title": "Checked out by",
       "property": "jcr:content/cq:drivelock",
       "operation": "like",
       "itemConfig": {
         "component": "textfield",
         "placeholder": "Checked out by"
       },
       "children": [
         {
           "title": "Check out"
         }
       ]
     },
     {
       "title": "Tags",
       "property": "jcr:content/metadata/cq:tags",
       "itemConfig": {
         "component": "textfield",
         "placeholder": "Enter Tag"
       },
       "children": [
         {
           "title": "Tags"
         }
       ]
     }
   ]
   ```

   Dans le fragment de code ci-dessus, le premier filtre concerne les fichiers DITA. La définition de filtre utilise les paramètres suivants :

   - **Titre :** nom d’affichage du filtre. Ce titre apparaît comme option de filtrage dans la boîte de dialogue de navigation des fichiers.

   - **Propriété :** Propriété à faire correspondre dans les métadonnées du fichier. Par exemple, pour n’autoriser que les fichiers dont la propriété contient des métadonnées de classe dita\, le filtre de propriété prend comme valeur &quot;jcr:content/metadata/dita\_class&quot;.

   - **Operation** Spécifiez &quot;exists&quot; pour correspondre à l’existence de la valeur spécifiée dans le paramètre de propriété.

1. Téléchargez le fichier ui\_config.json mis à jour qui contient les filtres ajoutés.

Les filtres configurés sont disponibles dans le panneau Filtres .

**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
