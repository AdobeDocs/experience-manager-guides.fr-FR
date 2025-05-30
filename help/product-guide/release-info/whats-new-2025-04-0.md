---
title: Notes de mise à jour | Nouveautés de la version Adobe Experience Manager Guides 2025.04.0
description: Découvrez les fonctionnalités nouvelles et améliorées de la version 2025.04.0 d’Adobe Experience Manager Guides
role: Leader
exl-id: 5d28119b-641f-402b-833c-6f7554e7c273
source-git-commit: fe7d81f1826fe4ee0c716df36daabe3c5efd8994
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 3%

---

# Nouveautés de la version 2025.04.0 (avril 2025)

Cet article présente les nouvelles fonctionnalités améliorées introduites dans la version 2025.04.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour connaître la liste des problèmes résolus dans cette version, voir la section [Problèmes résolus dans la version 2025.04.0](fixed-issues-2025-04-0.md).

Découvrez les [instructions de mise à niveau pour la version 2025.04.0](../release-info/upgrade-instructions-2025-04-0.md).

## Attribut &#39;Format&#39; ajouté pour les liens de référence

Adobe Experience Manager Guides ajoute désormais un attribut **format** pour les liens de référence dans l’éditeur. Cet attribut s&#39;affiche dans la vue **Source** et indique clairement le type de fichier, par exemple :

- Pour les fichiers dotés de l’extension **.pdf**, le format est défini sur **pdf**
- Pour les fichiers dotés de l’extension **.html**, le format est défini sur **html**
- Pour les fichiers contenant un fichier **.dita** ou **.ditamap**, le format est défini sur **dita**

En outre, le format des fichiers dotés de l’extension **.xml** est également défini sur **dita**. Pour les fichiers sans extension, le format reste vide. En outre, pour les liens de référence dont la portée est définie sur **externe**, le format est défini sur **html** quelle que soit l’extension de fichier dans les liens de référence.

## La ligne de base exportée inclut désormais l’état du document

La fonction Exporter la ligne de base inclut désormais le **état du document** ainsi que des détails clés tels que le titre, le nom de fichier, le type de fichier et le numéro de version de l’instantané de la ligne de base. Cette amélioration améliore la gestion de la ligne de base en fournissant un aperçu plus complet de la ligne de base.

Pour plus d’informations, voir [Création et gestion des lignes de base à partir de la console Carte](../user-guide/web-editor-baseline.md#manage-baselines).

## Amélioration de l’expérience de recherche pour le panneau Contenu réutilisable

Experience Manager Guides offre une expérience de recherche améliorée dans le panneau Contenu réutilisable. Avec cette mise à jour, la recherche de n’importe quel mot-clé analyse désormais tous les fichiers ajoutés en tant que contenu réutilisable, et pas seulement les fichiers ouverts, en s’assurant que vous trouvez la position exacte du mot-clé sur toutes les occurrences, que les conteneurs soient ouverts ou réduits. En outre, lorsque vous effacez la barre de recherche, l’état d’origine de tous les conteneurs est conservé, offrant ainsi une fonctionnalité de recherche plus efficace et plus conviviale.

Pour plus d’informations, consultez la section [Contenu réutilisable](../user-guide/web-editor-features.md#reusable-content).


## Mise à niveau de la version Java des conteneurs de microservice

Pour les environnements cloud activés pour les microservices, nous passerons à l’utilisation de Java 21, en veillant à ce que les processus de génération DITA-OT et PDF natifs existants ne soient pas affectés. Le workflow existant de DITA-OT 3 continuera à fonctionner de manière transparente avec Java 21.  En outre, DITA-OT 4 sera entièrement opérationnel, ce qui permettra aux utilisateurs de générer des fichiers PDF à l’aide de DITA-OT et de PDF natifs, ainsi que de produire des sorties pour les sites AEM natifs et d’autres formats.
