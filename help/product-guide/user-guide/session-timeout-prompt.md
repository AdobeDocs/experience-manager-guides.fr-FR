---
title: Présentation des temporisations de session dans Experience Manager Guides
description: Découvrez les délais d’expiration des sessions dans Experience Manager Guides.
feature: Authoring, Publishing
role: User
source-git-commit: a6e015817bc9a964e3ca6a83c50089e7fabcdd94
workflow-type: tm+mt
source-wordcount: '247'
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





