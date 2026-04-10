---
title: Configuration des filtres de texte
description: Découvrez comment configurer des filtres de texte
exl-id: 0963606c-010e-4a72-b7bf-850b86b34a84
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 0%

---

# Configuration des filtres de texte {#id21BPD0FK0XA}

AEM Guides permet de rechercher du texte dans les fichiers présents sur le chemin d’accès sélectionné du référentiel AEM. Vous pouvez utiliser la recherche par filtre pour rechercher des fichiers dans le panneau du référentiel ou pour parcourir les fichiers. Lorsque vous travaillez dans l’éditeur web, vous devez utiliser la boîte de dialogue de navigation du fichier pour insérer des éléments tels qu’une image, une référence ou une référence de clé.

Par défaut, vous pouvez utiliser certains filtres améliorés pour rechercher les fichiers dans le référentiel AEM. Vous pouvez filtrer tous les fichiers DITA ou les fichiers non DITA présents sur le chemin d&#39;accès sélectionné. Vous pouvez également rechercher des valeurs spécifiques dans les attributs des éléments DITA. Vous pouvez également rechercher les fichiers qui sont extraits par l’utilisateur spécifié.

>[!NOTE]
>
> Vous pouvez également configurer le profil global et ajouter d’autres filtres pour la recherche.

Pour configurer les filtres de texte, procédez comme suit :

1. Connectez-vous à Adobe Experience Manager en tant qu’administrateur.
1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.
1. Sélectionnez **Guides** dans la liste des outils, puis cliquez sur le **Profils de dossier**.
1. Cliquez sur la mosaïque **Profil global**.
1. Cliquez sur **Configuration de l’éditeur XML**.
1. Cliquez sur l’icône **Modifier** dans la partie supérieure.
1. Cliquez sur l’icône **Télécharger** pour télécharger le fichier ui\_config.json sur votre système local. Vous pouvez ensuite apporter des modifications au fichier , puis le charger.
   1. Configurez les filtres dans le fichier . Vous pouvez également ajouter des filtres personnalisés comme illustré dans l’exemple ci-dessous :

      Le fragment de code suivant montre comment ajouter des options de filtrage : Fichiers DITA, Non-DITA, Éléments DITA et Extraits par fichiers. Il contient également un filtre personnalisé - Balises.

      ```
       "operation":"like"
                                      },
                                      {
                                      "title":"Checked out by",
                                      "property":"jcr:content/cq:drivelock",
                                      "operation":"like",
                                      "itemConfig":{
                                      "component":"textfield",
                                      "placeholder":"Checked out by"
                                      },
                                      "children":[
                                      {
                                      "title":"Check out"
                                      }
                                      ]
                                      },
                                      {
                                      "title":"Tags",
                                      "property":"jcr:content/metadata/cq:tags",
                                      "itemConfig":{
                                      "component":"textfield",
                                      "placeholder":"Enter Tag"
                                      },
                                      "children":[
                                      {
                                      "title":"Tags"
                                      }
                                      ]
                                      }
                                      ]
      ```

      Dans le fragment de code ci-dessus, le premier filtre concerne les fichiers DITA. La définition du filtre utilise les paramètres suivants :

      ****Titre**** : nom d’affichage du filtre. Ce titre apparaît comme option de filtrage dans la boîte de dialogue de navigation des fichiers.

      ****Property**** : propriété à faire correspondre dans les métadonnées du fichier. Par exemple, pour autoriser uniquement les fichiers dont la propriété contient les métadonnées dita\_class, le filtre de propriété prend la valeur « jcr:content/metadata/dita\_class ».

      ****Opération **:**spécifiez « exists » pour correspondre à l’existence de la valeur spécifiée dans le paramètre de propriété

1. Chargez le fichier ui\_config.json mis à jour contenant les filtres ajoutés.

Les filtres configurés sont disponibles dans le panneau Filtres .

**Rubrique parente :**[ Personnaliser l’éditeur web](conf-web-editor.md)
