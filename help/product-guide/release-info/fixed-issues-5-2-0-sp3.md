---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides 5.2.0 Service Pack 3
description: Découvrez les correctifs de bugs dans la version 5.2.0 Service Pack 3 d’Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: a3144f0078b2073289043befacc5e2358b9c0e02
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 1%
---
# Correction de problèmes dans la version 5.2.0 Service Pack 3 (novembre 2026)

Cet article couvre les bugs corrigés dans différentes zones de la version 5.2.0 Service Pack 3 d’Adobe Experience Manager Guides.

Découvrez les [instructions de mise à niveau pour le pack de services 3 version 5.2.0](upgrade-instructions-5-2-0-sp3.md).

## Éditeur 2.0

- La copie d&#39;un tableau à partir du mode Création et son collage en mode Création suppriment des attributs tels que `colwidth` et tout autre attribut défini sur `colspec`, ce qui entraîne la perte des paramètres de largeur de colonne. (GUIDES-52916)
- Lorsqu’un tableau est collé à partir de Microsoft Word, les cellules des lignes d’en-tête sont créées, mais leur contenu est perdu. (GUIDES-49847)
- Lorsque du code est collé dans un élément `codeblock`, à partir de Microsoft Word ou d’éditeurs de texte similaires, en utilisant Ctrl+V, les sauts de ligne et les espaces de début sont perdus et le code est aplati en une seule ligne. (GUIDES-33247)

## Gestion des ressources numériques

- L’API de statut de la ressource ne renvoie pas le statut correct pour les ressources dont le chemin contient une virgule. (GUIDES-49065)

## Publication

- Lors de la publication d&#39;un plan DITA avec `processing-role=resource-only` éléments sur AEM Sites (avec le mappage de composant hérité), des pages de site orphelines sont générées pour ces éléments dans des scénarios supplémentaires tels que `topicgroup` éléments et des configurations de contenu spécifiques. (GUIDES-37650)
- Le filtrage des branches génère des pages supplémentaires pour les rubriques indésirables utilisées comme `keydef` (qui sont marquées `resource-only ="true"` par DITA-OT). (GUIDES-19701)
- Dans le tableau de bord Mappage , la sélection d’un autre paramètre prédéfini déclenche un appel pour récupérer les liens d’homologue, ce qui entraîne un traitement supplémentaire. (GUIDES-53703)
- Dans la sortie PDF native, les références de rubrique marquées d’un attribut `toc="no"` sont toujours incluses dans la table des matières, ce qui entraîne une table des matières longue et encombrée. (GUIDES-20156)
- Dans certains cas, lorsqu&#39;un plan DITA complet est généré et publié dans AEM Sites à l&#39;aide d&#39;une ligne de base dynamique, certaines rubriques sont publiées avec des versions antérieures ou non approuvées au lieu des versions approuvées actuelles. (GUIDES-55646)
- Lors du traitement d’un grand nombre de ressources, `PurgePresetExecutionDataJob` rencontre parfois un `RuntimeNodeTraversalException` non géré, ce qui bloque la tâche dans une boucle infinie et génère un nombre excessif de journaux. (GUIDES-53897)
- Dans la sortie PDF native, l’attribut `outputclass` défini sur un élément `topichead` ou `topicgroup` n’est pas appliqué ou transféré vers la section PDF résultante. (GUIDES-22950)
- Dans certains cas, lors de la publication avec le moteur PDF natif v1, l’ordre de lecture du contenu avec l’accessibilité `settingsenabled` est incorrect. Les numéros de page des pieds de page sont lus avant le contenu principal et non à la fin.(GUIDES-27790)


## Traduction

- L’application d’une ligne de base à une carte avec de nombreuses ressources retarde le chargement du rapport de traduction pour la langue sélectionnée, ce qui entraîne parfois un délai d’expiration de la demande avant le rendu du rapport. (GUIDES-45508)
- Les groupes de langues de l’onglet Traduction dans les Paramètres Workspace ne sont pas conservés lorsque le dossier de langue sélectionné utilise un code de paramètre régional avec trait d’union (par exemple, `da-DK`) au lieu d’un format de trait de soulignement (`da_dk`). (GUIDES-37843)
- Le démarrage d’une traduction à l’aide d’un projet XLIFF crée un projet vide qui ne passe jamais à un statut en cours. (GUIDES-51759)
- Le paramètre `propagateVersionLabel` du profil de dossier global est réinitialisé par intermittence sur `false` lorsqu’un utilisateur disposant uniquement du rôle Contributeur accède à l’éditeur. (GUIDES-51870)

## Ligne de base

- La sélection de la ligne de base enregistrée d’un paramètre prédéfini s’affiche incorrectement comme *Aucune ligne de base* après la suppression de la ligne de base ou pendant la création d’une ligne de base dynamique. (GUIDES-52690)
- Dans certains cas, les lignes de base dynamiques restent bloquées à l&#39;état de traitement après un échec de reconstruction, ce qui entraîne l&#39;utilisation de versions de rubrique et de mappage obsolètes par la génération d&#39;export et de sortie sans afficher d&#39;erreur. (GUIDES-56739)

## Révision

- Dans les scénarios impliquant un grand nombre de tâches de révision, l’ouverture du panneau de révision ou l’application d’un filtre de projet prend plus de temps que prévu pour charger la liste de tâches. (GUIDES-48893)
- Le volet Contenu de l’interface utilisateur de révision affiche une barre de défilement horizontale dans certaines résolutions d’écran, notamment la résolution recommandée de 1 600 px, ce qui masque les commentaires de révision lorsque le contenu s’étend au-delà de la largeur du volet. (GUIDES-44082)

## Plateforme

- L&#39;API Move, l&#39;API Rename et l&#39;interface utilisateur Assets empêchent de renommer une ressource DITA avec un nom de fichier basé sur une GUID en un nom de fichier lisible par l&#39;utilisateur. Assets peut désormais être renommé en noms de fichier lisibles par l’utilisateur, mais le changement de nom d’un fichier basé sur une GUID en un autre basé sur une GUID n’est toujours pas autorisé. (GUIDES-43006, GUIDES-59684)
- Lorsqu&#39;une ressource non DITA, telle qu&#39;une image, qui a été migrée d&#39;une configuration non-UUID vers une configuration UUID est rétablie ou branchée sur une autre version, son UUID change. Les références existantes à la ressource ne sont plus résolues et l’image apparaît endommagée dans les rubriques qui y font référence. (GUIDES-58414)
- L’installation du pack de services Experience Manager Guides supprime les outils externes précédemment installés, tels qu’ACS Commons, de la section **Outils** d’AEM. (GUIDES-60365)

## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 5.2.0 Service Pack 3 :

- Après avoir installé le pack de services, la validation de Schematron peut échouer avec une exception `NoClassDefFoundError` et vous ne pouvez pas enregistrer les rubriques dans l&#39;éditeur. (GUIDES-60062)<br>**Solution :** Actualisez le lot `com.adobe.fmdita.schematron-wrapper` à partir de la console web AEM (`/system/console/bundles`).
