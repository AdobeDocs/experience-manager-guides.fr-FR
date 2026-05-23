---
title: Publication de la table des matières à l’aide de NativePDF
description: Publication de la table des matières et d’autres listes de vos signets dita à l’aide de NativePDF
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: c551f0a8-f973-4c5a-bd34-f52890a91342
TQID: https://experienceleague.adobe.com/GyB4TpCF64rEGNgHVPKq4fUCBQsJjqh4jWA0CJC4A-0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 322
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

- [Documentation sur la mise en page de la conception native de PDF](https://experienceleague.adobe.com/fr/docs/experience-manager-guides/using/install-guide/on-prem-ig/output-gen-config/config-native-pdf-publish/design-page-layout)
- [Session d’expert préenregistrée de Native PDF Essentials](https://experienceleague.adobe.com/fr/docs/experience-manager-guides/using/knowledge-base/expert-session/native-pdf-publishing-essentials-feb23)

<br>
<br>

Publiez sur le [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation?profile.language=fr) de la communauté AEM Guides pour toute requête.



