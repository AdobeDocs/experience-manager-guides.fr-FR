---
title: Notes de mise à jour | Nouveautés de la version Adobe Experience Manager Guides 2024.10.0
description: Découvrez les fonctionnalités nouvelles et améliorées de la version 2024.10.0 d’Adobe Experience Manager Guides
role: Leader
exl-id: 13135928-f0fe-4147-83ac-8b06ca241ed7
TQID: https://experienceleague.adobe.com/PFM-i4fVsgpBUJy4BeOpvyY4GWxGS8F24jEGb0Y2oiI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 1026
ht-degree: 1%

---

# Nouveautés de la version 2024.10.0 (octobre 2024)

Cet article couvre les nouvelles fonctionnalités améliorées introduites dans la version 2024.10.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour connaître la liste des problèmes résolus dans cette version, voir la section [Problèmes résolus dans la version 2024.10.0](fixed-issues-2024-10-0.md).

Découvrez les [instructions de mise à niveau pour la version 2024.10.0](../release-info/upgrade-instructions-2024-10-0.md).


## Améliorations de la publication

Les améliorations de publication de contenu suivantes ont été apportées à la version 2024.10.0 :




### Améliorations apportées à la publication de fragments de contenu

Experience Manager Guides propose également des améliorations utiles dans les fragments de contenu :

- Experience Manager Guides vous permet de publier une rubrique ou ses éléments dans un fragment de contenu.

- Vous pouvez publier et afficher les fragments de contenu d’une rubrique à partir de la section **Sorties** de la section **Propriétés du fichier**.


- Vous pouvez facilement créer des variations de fragment de contenu en filtrant le contenu avec des conditions lors de la publication dans un fragment de contenu.

- Utilisez la nouvelle interface de mappage pour sélectionner et publier facilement les éléments dans un fragment de contenu.

Désormais, la publication des fragments de contenu ne remplace que le contenu mappé au lieu de remplacer le fragment de contenu complet. Cette fonctionnalité permet à un fragment de contenu de contenir des données provenant de plusieurs sources, telles que plusieurs rubriques ou l’éditeur de fragment de contenu.

![Ajoutez le modèle de fragment et les détails de mappage dans la boîte de dialogue Publier en tant que fragment de contenu](assets/content-fragment-mapping.png)

Pour plus d’informations, voir [Publication de fragments de contenu](../user-guide/publish-content-fragment.md).


### Publication de variantes de fragments d’expérience en fonction de filtres de condition

Experience Manager Guides vous permet de publier une rubrique ou ses éléments dans un fragment d’expérience. Désormais, vous pouvez également créer des variantes de fragments d’expérience à l’aide de la condition ou des filtres DITAVAL et les réutiliser sur différents canaux ou pour différentes audiences.

En savoir plus sur la [Publication de fragments d’expérience](../user-guide/publish-experience-fragment.md).


### Réorganisation du paramètre prédéfini d’AEM Sites pour faciliter son utilisation

Les paramètres ont été réorganisés pour vous aider à configurer rapidement le paramètre prédéfini de sortie et à générer la sortie AEM Sites.
Vous pouvez créer les paramètres prédéfinis AEM Sites existants en sélectionnant l’option **Utiliser le mappage de composant hérité** dans la boîte de dialogue **Nouveau paramètre prédéfini de sortie**.

Affichez les onglets **Général**, **Contenu** et **Référence croisée** dans les paramètres prédéfinis AEM Sites :
- **Général** : contient les configurations générales pour générer la sortie. Vous pouvez spécifier le site et le chemin de sortie, supprimer ou remplacer des pages de sortie existantes, supprimer les pages générées précédemment pour les rubriques supprimées, sélectionner le modèle de conception, conserver les fichiers temporaires et spécifier le workflow de post-génération.
- **Contenu** : contient les paramètres applicables au contenu pour la génération de la sortie. Vous pouvez sélectionner les filtres, la ligne de base du plan DITA et les propriétés de métadonnées pour la publication.
- **Références cross-map** : cette liste contient des rubriques contenant des références cross-map avec une portée = « pair ». Vous pouvez spécifier le contexte de publication d&#39;une liste de références croisées avec scope=« peer » pour les rubriques disponibles dans d&#39;autres plans DITA. Cet onglet s’affiche si vous utilisez la version Experience Manager Guides (UUID).



### Références de mappage croisé à partir des paramètres prédéfinis AEM Sites dans l’éditeur web

La dernière amélioration de Experience Manager Guides introduit des références croisées dans les paramètres prédéfinis AEM Sites de l’éditeur web.
Les références de mappage croisé dans Experience Manager Guides permettent d’améliorer la navigation du contenu, la réutilisation du contenu et l’expérience utilisateur.


Vous pouvez spécifier le contexte de publication d&#39;une liste de références croisées à des rubriques disponibles dans d&#39;autres plans DITA avec scope=« peer ». Par exemple, la rubrique 1 de la carte A contient une référence à la rubrique 2. La rubrique 2 peut être présente dans une ou plusieurs cartes.  Vous pouvez sélectionner le mappage parent et un paramètre prédéfini spécifique ou la sortie publiée le plus récemment pour chaque lien.

Si la même rubrique est référencée plusieurs fois dans un fichier, vous pouvez ajouter un contexte de publication différent pour chaque instance. Vous bénéficiez ainsi d’une plus grande flexibilité et d’un meilleur contrôle sur leur contenu. Par exemple, la rubrique 3 est présente à la fois dans la carte B et dans la carte C. La rubrique 1 contient deux références à la rubrique 3. Vous pouvez choisir Mappage B comme mappage parent pour le premier lien et Mappage C comme parent pour le deuxième lien.

![Paramètre prédéfini AEM Sites hérité](assets/aem-sites-legacy.png)

*Spécifiez le contexte de publication des rubriques liées à partir de l’onglet **Références de mappage croisé**&#x200B;du préréglage **AEM Sites**.*

En savoir plus sur les [paramètres prédéfinis &#x200B;](../user-guide/generate-output-aem-site.md).

### Option permettant de choisir une hiérarchie de fichiers plate ou imbriquée pour la sortie HTML5

Désormais, Experience Manager Guides vous permet de conserver la hiérarchie de dossiers plate pour les fichiers temporaires dans lesquels l’intégralité du contenu est publiée au format de sortie HTML5 et enregistrée dans un seul dossier.
Si vous ne choisissez pas d’aplatir la hiérarchie de fichiers, la sortie HTML5 est générée dans une hiérarchie de dossiers imbriquée. Cela signifie que la structure de dossiers d’origine du contenu, avec des fichiers organisés en sous-dossiers, est répliquée dans la sortie. Cette hiérarchie de dossiers imbriqués permet une organisation et une catégorisation des fichiers plus complexes, ce qui facilite la gestion et la navigation dans de grands volumes de données.


En savoir plus sur la manière de [générer une sortie HTML5](../user-guide/generate-output-html5.md).


## Améliorations de l’éditeur

Les améliorations suivantes ont été apportées à l’éditeur dans la version 2024.10.0 :

### Accès en lecture seule au mode Auteur et Source pour les fichiers verrouillés

Si un fichier DITA ou Markdown est verrouillé ou extrait par un autre utilisateur, vous ne pouvez pas modifier le contenu. Outre l’aperçu, vous pouvez également l’afficher en tant que fichier en lecture seule en mode Création ou Source.
En mode lecture seule, vous pouvez afficher le contenu ainsi que les balises et les attributs en mode **Auteur** ou **Source** et modifier les propriétés du fichier.

Vous pouvez également accéder à la vue **Disposition** pour les plans DITA en lecture seule.
>[!NOTE]
>
> Les administrateurs de profils de dossiers doivent mettre à jour *ui_config.json* afin que vous puissiez accéder harmonieusement aux fichiers en lecture seule en modes Auteur, Source et Disposition.

![éditeur de fichier verrouillé](./assets/locked-file-editor.png)
*Afficher les fichiers verrouillés en mode Auteur et Source.*


Découvrez comment [ouvrir des fichiers verrouillés en modes Auteur et Source](../user-guide/web-editor-edit-topics.md#open-locked-files-in-author-and-source-modes).


### Conditions groupées pour une organisation de contenu améliorée

Experience Manager Guides vous permet désormais de regrouper des conditions et de les présenter dans une hiérarchie imbriquée, ce qui vous permet d’ajouter plusieurs conditions à un seul groupe. En regroupant les conditions, vous pouvez mieux les organiser et les appliquer à l’ensemble de votre contenu.

![conditions organisées dans une hiérarchie imbriquée](assets/conditions-nested-hierarchy.png){width="300"}

Pour en savoir plus sur la description de la fonctionnalité **Conditions**, consultez la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS).
