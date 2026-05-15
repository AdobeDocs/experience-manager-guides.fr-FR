---
title: Présentation des temporisations de session dans Experience Manager Guides
description: Découvrez les délais d’expiration des sessions dans Experience Manager Guides.
feature: Authoring, Publishing
role: User
exl-id: f09b1215-4753-4dfd-89ef-1629257e5efe
TQID: https://experienceleague.adobe.com/nrxkVxSUooy2-08PaUp1pjiH8w2kBBNGC9efarvepbQ
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 249
ht-degree: 0%

---

# Pourquoi Experience Manager Guides me déconnecte-t-il après un certain temps ?

Experience Manager Guides termine une session utilisateur après une période d’inactivité définie (délai d’inactivité). Cette fonctionnalité de déconnexion automatique est configurée dans Adobe Experience Manager. Lorsque la session expire, une alerte pop-up s’affiche pour informer l’utilisateur ou l’utilisatrice de la session expirée. Cette alerte empêche l’utilisateur d’apporter d’autres modifications au contenu.

**Comment fonctionne la temporisation de session ?**

Experience Manager Guides envoie une requête en arrière-plan `token.json` toutes les 30 secondes pour valider la session. Si la session est toujours active, un jeton valide est renvoyé. Si la session a expiré en raison d’une période d’inactivité, un jeton vide est renvoyé et la session est considérée comme inactive.

**Que se passe-t-il lorsque la session expire ?**

Lorsqu’une session inactive est détectée :

- Une alerte contextuelle s’affiche pour vous informer que vous avez été déconnecté.

  ![](images/sign-out-prompt.png)

- L’alerte désactive toutes les interactions avec l’application.

- Sélectionner **OK** actualise le navigateur et vous redirige vers la page de connexion.
- Lors de la connexion, vous êtes redirigé vers la dernière page ouverte de Experience Manager Guides.

**Étapes suivantes**

L’alerte d’expiration de session permet de prévenir les pertes de données en vous empêchant d’apporter des modifications à l’application au cours d’une session inactive. Pour éviter toute perte accidentelle de contenu, il est recommandé d’enregistrer régulièrement votre travail dans l’éditeur, en particulier avant de quitter votre système pendant une période prolongée.
