---
title: Suggestions intelligentes optimisées par l’IA pour créer du contenu
description: Découvrez comment afficher et utiliser les suggestions intelligentes optimisées par l’IA dans l’éditeur web.
exl-id: 23c5285e-0d4f-484a-a062-fe1ba1608b8d
source-git-commit: 75425d82ee55485503ea6678030c5e919e50a691
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 0%

---

# Suggestions intelligentes optimisées par l’IA pour créer du contenu

Experience Manager Guides fournit la fonctionnalité **Suggestions intelligentes** qui vous permet de créer du contenu cohérent et précis.

Lorsque vous créez du contenu, la fonction **Suggestions intelligentes** peut effectuer des recherches à l’aide de l’IA et afficher le contenu existant sémantiquement similaire à votre contenu. Vous pouvez ensuite choisir comme référence le meilleur contenu correspondant que vous souhaitez inclure dans votre rubrique actuelle.

Vous pouvez ainsi réutiliser du contenu existant de votre référentiel de documentation et créer un contenu cohérent. Par exemple, vous créez un document contenant des informations sur **Adobe Firefly**, y compris un paragraphe sur **Adobe**. Dans ce cas, vous pouvez rapidement afficher et ajouter la référence de contenu d’une autre rubrique, telle que **Adobe Photoshop**, qui inclut le même paragraphe.





Lorsque vous ouvrez une rubrique dans l’éditeur Web, le panneau **Suggestions intelligentes** s’affiche à droite.

>[!NOTE]
>
> Votre administrateur doit configurer la fonction **Suggestions intelligentes**. Pour plus d’informations, consultez la section [Configuration des suggestions intelligentes optimisées par l’IA pour la création](../cs-install-guide/conf-smart-suggestions.md) du Guide d’installation et de configuration pour les Cloud Service.

![Panneau de suggestions dynamiques](images/smart-suggestions-panel.png){width="300" align="left"}

*Affichez le panneau **Suggestions intelligentes**.*

Effectuez les étapes suivantes pour afficher les suggestions intelligentes pour ajouter des références de contenu appropriées à votre rubrique :

1. Sélectionnez **Suggestions intelligentes** ![ icône de suggestions intelligentes](images/smart-suggestions-icon.svg) pour ouvrir le panneau.



   >[!NOTE]
   >
   > Dans les [ profils globaux ou de niveau dossier ](../cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions), votre administrateur doit définir les fichiers ou les dossiers à indexer pour les suggestions intelligentes, le nombre minimum de caractères à saisir pour afficher les suggestions et le nombre maximum de suggestions que vous pouvez afficher dans la liste.

1. Saisissez dans le contenu de votre rubrique pour afficher les suggestions associées. Assurez-vous que la longueur du caractère du contenu dépasse ce que votre administrateur a défini dans le profil de dossier pour que les suggestions de contenu apparaissent.

1. Sélectionnez **Suggestions pour la balise actuelle** ![Icône de balise active de suggestions dynamiques](images/smart-suggestions-current-tag-icon.svg) pour afficher les suggestions de création pour la balise actuelle où vous placez le pointeur de la souris.  Les suggestions pour afficher et ajouter des références de contenu à partir des fichiers indexés s’affichent en fonction du contenu de la balise active.

   Raccourci clavier : **Windows** (*Ctrl* + *K*), **macOS** (*Commande* + *K*)
1. Sélectionnez **Suggestions pour le document complet** ![Icône de document complet de suggestions dynamiques](images/smart-suggestions-complete-document-icon.svg) pour afficher les suggestions en fonction du contenu présent dans le document complet.  L’icône de suggestions intelligentes ![icône de suggestions intelligentes](images/smart-suggestions-complete-document-icon.svg) s’affiche en regard du contenu où une correspondance appropriée est trouvée.

   Raccourci clavier : **Windows** ( *Ctrl* + *Maj* + *K* ), **macOS** (*Commande* + *Maj* + *K* )

   >[!NOTE]
   >
   > Vous pouvez uniquement afficher les suggestions pour la fenêtre d’affichage actuelle (le contenu visible à l’écran). Pour afficher des suggestions pour tout autre contenu du document, faites défiler le document vers le haut ou vers le bas pour l’afficher dans la fenêtre d’affichage, puis sélectionnez l’icône ![Icône de suggestions intelligentes](images/smart-suggestions-complete-document-icon.svg) .

1. Sélectionnez l’icône **Suggestions intelligentes** ![ ](images/smart-suggestions-complete-document-icon.svg) près des balises que vous avez ajoutées à votre document pour afficher les suggestions intelligentes.
1. Vous pouvez afficher les suggestions intelligentes dans la zone de suggestions **Réutilisation de contenu** .  Experience Manager Guides fournit des suggestions pour faire correspondre exactement le contenu et le contenu avec la même signification. Par exemple, vous pouvez rechercher la rubrique qui contient le numéro exact de la version, telle que &quot;version 2023.03.12&quot;. Vous pouvez également rechercher &quot;Adobe a son siège à San Jose, en Californie&quot; et trouver des contenus similaires comme &quot;San Jose a les quartiers de nombreuses sociétés de logiciels comme Adobe&quot;.
1. Sélectionnez **Content Information** ![Content Information](images/smart-suggestions-content-info-icon.svg) pour afficher les détails.
   ![Panneau d’informations sur le contenu](images/smart-suggestions-content-information.png){width="300" align="left"}

   *Affichez les informations détaillées sur la référence de contenu.*

   1. Le titre de la rubrique qui contient la référence au contenu s’affiche sous la forme d’un lien hypertexte.
   1. Chemin d’accès du fichier contenant la référence de contenu.
   1. Type de référence à l’emplacement où le contenu est référencé.
   1. Les noms des fichiers DITA auxquels la rubrique est référencée s’affichent sous la forme de liens hypertexte.
1. Sélectionnez **Aperçu de contenu suggéré** ![Icône d’aperçu de suggestions intelligentes](images/smart-suggestions-preview-icon.svg) pour comparer le contenu actuel au contenu suggéré. Vous pouvez ainsi comparer les différences et déterminer si vous souhaitez ajouter la référence de contenu pour le contenu suggéré et la rendre cohérente ou conserver votre contenu actuel.

   ![Aperçu du contenu suggéré](images/smart-suggestions-suggested-content-preview.png){width="800" align="left"}

   *Prévisualisez la comparaison entre le contenu actuel et le contenu suggéré.*

1. Cliquez sur **Accepter** pour ajouter la référence de contenu suggérée dans la boîte de dialogue **Aperçu de contenu suggéré**.
1. Vous pouvez également sélectionner **Accepter** ou **Refuser** dans la zone de suggestions **Réutilisation de contenu** pour les recommandations appropriées.


Cette fonctionnalité intelligente est pratique et minimise les efforts de recherche manuelle de contenu, ce qui vous permet de vous concentrer davantage sur la génération de nouveau contenu. Il facilite également la collaboration entre les équipes et contribue à maintenir la cohérence du contenu créé par les différents auteurs.

>[!NOTE]
>
>Les suggestions intelligentes ne conservent pas vos données au-delà de la session en cours. Pour les réponses, les suggestions intelligentes dépendent uniquement de l’index créé sur le contenu résidant dans votre base de données interne. Les outils d’IA externe ne sont pas utilisés, ce qui garantit que vos données restent dans le système.
