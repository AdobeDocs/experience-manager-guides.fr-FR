---
title: Publication de la table des matières à l’aide de NativePDF
description: Publication de la table des matières et d’autres listes de vos signets dita à l’aide de NativePDF
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: c551f0a8-f973-4c5a-bd34-f52890a91342
source-git-commit: 9c53ac725618db1164b0ed310a47b258a7224778
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Générer la table des matières de la liasse dans la publication PDF

## Configurer votre plan

Incluez l’élément `<toc>` :
Dans l’élément `<frontmatter>` de votre carte, recherchez l’élément `<booklists>`.  Imbriquez un élément `<toc>` à l’intérieur de `<booklists>` comme suit :

```
<frontmatter>
  <booklists>
    <toc/>  <figurelist/>
    <tablelist/>
  </booklists>
</frontmatter>
```

La spécification DITA permet également de placer la table des matières et les listes de livres dans la section `<backmatter>`.


```
<backmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <indexlist/>
    </booklists>
  </backmatter>
```

Exemple de structure de bookmap avec TOC , figure-list et table-list dans frontend et index-list dans backMATTER.

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

La table des matières et les listes de livres sont automatiquement générées en fonction de la structure définie dans votre bookmap.

Une fois votre bookmap configuré, utilisez le PDF natif pour générer la sortie PDF. Il traite la structure et les références de la carte, y compris la table des matières et les listes de livres.

## Conception de la table des matières et ordre dans PDF

La fonctionnalité native de PDF offre une méthode pratique pour personnaliser la mise en page et la conception de votre table des matières.

Vous pouvez contrôler la conception via une mise en page distincte pour la table des matières et les styles via layout.css.

La table des matières et l’ordre des autres listes de livres dans PDF reposent uniquement sur la structure de la carte des livres.

![table des matières](../assets/publishing/toc.png)


## Questions fréquentes

### Comment inclure une table des matières Ditamap dans un PDF

Les diamaps eux-mêmes n&#39;ont pas directement de table des matières (TOC) comme un bookmap. Cependant, les diamaps jouent un rôle essentiel dans la définition de la structure de votre contenu et contribuent indirectement au processus de génération de la table des matières.

Si vous publiez Ditamap, Native PDF offre la fonctionnalité de génération automatique de la table des matières et de la liste de livres . Vous pouvez activer/désactiver la génération de la table des matières à ditamap à partir des paramètres Native PDF.

![Activer Désactiver la table des matières](../assets/publishing/pageorder.png)

## Ressources supplémentaires :

- [Documentation de mise en page de la conception native de PDF](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/install-guide/on-prem-ig/output-gen-config/config-native-pdf-publish/design-page-layout)
- [Session d’expert préenregistrée pour Native PDF essentials](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/expert-session/native-pdf-publishing-essentials-feb23)

<br>
<br>

Publiez sur le [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) de la communauté AEM Guides pour toute requête.



