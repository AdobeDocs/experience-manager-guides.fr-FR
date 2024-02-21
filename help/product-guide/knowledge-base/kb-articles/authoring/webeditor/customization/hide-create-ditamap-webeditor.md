---
title: Masquez l’option Créer DitaMap dans les options du menu contextuel Dossier pour des utilisateurs ou des groupes spécifiques.
description: Découvrez comment personnaliser l’éditeur de weets en masquant l’option "DitaMap" dans le menu contextuel du dossier pour des utilisateurs/groupes spécifiques.
source-git-commit: ea8fb646287f68676b6530b4cc5f56e7ba2d9b0c
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---


# Afficher/masquer &quot;Créer DitaMAP&quot; à partir du menu contextuel du dossier dans l’éditeur de texte web

Dans cet article, nous allons apprendre à personnaliser l’éditeur Web de guides afin de masquer ou d’afficher l’option &quot;Créer une carte dynamique&quot; dans le menu contextuel du dossier en fonction des autorisations de l’utilisateur/du groupe.
Dans ce cas d’utilisation, cette option sera masquée pour tous les utilisateurs non-auteurs.

## Prérequis

Nous utiliserons le package d’extension AEM Guides qui vous permet de personnaliser l’interface utilisateur de votre application selon vos besoins.
Veuillez passer en revue ceci [documentation](https://github.com/adobe/guides-extension/tree/main) pour obtenir plus d’informations sur le fonctionnement de Guides Extension Framework.

Commençons maintenant et apprenons à personnaliser le menu contextuel du dossier afin de masquer cette option pour tous les utilisateurs non-auteurs.

Comme vous pouvez le voir sous le fragment de code, l’option &quot;créer DitaMap&quot; est visible pour un utilisateur auteur.

![Afficher l’option Créer DitaMap](../../../assets/authoring/ditamap-show-author.png)

Voyons maintenant comment masquer cette option à l’aide de Guides Extension Framework.

## Procédure de mise en oeuvre

L’implémentation est divisée en plusieurs parties :

- **Changements dans le contrôleur Folder_options**

  Un identifiant de contrôleur est associé à chaque menu contextuel. Ce contrôleur gère la fonctionnalité sur événement pour les différentes options de menu contextuel.

  Dans cet exemple, nous allons personnaliser le menu contextuel du dossier pour masquer l’option &quot;Créer une carte dynamique&quot; pour les non-auteurs. Pour ce faire, nous allons apporter des modifications au fichier folder_options.ts présent sous /src dans le référentiel de structure de l’extension des guides.

  &quot;viewState&quot; est utilisé comme &quot;REPLACE&quot; pour masquer cette option dans le menu contextuel.
Nous appelons un nouveau widget dans cette option folder_options via la clé &quot;id&quot;.

```typescript
const folderOptions = {
  id: "folder_options",
  contextMenuWidget: "repository_panel",
  view: {
    items: [
      {
        component: "widget",
        id: "customditamap",
        target: {
          key: "displayName",
          value: "DITA Map",
          viewState: VIEW_STATE.REPLACE,
        },
      },
    ],
  },
};
```

- **Création d’un widget pour gérer la logique**

  Une nouvelle création de widgets (customoptions.ts) est nécessaire pour écrire la logique afin de masquer cette option pour les utilisateurs non-auteurs uniquement. Pour ce faire, nous avons utilisé la clé &quot;show&quot; qui agit comme une bascule dans notre structure JSON.

  Vous pouvez écrire votre propre servlet externe pour vérifier les détails du groupe. Vous pouvez ainsi personnaliser les options de menu de dossiers de votre groupe personnalisé.
Dans cet exemple, nous avons utilisé l’appel &quot;rolesapi&quot; de l’AEM OOTB pour récupérer les détails de l’utilisateur et définir la réponse dans &quot;isAuthor&quot;, comme illustré ci-dessus dans les fragments de code.

```typescript
const folderOptions = {
  id: "customditamap",
  view: {
    component: "button",
    quiet: true,
    icon: "breakdownAdd",
    label: "DITA Map",
    "on-click": "createNewDitaMap",
    show: "@extraProps.isAuthor",
  },
};
```

Grâce à cela, nous pouvons masquer le bouton avec le libellé &quot;Carte Dita&quot; en fonction de la valeur de &quot;show&quot;.

Nous avons ajouté un contrôleur pour définir l’attribut &#39;isAuthor&#39; dans le modèle, cela peut être effectué à l’aide de la syntaxe suivante dans le contrôleur.

```typescript
this.model.extraProps.set("key", value);
```

Ici, la clé est &#39;isAuthor&#39; et la valeur est la réponse de l’appel rolesapi.
Nous avons également défini l’événement &#39;createNewDitaMap&#39; pour activer l’option create DitaMap (pour les utilisateurs de création).

```typescript
controller: {
    init: function () {
      this.model.extraProps.set("isAuthor", false);

      rolesApiResponse.then((result) => {
        console.log(result);
        this.model.extraProps.set(
          "isAuthor",
          result["/content/dam"].roles.authors
        );

        console.log("testresult" + result["/content/dam"].roles.authors);
      });
    },
    createNewDitaMap() {
      repositoryController && repositoryController.next("create_new.map");
    },
  },
```

- **Ajout du code personnalisé**

  Importez le fichier folder_options.ts et customoptions.ts dans le fichier index.ts sous /src.

## Tests

- Connectez-vous à AEM avec un utilisateur qui ne fait pas partie du groupe d’auteurs. L’option Créer une carte dynamique est masquée dans le menu contextuel de n’importe quel dossier, comme illustré ci-dessous.
Ce cas pratique a été ajouté à GIT. Veuillez trouver les ressources connexes ci-dessous.

![Masquer l’option Créer DitaMap](../../../assets/authoring/ditamap-hide-non-author.png)

### Ressources connexes

- **Référentiel de base de la structure d’extension** - [GIT](https://github.com/adobe/guides-extension/tree/main)

- **Documentation** - [sur Experience League](../../../../../guides-ui-extensions/aem_guides_framework/basic-customisation.md)

- **Cas d’utilisation courants documentés** - [sur Experience League](../../../../../guides-ui-extensions/aem_guides_framework/jui-framework.md)

- **Référentiel public avec exemples** - [sur GIT](https://github.com/adobe/guides-extension/tree/sc-expert-session). Reportez-vous à la branche sc-expert-session

```

```
