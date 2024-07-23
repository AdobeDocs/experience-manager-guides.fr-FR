---
title: Rapport de mappage DITA à partir du tableau de bord de mappage
description: Générez des rapports de mappage DITA à partir du tableau de bord de mappage dans AEM Guides. Découvrez comment générer le fichier CSV d’un rapport de mappage DITA.
feature: Report Generation
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 0%

---

# Rapport de mappage DITA à partir du tableau de bord de mappage {#id205BB800EEN}

AEM Guides fournit à vos administrateurs des fonctionnalités de reporting pour vérifier l’intégrité globale de la documentation avant qu’elle ne soit publiée ou mise à la disposition des utilisateurs finaux. Le rapport de mappage DITA du tableau de bord de mappage dans AEM Guides fournit des informations précieuses telles que les rubriques manquantes, les rubriques avec des éléments manquants, l’UUID des rubriques et des fichiers multimédias référencés et l’état de révision de chaque rubrique. Un rapport détaillé individuel au niveau de la rubrique fournit également des informations relatives au contenu DITA telles que des références de contenu et des images manquantes ou des références croisées.

>[!NOTE]
>
> AEM Guides actualise ce rapport à chaque événement qui entraîne un changement dans votre fichier de mappage ou lorsque toute référence dans votre fichier de rubrique est mise à jour.

Effectuez les étapes suivantes pour afficher le rapport de mappage DITA :

1. Dans l’interface utilisateur d’Assets, accédez au fichier de mappage DITA pour lequel vous souhaitez afficher le rapport, puis cliquez dessus.

1. Cliquez sur **Rapports**.

   ![](images/reports-page-uuid.png){width="800" align="left"}

   La page Rapports est divisée en deux parties :

   - **Résumé de la rubrique :**

     Répertorie le résumé global du fichier de mappage sélectionné. En regardant le résumé, vous pouvez rapidement connaître le nombre total de rubriques dans la carte, les rubriques manquantes, le nombre de rubriques comportant des éléments manquants, l’état des rubriques — En version préliminaire, En révision ou En révision.

   - **Détails :**

     Lorsque vous cliquez sur une rubrique, un rapport détaillé de la rubrique sélectionnée s’affiche.

     ![](images/detailed-report-uuid.png){width="800" align="left"}

     Les éléments surlignés sous **A**, **B**, **C** et **D** sont décrits ci-dessous :

      - **Rubrique** : titre de la rubrique spécifiée dans le mappage DITA. Placez le pointeur de la souris sur le titre de la rubrique pour afficher le chemin d’accès complet de la rubrique. S’il existe des problèmes dans la rubrique, tels que des références ou des images manquantes, un point rouge s’affiche avant le titre de la rubrique.

      - **Nom de fichier** : nom du fichier.

      - **UID** : identifiant unique universelle \(UUID\) du fichier.

      - **Auteur** : utilisateur qui a travaillé en dernier sur cette rubrique.

      - **État du document** : état actuel du document - Version préliminaire, En révision ou Révisé.

      - **Rubriques manquantes \(B\)** : S’il existe des rubriques avec des références rompues, ces rubriques sont répertoriées sous la liste Rubriques manquantes.

      - **Éléments manquants** : répertorie le nombre d’images manquantes ou de références croisées rompues, le cas échéant.

      - **Ouvrir dans l’éditeur \(D\)** : cliquer sur cette icône ouvre la rubrique dans l’éditeur web.


   Les éléments surlignés sous **E** sont décrits ci-dessous :

   - **Multimédia** : le chemin des images utilisées dans la rubrique est affiché avec son UUID. Si vous cliquez sur le chemin de l’image, l’image correspondante est ouverte dans une fenêtre contextuelle. Les liens d’image rompus sont répertoriés en rouge.

   - **Références du contenu** : le chemin du contenu référencé dans la rubrique est affiché avec son UUID. Si vous cliquez sur le titre du contenu référencé, la rubrique correspondante est ouverte en mode Aperçu.

   - **Cross Reference** : le chemin d’accès au contenu référencé croisé s’affiche avec son UUID. Si vous cliquez sur le titre du contenu référencé, la rubrique correspondante est ouverte en mode Aperçu. Les références croisées rompues sont répertoriées en rouge.

   - **Révision** : affiche l’état de la tâche de révision de la rubrique. Vous pouvez voir l’état \(ouverture ou fermeture\), la date d’échéance et la personne désignée pour la rubrique en cours de révision. Si vous cliquez sur le lien de la rubrique, elle s’ouvre en mode de révision.

   - **Utilisé dans** : affiche une liste d’autres rubriques ou mappages où la rubrique est utilisée. L’UUID de toutes ces rubriques et cartes est également répertorié.

Outre le rapport pour chaque rubrique, les administrateurs ont également accès à des informations telles que l’historique de publication d’un mappage DITA. Pour plus d’informations sur l’historique des sorties générées, voir [Affichage de l’état de la tâche de génération de sortie](generate-output-for-a-dita-map.md#viewing_output_history).

## Génération du fichier CSV du rapport de mappage DITA

Vous pouvez télécharger et exporter le fichier CSV d’un rapport de mappage DITA. Le fichier CSV contient le rapport de mappage DITA détaillé.

Effectuez les étapes suivantes pour générer le fichier CSV d’un rapport de mappage DITA :

1. Cliquez sur **Générer le rapport** en haut à gauche pour générer le rapport de mappage DITA.

   ![](images/generate-DITA-map-report.png){width="800" align="left"}

1. Une fois le rapport prêt à être téléchargé, vous recevrez une notification. Cliquez sur **Télécharger** pour télécharger le fichier CSV du rapport généré.

   ![](images/download-report-dialog.png){width="550" align="left"}


   Vous pouvez également télécharger le fichier CSV du rapport généré ultérieurement à partir de la boîte de réception de notification AEM.

   Cliquez sur le rapport généré dans la boîte de réception pour télécharger le rapport.

   ![](images/report-inbox--notification.png){width="300" align="left"}

Une fois le rapport téléchargé dans la boîte de réception, vous pouvez également le sélectionner et utiliser l’icône Ouvrir dans la partie supérieure pour ouvrir le rapport sélectionné.

**Rubrique parente :**[ Rapports](reports-intro.md)
