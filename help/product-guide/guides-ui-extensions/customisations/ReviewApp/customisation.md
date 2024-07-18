---
title: Personnalisation
description: Personnalisation de l’application de révision
role: User, Admin
exl-id: 9f6a4e9f-fc13-40b5-a30f-151c94faff81
source-git-commit: 492f72768e0de74a91eb7acc9db8264e21bfc810
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Personnalisation de l’application de révision

Pour faciliter la personnalisation de l’application de révision, nous avons fourni quelques crochets répertoriés et expliqués ci-dessous :

## Révision-Commentaire

- id : `review_comment`
- hook : `this.next('updateExtraProps')` :

Comme mentionné [ici](../../aem_guides_framework/basic-customisation.md), tout nouvel attribut ajouté lors de la personnalisation passe sous `this.model.extraProps`. La méthode `updateExtraProps` vous permet d’ajouter des attributs à un commentaire de révision, en gérant également la mise à jour et le stockage de l’attribut ajouté sur le serveur.

### Exemple d’utilisation

Par exemple, vous souhaitez ajouter des champs `commentRationale` et `severity` à vos commentaires.
Mettons à jour le `commentRationale` en &quot;C&#39;est une phrase importante.&quot; et le `severity` sur &quot;CRITICAL&quot;.
Vous pouvez le faire en utilisant la syntaxe :

```typescript
  this.next('updateExtraProps', {
    'commentRationale': 'This is an important sentence.',
    'severity': 'CRITICAL'
  })
```

Le fragment de code ci-dessus va gérer la mise à jour et l’enregistrement des valeurs. Les valeurs enregistrées peuvent être rendues sur l’interface utilisateur en définissant la vue.

```JSON
{
    "component" : "label",
    "label": "@extraProps.commentRationale"
}
```

## Panneau de révision en ligne

- id : `inline_review_panel`

1. hook : `onNewCommentEvent`
Le point d’extension `onNewCommentEvent` vous permet de lancer un événement ou d’appeler une méthode sur un nouveau commentaire ou événement de réponse.
Les arguments reçus dans le `onNewCommentEvent` incluent :
   - events : l’événement de commentaire/réponse qui a été distribué.
   - newComment : boolean
Si l’événement distribué était un nouvel événement de commentaire, c’est-à-dire `highlight`, `insertion`, `deletion`, `sticky note comment`
   - newReply: boolean
Si l’événement distribué était un nouvel événement de réponse.

2. hook : `sendExtraProps`

Ce point d’extension est bénéfique si vous souhaitez étendre un `event` et envoyer `extraProps` à partir du panneau de révision en ligne. Nous allons expliquer l&#39;utilisation de ces deux points d&#39;extension ci-dessous.

### Exemple de panneau de révision intégré

Supposons que nous souhaitions envoyer un extraProp, `userInfo`, chaque fois qu’un nouveau commentaire ou une nouvelle réponse est distribué. Maintenant, cela sera effectué via le panneau de révision intégré, mais nous n’avons pas la référence au commentaireId du commentaire nouvellement généré. Pour ce faire, nous pouvons écrire le code suivant.

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

Dans le fragment de code ci-dessus, nous vérifions si l’événement distribué était un nouveau commentaire ou une nouvelle réponse. En cas de nouveau commentaire ou réponse, nous appelons la méthode `setUserInfo`

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

Dans la méthode ci-dessus, nous étendons l’événement pour envoyer extraProps qui inclut le prénom, l’email, le titre de l’utilisateur, etc. L’extension de l’événement de cette manière garantit que extraProps est envoyé avec le commentaireId correct, en s’assurant qu’il est joint au commentaire approprié.

Le point d&#39;extension `updateExtraProps` appelle par nature le point d&#39;extension `sendExtraProps`, donc quand utiliser quoi ?

Nous utilisons `updateExtraProps` dans le contrôleur `review_comment`, qui possède déjà le `id` du commentaire et par conséquent vous devez simplement mentionner le `extraProps.`

`inline_review_panel` n’a toutefois pas accès à l’ID du commentaire. Par conséquent, chaque fois que vous devez distribuer un événement à partir du panneau de révision intégré, `sendExtraProps` sera pratique.
