---
title: Masquez l’option Créer une carte numérique dans les options de menu contextuel Dossier pour des utilisateurs ou des groupes spécifiques.
description: Découvrez comment personnaliser l’éditeur web en masquant l’option « DitaMap » dans le menu contextuel du dossier pour des utilisateurs/groupes spécifiques
exl-id: 796bfe3a-3950-4ade-9215-c33534791055
TQID: https://experienceleague.adobe.com/fAMBEOKlPA4KHsE81zfI-6EJ6zwaQOgRfx0w-cx-mmw
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 444
ht-degree: 1%

---

# Afficher/masquer « Créer DitaMAP » dans le menu contextuel du dossier dans l’éditeur web

Dans cet article, nous allons apprendre à personnaliser l’éditeur de guides pour masquer ou afficher l’option « Créer une carte numérique » dans le menu contextuel de dossier en fonction des autorisations d’utilisateur/de groupe.
Dans ce cas d’utilisation, nous masquerons cette option pour tous les utilisateurs non auteurs.

## Conditions préalables

Nous utiliserons le package d’extension AEM Guides qui vous permet de personnaliser l’interface utilisateur de votre application en fonction de vos besoins.
Veuillez parcourir cette [documentation](https://github.com/adobe/guides-extension/tree/main) pour obtenir plus d’informations sur le fonctionnement de Guides Extension Framework.

Commençons maintenant et apprenons à personnaliser le menu contextuel du dossier pour masquer cette option à tous les utilisateurs non auteurs.

Comme vous pouvez le voir dans le fragment de code ci-dessous, l’option « Créer un DitaMap » est visible pour un utilisateur auteur.

![Afficher l’option Créer DitaMap ](../../../assets/authoring/ditamap-show-author.png)

Voyons maintenant comment masquer cette option à l’aide de Guides Extension Framework.

## Étapes de mise en œuvre

L’implémentation est divisée en plusieurs parties :

- **Modifications dans le contrôleur Folder_options**

  Chaque menu contextuel est associé à un ID de contrôleur. Ce contrôleur gère la fonctionnalité sur événement pour les différentes options du menu contextuel.

  Dans cet exemple, nous allons personnaliser le menu contextuel du dossier pour masquer l’option « Créer un DitaMap » pour les non-auteurs. Pour ce faire, nous apporterons des modifications au fichier folder_options.ts situé sous /src dans le référentiel de la structure d’extension guides.

  Nous utilisons « viewState » comme « REPLACE » pour masquer cette option du menu contextuel.
Nous appelons un nouveau widget dans ce dossier_options via la clé &#39;id&#39;.

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

- **Création d’un nouveau widget pour gérer la logique**

  Une nouvelle création de widget (customoptions.ts) est nécessaire pour écrire la logique afin de masquer cette option pour les utilisateurs non auteurs uniquement. Pour ce faire, nous avons utilisé la clé « show » qui agit comme un bouton dans notre structure JSON.

  Vous pouvez écrire votre propre servlet externe pour vérifier les détails du groupe. Vous pouvez ainsi personnaliser les options de menu des dossiers pour votre groupe personnalisé.
Dans cet exemple, nous avons exploité l’appel « rolesapi » d’AEM prêt à l’emploi pour récupérer les détails de l’utilisateur et définir la réponse dans « isAuthor », comme illustré dans les fragments de code ci-dessus.

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

Grâce à cela, nous sommes en mesure de masquer le bouton avec le libellé comme « Carte numérique » en fonction de la valeur de « show ».

Nous avons ajouté un contrôleur pour définir l&#39;attribut &#39;isAuthor&#39; dans le modèle. Pour ce faire, utilisez la syntaxe suivante dans le contrôleur.

```typescript
this.model.extraProps.set("key", value);
```

Ici, la clé est « isAuthor » et la valeur est la réponse de l’appel rolesapi.
Nous avons également défini l’événement « createNewDitaMap » pour activer l’option Créer DitaMap (pour les utilisateurs auteurs).

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

  Importez les fichiers folder_options.ts et customoptions.ts dans le fichier index.ts sous /src.

## Tests

- Connectez-vous à AEM avec un utilisateur qui ne fait pas partie du groupe auteurs . L’option Créer une DitaMap est masquée dans le menu contextuel de n’importe quel dossier, comme illustré ci-dessous.
Ce cas d’utilisation a été ajouté à GIT. Consultez les ressources associées ci-dessous.

![Masquer l’option Créer DitaMap ](../../../assets/authoring/ditamap-hide-non-author.png)

### Ressources connexes

- **Référentiel de base du framework d’extension** - [GIT](https://github.com/adobe/guides-extension/tree/main)

- **Documentation** - [sur Experience League](../../../../../guides-ui-extensions/aem_guides_framework/basic-customisation.md)

- **Cas d’utilisation courants documentés** - [sur Experience League](../../../../../guides-ui-extensions/aem_guides_framework/jui-framework.md)

- **Référentiel public avec exemples** - [sur GIT](https://github.com/adobe/guides-extension/tree/sc-expert-session). Reportez-vous à la branche sc-expert-session .

```

```
