---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides, version 2026.09.0
description: Découvrez les correctifs de la version 2026.09.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 2123962f8c168928c9b0a1ee1331e5cfd86db319
workflow-type: tm+mt
source-wordcount: '1241'
ht-degree: 0%

---

# Correction de problèmes dans la version 2026.09.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2026.09.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, consultez [Nouveautés de la version 2026.09.0](./whats-new-2026-09-0.md).

Découvrez les [instructions de mise à niveau pour la version 2026.09.0](./upgrade-instructions-2026-09-0.md).

## Éditeur 2.0

- La copie d’un tableau en mode Création et son collage en mode Création suppriment des attributs tels que `colwidth` et tout autre attribut défini sur `colspec`, ce qui entraîne la perte des paramètres de largeur de colonne. (GUIDES-52916)
- Espace saisi juste avant la suppression d’une balise intégrée dans une cellule de tableau `<entry>`. (GUIDES-49144)

## Création

Cette section traite des bogues résolus dans la création, qui sont communs aux versions 1.0 et 2.0 de l’éditeur.

- Sur les écrans basse résolution, la boîte de dialogue Insérer un mot-clé ne s’affiche pas lors de l’insertion d’un mot-clé à partir de la barre d’outils, tandis qu’elle s’ouvre comme prévu lors de l’utilisation de l’option **Plus**. (GUIDES-48304)
- L’enregistrement d’une rubrique lorsque la validation du schéma est configurée avec un fichier de règle vide affiche un message d’erreur générique inexact. (GUIDES-48106)
- Les règles de schéma utilisant un contexte de nœud de texte ne déclenchent pas de validation. (GUIDES-14500)
- L&#39;insertion d&#39;une référence croisée à l&#39;aide de l&#39;option **Lien web** permet d&#39;ajouter un lien `scope=local` et de modifier la valeur `href`, au lieu d&#39;insérer un `scope=external` comme prévu. (GUIDES-48457)
- L’enregistrement d’un mappage de référence rompt la référence au lieu de la résoudre sur le mappage correct lorsqu’un auteur déplace le mappage référencé tandis qu’un autre auteur y ajoute simultanément une référence dans un mappage non enregistré. (GUIDES-47467)

## Gestion des ressources numériques

- L’API de statut de la ressource ne renvoie pas le statut correct pour les ressources dont le chemin contient une virgule. (GUIDES-49065)
- Le filtre d’élément DITA du rail de recherche d’administration d’Assets n’applique pas la valeur saisie. Les résultats de la recherche ne sont donc pas filtrés. (GUIDES-48450)
- L’utilitaire de purge de version ne se termine pas dans plusieurs scénarios, notamment certains types de fichiers, les ressources avec des métadonnées manquantes et les rapports volumineux, au lieu de terminer la purge et de générer un rapport précis. (GUIDES-43453)
- Le changement du nom d’une ressource avec un nom de fichier basé sur un GUID à l’aide de l’opération Déplacer dans l’interface utilisateur d’Assets remplace le GUID unique d’origine de la ressource par le nouveau GUID. (GUIDES-43006)

## Publication

- Lorsque vous générez une sortie AEM Sites (avec mappage de composants composites) avec une ligne de base ciblant une ancienne version, le contenu de la page affiche correctement cette ancienne version, mais les métadonnées de la page affichent la version actuelle à la place. (GUIDES-49325)
- Lorsque des pages sont répliquées à l’aide de l’activation en bloc, les propriétés de suivi de la réplication sont définies uniquement sur la page racine et non sur les pages enfants, ce qui rend difficile la détermination du contenu modifié depuis la dernière réplication. (GUIDES-37871)
- Lorsque le champ **Libellé** de la boîte de dialogue Créer/Modifier la ligne de base reçoit le focus pour la première fois, coller ou saisir le premier caractère ne filtre pas correctement les suggestions de saisie semi-automatique et le champ affiche toutes les suggestions au lieu des résultats filtrés.(GUIDES-50143)
- Le filtrage des branches génère des pages supplémentaires pour les rubriques indésirables utilisées comme `keydef` (qui sont marquées `resource-only ="true"` par DITA-OT). (GUIDES-19701)
- La collecte des cartes active l’option **Publier** pour les paramètres prédéfinis qui n’ont pas encore été générés. (GUIDES-50510)
- La section Historique de publication n’affiche pas le texte d’espace réservé lorsqu’une collection de cartes nouvellement créée ne comporte aucun enregistrement de publication. (GUIDES-50366)
- L’application d’un profil de couleurs ICC sur un paramètre prédéfini de PDF natif entraîne l’échec de la génération de sortie et les couleurs CMJN ne s’affichent pas correctement même lorsqu’un chemin de profil direct est utilisé. (GUIDES-47137)
- Le paramètre de fond perdu configuré sur un paramètre prédéfini PDF natif n’est pas reflété dans la sortie générée. (GUIDES-47034)
- Le champ **Texte avant saut** pour la suite du tableau effectue uniquement le rendu de la chaîne localisée et ne remplace pas l’espace réservé du numéro de page. (GUIDES-32872)
- Le navigateur de profils ICC affiche incorrectement les fichiers DITA au lieu d&#39;afficher uniquement les fichiers ICC. (GUIDES-25017)
- Les commentaires de brouillon ne sont pas rendus dans la sortie native de PDF. (GUIDES-47044)
- Un commentaire de brouillon placé dans un élément de `title` apparaît de manière inattendue dans la sortie publiée. (GUIDES-10686)
- Dans le tableau de bord Mappage , la sélection d’un autre paramètre prédéfini déclenche un appel pour récupérer les liens d’homologue, ce qui entraîne un traitement supplémentaire. (GUIDES-53703)

## Traduction

- Le démarrage d’une traduction à l’aide d’un projet XLIFF crée un projet vide qui ne passe jamais à un statut en cours. (GUIDES-51759)
- Le déplacement de contenu d’un dossier de langue à un autre à l’aide de l’opération de déplacement des ressources empêche les auteurs de sélectionner ce contenu pour traduction dans le panneau Traduction . (GUIDES-49386)
- L’envoi de ressources pour traduction à l’aide de l’option **Ajouter à un projet de traduction existant** alors qu’une autre demande de traduction (création d’un nouveau projet ou *Ajouter à un projet existant*) pour le même projet est toujours en cours de traitement entraîne un conflit. (GUIDES-49354)

## Ligne de base

- La sélection de la ligne de base enregistrée d&#39;un paramètre prédéfini affiche incorrectement le statut *Aucune ligne de base* une fois la ligne de base supprimée ou pendant la création d&#39;une ligne de base dynamique. (GUIDES-52690)

## Révision

- L’ouverture du panneau Révision ou l’application d’un filtre de projet prend un certain temps pour charger la liste des tâches. (GUIDES-48893)

## Rapports

- La génération du rapport Liens rompus pour une carte comportant un grand nombre de rubriques bloque l’interface du rapport au niveau du message **Récupération des détails des liens rompus** indéfiniment, ce qui entraîne une non-réponse du navigateur et, finalement, son blocage. (GUIDES-37845)

## Contenu d’apprentissage

- Lorsqu’une nouvelle rubrique d’apprentissage est créée à l’aide d’un HTML ou d’un modèle d’apprentissage avec un en-tête personnalisé, le titre de la rubrique n’apparaît pas dans l’en-tête personnalisé. (GUIDES-52343)
- Le pourcentage de précision calculé pour un quiz de cours diffère légèrement de la valeur attendue. (GUIDES-52346)
- Pour un cours, lors de la tentative d’un quiz, les notes obtenues diffèrent légèrement du score calculé attendu. (GUIDES-52345)

## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 2026.09.0 :

- La modification de l’état du document d’une rubrique déjà verrouillée actualise l’intégralité du document. (GUIDES-53905)
- Lors de l’utilisation de la fonction Aperçu à l’aide de la ligne de base, les demandes d’aperçu expirent pour les cartes volumineuses (plus de 10 000 rubriques) ou les cartes comportant un grand nombre de `keydefs` (par exemple, 100 `keydefs` et 3 500 rubriques). (GUIDES-54147)
- Pour les serveurs de base de données, lorsqu’une carte contenant un `keydef` sans `href` est prévisualisée avec une option Aperçu à l’aide de la ligne de base activée, le `keydef` n’est pas résolu. (GUIDES-53878)
- Les zones réactives configurées sur une ressource de zone cliquable ne sont pas interactives en mode Aperçu, ce qui empêche les auteurs de valider les liens de zone réactive avant la publication. (GUIDES-53398)<br>**Solution de contournement** : insérez l’image à convertir en zone cliquable, sélectionnez **Modifier la zone cliquable** dans le menu contextuel, puis configurez les liens des zones réactives.
- Lorsque vous déplacez un mappage avec une ligne de base existante vers un autre dossier alors que le mappage est ouvert, le bouton (bascule) **Prévisualiser à l’aide de la ligne de base** reste sélectionné en mode Prévisualisation, mais la ligne de base n’apparaît plus dans la liste déroulante. (GUIDES-54284)<br>**Solution de contournement** : vous pouvez fermer puis rouvrir la carte pour résoudre le problème.
- Sur un environnement AEM Cloud Service nouvellement configuré (AEM as a Cloud Service SDK), toute tentative de création d’un fichier de mappage ou de rubrique entraîne une *Échec de la création du fichier* erreur ou *Erreur lors de la récupération de la règle DTD*. (GUIDES-53904)<br>**Solution de contournement** : vous pouvez redémarrer l’environnement AEM Cloud Service.
- Lorsque deux auteurs travaillent simultanément sur la même rubrique, le verrouillage d’une rubrique ouverte depuis un certain temps par un auteur n’actualise pas les propriétés de métadonnées telles que le numéro de version, les libellés, l’état du document, les balises, etc., même après leur modification par l’autre auteur, ce qui entraîne l’affichage continu de valeurs obsolètes. (GUIDES-54810)<br>**Solution** : fermez et rouvrez la rubrique pour actualiser les métadonnées et afficher les dernières valeurs.