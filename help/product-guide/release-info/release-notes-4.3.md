---
title: Notes de mise à jour | Instructions de mise à niveau et problèmes résolus dans la version 4.3.0 de Adobe Experience Manager Guides
description: Découvrez les correctifs et comment mettre à niveau vers les versions 4.3.0 des Guides Adobe Experience Manager.
exl-id: 7fb568a0-0b88-4ea0-9b79-2625336348ff
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 1%

---

# Version 4.3.0 des guides Adobe Experience Manager (juillet 2023)

Cette note de mise à jour traite des instructions de mise à niveau, de la matrice de compatibilité et des problèmes résolus dans la version 4.3.0 des Guides Adobe Experience Manager (ultérieurement appelés *Guides d’AEM*).

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, voir [Nouveautés de la version 4.3.0 des guides Adobe Experience Manager](./whats-new-4.3-release.md).

## Mise à niveau vers la version 4.3.0 des Guides d’AEM


Vous pouvez facilement mettre à niveau votre version actuelle des AEM Guides vers la version 4.3.0. Avant de procéder à la mise à niveau vers la version 4.3.0 des AEM Guides, vous devez tenir compte des points suivants : vous pouvez mettre à niveau votre version actuelle des AEM Guides vers la version 4.3.0.

- Si vous utilisez la version 4.2 ou 4.2.x, vous pouvez directement effectuer la mise à niveau vers la version 4.3.0.
- Si vous utilisez la version 4.1 ou 4.1.x, vous devez effectuer la mise à niveau vers la version 4.2 ou 4.2.x avant de passer à la version 4.3.0.
- Si vous utilisez la version 4.0, vous devez effectuer la mise à niveau vers la version 4.2 avant de passer à la version 4.3.0.
- Si vous utilisez la version 3.8.5, vous devez effectuer la mise à niveau vers la version 4.0 avant de passer à la version 4.2.
- Si vous utilisez une version antérieure à 3.8.5, reportez-vous à la section Guides d’AEM de mise à niveau du guide d’installation spécifique au produit.



>[!NOTE]
>
>Vous devez installer AEM Service Pack avant de mettre à niveau AEM version de Guides.

Pour plus d’informations, voir [Instructions de mise à niveau](../install-guide/upgrade-xml-documentation.md).

## Matrice de compatibilité

Cette section répertorie le tableau de compatibilité des applications logicielles prises en charge par AEM Guides 4.3.0.

### Adobe Experience Manager

**4.3.0 Non UID**
Version 6.5 Service Pack 18, 17, 16, 15 ou 14

**UUID 4.3.0**
Version 6.5 Service Pack 18, 17, 16, 15 ou 14

Pour plus d’informations, voir *Exigences techniques* dans le guide d’installation et de configuration de Adobe Experience Manager Guides.

### FrameMaker et FrameMaker Publishing Server

| Version | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.0 (non UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.3 ou version ultérieure |
| 4.3.0 (UUID) | 2022 ou version ultérieure | 2020.2 ou version ultérieure* | 2022 ou version ultérieure | 2020.4 ou version ultérieure |
| | | | |

*Les conditions de base et créées dans AEM sont prises en charge dans les versions FMPS à partir de 2020.2.

### Connecteur Oxygen

| Version | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen | Modifier sous Windows Oxygen | Modifier dans Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.3.0 (non UUID) | 2.3-normal-5 | 2.3-normal-5 | 1,6 | 1,6 |
| 4.3.0 (UUID) | 3.0-uuid-4 | 3.0-uuid-3 | 2,3 | 2,3 |
|  |  |   |

## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

### Création

- Le fichier de rubrique n’est pas déverrouillé dans l’éditeur web, bien que les options Déverrouiller le fichier et Ne pas enregistrer soient sélectionnées. 12558
- Impossible d’extraire un fichier dans l’éditeur web, bien que vous ayez choisi l’option NON pour ignorer les modifications avant l’archivage. (12557)
- Les info-bulles des icônes Verrouiller et déverrouiller le fichier dans la barre d’outils principale de l’éditeur web ne sont pas cohérentes avec les icônes affichées dans la vue Repository.12555
- L’option Annuler l’extraction et Déverrouiller s’affiche pour un fichier dans l’éditeur web qui n’est pas encore extrait en mode Carte. 12556
- Impossible de sélectionner les ressources du PDF dans les liens &quot;topicref&quot; existants. (12477)
- Lors d’une fusion et d’un partage dans les tableaux, AEM Guides 4.2 génère des cellules de tableau supplémentaires. (11793)
- Dans la vue Repository, les rubriques ou les images ne peuvent pas être glissées après l’utilisation de la fonctionnalité Search/Filter . (12396)
- Les résultats de recherche sont désactivés dans le panneau Rechercher et remplacer après l’ouverture d’un fichier de recherche. (12142)
- La touche numérique &quot;8&quot; du clavier latéral ne fonctionne pas dans l’éditeur AEM Guides. (12106)
- Les attributs intégrés/affichés ne s’affichent pas dans la vue Disposition de l’éditeur web. (12498)
- La configuration de l’interface utilisateur du profil global ne correspond pas au profil du dossier. (1970)
- Les références au contenu sont rompues lorsque les fichiers DITA sont copiés et collés. (1959)
- Impossible de modifier le fragment de contenu en mode Colonne avec les AEM Guides installés. (7342)
- Le contenu est perdu lorsqu’un xref non encapsulé se trouve sous des balises de sous-élément. 12532
- Le processus d’approbation ne fonctionne pas lorsque la propriété docstate est remplacée par &quot;end state&quot; à partir des propriétés File du panneau de droite. (11026)
- Interface utilisateur des ressources | En mode Liste, les colonnes disponibles superposées ne sont pas fusionnables. (11528)
- Keyref n’est pas résolu dans la vue map. (11490)
- Le menu supérieur n’apparaît pas lors de la navigation dans l’éditeur XML. 10868
- `conref` balise h | La boîte de dialogue de navigation affichée est incorrecte. (9481)
- Les liens locaux vers d’autres éléments ne sont pas résolus dans l’éditeur web. (8790)
- La fonction Matches() ne fonctionne pas dans la fonction de schéma. (11224)



### Gestion

- Le champ &quot;titre&quot; des propriétés de métadonnées de mappage DITA est remplacé par `<title>` pour la carte. 10702
- Lorsque vous essayez d’ouvrir ou de mettre à jour la version des rubriques dans la ligne de base, le chargeur &quot;Récupération des informations à partir du serveur&quot; s’exécute indéfiniment.(12478)


### Révision

- Nouvelle interface utilisateur de révision | Les conditions de mise en surbrillance et d’affichage du masquage fonctionnent différemment de leur fonctionnement dans l’éditeur web. (11628)

### Publication

- La publication échoue lors du changement du nom d’un paramètre prédéfini de PDF natif. 12564
- La duplication d’un modèle de PDF natif duplique l’emplacement du modèle par défaut au lieu de l’emplacement du modèle personnalisé fourni. 12563
- PDF natif | Les métadonnées de langue ne peuvent pas être définies dans le PDF généré pour être conformes à WCAG 2.0. (12407)
- La publication sur AEM site échoue lors de la lecture de fichiers temporaires à partir d’une capsule qui peuvent avoir été actualisés ou redémarrés. (12113)
- PDF natif | Les attributs personnalisés ne sont pas propagés au moteur de HTML ou de PDF temporaire. (DXML-12005)
- PDF natif | Java OutOfMemoryError survient lors de la publication de contenu volumineux. (11789)
- PDF natif | Xref imprime le contenu du titre de la rubrique href au lieu de l’étiquette Xref. (11322)
- PDF natif | Impossible d’enregistrer les paramètres du modèle de PDF. (10751)
- PDF natif | Le texte s’étend au-delà de la largeur de colonne sur l’inclusion de plusieurs xrefs. (10876)
- PDF natif | `<note>``</note>` ne génère pas de titre d’étendue supplémentaire de son type. (10549)
- Sortie JSON | Le `fmUuid` sur le noeud jcr:content de JSON est différent de &quot;id&quot; dans le fichier JSON. (11564)
- Sortie JSON | Si la carte et la rubrique portant le même nom de fichier sont présentes, JSON de la carte est supprimé. (11524)

## Problème connu

Adobe a identifié le problème connu suivant pour la version 4.3.0 d’AEM Guides :

- La mise en page courante définie dans le modèle De base n’est pas appliquée comme modèle par défaut.

  Solution de contournement : ajoutez la mise en page courante en tant que couverture avant et arrière, puis elle commence à venir pour chaque page.
- Un problème se produit dans la recherche de site lors de la recherche dans la page de sortie du site AEM sur AEM Service Pack 16 ou 17.

  Solution :

   1. Ouvrez le fichier avec le chemin d’accès : `/libs/foundation/components/search/search.jsp` in `crx/de`
   1. Remplacez la ligne 234 par le code suivant :

      ```
      <a href="<c:url value="${hit.URL}" context="/"/>" onclick="trackSelectedResult(this, ${status.index + 1})"><%= xssAPI.filterHTML(((Search.Hit) pageContext.getAttribute("hit")).getTitle()) %></a>
      
      *(Add the missing closing anchor tag at the end).
      ```

   1. Enregistrez le fichier.
