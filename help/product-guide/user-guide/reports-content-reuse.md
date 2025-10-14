---
title: Rapport sur la réutilisation du contenu
description: Découvrez comment afficher le rapport de réutilisation du contenu dans AEM Guides. Générez le rapport pour trouver le pourcentage de réutilisation du contenu.
exl-id: ccae4303-75b1-4077-829a-7ef6a14fd8ad
feature: Report Generation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# Rapport sur la réutilisation du contenu {#id205BB900OQD}

Le rapport de réutilisation du contenu est un autre rapport utile que vous pouvez générer. Ce rapport calcule le pourcentage moyen d’utilisation du contenu, ce qui est très utile pour les chefs de projet et les propriétaires d’entreprise qui souhaitent afficher la quantité de contenu réutilisée.

>[!TIP]
>
> Pour garantir le bon fonctionnement du rapport de réutilisation du contenu, vous devez activer le workflow de post-traitement. Contactez votre administrateur système pour activer les workflows de post-traitement.

Pour afficher le rapport de réutilisation du contenu, procédez comme suit :

1. Sélectionnez le logo Adobe Experience Manager en haut et choisissez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils.

1. Sélectionnez la mosaïque **Rapport de réutilisation du contenu**.

1. Sélectionnez **Parcourir** pour choisir un chemin d’accès où se trouvent vos rubriques ou saisissez manuellement le chemin d’accès.

   Le rapport est généré en analysant le contenu dans le dossier parent et tous les dossiers enfants.

1. Sélectionnez **Générer le rapport** pour obtenir le rapport de réutilisation du contenu.

   ![](images/content-reuse-uuid.png){align="left"}

   La page du rapport est divisée en deux parties :

   - **Résumé du rapport :**

     Répertorie la réutilisation moyenne du contenu, calculée en tant qu’instances de réutilisation de contenu/nombre total de rubriques. Ce rapport prend en compte toutes les références de contenu direct de premier niveau et les références de rubrique pour le calcul. Les instances de réutilisation de contenu sont calculées comme la somme totale des valeurs du champ Nombre de fois réutilisées . La rubrique la plus largement réutilisée est également répertoriée dans le résumé du rapport. Si vous sélectionnez le lien de la rubrique dans la rubrique La plus réutilisée, vous accédez à l&#39;aperçu de la rubrique.

   - **Détails:**

     La section Détails contient les colonnes suivantes :

      - **Titre** : titre de la rubrique. En sélectionnant le lien de titre de la rubrique, vous ouvrez l’aperçu de la rubrique.

      - **UUID** : identifiant universel unique \(UUID\) du fichier.

      - **Size** : taille des fichiers en octets.

      - **Statut** : statut actuel du document (brouillon, en cours de révision ou révisé).

      - **Nombre de réutilisations** : nombre de fois où la rubrique correspondante a été réutilisée. Il s’agit de la somme des entrées des colonnes Référencé par moins 1.

      - **Référencé par** : les rubriques dans lesquelles la rubrique correspondante a été référencée. Ici, seules les références directes \(premier niveau\) sont prises en compte. Plusieurs rubriques sont séparées par des virgules. L’UUID du fichier référencé est également mentionné entre parenthèses. Si vous sélectionnez le lien du titre de la rubrique, vous accédez à l’aperçu de la rubrique.


>[!NOTE]
>
> Vous pouvez également exporter le rapport de réutilisation du contenu au format CSV. Pour ce faire, sélectionnez Exporter au format CSV dans le coin supérieur gauche de l’écran et choisissez un emplacement pour enregistrer le fichier CSV. Vous pouvez ensuite ouvrir ce fichier CSV dans n’importe quel éditeur CSV.

**Rubrique parente :**&#x200B;[&#x200B; Présentation des rapports](reports-intro.md)
