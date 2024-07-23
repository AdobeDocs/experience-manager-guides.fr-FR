---
title: Rapport Réutilisation du contenu
description: Découvrez comment afficher le rapport de réutilisation du contenu dans AEM Guides. Générez le rapport pour connaître le pourcentage de réutilisation du contenu.
feature: Report Generation
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Rapport Réutilisation du contenu {#id205BB900OQD}

Le rapport Réutilisation du contenu est un autre rapport utile que vous pouvez générer. Ce rapport calcule le pourcentage moyen d’utilisation du contenu, ce qui est très utile pour les chefs de projet et les chefs d’entreprise afin de déterminer la quantité de contenu réutilisé.

>[!TIP]
>
> Pour garantir le bon fonctionnement du rapport Réutilisation du contenu, vous devez activer le workflow de post-traitement. Contactez votre administrateur système pour activer les workflows de post-traitement.

Effectuez les étapes suivantes pour afficher le rapport Réutilisation du contenu :

1. Cliquez sur le lien Adobe Experience Manager en haut de l’écran et sélectionnez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils.

1. Cliquez sur la mosaïque **Rapport de réutilisation de contenu** .

1. Cliquez sur **Parcourir** pour choisir un chemin où se trouvent vos rubriques ou saisissez le chemin manuellement.

   Le rapport est généré en analysant le contenu dans les dossiers parents et tous les dossiers enfants.

1. Cliquez sur **Générer le rapport** pour obtenir le rapport Réutilisation du contenu.

   ![](images/content-reuse-uuid.png){width="800" align="left"}

   La page du rapport se divise en deux parties :

   - **Résumé du rapport :**

     Répertorie la Réutilisation moyenne du contenu, qui est calculée en tant qu’ Instances/Nombre total de rubriques de la réutilisation du contenu. Ce rapport prend en compte toutes les références de contenu direct de premier niveau et les références de rubrique pour le calcul. Les instances de réutilisation du contenu sont calculées comme la somme totale des valeurs du champ Nombre de fois réutilisées . Le sujet qui est le plus réutilisé est également répertorié dans le résumé du rapport. Cliquez sur le lien de la rubrique dans la rubrique la plus sollicitée pour ouvrir l’aperçu de la rubrique.

   - **Détails :**

     La section Détails contient les colonnes suivantes :

      - **Titre** : titre de la rubrique. Cliquez sur le lien de titre de la rubrique pour ouvrir l’aperçu de la rubrique.

      - **UID** : identifiant unique universelle \(UUID\) du fichier.

      - **Size** : taille des fichiers en octets.

      - **Status** : état actuel du document - Version préliminaire, En révision ou révision.

      - **Nombre de fois réutilisées** : nombre de fois où la rubrique correspondante a été réutilisée. Ce calcul correspond à la somme des entrées dans les colonnes Référencé par moins 1.

      - **Référencé par** : rubriques dans lesquelles la rubrique correspondante a été référencée. Ici, seules les références directes \(premier niveau\) sont prises en compte. Plusieurs rubriques sont séparées par une virgule. L’UUID du fichier référencé est également mentionné entre crochets. Cliquez sur le lien de titre de la rubrique pour ouvrir l’aperçu de la rubrique.


>[!NOTE]
>
> Vous pouvez également exporter le rapport Réutilisation du contenu au format CSV. Pour ce faire, cliquez sur le lien Exporter au format CSV dans le coin supérieur gauche de l’écran et choisissez l’emplacement d’enregistrement du fichier CSV. Vous pouvez ensuite ouvrir ce fichier CSV dans n’importe quel éditeur CSV.

**Rubrique parente :**[ Rapports](reports-intro.md)
