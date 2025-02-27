---
title: Suggestions intelligentes optimisées par l’IA pour créer du contenu
description: Découvrez comment afficher et utiliser des suggestions intelligentes optimisées par l’IA dans l’éditeur web.
hide: true
exl-id: 30c85d46-61ba-486c-979c-1a2ed95f5a32
source-git-commit: 7286c3fb36695caa08157296fd6e0de722078c2b
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 0%

---

# Suggestions intelligentes optimisées par l’IA pour créer du contenu

Experience Manager Guides fournit des suggestions intelligentes qui vous aident à créer un contenu cohérent et précis.

Lorsque vous créez du contenu, la fonction **Suggérer du contenu réutilisable** de l’outil Assistant AI peut effectuer une recherche à l’aide de l’IA et afficher le contenu existant qui est sémantiquement similaire à votre contenu. Vous pouvez ensuite choisir le meilleur contenu correspondant que vous souhaitez inclure dans votre rubrique actuelle comme référence.

Cela vous permet de réutiliser du contenu existant de votre référentiel de documentation et de créer du contenu cohérent. Par exemple, vous créez un document contenant des informations sur **Adobe Firefly**, y compris un paragraphe sur **Adobe**. Dans ce cas, vous pouvez rapidement afficher et ajouter la référence au contenu d’une autre rubrique, comme **Adobe Photoshop**, qui inclut le même paragraphe.
>[!NOTE]
>
> Dans les [profils globaux ou de niveau dossier](/help/product-guide/cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions), votre administrateur doit définir les fichiers ou dossiers à indexer pour les suggestions intelligentes, le nombre minimum de caractères à saisir pour afficher les suggestions et le nombre maximum de suggestions que vous pouvez afficher dans la liste.

Pour afficher les suggestions intelligentes permettant d’ajouter des références de contenu appropriées à votre rubrique, procédez comme suit :


1. Sélectionnez le contenu de la rubrique pour afficher les suggestions associées. Assurez-vous que la longueur de caractères du contenu dépasse ce que votre administrateur a défini dans le profil de dossier pour que les suggestions de contenu s’affichent.
1. Dans le panneau de l’assistant d’IA, sélectionnez **Suggérer du contenu réutilisable** ![ai suggérer l’icône de contenu réutilisable ](./images/ai-suggest-reusable-content-icon.svg).

1. Sélectionnez une balise pour afficher les suggestions de création pour la balise active .  Les suggestions d’affichage et d’ajout de références de contenu à partir des fichiers indexés s’affichent en fonction du contenu de la balise active. Vous pouvez également sélectionner plusieurs balises.


1. Sélectionnez toutes les balises pour afficher les suggestions en fonction du contenu présent dans le document complet.  L’icône **Suggérer du contenu réutilisable** ![ai suggérer un contenu réutilisable ](./images/ai-suggest-reusable-content-icon.svg) s’affiche en regard du contenu pour lequel une correspondance appropriée a été trouvée.



   >[!NOTE]
   >
   > Vous pouvez uniquement afficher les suggestions de la fenêtre d’affichage actuelle (le contenu visible à l’écran). Pour afficher des suggestions pour tout autre contenu du document, faites défiler la page vers le haut ou vers le bas pour l’afficher dans la fenêtre d’affichage, puis sélectionnez **Suggérer du contenu réutilisable** ![ai Suggérer l’icône de contenu réutilisable ](./images/ai-suggest-reusable-content-icon.svg).


1. Vous pouvez afficher les suggestions intelligentes dans le panneau de suggestions.  Experience Manager Guides fournit des suggestions dont le contenu est contextuellement similaire ou a la même signification. Par exemple, vous pouvez rechercher la rubrique qui contient le numéro de version exact, comme « version 2023.03.12 ». Vous pouvez également rechercher « Adobe a son siège à San Jose, en Californie » et trouver du contenu similaire comme « San Jose a les quartiers de nombreuses sociétés de logiciels comme Adobe ».
1. Sélectionnez **Informations sur le contenu** ![Informations sur le contenu](images/smart-suggestions-content-info-icon.svg) pour afficher les détails.

   ![Panneau Informations sur le contenu](images/smart-suggestions-content-information.png){width="300" align="left"}

   *Affichez les informations détaillées sur la référence de contenu.*

   1. Le titre de la rubrique qui contient la référence de contenu s’affiche sous la forme d’un lien hypertexte.
   1. Chemin d’accès au fichier contenant la référence de contenu.
   1. Type de référence auquel le contenu est référencé.
   1. Les noms des fichiers DITA dans lesquels la rubrique est référencée sont affichés sous forme de liens hypertexte.
1. Sélectionnez **Aperçu** ![icône d’aperçu](./images/expand-icon.svg) pour comparer le contenu actuel au contenu suggéré. Vous pouvez ainsi comparer les différences et déterminer si vous souhaitez ajouter la référence de contenu pour le contenu suggéré et le rendre cohérent ou conserver votre contenu actuel.

   ![Suggérer un aperçu de contenu réutilisable](images/ai-assistant-suggest-reusable-content.png)

   *Prévisualiser la comparaison entre le contenu actuel et le contenu suggéré.*

1. Cliquez sur **Accepter** pour ajouter la référence de contenu suggérée dans l’aperçu **Suggérer du contenu réutilisable**.
1. Vous pouvez également sélectionner **Accepter** ou **Ignorer** dans le panneau de suggestions pour obtenir les recommandations appropriées.


Cette fonctionnalité intelligente est pratique et minimise l’effort de recherche manuelle de contenu, ce qui vous permet de vous concentrer davantage sur la génération de nouveau contenu. Cela facilite également une meilleure collaboration entre les équipes et permet de maintenir la cohérence du contenu créé par les différents auteurs.

>[!NOTE]
>
>Les suggestions intelligentes ne conservent pas vos données au-delà de la session en cours. Pour les réponses, les suggestions intelligentes reposent uniquement sur l’index créé sur le contenu résidant dans votre base de données interne. Les outils d’IA externes ne sont pas utilisés, ce qui garantit que vos données restent dans le système.
