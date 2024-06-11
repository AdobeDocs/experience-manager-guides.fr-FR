---
title: Personnalisation
description: Personnalisation de l’application de révision
role: User, Admin
exl-id: 9f6a4e9f-fc13-40b5-a30f-151c94faff81
source-git-commit: 4f00d6b7ad45636618bafe92e643b3e288ec2643
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Personnalisation de l’application de révision

Pour faciliter la personnalisation de l’application de révision, nous avons fourni quelques crochets répertoriés et expliqués ci-dessous :

## Révision-Commentaire

- id: `review_comment`
- hook : `this.updateExtraProps`:

Comme décrit [here](../../aem_guides_framework/basic-customisation.md), tout nouvel attribut ajouté pendant la personnalisation passe sous `this.model.extraProps`. La méthode `updateExtraProps` vous permet d’ajouter des attributs à un commentaire de révision, en gérant la mise à jour et le stockage de l’attribut ajouté sur le serveur.

### Exemple d’utilisation

Par exemple, si vous souhaitez ajouter des champs `commentRationale` et `severity` à vos commentaires.
Mettons à jour la variable `commentRationale` &quot;C&#39;est une phrase importante.&quot; et la variable `severity` à &quot;CRITIQUE&quot;.
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

- id: `inline_review_panel`

1. hook : `onNewCommentEvent`
Le crochet `onNewCommentEvent` vous permet de lancer un événement ou d’appeler une méthode sur un nouveau commentaire ou événement de réponse.
Les arguments reçus dans la variable `onNewCommentEvent` inclure :
   - events : l’événement de commentaire/réponse qui a été distribué.
   - newComment : booléen Si l’événement distribué était un nouvel événement de commentaire, par exemple : `highlight`, `insertion`, `deletion`, `sticky note comment`
   - newReply : booléen Si l’événement distribué était un nouvel événement de réponse.

2. hook : `sendExtraProps`

Ce point d’extension est utile si vous souhaitez étendre une `event` et envoyer `extraProps` dans le panneau de révision en ligne. Nous allons expliquer l&#39;utilisation de ces deux points d&#39;extension ci-dessous.

### Exemple de panneau de révision intégré

Dites que nous voulons envoyer un extraProp, `userInfo`, chaque fois qu’un nouveau commentaire ou une nouvelle réponse est distribué. Maintenant, cela sera effectué via le panneau de révision intégré, mais nous n’avons pas la référence au commentaireId du commentaire nouvellement généré. Pour ce faire, nous pouvons écrire le code suivant.

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
    setUserInfo(event) {
      this.loader?.getUserInfo(event.user).subscribe(userData => {
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

Le crochet `updateExtraProps` appelle par nature le point d’extension `sendExtraProps`, alors quand utiliser quoi ?

Nous utilisons `updateExtraProps` dans le `review_comment` contrôleur, qui possède déjà le commentaire `id` et par conséquent, il vous suffit de mentionner le `extraProps.`

La variable `inline_review_panel` toutefois, n’a pas accès à l’identifiant du commentaire. par conséquent, chaque fois que vous devez distribuer un événement à partir du panneau de révision intégré, la variable `sendExtraProps` sera pratique.
