---
title: Publication de la table des matières à l’aide de NativePDF
description: Publication de la table des matières et d’autres listes d’applet pour votre carte d’utilisateur dita à l’aide de NativePDF
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: c551f0a8-f973-4c5a-bd34-f52890a91342
source-git-commit: 7638f3634ad45bbadda64ec6e3f706cbb65d696c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Générer la table des matières de Bookmap dans une publication PDF

## Configuration de votre carte d’utilisateur

Incluez l’élément `<toc>` :
Recherchez l’élément `<frontmatter>` de votre carte de navigation dans l’élément `<booklists>`.  Imbriquez un élément `<toc>` dans `<booklists>` comme suit :

```
<frontmatter>
  <booklists>
    <toc/>  <figurelist/>
    <tablelist/>
  </booklists>
</frontmatter>
```

La spécification DITA permet également de placer la table des matières et les listes de signets dans la section `<backmatter>`.


```
<backmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <indexlist/>
    </booklists>
  </backmatter>
```

Exemple de structure de bookmap avec table des matières , liste-figure et liste-tableau en préface et liste-index en arrière-plan.

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

La table des matières et les listes de signets sont automatiquement générées en fonction de la structure définie dans votre carte de pages.

Une fois votre carte d’utilisateur configurée, utilisez le PDF natif pour générer la sortie du PDF. Il traite la structure et les références du plan d’applet, y compris la table des matières et les listes de signets.

## Conception de la table des matières et son ordre dans PDF

La fonctionnalité de PDF natif offre une méthode pratique pour personnaliser la disposition et la conception de votre table des matières.

Vous pouvez contrôler la conception via une mise en page distincte pour la table des matières et les styles via layout.css.

L’ordre de la table des matières et des autres listes de signets en PDF est basé uniquement sur la structure de la carte des pages.

![toc](../assets/publishing/toc.png)


## Questions fréquentes

- ### Comment inclure la table des matières d’un Ditamap dans un PDF

Les cartes numériques elles-mêmes n’ont pas directement une table des matières comme le fait une carte des pages. Toutefois, les graphiques numériques jouent un rôle essentiel dans la définition de la structure de votre contenu et contribuent indirectement au processus de génération de la table des matières.

Si vous publiez Ditamap, alors Native PDF offre la fonctionnalité de génération automatique de la table des matières et de la liste des pages d’applet . Vous pouvez activer/désactiver la génération de la table des matières à ditamap à partir des paramètres Native PDF .

![Activer Désactiver la table des matières](../assets/publishing/pageorder.png)

## Ressources supplémentaires :

- [Documentation sur la mise en page de la page de conception de PDF native](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/install-guide/on-prem-ig/output-gen-config/config-native-pdf-publish/design-page-layout)
- [ Session d’experts pré-enregistrée des PDF natifs ](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/expert-session/native-pdf-publishing-essentials-feb23)

<br>
<br>

Post sur le [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) de la communauté AEM Guides pour toutes les requêtes.



