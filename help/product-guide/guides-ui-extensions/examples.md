---
sidebar_position: 8
source-git-commit: eb3fe92d36bc58a11e47f786a10d5938e2ed0184
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 0%

---


# Exemples

Dans ce package, nous avons également fourni quelques exemples de personnalisation (disponibles à l’adresse `guides_extension/src`) . Vous trouverez ci-dessous une brève description de chacun d&#39;entre eux.

1. [Menu contextuel](./../../src/file_options.ts)
Dans cet exemple, nous avons personnalisé la variable `file_options` pour supprimer le menu contextuel `Delete` et `Edit` et remplacez la variable `Duplicate` avec une `Download` .

2. [Panneau gauche](../../src/left_panel_container.ts)
Dans cet exemple, nous avons personnalisé la variable `left tab panel` pour avoir un autre`tab` intitulée &quot;EXTENSION DE TEST&quot;, et une `tab panel` qui possède un libellé : `Test Tab Panel`

3. [Panneau droit](../../src/right_panel_container.ts)
Dans cet exemple, nous avons personnalisé la variable `right tab panel` pour avoir un autre `tab` intitulée &quot;EXTENSION DE TEST&quot;, et une `tab panel` qui possède un libellé : `New Tab Panel`

4. [Panneau Référentiel](../../src/repository_panel.ts)

5. [Barre d’outils](../../src/toolbar.ts)
Dans cet exemple, nous avons remplacé le `Insert Element`, `Insert Paragraph`, `Insert Numbered List`, `Insert Bulleted List` boutons avec une seule `More Insert Options` contenant tous ces éléments.

[Vérification des exemples d’applications]

1. [Annotation Toolbox](../../src/review_app_examples/annotation_extension.ts)
Dans cet exemple, nous avons ajouté un autre bouton à la boîte à outils d’annotation qui ouvre la rubrique de révision actuelle dans AEM.

2. [Commentaire de révision](../../src/review_app_examples/review_comment.ts)
Dans cet exemple, nous avons ajouté le nom d’utilisateur aux informations sur l’utilisateur (qui comprennent le nom complet et le titre du commentateur), ajouté un identifiant de commentaire unique, une icône mailTo et ajouté des champs de saisie pour mentionner la gravité et la logique des commentaires.
Nous avons également ajouté une `accept with modification` sur les commentaires du côté XMLEditor qui ouvre une boîte de dialogue.

3. [Réponse du commentaire](../../src/review_app_examples/comment_reply.ts)
Dans cet exemple, nous avons ajouté le nom d’utilisateur aux informations sur l’utilisateur (qui comprennent le nom complet et le titre du commentateur) et ajouté une icône mailTo dans l’en-tête du commentaire.

4. [Panneau de révision en ligne](../../src/review_app_examples/inline_review_panel.ts)
Dans ce fichier, nous calculons et affectons l’identifiant de commentaire unique, mentionné dans la variable `Review Comment` et `Comment Reply` exemples.
   - La variable `setCommentId` définit l’identifiant unique du commentaire sur chaque commentaire en fonction du nombre de commentaires.

   - La variable `setUserInfo` définit la valeur de userInfo à l’aide du nom complet et du titre de chaque commentaire.

   - La variable `onNewCommentEvent` assure la `setUserInfo` est appelée pour chaque nouveau commentaire ou réponse.

   - La variable `updatedProcessComments` s’exécute pour chaque nouvel événement de commentaire et s’assure que `setCommentId` est appelé si nous obtenons un nouvel événement de commentaire.

5. [Panneau des révisions des rubriques](../../src/review_app_examples/topic_reviews.ts): ce fichier étend [Panneau de révision en ligne](../../src/review_app_examples/inline_review_panel.ts) afin que les personnalisations ajoutées fonctionnent également du côté de l’application de révision.

6. [Boîte de dialogue Accepter avec modification](../../src/review_app_examples/accept_with_modification_dialog.ts)
Il s’agit d’un exemple d’ajout de nouveaux widgets à l’application. Nous avons ici créé une nouvelle boîte de dialogue, qui comporte deux champs de texte de saisie : `Revised Text` et `Adjudicator Comment Rationale`

![Boîte De Dialogue Accepter Avec Modification](./imgs/accept_with_modification_dialogue.png)

Voici le panneau de révision avant et après la personnalisation :

![Panneau de révision;](./imgs/review_panel.png)
![Boîte De Dialogue Accepter Avec Modification](./imgs/customised_review_panel.png)
