---
title: Personnalisation
description: Personnalisation de l’application de révision
role: User, Admin
exl-id: 9f6a4e9f-fc13-40b5-a30f-151c94faff81
TQID: https://experienceleague.adobe.com/s98wa8vFTKBHZ--qCeFjmynYwr3BRVOekxOlGJFIqds
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 403
ht-degree: 0%

---

# Personnalisation de l’application de révision

Pour faciliter la personnalisation de l’application de révision, nous avons fourni quelques points d’extension répertoriés et expliqués ci-dessous :

## Review-Comment

- id : `review_comment`
- hook : `this.next('updateExtraProps')` :

Comme expliqué [ici](../../aem_guides_framework/basic-customisation.md), tout nouvel attribut ajouté lors de la personnalisation est `this.model.extraProps`. La méthode vous permet `updateExtraProps` d’ajouter des attributs à un commentaire de révision, en gérant également la mise à jour et le stockage de l’attribut ajouté sur le serveur.

### Exemple d’utilisation

Supposons, par exemple, que vous souhaitiez ajouter des champs `commentRationale` et `severity` à vos commentaires.
Mettons à jour la `commentRationale` en disant : « Ceci est une phrase importante ». et la `severity` à « CRITIQUE ».
Pour ce faire, utilisez la syntaxe suivante :

```typescript
  this.next('updateExtraProps', {
    'commentRationale': 'This is an important sentence.',
    'severity': 'CRITICAL'
  })
```

Le fragment de code ci-dessus gère la mise à jour et l’enregistrement des valeurs. Les valeurs enregistrées peuvent être rendues dans l’interface utilisateur en définissant la vue.

```JSON
{
    "component" : "label",
    "label": "@extraProps.commentRationale"
}
```

## Panneau de révision intégré

- id : `inline_review_panel`

1. hook : `onNewCommentEvent`
Le `onNewCommentEvent` de hook vous permet de lancer un événement ou d’appeler une méthode sur un nouvel événement de commentaire ou de réponse.
Les arguments reçus dans le `onNewCommentEvent` sont les suivants :
   - événements : événement commentaire/réponse qui a été distribué.
   - newComment : booléen
Si l’événement distribué était un nouvel événement de commentaire, c’est-à-dire `highlight`, `insertion`, `deletion`, `sticky note comment`
   - newReply : booléen
Si l’événement distribué était un nouvel événement de réponse.

2. hook : `sendExtraProps`

Ce hook est utile si vous souhaitez étendre un `event` et envoyer des `extraProps` à partir du panneau de révision intégré. Nous expliquerons ci-dessous l’utilisation de ces deux points d’extension.

### Exemple de panneau de révision intégré

Supposons que nous souhaitions envoyer un extraProp, `userInfo`, chaque fois qu’un nouveau commentaire ou une nouvelle réponse est envoyé. Désormais, cette opération s’effectue via le panneau de révision intégré. Toutefois, nous n’avons pas la référence à l’ID de commentaire du commentaire nouvellement généré. Pour ce faire, nous pouvons donc écrire le code suivant.

```typescript
    onNewCommentEvent(args){
      const events = _.get(args, "events")
      const currTopicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC) || this.getValue('currTopicIndex') || "0"
      const event = _.get(_.get(events, currTopicIndex), '0')
      const newComment = _.get(args, 'newComment')
      const newReply = _.get(args, 'newReply')
      if ((newComment || newReply) && event) {
        this.next('setUserInfo', event)
      }
    },
```

Dans l’extrait de code ci-dessus, nous vérifions si l’événement distribué était un nouveau commentaire ou une nouvelle réponse. En cas de nouveau commentaire ou réponse, nous appelons la méthode `setUserInfo`

```typescript
    const getUserInfo = (userId) => {
      return $.ajax({
        url: '/bin/dxml/xmleditor/userinfo',
        data: {
          username: userId,
        },
        success: (data) => {
          return data
        }
      })
    }

    setUserInfo(event) {
      getUserInfo(event.user).done(userData => {
        const extraProps = {
          "userFirstName": userData?.givenName || '',
          "userLastName": userData?.familyName || '',
          "userTitle": userData?.title || '',
          "userJobTitle": userData?.jobTitle || '',
          'userEmail': userData?.email || '',
        }
        const data = {... event, extraProps}
        this.next(
          'sendExtraProps',
          data
        )
      })
    },
```

Dans la méthode ci-dessus, nous étendons l’événement pour envoyer des extraProps qui incluent le prénom, l’adresse e-mail, le titre, etc. de l’utilisateur. En étendant l’événement de cette manière, vous vous assurez que les extraProps sont envoyés avec le commentId correct, et qu’ils sont associés au bon commentaire.

Le hook `updateExtraProps` appelle intrinsèquement le hook `sendExtraProps`, alors quand utiliser quoi ?

Nous utilisons `updateExtraProps` dans le contrôleur de `review_comment`, qui a déjà le `id` du commentaire et donc vous avez juste besoin de mentionner le `extraProps.`

Le `inline_review_panel` n’a toutefois pas accès à l’identifiant du commentaire. Par conséquent, chaque fois que vous devez envoyer un événement à partir du panneau de révision intégré, le `sendExtraProps` est pratique.
