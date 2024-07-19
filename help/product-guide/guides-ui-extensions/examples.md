---
title: Exemples
description: Liste d'exemples de personnalisation
source-git-commit: fc0b19ac44ca9cbc1e9c5cf046f9a0a24f2a1794
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---


# Exemples

Dans ce package, nous avons également fourni quelques exemples de personnalisation (disponibles sur `guides_extension/src`) . Vous trouverez ci-dessous une brève description de chacun d&#39;entre eux.

1. [Menu contextuel](./examples/file_options.ts)
Dans cet exemple, nous avons personnalisé le menu contextuel `file_options` pour supprimer les options `Delete` et `Edit` et remplacer l’option `Duplicate` par une option `Download`.

2. [Panneau de gauche](./examples/left_panel_container.ts)
Dans cet exemple, nous avons personnalisé le `left tab panel` pour qu’il y ait un autre `tab` intitulé &quot;EXTENSION TEST&quot;, et un `tab panel` correspondant qui possède un libellé : `Test Tab Panel`

3. [Panneau de droite](./examples/right_panel_container.ts)
Dans cet exemple, nous avons personnalisé le `right tab panel` pour qu’il y ait un autre `tab` intitulé &quot;EXTENSION TEST&quot;, et un `tab panel` correspondant qui a une étiquette : `New Tab Panel`

4. [Panneau Référentiel](./examples/repository_panel.ts)

5. [Barre d’outils](./examples/toolbar.ts)
Dans cet exemple, nous avons remplacé les boutons `Insert Element`, `Insert Paragraph`, `Insert Numbered List` et `Insert Bulleted List` par un seul bouton `More Insert Options` contenant tous ces boutons.

[Vérifier les exemples d’applications]

1. [Annotation Toolbox](./examples/review_app_examples/annotation_extension.ts)
Dans cet exemple, nous avons ajouté un autre bouton à la boîte à outils d’annotation qui ouvre la rubrique de révision actuelle dans AEM.

2. [Commentaire de révision](./examples/review_app_examples/review_comment.ts)
Dans cet exemple, nous avons ajouté le nom d’utilisateur aux informations sur l’utilisateur (qui comprennent le nom complet et le titre du commentateur), ajouté un identifiant de commentaire unique, une icône mailTo et ajouté des champs de saisie pour mentionner la gravité et la logique des commentaires.
Nous avons également ajouté un bouton `accept with modification` sur les commentaires du côté XMLEditor qui ouvre une boîte de dialogue.

3. [Réponse du commentaire](./examples/review_app_examples/comment_reply.ts)
Dans cet exemple, nous avons ajouté le nom d’utilisateur aux informations sur l’utilisateur (qui comprennent le nom complet et le titre du commentateur) et ajouté une icône mailTo dans l’en-tête du commentaire.

4. [Panneau de révision intégré](./examples/review_app_examples/inline_review_panel.ts)
Dans ce fichier, nous calculons et affectons l’identifiant de commentaire unique, mentionné dans les exemples `Review Comment` et `Comment Reply` .
   - La méthode `setCommentId` définit l’identifiant de commentaire unique sur chaque commentaire en fonction du nombre de commentaires.

   - `setUserInfo` définit la valeur de userInfo, à l’aide du nom complet et du titre de chaque commentaire.

   - `onNewCommentEvent` s’assure que la méthode `setUserInfo` est appelée pour chaque nouveau commentaire ou réponse.

   - La fonction `updatedProcessComments` s’exécute pour chaque nouvel événement de commentaire et s’assure que `setCommentId` est appelé si nous obtenons un nouvel événement de commentaire.

5. [Panneau des révisions des rubriques](./examples/review_app_examples/topic_reviews.ts) : ce fichier étend le [panneau de révision en ligne](./examples/review_app_examples/inline_review_panel.ts) de sorte que les personnalisations ajoutées fonctionnent également du côté de l’application de révision.

6. [Boîte de dialogue Accepter avec modification](./examples/review_app_examples/accept_with_modification_dialog.ts)
Il s’agit d’un exemple d’ajout de nouveaux widgets à l’application. Ici, nous avons créé une nouvelle boîte de dialogue, qui comporte deux champs de texte de saisie : `Revised Text` et `Adjudicator Comment Rationale`

7. [Enregistrer la révision](./examples/save_revision.ts)
Voici un exemple de mise à jour d’une boîte de dialogue existante. Nous y ajoutons un bouton pour la publication. Nous autorisons la modification du contenu de la boîte de dialogue. Reportez-vous à son json ici : [`save_revision`](./jsons/dialogs/save_revision.json)

![Boîte De Dialogue Accepter Avec Modification](./imgs/accept_with_modification_dialogue.png)

Voici le panneau de révision avant et après la personnalisation :

![Panneau de révision;](./imgs/review_panel.png)
![Boîte De Dialogue Accepter Avec Modification](./imgs/customised_review_panel.png)
