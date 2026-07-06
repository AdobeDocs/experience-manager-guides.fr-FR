---
title: Notes de mise à jour d’Adobe Experience Manager Guides 3.8 et 3.8.5
description: Nouvelles fonctionnalités et améliorations majeures des versions 3.8 et 3.8.5 d’Adobe Experience Manager Guides (anciennement appelée solution XML Documentation).
source-git-commit: ff3d35832b80f6221f1261498934ab74261b282b
workflow-type: tm+mt
source-wordcount: '1589'
ht-degree: 0%

---


# Notes de mise à jour | Adobe Experience Manager Guides 3.8

**Clause de non-responsabilité** :

** était auparavant marqué comme *XML Documentation pour Adobe Experience Manager*. Veuillez noter que certaines références contenues dans la documentation peuvent toujours faire référence à une image de marque antérieure, mais s’appliquent toujours à l’offre actuelle.

Ces notes de mise à jour répertorient les nouvelles fonctionnalités et améliorations majeures de la version 3.8.x de XML Documentation for Adobe Experience Manager.

## Nouvelles fonctionnalités et améliorations de la version 3.8.5

### Correctifs

Les bogues corrigés dans la version 3.8.5 sont répertoriés ci-dessous :

- La prise en charge de base est manquante pour la sortie PDF via FrameMaker Publishing Server.
- L’API d’extraction et d’archivage pour FrameMaker ou Oxygen ne fonctionne pas correctement si les autorisations au niveau des dossiers ont été configurées pour divers groupes dans AEM.
- L’aperçu du contenu ne s’affiche pas dans la page de l’interface utilisateur d’Assets.
- Le bouton « Source » ne fonctionne pas sur la page de l’interface utilisateur d’Assets.
- Lorsqu’une image est insérée via la fonction Insérer une image de l’éditeur web, le chemin d’accès relatif de l’image insérée passe à son chemin d’accès absolu.
- La liste déroulante de paramètres prédéfinis FMPS ne s’affiche pas dans l’interface utilisateur avec la dernière version 3.8.
- Le panneau Favoris ne s’affiche pas lorsqu’il contient un grand nombre de ressources dans la gestion des ressources numériques (DAM) et qu’un nouvel élément favori est ajouté à partir de l’éditeur web XML.
- La redirection interne *sling:mapping* qui redirige tous les liens ne fonctionne pas et affiche des URL longues (avec des chemins internes) au lieu des URL courtes pour les pages web.
- Dans la vue Liste, la colonne Modifié affiche « Utilisateur externe » au lieu du nom d’utilisateur lorsque des ressources sont chargées ou importées à partir de la page de l’interface utilisateur d’Assets (sauf via le gestionnaire de packages).
- Le titre ne s’affiche pas correctement dans l’onglet Rubriques du tableau de bord de carte.
- Lors de l’activation de la fonction d’aplatissement des nœuds , certains caractères indésirables sont stockés dans la sortie HTML.
- Les modifications apportées au profil du dossier depuis les préférences utilisateur ne sont pas rechargées automatiquement pour un fichier déjà ouvert, mais le navigateur doit être actualisé.
- La sortie générée via l’option Télécharger la carte comporte des rubriques manquantes en cas d’erreurs de validation.

## Nouvelles fonctionnalités et améliorations de la version 3.8

### Mises à jour de la configuration de dénomination des fichiers

Lors de la création de rubriques DITA dans la solution XML Documentation, les utilisateurs sont autorisés à utiliser des caractères spéciaux dans le cadre des noms de fichier. Cela entraînait l’encodage d’URL sur la génération de pages du site AEM. Pour éviter cette conversion dans l’URL, la version 3.8 des solutions XML Documentation permet à un administrateur de définir une liste de caractères spéciaux autres que les configurations de nom de fichier valides par défaut (a-z A-Z 0-9 - _). Cela signifie que bien que vous puissiez configurer une liste de caractères spéciaux dans un nom de fichier, y compris un espace, elle sera remplacée par un trait d’union (-).

### Modifications de la génération du nom de page du site AEM

Lors de la création, il est possible d’avoir le même nom de fichier pour un ou plusieurs fichiers sous différents dossiers. Lors du processus de publication sur le site AEM, les noms de page étaient ajoutés avec un suffixe lorsqu’il existe au moins un nom de fichier en double. Avec la version 3.8 de la solution XML Documentation, le processus de génération du nom de page du site AEM a été corrigé. Le suffixe n’est ajouté au nom de page généré que s’il existe un nom de fichier en double.

### Nouvelles fonctionnalités et améliorations

Un certain nombre de nouvelles fonctionnalités et améliorations ont été introduites dans les domaines suivants du produit.

#### Éditeur web

- Vous pouvez désormais choisir un libellé dans une liste déroulante lors de la création d&#39;une version d&#39;une rubrique à partir de l&#39;éditeur Web.

  ![Libellés dans une liste déroulante](assets/labels-drop-down-saving-topic-res.avif)

- Le panneau Révision dans l’éditeur web est désormais plus puissant, ce qui vous permet de rétablir une rubrique dans une version qui a été partagée pour la révision. Vous pouvez facilement incorporer des commentaires de révision dans la version révisée sans avoir à vous rappeler quelle version de la rubrique a été partagée pour la révision.

  ![Revenir à la rubrique pour réviser la version](assets/revert-review-topic.avif)

- Un nouvel indice visuel a été introduit pour indiquer si vous travaillez sur la dernière version d&#39;une rubrique ou sur une version antérieure.

  ![Indice de version](assets/old-version-icon.avif)

- Une nouvelle fonctionnalité Historique des versions a été introduite dans cette version. Utilisez la fonction Historique des versions pour :
   - Affichez la liste de toutes les versions de la rubrique active, ainsi que les libellés ajoutés pour chaque version.
   - Revenir à une version précédente de la rubrique.

  ![Historique des versions](assets/version-history.avif)

- Une nouvelle fonctionnalité de gestion des libellés de version a été ajoutée. Elle vous permet d&#39;appliquer des libellés aux versions actuelles ou antérieures d&#39;une rubrique.

  ![ Gestion des libellés de version ](assets/version-label-management.avif)

- Ajout d’une nouvelle fonctionnalité : « Approuver pour publication » avec laquelle un auteur peut marquer une ressource comme approuvée et la verrouiller pour modification.
- Lors du lancement d’un processus de révision, vous pouvez désormais filtrer les rubriques en fonction de leur état.

  ![Sélectionnez les rubriques de révision en fonction de leur état](assets/review-select-topic-on-state.avif)

- Le `<navtitle>` d’un mappage est automatiquement renseigné avec le titre d’une rubrique ajouté au fichier de mappage. Vous pouvez également actualiser facilement le `<navtitle>` à partir de l’éditeur web.
- La prévisualisation d’un tableau avec un grand nombre de colonnes est désormais affichée dans la zone de page.
- Vous pouvez appliquer plusieurs classes de sortie simultanément à partir du panneau Propriétés (sélection multiple).
- Lors de la prévisualisation d’une rubrique, vous pouvez également générer une sortie PDF (inconditionnelle) d’une seule rubrique directement à partir de l’éditeur web.

  ![Sortie PDF de l&#39;aperçu](assets/pdf-output-from-preview.avif)

- Bloquez une requête de publication si la génération de sortie du même préréglage est en cours.
- Possibilité pour un ensemble d’utilisateurs dotés de privilèges limités de supprimer les ressources comportant des références principales actives.
- Ajout d’une fonctionnalité permettant d’afficher ou de copier le code XML à partir de la vue Source de l’interface utilisateur d’Assets, et ce, même si le fichier est extrait par un autre utilisateur.

  ![Vue XML Source](assets/xml-source-view-from-assets-ui.avif)

- Le nom de fichier est maintenant remplacé par le titre du fichier dans la boîte de dialogue Enregistrer, le panneau Contenu réutilisable et le panneau Rechercher et remplacer.

#### Publication

- **Autoriser la configuration des règles d&#39;assainissement pour les pages de site générées** : en tant qu&#39;administrateur, vous pouvez définir les règles d&#39;assainissement pour les noms de fichier des sorties AEM Site ou DITA-OT générées. Chaque fois que vous générez une sortie de site AEM à l’aide de DITA-OT, vous pouvez configurer les règles suivantes pour nettoyer les URL ou les noms de fichier générés par la sortie :
   - Convertissez tous les caractères en minuscules.
   - Remplacez les caractères spéciaux par un séparateur.
   - Limitez un nom de fichier long à un nombre prédéfini de caractères.

- Transmettez facilement la sortie de votre instance d’auteur à l’instance de publication à l’aide du tableau de bord d’activation en bloc. Vous pouvez utiliser un mappage unique ou une collection de mappages et choisir le paramètre prédéfini de sortie à utiliser pour la publication.

  ![Tableau de bord de publication en bloc](assets/bulk-publish-dashboard.avif)

#### Améliorations des performances

- Aplatissement des nœuds pour la sortie AEM Sites : auparavant, la structure des nœuds du site de la sortie AEM Sites était trop profonde. Désormais, vous avez la possibilité d’aplatir la structure du nœud pour de meilleures performances.
- Prise en charge de la dernière version de FrameMaker Publishing Server pour l’été 2020.
- Les fichiers temporaires générés lors de la traduction sont désormais supprimés, ce qui améliore le processus de traduction.

#### Autres améliorations

- La dépendance du workflow Ressource de mise à jour de la gestion des ressources numériques lors de la suppression du contenu DITA de post-traitement. Si des étapes de processus personnalisées sont définies dans le workflow Ressource de mise à jour de la gestion des ressources numériques , vous devez les mettre à jour pour les exécuter une fois le post-traitement terminé.
- L’initiateur du processus de traduction reçoit désormais une notification dans sa boîte de réception lorsque la tâche de traduction est créée avec succès.

### Correctifs

Les bogues corrigés dans la version 3.8 sont répertoriés ci-dessous :

- Les objets audio ne s’affichent pas dans la sortie HTML.
- La fenêtre Forcer la suppression affichée lors de la suppression d&#39;une rubrique DITA comporte plusieurs boutons Forcer la suppression.
- L’option Transférer la ligne de base vers les copies de langue ne fonctionne pas pour la ligne de base créée en mode côté serveur.
- Parfois, la version 3.0 d’une rubrique apparaît avec la mention 3 en mode côte à côte, ce qui empêche l’importation des commentaires de révision.
- Chargement lent des détails du contenu référencé dans l&#39;onglet Lignes de base pour le plan DITA déplacé.
- Le rétablissement d’une version antérieure ne fonctionne pas pour les ressources non numériques.
- De nombreux nœuds _text vides sont créés avec la génération de sortie AEM Sites.
- Éditeur XML : la résolution de lien dans les zones cliquables après la génération de la page ne fonctionne pas.
- Appliquer des libellés depuis l’onglet Lignes de base n’ajoute pas de libellés au contenu référencé, comme les images.
- Les fichiers SVG sont téléchargés dans un format incorrect via l’option Télécharger la carte .
- Impossible de modifier le fragment de contenu dans une vue Liste.
- Impossible d’extraire et d’ouvrir des fichiers dans l’auteur XML Oxygen à l’aide du connecteur.
- Le texte de l’élément `<alt>` n’est pas visible en mode Création.
- La ressource image s’affiche toujours comme Obsolète même si une copie traduite existe.
- Le titre du modèle de carte personnalisé est incorrect et la miniature n’est pas affichée.
- Les éléments de marque appliqués ne s’affichent pas dans la vue de création de l’éditeur web.
- Les notes de bas de page liées ne sont pas visibles dans le contenu.
- Le codage des couleurs dans l’éditeur web ne fonctionne pas avec les attributs conditionnels spécialisés.
- La liste déroulante de @keyref n’est pas conviviale, la jugeant presque inutilisable pour les clients ayant un grand nombre de @keyref.
- Le texte variable référencé par @keyref n’est pas rendu.
- Connecteur Oxygen | Le bouton « Modifier dans Oxygen » ouvre désormais le fichier en mode d’édition même si le fichier n’est pas extrait.
- Les préréglages de sortie personnalisés ne sont pas créés avec un modèle de mappage personnalisé.
- La conversion de Microsoft Word (.docx) en DITA ne crée pas de nœud jcr:content et autorise les caractères spéciaux pour les noms de dossier.
- Une fois qu’un MAP est déplacé (ayant plus de 150 références), les références sont rompues et des erreurs sont observées lors de l’ouverture des rubriques.
- La résolution d’une image n’est pas correctement calculée lorsque sa largeur est modifiée.
- Lorsqu’une image est ajoutée dans un `<codeblock>`, des espaces indésirables sont trouvés dans la sortie du site AEM.

