---
title: Rapport sur la réutilisation du contenu
description: Découvrez comment afficher le rapport de réutilisation du contenu dans AEM Guides. Générez le rapport pour trouver le pourcentage de réutilisation du contenu.
feature: Report Generation
role: User
hide: true
exl-id: 1a61fc05-b2b4-4665-a15a-0058fbbc2942
TQID: https://experienceleague.adobe.com/VpM0bDhlBIh5R1JA97j-k1YYfWoyss0exz8d5tUuKTE
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: cdab8659-8d50-4417-b6fd-762f347c13ee
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 428
ht-degree: 0%

---

# Rapport sur la réutilisation du contenu {#id205BB900OQD}

![](images/test-version-info-table-original.svg)

Le rapport de réutilisation du contenu est un autre rapport utile que vous pouvez générer. Ce rapport calcule le pourcentage moyen d’utilisation du contenu, ce qui est très utile pour les chefs de projet et les propriétaires d’entreprise qui souhaitent voir la quantité de contenu réutilisée.

>[!TIP]
>
> Pour garantir le bon fonctionnement du rapport de réutilisation du contenu, vous devez activer le workflow de post-traitement. Contactez votre administrateur système pour activer les workflows de post-traitement.

Pour afficher le rapport de réutilisation du contenu, procédez comme suit :

1. Cliquez sur le lien Adobe Experience Manager en haut et choisissez **Outils**.

1. Sélectionnez **Guides** dans la liste des outils.

1. Cliquez sur la mosaïque **Rapport de réutilisation du contenu**.

1. Cliquez sur **Parcourir** pour choisir un chemin d’accès où se trouvent vos rubriques ou saisissez manuellement le chemin d’accès.

   Le rapport est généré en analysant le contenu dans le dossier parent et tous les dossiers enfants.

1. Cliquez sur **Générer le rapport** pour obtenir le rapport de réutilisation du contenu.

   ![](images/content-reuse-uuid.png){width="800"}

   La page du rapport est divisée en deux parties :

   - **Résumé du rapport :**

     Répertorie la réutilisation moyenne du contenu, calculée en tant qu’instances de réutilisation de contenu/nombre total de rubriques. Ce rapport prend en compte toutes les références de contenu direct de premier niveau et les références de rubrique pour le calcul. Les instances de réutilisation de contenu sont calculées comme la somme totale des valeurs du champ Nombre de fois réutilisées . La rubrique la plus largement réutilisée est également répertoriée dans le résumé du rapport. Cliquez sur le lien de la rubrique dans la rubrique la plus réutilisée pour ouvrir l’aperçu de la rubrique.

   - **Détails:**

     La section Détails contient les colonnes suivantes :

      - **Titre** : titre de la rubrique. Cliquez sur le lien du titre de la rubrique pour ouvrir l’aperçu de la rubrique.

      - **UUID** : identifiant universel unique \(UUID\) du fichier.

      - **Size** : taille des fichiers en octets.

      - **Statut** : statut actuel du document (brouillon, en cours de révision ou révisé).

      - **Nombre de réutilisations** : nombre de fois où la rubrique correspondante a été réutilisée. Il s’agit de la somme des entrées des colonnes Référencé par moins 1.

      - **Référencé par** : les rubriques dans lesquelles la rubrique correspondante a été référencée. Ici, seules les références directes \(premier niveau\) sont prises en compte. Plusieurs rubriques sont séparées par des virgules. L&#39;UUID du fichier référencé est également mentionné entre parenthèses.Cliquez sur le lien du titre de la rubrique pour ouvrir l’aperçu de la rubrique.


>[!NOTE]
>
> Vous pouvez également exporter le rapport de réutilisation du contenu au format CSV. Pour ce faire, cliquez sur le lien Exporter au format CSV dans le coin supérieur gauche de l’écran et choisissez un emplacement pour enregistrer le fichier CSV. Vous pouvez ensuite ouvrir ce fichier CSV dans n’importe quel éditeur CSV.

**Rubrique parente :**[ Rapports](reports-intro.md)
