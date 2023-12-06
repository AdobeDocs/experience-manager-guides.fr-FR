---
title: Rubriques de révision
description: Découvrez comment passer en revue des rubriques et utiliser les fonctionnalités comme réviseur, vue de document, vue de rubrique, barre d’outils contextuelle, mode Aperçu, ajouter des pièces jointes aux commentaires et panneau des conditions dans les Guides d’AEM.
exl-id: fc87fc37-f1cd-4a19-96c2-3a08a8222002
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '2351'
ht-degree: 0%

---

# Rubriques de révision {#id2056B0W0FBI}

Si vous êtes un réviseur, vous recevez un courrier électronique de demande de révision contenant le lien vers les rubriques de la révision. Cliquez sur le lien pour accéder à la page de révision dans laquelle vous pouvez ajouter vos commentaires sur les rubriques partagées.

Pour passer en revue une rubrique, procédez comme suit :

1. Cliquez sur le lien direct fourni dans l’e-mail de demande de révision.

   Le lien de rubrique ou de mappage s’ouvre dans un navigateur.

   >[!NOTE]
   >
   > Vous pouvez également accéder au lien de révision de rubrique à partir de votre zone de notifications de boîte de réception dans l’interface utilisateur d’AEM.

1. Selon la manière dont la révision de la rubrique est lancée, vous pouvez voir l’un des deux écrans suivants :

   >[!NOTE]
   >
   > L’interface utilisateur peut être différente si vous avez créé la révision dans :
   >
   > - AEM Guides version as a Cloud Service de novembre 2022 ou antérieure
   > - AEM Guides version 4.1 ou antérieure



   L’écran suivant s’affiche lorsqu’un mappage DITA est utilisé pour lancer le processus de révision :

   ![](images/multiple-topics-review.png){width="800" align="left"}

   Les options suivantes sont disponibles dans cet écran :

   - **A**: nom de la tâche de révision.
   - **B**: cliquez sur l’icône Mode Rubriques pour afficher ou masquer le panneau Rubriques.

   - **C**: vous pouvez rechercher la rubrique requise en saisissant une partie du texte du titre ou du chemin de fichier dans la barre de recherche.

     Sélectionner  ![](images/view-options.svg) près de la barre de recherche pour afficher toutes les rubriques ou afficher les rubriques avec des commentaires. Par défaut, vous pouvez afficher toutes les rubriques présentes dans la tâche de révision.


   - **D**: les nombres mis en surbrillance par ***F*** peut être filtré en sélectionnant l’option de filtre souhaitée à partir de cet emplacement. Vous pouvez filtrer les commentaires par type, statut, réviseur ou version. Par exemple, si vous souhaitez voir le nombre de commentaires de type Barré dans chaque rubrique de révision en cours, cliquez sur l’icône de filtre, puis choisissez **Type de révision** \> **Suppression**.

     >[!NOTE]
     >
     > Lorsque vous appliquez les filtres, seuls les commentaires correspondant aux filtres sélectionnés s’affichent dans le panneau des commentaires. Le nombre de commentaires filtrés s’affiche à gauche dans le panneau des rubriques.

   - **E**: une rubrique affectée à la révision au réviseur actuel s’affiche en noir et peut faire l’objet d’un clic. Lorsque le réviseur clique sur un lien de rubrique, cette rubrique est placée en haut de l’écran.
   - **F**: une rubrique qui n’est pas disponible pour la révision est grisée. La rubrique s’affiche en mode lecture seule et vous n’êtes pas autorisé à ajouter des commentaires de révision sur ces rubriques.

   - **G**: nombre de commentaires reçus sur un sujet. Ce nombre change en fonction du filtre que vous appliquez.

   Toutes les rubriques du mappage s’affichent sous la forme d’un document composite unique. Les rubriques que le réviseur est autorisé à réviser s’affichent normalement. Les rubriques que la révision n’est pas autorisée à réviser ne s’affichent pas.

   ![](images/review-read-only.png){width="800" align="left"}

   Dans la capture d’écran ci-dessus, la rubrique Description générale est partagée pour la révision du réviseur actuel, qui s’affiche normalement. Cependant, la rubrique suivante, Historique du contenu du vol, n’est pas partagée pour révision et s’affiche en mode lecture seule. La rubrique actuellement en cours est également mise en évidence dans la table des matières.

   L’écran suivant s’affiche lorsqu’une ou plusieurs rubriques sont sélectionnées et partagées en vue de la révision :

   ![](images/review-composite-view.png){width="800" align="left"}

   >[!NOTE]
   >
   > En cas de rubriques multiples, elles s’affichent sous la forme d’un document composite dans la vue document. La capture d’écran ci-dessus met en évidence deux rubriques différentes présentées l’une après l’autre dans une seule vue.

1. Ouvrez le panneau Commentaires en cliquant sur le bouton **Commentaires** dans le coin supérieur droit de la barre d’outils.

   Saisissez les commentaires de révision en sélectionnant un type de commentaire approprié dans la barre d’outils, puis appuyez sur Entrée pour envoyer votre commentaire.

   >[!NOTE]
   >
   > Le panneau Commentaires affiche uniquement les commentaires sur les sujets en cours. Lorsque vous déplacez le focus vers une autre rubrique, les commentaires donnés sur l’autre rubrique s’affichent.

1. Cliquez sur **Fermer** une fois que vous avez terminé de passer en revue la rubrique. Lorsque vous cliquez sur le bouton **Fermer** , vous êtes redirigé vers la page à partir de laquelle vous avez accédé à la rubrique de révision.

## Fonctionnalités supplémentaires disponibles dans l’écran de révision

**Mode document et mode rubrique** - Par défaut, si plusieurs rubriques sont partagées en vue de la révision, une vue de document composite des rubriques est présentée aux réviseurs. Dans le cas d’une révision de mappage DITA, toutes les rubriques de la carte sont présentées sous la forme d’un document unique, ressemblant à une vue de livre. Si vous le souhaitez, vous pouvez également cliquer sur une rubrique spécifique pour afficher uniquement cette rubrique dans l’écran de révision.

Lorsque vous affichez une seule rubrique, vous disposez d’une option supplémentaire pour revenir à la vue de document. Dans la capture d’écran suivante, une rubrique particulière d’un fichier de mappage est ouverte pour révision. L’option mise en surbrillance — **Afficher la vue du document** permet à l’utilisateur de revenir à la vue de document du fichier map.

![](images/switch-document-view.png){width="800" align="left"}

**Utilisation de différents types d’outils de commentaires** - Vous pouvez ajouter des commentaires insérés en mettant le texte en surbrillance, en frappant le texte, en insérant du texte ou en ajoutant une note de commentaire. Les différents types d’outils de commentaires fournis dans la barre d’outils Commentaires sont décrits ci-dessous :

![](images/comments-toolbar.png){width="350" align="left"}

- **Surligner** \(![](images/review-highlight-icon.svg)\) : pour ajouter un commentaire en surbrillance, sélectionnez le texte et cliquez sur l’icône Mettre en surbrillance . Vous pouvez également cliquer sur l’icône Mettre en surbrillance et sélectionner le texte de votre choix :

  ![](images/highlight-comment.png){width="650" align="left"}

  Une fenêtre contextuelle s’affiche dans le panneau Commentaires, dans laquelle vous pouvez ajouter votre commentaire pour le contenu mis en surbrillance.

- **Barré** \(![](images/review-text-strike-through-icon.svg)\) : si vous souhaitez suggérer la suppression du contenu, vous pouvez le faire en sélectionnant le contenu et en cliquant sur l’icône Barrer . Vous pouvez également sélectionner le texte de votre choix et cliquer sur la touche Supprimer :

  Une fenêtre contextuelle s’affiche dans le panneau Commentaires, dans laquelle vous pouvez ajouter votre commentaire pour le contenu supprimé.

- **Insérer du texte** \(![](images/review-insert-text-icon.svg)\) : si vous souhaitez insérer du texte, cliquez sur l’icône Insérer du texte et placez le curseur à l’endroit où vous souhaitez insérer le texte et saisissez les informations. Vous pouvez également placer le curseur à l’endroit où vous souhaitez insérer du texte et commencer à saisir du texte. Les informations ajoutées apparaissent en vert :

- **Ajouter un commentaire**\(![](images/review-comment-icon.svg)\) : si vous souhaitez ajouter un type de commentaire de post-it, cliquez sur l’icône Ajouter un commentaire et saisissez le commentaire dans la fenêtre contextuelle.


**Barre d’outils contextuelle**

Vous pouvez également mettre rapidement le texte en surbrillance ou barré à l’aide de la barre d’outils contextuelle. Effectuez les étapes suivantes pour commenter à l’aide de la barre d’outils contextuelle :

1. Sélectionnez le texte que vous souhaitez mettre en surbrillance ou percer. La barre d’outils contextuelle s’affiche.

   ![](images/review-quick-launch-toolbar.png){width="550" align="left"}

1. Cliquez sur le bouton **Surligner** ou **Barré** Icône
1. Vous pouvez ajouter des commentaires dans le panneau des commentaires pour l’action de surbrillance ou de barrage.

**Révision à l’aide du panneau Commentaires** - Le panneau Commentaires affiche une liste des commentaires relatifs à la rubrique actuelle. Ce panneau répertorie également les commentaires des autres réviseurs si la rubrique est envoyée à plusieurs réviseurs. Chaque commentaire du panneau des commentaires est associé au texte correspondant dans la rubrique actuelle. Il permet d’identifier le texte commenté. Chaque commentaire affiche le nom du réviseur qui a ajouté le commentaire avec l’horodatage.

Les commentaires sont affichés dans l’ordre du texte commenté dans le document. Par exemple, il y a un commentaire en surbrillance sur la première phrase et un commentaire en insertion de texte sur la deuxième phrase du premier paragraphe, puis le commentaire en surbrillance est affiché avant le commentaire en texte inséré.

Les tâches que vous pouvez effectuer à l’aide du panneau Commentaires sont décrites ci-dessous :

- Cliquez sur un commentaire pour mettre en surbrillance et afficher l’emplacement du commentaire correspondant dans le document.
- Vous pouvez ajouter des réponses aux commentaires.
- Vous pouvez modifier votre propre commentaire en cliquant sur le texte de votre commentaire dans le panneau Commentaires , puis en sélectionnant **Modifier** dans le menu Options.
- Vous pouvez supprimer vos propres commentaires en cliquant sur le commentaire dans le panneau Commentaires , puis en sélectionnant **Supprimer** dans le menu Options.

  ![](images/review-comment-options-menu.png){width="300" align="left"}

  >[!NOTE]
  >
  > Le menu Options s’affiche uniquement lorsque vous passez la souris sur vos propres commentaires. Il n&#39;est pas affiché pour les commentaires des autres réviseurs.

- Tous les utilisateurs participants peuvent répondre aux commentaires des autres utilisateurs. Sur un commentaire, cliquez sur **Répondre** et appuyez sur Entrée pour envoyer une réponse.

**Mode Aperçu**

- L’ouverture d’une rubrique en mode Aperçu affiche l’affichage d’une rubrique lorsqu’elle est consultée par un auteur après avoir appliqué toutes les modifications. Par exemple, tout le texte inséré s’affiche sous forme de texte normal et tout le texte supprimé \(supprimé\) est supprimé du contenu.

- La capture d’écran suivante affiche le contenu dans *Réviser* mode :

![](images/review-author-mode.png){width="550" align="left"}

La capture d’écran suivante affiche le contenu dans *Aperçu* mode :

![](images/review-preview-mode.png){width="550" align="left"}

**Ajout de pièces jointes aux commentaires** - Si vous souhaitez compléter votre commentaire en fournissant des informations supplémentaires disponibles dans un autre fichier, vous pouvez le faire en le joignant à votre commentaire. En tant que réviseur, vous pouvez facilement ajouter un ou plusieurs fichiers de votre système local à votre commentaire. Un fichier peut être ajouté à tous les formulaires de commentaires pris en charge : Mise en surbrillance, Barré, Insérer du texte ou un commentaire.

Lorsque vous insérez l’un des commentaires, la fenêtre contextuelle de commentaire s’affiche. Après avoir fourni des commentaires ou des informations supplémentaires dans la fenêtre contextuelle, vous pouvez les envoyer en appuyant sur Entrée. Une fois le commentaire ajouté, vous avez la possibilité d’ajouter une pièce jointe à ce commentaire.

![](images/comment-pop-up-panel.png){width="800" align="left"}

Dans la capture d’écran ci-dessus, le document contient la fenêtre contextuelle du commentaire de surbrillance et le commentaire est également ajouté au panneau Commentaires . Icône de pièce jointe ![](images/file-attach-review.svg)est disponible avec le commentaire aux deux emplacements.

Effectuez les étapes suivantes pour ajouter une pièce jointe à votre commentaire :

1. Cliquez sur le bouton *Ajouter un fichier attaché* icon ![](images/file-attach-review.svg) sur le commentaire auquel vous souhaitez ajouter une pièce jointe.

   La boîte de dialogue Ouvrir le fichier s’affiche.

1. Sélectionnez un ou plusieurs fichiers à joindre.

   Les fichiers sélectionnés s’affichent avec le commentaire dans le panneau Commentaires.

   Dans le panneau Commentaires , vous pouvez voir le nom du fichier et sa taille. Vous pouvez également supprimer un fichier en cliquant sur l’icône Supprimer ![](images/Delete_icon.svg) associée au nom du fichier.

1. Cliquez sur **Envoyer**.

   Les pièces jointes sont chargées et ajoutées au commentaire.


**Remarques supplémentaires sur l’utilisation des pièces jointes :**

- Par défaut, seuls deux fichiers joints avec un commentaire s’affichent. S’il existe d’autres fichiers, alors **Afficher la pièce jointe** sur la droite affiche le nombre de toutes les pièces jointes \(qui sont plus de deux\) associées au commentaire. Vous pouvez cliquer sur le nombre pour afficher toutes les pièces jointes. Par exemple, si vous avez quatre pièces jointes avec un commentaire, le bouton affiche +2.

![](images/review-view-attachment.png){width="550" align="left"}

- Placer le pointeur de la souris sur une pièce jointe permet de télécharger ou de supprimer la pièce jointe. La suppression de la pièce jointe n&#39;est disponible que si le validant actuel a ajouté ce commentaire, comme illustré dans la capture d&#39;écran suivante :

![](images/current-user-comment-options.png){width="550" align="left"}

Les autres réviseurs ou auteurs n’obtiennent que l’option de téléchargement de pièce jointe.

![](images/other-reviewer-download.png){width="550" align="left"}

- Vous pouvez télécharger toutes les pièces jointes associées à un commentaire à partir du **Afficher les pièces jointes** boîte de dialogue. Sélectionnez les pièces jointes et cliquez sur le bouton **Télécharger** au niveau du commentaire.

- Vous pouvez également supprimer les pièces jointes associées à un commentaire de la **Afficher les pièces jointes** boîte de dialogue. Sélectionnez les pièces jointes et cliquez sur le bouton **Supprimer** Icône

![](images/attach-files-comments-panel.png){width="550" align="left"}


**Panneau Conditions** - Si votre rubrique comporte du contenu conditionnel, le **Conditions** \(![](images/conditions-icon.svg)\) à droite. Cliquer sur **Conditions** Cette icône ouvre le panneau Conditions qui vous permet de mettre en surbrillance le contenu en fonction des conditions disponibles dans la rubrique.

: par défaut **Mettre en surbrillance toutes les conditions** est activée, toutes les conditions sont sélectionnées, l’intégralité du contenu est affichée et le contenu conditionnel est affiché en surbrillance en mode de révision et d’aperçu.

: vous pouvez désactiver **Mettre en surbrillance toutes les conditions** et afficher tout le contenu présent dans la rubrique comme du texte normal sans mise en surbrillance.

![](images/review-conditions-panel.png){width="350" align="left"}

Vous pouvez choisir de masquer ou d’afficher une condition spécifique.

- Si vous masquez une condition, le contenu comportant cette condition n’est pas mis en surbrillance en mode de révision.
- Si vous affichez une condition, le contenu conditionnel est mis en surbrillance en mode de révision. Par exemple, dans la capture d’écran suivante, seul le contenu utilise deux conditions : `win` et `mac` est mise en surbrillance.


![](images/review-condition-normal-mode.png){width="650" align="left"}

En mode aperçu, le contenu non conditionnel et le contenu conditionnel qui utilise les deux conditions affichées : `win` et `mac` s’affiche. Le contenu conditionnel restant pour lequel les conditions sont masquées ne s’affiche pas.

**Révision en temps réel** - Le panneau Commentaires se met à jour en temps réel avec des commentaires et les commentaires ou les actions entreprises par l’auteur sur les commentaires.

- Plusieurs réviseurs pourront laisser des commentaires ou répondre simultanément à des commentaires sur le même document. Vous pouvez savoir qui est en train de réviser le document en pointant la souris sur l’icône utilisateur dans le coin supérieur droit de l’écran.

- Si une rubrique fait partie de plusieurs tâches de révision, les commentaires effectués dans une tâche ne sont pas affichés dans l’autre tâche.

- Cliquer sur l’icône Commentaire obsolète \(![](images/outdated-comment-icon.svg)\) affiche les différences entre la dernière version et la version commentée du document. Les numéros de version \(des versions comparées\) s’affichent en haut des documents.

  ![](images/comments-page-review-mode.png){width="800" align="left"}

  >[!NOTE]
  >
  > Pointez sur l’icône Commentaire obsolète pour afficher le numéro de version de la rubrique sur laquelle le commentaire a été ajouté. Par exemple, si un commentaire a été donné sur la version 1.0, le même commentaire s’affiche.

- Cliquer sur un commentaire obsolète ouvre la version de ce commentaire dans le panneau de gauche. La version précédente s’affiche dans le panneau de gauche et la version actuelle dans le panneau de droite. Tous les commentaires sur la version obsolète sont importés sur le côté gauche. Vous pouvez comparer la version précédente à la version actuelle.

**Filtrage des commentaires** - Vous pouvez filtrer les commentaires d’un document afin d’afficher des commentaires spécifiques selon vos besoins. Pour filtrer les commentaires, cliquez sur le bouton **Filtrer** icon \(![](images/filter-search-icon.svg)\) qui s’affiche dans le menu à droite de la zone de texte Rechercher les commentaires dans le panneau Commentaires .

Sélectionnez une ou plusieurs des options de filtrage suivantes dans le **Type de filtre** puis cliquez sur **Appliquer**.

- **Type de révision** - Filtrez en fonction du type de commentaires : mise en surbrillance, suppression, insertion ou commentaire.
- **État de révision** - Filtrez en fonction de l’état du commentaire, comme Accepté, Refusé ou Aucun.
- **Réviseurs** - Filtrer selon le nom du validant.

- **Versions** - Filtrez en fonction des commentaires reçus sur une version spécifique du sujet.

  Lorsque vous utilisez les filtres, les commentaires sur le panneau de droite sont filtrés en fonction de la sélection et le nombre de commentaires dans le panneau de gauche est mis à jour en conséquence.


Pour supprimer le filtre et afficher tous les commentaires, désélectionnez tous les filtres de la **Type de filtre** puis cliquez sur **Appliquer**.

**Rubrique parente :**[ Révision de rubriques ou de mappages](review.md)
