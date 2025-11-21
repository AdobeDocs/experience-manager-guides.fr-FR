---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans la version 4.3.0 d’Adobe Experience Manager Guides
description: Découvrez les correctifs et comment effectuer une mise à niveau vers la version 4.3.0 d’Adobe Experience Manager Guides
exl-id: 7fb568a0-0b88-4ea0-9b79-2625336348ff
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 1%

---

# Version 4.3.0 d’Adobe Experience Manager Guides (juillet 2023)

Cette note de mise à jour couvre les instructions de mise à niveau, la matrice de compatibilité et les problèmes résolus dans la version 4.3.0 d’Adobe Experience Manager Guides (ultérieurement appelée *AEM Guides*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version 4.3.0 d’Adobe Experience Manager Guides](./whats-new-4-3-release.md).

## Mise à niveau vers la version 4.3.0 d’AEM Guides


Vous pouvez facilement mettre à niveau votre version actuelle d’AEM Guides vers la version 4.3.0. Avant de procéder à la mise à niveau vers la version 4.3.0 d’AEM Guides, vous devez tenir compte des points suivants :
Vous pouvez mettre à niveau votre version actuelle d’AEM Guides vers la version 4.3.0

- Si vous utilisez la version 4.2 ou 4.2.x, vous pouvez directement effectuer la mise à niveau vers la version 4.3.0.
- Si vous utilisez la version 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.2 ou 4.2.x avant la mise à niveau vers la version 4.3.0.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant la mise à niveau vers la version 4.3.0.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à la version 3.8.5, reportez-vous à la section Mise à niveau d’AEM Guides dans le guide d’installation spécifique au produit.



>[!NOTE]
>
>Vous devez installer le pack de services AEM avant de mettre à niveau la version d’AEM Guides.

Pour plus d’informations, voir [Instructions de mise à niveau](../install-guide/upgrade-xml-documentation.md).

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité pour les applications logicielles prises en charge par la version 4.3.0 d’AEM Guides.

### Adobe Experience Manager

**4.3.0 Non-UUID**
Version 6.5 Service Pack 18, 17, 16, 15 ou 14

**4.3.0 UUID**
Version 6.5 Service Pack 18, 17, 16, 15 ou 14

Pour plus d’informations, consultez la section *Exigences techniques* du guide Installation et configuration d’Adobe Experience Manager Guides .

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.0 (Non-UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.3 ou version ultérieure |
| 4.3.0 (UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.4 ou version ultérieure |
| | | | | |

*La ligne de base et les conditions créées dans AEM sont prises en charge dans les versions FMPS à compter de 2020.2.

### Connecteur D&#39;Oxygène

| Version | Fenêtres du connecteur d&#39;oxygène | Mac du connecteur d&#39;oxygène | Modifier dans Oxygen Windows | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.3.0 (Non-UUID) | 2.3-standard-5 | 2.3-standard-5 | 1,6 | 1,6 |
| 4.3.0 (UUID) | 3.0-uuid-4 | 3.0-uuid-3 | 2,3 | 2,3 |
|  |  |   |  |  |

## Problèmes résolus

Les bogues corrigés dans différentes zones sont répertoriés ci-dessous :

### Création

- Le fichier rubrique n&#39;est pas déverrouillé dans l&#39;éditeur Web, bien que les options Déverrouiller le fichier et Ne pas enregistrer soient sélectionnées. (12558)
- Impossible d&#39;extraire un fichier dans l&#39;éditeur Web, bien que vous ayez choisi l&#39;option NON pour ignorer les modifications avant l&#39;archivage. (12557)
- Les info-bulles des icônes Verrouiller et Déverrouiller le fichier dans la barre d’outils principale de l’éditeur web ne sont pas cohérentes avec les icônes affichées dans la vue Référentiel.(12555)
- L&#39;option Annuler l&#39;extraction et Déverrouiller s&#39;affiche pour un fichier dans l&#39;éditeur Web qui n&#39;est pas encore extrait en mode Carte. (12556)
- Impossible de sélectionner les ressources PDF dans les liens « topicref » existants. (12477).
- Lors d’une fusion et d’un fractionnement dans les tableaux, AEM Guides 4.2 génère des cellules de tableau supplémentaires. (11793)
- Dans la vue Référentiel, les rubriques ou images ne peuvent pas être déplacées après avoir utilisé la fonctionnalité Rechercher/Filtrer. (12396)
- Les résultats de la recherche sont désactivés dans le panneau Rechercher et remplacer après l’ouverture d’un fichier recherché. (12142)
- La touche numérique « 8 » du clavier latéral ne fonctionne pas dans l’éditeur d’AEM Guides. (12106)
- Les attributs intégrés/d’affichage ne s’affichent pas en mode Mise en page de l’éditeur web. (12498)
- La configuration de l’interface utilisateur du profil global ne correspond pas au profil de dossier. (11970)
- Les références de contenu sont rompues lorsque des fichiers DITA sont copiés et collés. (11959)
- Impossible de modifier le fragment de contenu dans la vue Colonnes avec AEM Guides installé. (7342)
- Le contenu est perdu lorsqu’une xréf non encapsulée se trouve sous des balises de sous-élément. (12532)
- Le workflow d’approbation ne fonctionne pas lorsque l’état du document est remplacé par « état de fin » dans les propriétés de fichier du panneau de droite. (11026)
- Interface utilisateur d’Asset | Dans la vue Liste, les colonnes disponibles superposées ne peuvent pas être fusionnées. (11528)
- Keyref n’est pas résolu en mode Carte. (11490)
- Le menu supérieur n’apparaît pas lors de la navigation dans l’éditeur XML. (10868)
- `conref` dans la balise ph | La boîte de dialogue de navigation affichée est incorrecte. (9481)
- Les liens locaux vers d’autres éléments ne sont pas résolus dans l’éditeur web. (8790)
- La fonction Matches() ne fonctionne pas dans la fonction schematron. (11224)



### Gestion

- Le champ « title » des propriétés de métadonnées de plan DITA est remplacé par `<title>` élément pour le plan. (10702)
- Lors de la tentative d’ouverture ou de mise à jour de la version des rubriques de la ligne de base, le chargeur « Récupération des informations du serveur » s’exécute indéfiniment.(12478)


### Révision

- Nouvelle interface utilisateur de révision | Les conditions sont mises en surbrillance et indiquent que le fonctionnement des masques diffère de celui de l’éditeur web. (11628)

### Publication

- La publication échoue lors du changement du nom d’un paramètre prédéfini de PDF natif. (12564)
- La duplication d’un modèle PDF natif duplique l’emplacement du modèle par défaut au lieu de l’emplacement du modèle personnalisé fourni. (12563)
- PDF natif | Les métadonnées de langue ne peuvent pas être définies dans le PDF généré pour se conformer au WCAG 2.0. (12407)
- La publication sur le site AEM échoue lors de la lecture des fichiers temporaires du pod qui peuvent avoir été actualisés ou redémarrés. (12113)
- PDF natif | Les attributs personnalisés ne sont pas propagés au moteur temporaire HTML ou PDF. (DXML-12005)
- PDF natif |  Java OutOfMemoryError se produit lors de la publication de contenu volumineux. (11789)
- PDF natif | Xref imprime le contenu du titre de la rubrique href au lieu du libellé Xref. (11322)
- PDF natif | Impossible d’enregistrer les paramètres du modèle PDF. (10751)
- PDF natif | Le texte s’étend au-delà de la largeur de colonne en incluant plusieurs xréfs. (10876)
- PDF natif | `<note>` `</note>`’élément ne génère pas de titre d’étendue supplémentaire de son type. (10549)
- Sortie JSON | La propriété `fmUuid` sur le nœud jcr:content de JSON est différente de l’« id » dans le fichier JSON. (11564)
- Sortie JSON | Si le mappage et la rubrique portant le même nom de fichier sont présents, le JSON du mappage est supprimé. (11524)

## Problème connu

Adobe a identifié le problème connu suivant pour la version 4.3.0 d’AEM Guides :

- La mise en page commune définie dans le modèle de base n’est pas appliquée en tant que modèle par défaut.

  Solution :
Ajoutez une disposition de page commune en première et deuxième couverture, puis elle commence à apparaître pour chaque page.
- Problème lors de la recherche de site lors de la recherche dans la page de sortie de site AEM dans les pack de services 16 ou 17 d’AEM.

  Solution :

   1. Ouvrez le fichier dont le chemin d’accès est : `/libs/foundation/components/search/search.jsp` dans `crx/de`
   1. Remplacez le numéro de ligne 234 par le code suivant :

      ```
      <a href="<c:url value="${hit.URL}" context="/"/>" onclick="trackSelectedResult(this, ${status.index + 1})"><%= xssAPI.filterHTML(((Search.Hit) pageContext.getAttribute("hit")).getTitle()) %></a>
      
      *(Add the missing closing anchor tag at the end).
      ```

   1. Enregistrez le fichier.
