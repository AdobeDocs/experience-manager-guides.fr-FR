---
title: Publication de la table des matières à l’aide de NativePDF
description: Publication de la table des matières et d’autres listes d’applet pour votre carte d’utilisateur dita à l’aide de NativePDF
feature: Native PDF Output
role: User, Admin
source-git-commit: 6ccaef5d35d492fe8dbe0f8b52af8d11258f3d2a
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# Générer la table des matières de Bookmap dans une publication PDF

## Configuration de votre carte d’utilisateur

Inclure la variable `<toc>`  élément : dans la bibliothèque `<frontmatter>`, recherchez l’élément `<booklists>` élément .  Imbriquer une `<toc>` element inside `<booklists>` comme ceci :

```
<frontmatter>
  <booklists>
    <toc/>  <figurelist/>
    <tablelist/>
  </booklists>
</frontmatter>
```

La spécification DITA permet de placer la table des matières et les listes de signets dans `<backmatter>` également.


```
<backmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <indexlist/>
    </booklists>
  </backmatter>
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
- [Session d’experts pré-enregistrée sur l’essentiel pour les PDF natifs](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/expert-session/native-pdf-publishing-essentials-feb23)

<br>
<br>

Posez vos questions sur la communauté AEM Guides [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) pour toutes les requêtes.


