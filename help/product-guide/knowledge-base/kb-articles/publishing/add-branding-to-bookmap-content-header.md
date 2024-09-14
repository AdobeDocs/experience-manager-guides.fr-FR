---
title: Ajout d’une valorisation de marque d’entreprise à la première page d’un PDF DITA
description: Obtenez une valorisation de marque de l’entreprise en intégrant la page de couverture et la page de chapitres, en veillant à ce que l’identité de l’entreprise s’affiche clairement en haut du contenu.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
source-git-commit: a9f8622dc5a2647bcff32c8895700d5c5933be4a
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# Ajout d’une valorisation de marque d’entreprise à la première page d’un PDF DITA

## Cet article traite des sujets suivants :

Pour obtenir une image de marque d’entreprise, fusionnez facilement la page FrontCover avec la page de chapitre, en veillant à ce que l’identité de l’entreprise s’affiche en haut du contenu.

- [Configuration du contenu](#set-up-your-content)
- [Apportez les modifications nécessaires au modèle de PDF](#create-necessary-changes-in-pdf-template)

**Avant :**

![Avant de corriger l’identité graphique : capture d’écran montrant la disposition d’un PDF prédéfini](../assets/publishing/branding-image1.png)
<br>
<br>

**Après :**

![Après correction de la marque : capture d’écran montrant la disposition du PDF post-marque](../assets/publishing/branding-image2.png)

## Configuration du contenu

Pour publier du contenu au format PDF, vous devez créer un Ditamap ou un Bookmap.

Exemple de structure Bookmap :

```
<bookmap>
  <title>My Bookmap Title </title>
  <frontmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <tablelist/>
    </booklists>
  </frontmatter>

  <chapter href="chapter1.ditamap">
  <chapter href="chapter2.ditamap">
  </chapter>

  <backmatter>
    <booklists>
      <indexlist/>
    </booklists>
  </backmatter>
</bookmap>
```

Exemple de structure Ditamap :

```
<map title="My map Title">

  <topicref href="topic1.dita" >
  </topicref>
  <topicref href="topic2.dita">
  </topicref>
  
</map>
```

Le FrontCover du PDF est automatiquement généré si Bookmap contient `<frontmatter>`.


## Apportez les modifications nécessaires au modèle de PDF

Dans cette section, nous allons configurer notre modèle. (Vous pouvez utiliser ou dupliquer le modèle high-tech pour commencer.)

### Configurez votre modèle :

- Accédez à votre modèle de PDF natif .
- Accédez à la mise en page de votre page FrontCover et modifiez-la.
- Ajoutez ici votre image de marque dans `data-region="content"`.
- Au besoin, ajoutez d’autres modifications nécessaires dans votre modèle de chapitre.
- Suivez maintenant les étapes ci-dessous en fonction de votre contenu.


#### Si vous utilisez Ditamap pour générer des PDF :

Lors de la publication d’un fichier DITAMAP, le PDF natif fournit la fonctionnalité permettant de générer automatiquement une page FrontCover. L’option permettant d’activer ou de désactiver la génération de pages FrontCover peut être configurée dans le modèle PDF natif .

Pour fusionner :
- Accédez à vos paramètres de modèle de PDF natif —> Ordre de mise en page
- Fusionnez maintenant FrontCover avec la page suivante, à savoir Chapitre et rubriques.
  ![Fusion de FrontCover avec chapitre : capture d’écran montrant les paramètres de modèle de PDF natif](../assets/publishing/branding-image3.png)
- Enregistrez le modèle, sélectionnez ce modèle pour votre paramètre prédéfini et publiez-le.


#### Si vous utilisez le signet d’applet pour la génération du PDF

Dans le cas d’une cartographie dynamique, la séquence de l’ordre de mise en page est contrôlée par la structure de la carte dynamique plutôt que par l’ordre du modèle.

Pour ce faire, nous utiliserons la fonctionnalité JavaScript d’NativePDF.

- Ajoutez sous JavaScript dans le dossier de ressources de votre modèle.

```
window.addEventListener('DOMContentLoaded', function () {
    window.pdfLayout.onAfterPagination(function () {
        var frontMatterWrappers = document.querySelectorAll('.rh-front-matter-wrapper');

        frontMatterWrappers.forEach(function(wrapper) {
            var contentDiv = wrapper.querySelector('div[data-region="content"]');
            var chapterBody = document.querySelector('.chapter-body');

            if (contentDiv && chapterBody) {
                chapterBody.insertBefore(contentDiv, chapterBody.firstChild);
            }

            wrapper.remove();
        });
    });
});
```

- Incluez ce JavaScript dans votre modèle de chapitre.
  ![Inclure JavaScript dans le modèle de chapitre : capture d’écran montrant l’entrée dans le modèle de PDF de mise en page](../assets/publishing/branding-image4.png)

- Activation de JavaScript à partir de votre option prédéfinie
  ![Activer le paramètre prédéfini JavaScript : capture d’écran montrant le paramètre prédéfini pour activer JavaScript](../assets/publishing/branding-image5.png)

- PUBLISH !

## Pièces jointes :

- [Téléchargez l’exemple de module de modèle de PDF pour afficher les modifications appliquées.](../assets/publishing/NativePDF_DemoTemplate.zip)
- [Téléchargez l’exemple de package de paramètres prédéfinis de PDF pour afficher les modifications appliquées.](../assets/publishing/Preset_Package.zip)


## Autres ressources :

- [Comment inclure la balise de la carte d’utilisateur DITA en PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Vidéo d’une session d’experts sur le PDF natif](../../expert-sessions/native-pdf-publishing-eamples-part1-june2023.md)

