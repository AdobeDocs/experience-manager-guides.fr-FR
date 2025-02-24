---
title: Personnaliser l’éditeur web
description: Découvrez comment personnaliser l’affichage des tableaux collés dans l’éditeur
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: d03ac6ba3ec8e5c52c31a3239e2043bbae79622e
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Configuration de l’affichage des tableaux collés

À l’aide de la barre d’outils secondaire de l’éditeur, vous pouvez insérer un tableau simple à l’emplacement valide actuel ou suivant d’une rubrique. Vous pouvez également copier un tableau à partir de Microsoft Word ou Excel et le coller directement dans un fichier de rubrique.

Les administrateurs peuvent configurer l’affichage des tableaux copiés. Par défaut, ces tableaux copiés sont affichés comme `simpletable` dans l’éditeur. Cependant, vous pouvez modifier ce paramètre pour afficher les tableaux copiés comme `tgroup` en mettant à jour le paramètre Configuration de l’éditeur XML.

>[!NOTE]
>
> Si vous copiez un tableau avec des lignes ou des colonnes fusionnées, le tableau est collé en tant que `trgoup` de tableau normal et non `simpletable`, quel que soit le paramètre du tableau configuré dans la configuration de l’éditeur XML.

Pour mettre à jour le format de tableau par défaut, procédez comme suit :

1. Ouvrez la page Navigations de Adobe Experience Manager et sélectionnez **Outils** à gauche.
2. Dans le panneau Outils, sélectionnez **Guides** dans la liste des outils.
3. Sélectionnez **Profils de dossier**, puis sélectionnez le profil dans lequel vous souhaitez mettre à jour le paramètre du tableau.
4. Accédez à l’onglet **Configuration de l’éditeur XML**.
5. Sélectionnez l’icône **Modifier** en haut.
6. Sélectionnez l’icône **Télécharger** pour télécharger le fichier `ui_config.json` sur votre système local.
7. Dans le fichier `ui_config.json`, mettez à jour le paramètre `simpletable` comme illustré ci-dessous :

   ```
   "htmlToDitaMapping":{ "table": {
   "name" : "tgroup",
   "wrapTag" : {
       "dita" : "table",
       "html" : "div"
   }
   } },
   ```


Une fois la mise à jour effectuée, enregistrez le fichier et chargez-le.

