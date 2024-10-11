---
title: Notes de mise à jour | Nouveautés de la version 2024.10.0 d’Adobe Experience Manager Guides
description: Découvrez les nouvelles fonctionnalités et les fonctionnalités améliorées de la version 2024.10.0 d’Adobe Experience Manager Guides
role: Leader
source-git-commit: 545e51cbd970aa3df01a0fe2461a2e730c0db66a
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 1%

---

# Nouveautés de la version 2024.10.0 (octobre 2024)

Cet article couvre les nouvelles fonctionnalités et les fonctionnalités améliorées introduites avec la version 2024.10.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour connaître la liste des problèmes résolus dans cette version, voir la section [Problèmes résolus dans la version 2024.10.0](fixed-issues-2024-10-0.md).

Découvrez les [instructions de mise à niveau pour la version 2024.10.0](../release-info/upgrade-instructions-2024-10-0.md).


## Améliorations apportées à la publication

Les améliorations suivantes ont été apportées à la publication de contenu dans la version 2024.10.0 :




### Améliorations de la publication de fragments de contenu

Experience Manager Guides fournit également quelques améliorations utiles dans les fragments de contenu :

- Experience Manager Guides vous permet de publier une rubrique ou ses éléments dans un fragment de contenu.

- Vous pouvez publier et afficher les fragments de contenu d’une rubrique à partir de la section **Sorties** dans les **Propriétés du fichier**.


- Vous pouvez facilement créer des variations de fragment de contenu en filtrant le contenu avec des conditions lors de la publication sur un fragment de contenu.

- Utilisez la nouvelle interface de mappage pour sélectionner et publier facilement les éléments dans un fragment de contenu.

Désormais, la publication de fragments de contenu remplace uniquement le contenu mappé au lieu d’écraser l’intégralité du fragment de contenu. Cette fonctionnalité permet à un fragment de contenu de contenir des données provenant de plusieurs sources, telles que plusieurs rubriques ou l’éditeur de fragment de contenu.

![Ajoutez le modèle de fragment et les détails de mappage dans la boîte de dialogue Publish en tant que fragment de contenu](assets/content-fragment-mapping.png)

Pour plus d’informations, voir [Fragments de contenu Publish](../user-guide/publish-content-fragment.md).


### Variantes de fragment d’expérience Publish basées sur des filtres de condition

Experience Manager Guides vous permet de publier une rubrique ou ses éléments dans un fragment d’expérience. Vous pouvez désormais également créer des variantes de fragments d’expérience à l’aide des filtres de condition ou DITAVAL et les réutiliser sur différents canaux ou pour différentes audiences.

Découvrez comment [Fragments d’expérience Publish](../user-guide/publish-experience-fragment.md).


### Réorganisation du paramètre prédéfini AEM Sites pour en faciliter l’utilisation

Les paramètres ont été réorganisés afin de vous aider à configurer rapidement le paramètre prédéfini de sortie et à générer la sortie AEM Sites.
Vous pouvez créer les paramètres prédéfinis AEM Sites existants en sélectionnant l’option **Utiliser le mappage de composant hérité** dans la boîte de dialogue **Nouveau paramètre prédéfini de sortie** .

Affichez les onglets **Général**, **Contenu** et **Référence de mappage croisé** dans les paramètres prédéfinis AEM Sites :
- **Général** : contient les configurations générales pour générer la sortie. Vous pouvez spécifier le site et le chemin de sortie, supprimer ou remplacer les pages de sortie existantes, supprimer les pages précédemment générées pour les rubriques supprimées, sélectionner le modèle de conception, conserver les fichiers temporaires et spécifier le workflow de post-génération.
- **Contenu** : contient les paramètres applicables au contenu pour la génération de sortie. Vous pouvez sélectionner les filtres, la ligne de base du mappage DITA et les propriétés de métadonnées pour la publication.
- **Références de mappage croisé** : cette liste contient des rubriques contenant des références de mappage croisé avec portée =&quot;peer&quot;. Vous pouvez spécifier le contexte de publication d’une liste de références croisées avec scope=&quot;peer&quot; pour les rubriques disponibles dans d’autres mappages DITA. Cet onglet s’affiche si vous utilisez la version Experience Manager Guides (UUID).



### Références de mappage croisé à partir de paramètres prédéfinis AEM Sites dans l’éditeur web

La dernière amélioration apportée à Experience Manager Guides introduit des références croisées dans les paramètres prédéfinis AEM Sites de l’éditeur web.
Les références de mappage croisé dans Experience Manager Guides permettent d’améliorer la navigation du contenu, d’augmenter la réutilisation du contenu et d’améliorer l’expérience utilisateur.


Vous pouvez spécifier le contexte de publication pour une liste de références croisées à des rubriques disponibles dans d’autres mappages DITA avec scope=&quot;peer&quot;. Par exemple, la rubrique 1 de la carte A contient une référence à la rubrique 2. La rubrique 2 peut être présente dans une ou plusieurs cartes.  Vous pouvez sélectionner le mappage parent et un paramètre prédéfini spécifique ou la sortie publiée le plus récemment pour chaque lien.

Si la même rubrique est référencée plusieurs fois dans un fichier, vous pouvez ajouter un contexte de publication différent pour chaque instance. Vous bénéficiez ainsi d’une plus grande flexibilité et d’un meilleur contrôle sur leur contenu. Par exemple, la rubrique 3 est présente dans les cartes B et C. La rubrique 1 contient deux références à la rubrique 3. Vous pouvez choisir la carte B comme mappage parent pour le premier lien et la carte C comme parent pour le second lien.

![Paramètre prédéfini AEM Sites hérité](assets/aem-sites-legacy.png)

*Spécifiez le contexte de publication pour les rubriques liées à partir de l’onglet **Références croisées**du paramètre prédéfini **AEM Sites**.*

En savoir plus sur les [paramètres prédéfinis AEM Sites](../user-guide/generate-output-aem-site.md).

### Option permettant de choisir une hiérarchie de fichiers plate ou imbriquée pour la sortie HTML5

Désormais, Experience Manager Guides vous permet de conserver l’arborescence des dossiers plats pour les fichiers temporaires, dans laquelle l’ensemble du contenu est publié au format de sortie HTML5 et enregistré dans un seul dossier.
Si vous ne choisissez pas d’aplatir la hiérarchie de fichiers, la sortie HTML5 est générée dans une hiérarchie de dossiers imbriquée. Cela signifie que la structure de dossiers d’origine du contenu, avec des fichiers organisés en sous-dossiers, est répliquée dans la sortie. Cette hiérarchie de dossiers imbriqués permet une organisation et une catégorisation des fichiers plus complexes, ce qui facilite la gestion et la navigation de grands volumes de données.


Découvrez comment [générer la sortie HTML5](../user-guide/generate-output-html5.md).


## Améliorations de l’éditeur

Les améliorations de l’éditeur suivantes ont été ajoutées à la version 2024.10.0 :

### Accès en lecture seule aux modes Auteur et Source pour les fichiers verrouillés

Si un fichier DITA ou Markdown est verrouillé ou extrait par un autre utilisateur, vous ne pouvez pas modifier le contenu. Outre l’aperçu, vous pouvez également l’afficher sous la forme d’un fichier en lecture seule en mode Auteur ou Source .
En mode lecture seule, vous pouvez afficher le contenu avec les balises et les attributs dans le mode **Auteur** ou **Source** et modifier les propriétés du fichier.

Vous pouvez également accéder à la vue **Disposition** pour les mappages DITA en lecture seule.
>[!NOTE]
>
> Les administrateurs de votre profil de dossier doivent mettre à jour *ui_config.json* afin que vous puissiez accéder harmonieusement aux fichiers en lecture seule dans les modes Auteur, Source et Mise en page.

![Éditeur de fichiers verrouillé](./assets/locked-file-editor.png)
*Affichez les fichiers verrouillés en mode Auteur et Source.*


Découvrez comment [ouvrir des fichiers verrouillés en modes Auteur et Source](../user-guide/web-editor-edit-topics.md#open-locked-files-in-author-and-source-modes).


### Conditions groupées pour une organisation de contenu améliorée

Experience Manager Guides vous permet désormais de regrouper des conditions et de les présenter dans une hiérarchie imbriquée, ce qui vous permet d’ajouter plusieurs conditions à un seul groupe. En regroupant les conditions, vous pouvez mieux les organiser et les appliquer dans l’ensemble de votre contenu.

![conditions organisées dans une hiérarchie imbriquée](assets/conditions-nested-hierarchy.png){width="300" align="left"}

Pour en savoir plus sur la description de la fonction **Conditions** dans la section [Panneau de gauche](../user-guide/web-editor-features.md#id2051EA0M0HS) .




