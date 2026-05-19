---
title: Ajouter l'image de marque d'entreprise à la première page d'un PDF DITA
description: Valorisez l’image de marque de l’entreprise en intégrant la page de garde et la page de chapitre, en veillant à ce que l’identité de l’entreprise soit clairement affichée en haut du contenu.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: ab452529-3c7f-4057-a0f6-212b9f52a99d
TQID: https://experienceleague.adobe.com/6CGRK2QWFZ6nIXmIAQZy3lX7t4KYP2-HeyqlVW2-7eE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 422
ht-degree: 0%

---

# Ajouter l&#39;image de marque d&#39;entreprise à la première page d&#39;un PDF DITA

## Cet article couvre les sujets suivants :

Valorisation de l’image de marque de l’entreprise en fusionnant de manière transparente la page FrontCover avec la page de chapitre, en veillant à ce que l’identité de l’entreprise soit affichée de manière bien visible en haut du contenu.

- [Configurer le contenu](#set-up-your-content)
- [Effectuez les modifications nécessaires dans le modèle PDF](#create-necessary-changes-in-pdf-template)

**Avant:**

![Avant de corriger l’identité graphique : capture d’écran affichant la disposition PDF prémarquée](../assets/publishing/branding-image1.png)
<br>
<br>

**Après:**

![Après correction de l’identité graphique : capture d’écran montrant la disposition du PDF post-branding](../assets/publishing/branding-image2.png)

## Configurer le contenu

Pour publier du contenu au format PDF, vous devez créer une Ditamap ou une Bookmap.

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

La couverture avant de PDF est automatiquement générée si Bookmap contient des `<frontmatter>`.


## Effectuez les modifications nécessaires dans le modèle PDF

Dans cette section, nous allons configurer notre modèle. (Vous pouvez utiliser ou dupliquer le modèle de haute technologie pour commencer.)

### Configurez votre modèle :

- Accédez à votre modèle PDF natif .
- Accédez à la mise en page FrontCover et modifiez-la.
- Ajoutez ici votre image de marque dans `data-region="content"`.
- Ajoutez d’autres modifications nécessaires dans votre modèle de chapitre, le cas échéant.
- Suivez maintenant les étapes ci-dessous en fonction de votre contenu.


#### Si vous utilisez Ditamap pour la génération PDF :

Lors de la publication d’un DITAMAP, Native PDF permet de générer automatiquement une page FrontCover. L’option permettant d’activer ou de désactiver la génération de pages FrontCover peut être configurée dans le modèle PDF natif.

À fusionner :
- Accédez aux paramètres de votre modèle PDF natif > Ordre de disposition de la page .
- Fusionnez maintenant FrontCover avec la page suivante, c’est-à-dire les chapitres et rubriques.
  ![Fusion de FrontCover avec le chapitre : capture d’écran affichant les paramètres du modèle PDF natif](../assets/publishing/branding-image3.png)
- Enregistrez le modèle, sélectionnez ce modèle pour votre préréglage et publiez !


#### Si vous utilisez Bookmap pour la génération PDF

Dans le cas d&#39;un Bookmap, l&#39;ordre de mise en page est contrôlé par la structure du Bookmap plutôt que par l&#39;ordre du modèle.

Pour ce faire, pour Bookmap , nous utiliserons la fonctionnalité JavaScript de NativePDF.

- Ajoutez sous JavaScript dans le dossier de ressources de votre modèle

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
  ![Inclure JavaScript dans le modèle de chapitre : capture d’écran affichant l’entrée dans le modèle PDF de mise en page](../assets/publishing/branding-image4.png)

- Activation de JavaScript à partir de votre paramètre prédéfini
  ![Activer le paramètre prédéfini de JavaScript : capture d’écran affichant le paramètre prédéfini pour activer JavaScript](../assets/publishing/branding-image5.png)

- Publier !

## Pièces jointes :

- [Téléchargez l’exemple de package de modèle PDF pour afficher les modifications appliquées.](../assets/publishing/NativePDF_DemoTemplate.zip)
- [Téléchargez l’exemple de package de paramètres prédéfinis PDF pour afficher les modifications appliquées.](../assets/publishing/Preset_Package.zip)


## Autres ressources :

- [Comment inclure la table des matières de DITA Bookmap dans PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Vidéo de session d’experts sur le PDF natif](../../expert-sessions/native-pdf-publishing-eamples-part1-june2023.md)
