---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides, version 2026.06.0
description: Découvrez les correctifs de bugs de la version 2026.06.0 d’Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 318f2b7a530e50ca4432313650801b2293d6697e
workflow-type: tm+mt
source-wordcount: '2171'
ht-degree: 0%

---

# Correction de problèmes dans la version 2026.06.0

Cet article couvre les bugs corrigés dans différentes zones de la version 2026.06.0 d’Adobe Experience Manager Guides as a Cloud Service.

Pour plus d’informations sur les nouvelles fonctionnalités et améliorations, consultez [Nouveautés de la version 2026.06.0](whats-new-2026-06-0.md).

Découvrez les [instructions de mise à niveau pour la version 2026.06.0](upgrade-instructions-2026-06-0.md).

## Création

- Lors du basculement de la sélection entre les champs **Largeur** et **Hauteur** dans la boîte de dialogue des propriétés de l’image à l’aide de tailles d’unité telles que `in`, `mm` ou `px`, les valeurs continuent d’augmenter progressivement au lieu de rester stables. (GUIDES-45929)

## Éditeur 2.0

- Si vous copiez et collez des `<keywords>` à l’intérieur de `<topicmeta>` dans une `<keydef>` ou une `<topicref>`, les mots-clés sont insérés dans des balises étrangères indésirables. (GUIDES-45800)
- Les dimensions d’image spécifiées avec des unités telles que `mm` ne s’affichent pas correctement, ce qui entraîne l’affichage des images à leur taille d’origine au lieu des dimensions spécifiées. (GUIDES-46275)
- Lors d’un glisser-déposer avec la vue Balise activée, la sélection de contenu avec des balises XML ou DITA partielles laisse des balises orphelines indésirables, ce qui entraîne un contenu ou une vue incorrect. (GUIDES-28191)
- Dans la vue Balise d’un tableau, appuyer sur la touche fléchée vers le haut lorsque le curseur est positionné dans la cellule située directement en dessous d’une balise d’entrée réduite ignore la balise réduite et déplace le curseur au début du document. (GUIDES-45408)
- Toute opération effectuée à partir de la barre d&#39;outils contextuelle du tableau ferme la barre d&#39;outils de manière inattendue, interrompant les opérations suivantes du tableau. (GUIDES-45405)
- Après avoir utilisé **Insérer après** ou **Insérer avant** à partir du chemin de navigation ou de la vue Plan, le curseur se déplace vers une position arbitraire au lieu de se trouver à l’intérieur de la balise nouvellement ajoutée. (GUIDES-45147)
- Lorsque l’option **Modifier MathML** s’affiche incorrectement en mode lecture seule ou lorsqu’un fichier est extrait par un autre utilisateur, elle permet aux utilisateurs de mettre à jour le contenu de MathML même si le fichier ne doit pas être modifiable. (GUIDES-45172)
- Lors de la suppression d’un commentaire XML à l’aide de la touche Retour arrière, la balise de commentaire n’est pas supprimée après la suppression de son contenu et l’opération de suppression se poursuit dans l’élément précédent. (GUIDES-45240)
- L’utilisation de l’option **Copier le chemin d’accès** ou **Copier l’UUID** pour les images renvoie le chemin d’accès complet au rendu au lieu du chemin d’accès à la ressource d’origine. (GUIDES-45278)
- Copier-coller du contenu dans la même rubrique vers un emplacement non valide dans l’éditeur insère une balise `<foreign>` involontaire. (GUIDES-45378)
- Sous Windows, la copie et le collage d’une ligne de tableau ajoutent des attributs inattendus, tels que `data-pm-slice`, à l’élément du tableau, provoquant des erreurs de balisage qui empêchent l’enregistrement du document. (GUIDES-45784)
- À l’aide de l’option **Copier** du menu contextuel dans un mappage ou une rubrique, puis en collant le contenu, insère des balises `<data>` supplémentaires dans la sortie collée. (GUIDES-45703)
- Lorsque vous faites glisser une sélection partielle à partir d’un élément de `cmd`, le contenu ne peut pas être déposé entre du texte existant ou à la fin d’un autre élément de `cmd`. (GUIDES-44883)
- Lors de l’application d’un attribut `scale` à un tableau, le tableau n’est pas rendu à la taille configurée en modes Création et Aperçu . (GUIDES-45984)
- Le collage d’images copiées à partir de sources externes telles que Paint ou l’outil Capture n’insère pas l’image dans la rubrique. (GUIDES-45983)
- Le `keyref` utilisé dans un titre de rubrique dérivé d’une correspondance de mots-clés n’apparaît pas dans l’onglet Table des matières ou rubrique après l’enregistrement, même après une actualisation du navigateur. (GUIDES-45799)
- L’ouverture d’une tâche de révision dans l’éditeur à l’aide de la vue côte à côte pour la version commentée affiche la version avec la valeur Aucune au lieu de la version associée pour la rubrique. (GUIDES-45127)
- Lors de l’accès à la page Tâche de révision , les sauts de page entre les rubriques ne s’affichent pas, ce qui entraîne le rendu continu des sections de contenu. (GUIDES-46777)
- Le style de la page de révision n’est pas cohérent avec la nouvelle expérience de l’éditeur, ce qui entraîne une expérience visuelle incohérente (GUIDES-46061)

## Gestion des ressources numériques

- Lorsqu&#39;un mappage contient un `topicref` externe pointant vers une ressource non DITA (telle que `.html`), son aperçu ne s&#39;affiche pas dans l&#39;interface utilisateur d&#39;Assets. (GUIDES-45409)
- La boîte de dialogue Outil de déplacement en bloc déborde et ne comporte pas de barre de défilement lorsqu’un grand nombre de dossiers source sont sélectionnés, ce qui rend le champ de chemin de destination et les boutons d’action inaccessibles aux utilisateurs uniquement avec la souris. (GUIDES-45805)
- Lorsque la ressource est copiée à partir de l’interface utilisateur d’Assets, nous obtenons une notification pour `DXML reprocessing failure`. Cette notification est trompeuse et contribue à encombrer les boîtes de réception, car la copie a réussi. (GUIDES-45012)
- Lors de l’ouverture du panneau Filtre dans le rail de gauche d’Assets dans un dossier, le champ de recherche et les facettes restent désactivés jusqu’à ce que le panneau soit fermé et rouvert. (GUIDES-42652)
- Les fragments de contenu et les ressources de traduction intermédiaires créés pendant les workflows de traduction sont involontairement traités par la tâche de traitement des ressources planifiée, ce qui entraîne des exceptions dans les journaux et un traitement incorrect des ressources qui ne sont pas encore prêtes. (GUIDES-42582)

## Publication

- Lorsque vous travaillez avec des fichiers `.plt` et `.css` dans des modèles PDF, l’option **Générer des identifiants** est disponible dans le menu contextuel accessible par un clic droit, bien qu’elle ne s’applique pas à ces types de fichiers. (GUIDES-45254)
- Le bouton **Enregistrer** est incorrectement activé par défaut lors de la réouverture d’un paramètre prédéfini d’AEM Sites natif nouvellement créé après une actualisation du navigateur, même si aucune modification n’a été apportée. (GUIDES-45171)
- Lors de la duplication d’un paramètre prédéfini PDF natif marqué comme valeur par défaut, le doublon est également défini comme paramètre prédéfini par défaut. Un seul paramètre prédéfini doit être désigné comme paramètre par défaut à la fois. (GUIDES-44786)
- L’attribut `outputclass` n’est pas propagé à la sortie HTML ou Native PDF générée, ce qui empêche les classes personnalisées appliquées aux équations de MathML d’affecter la sortie rendue. (GUIDES-44393)
- L’activation en bloc de la sortie AEM Sites générée à l’aide du nouveau modèle AEM Sites échouait, empêchant la réplication réussie vers l’instance de publication. (GUIDES-44049)
- Les fichiers JAR `jackson-databind` vulnérables (version 2.9.8) fournis avec AEM Guides dans le package DITA-OT sont identifiés. (GUIDES-43081)
- L’ouverture d’une sortie AEM Sites native à partir d’une collection de mappages entraîne une erreur indiquant que la ressource est introuvable, ce qui empêche l’accès à la sortie générée. (GUIDES-42065)
- L&#39;élément `<reltable>` dans un plan DITA est ignoré pendant la génération native de PDF, ce qui entraîne l&#39;absence des sections de référence croisée « Concepts associés », « Tâches associées » et similaires générées automatiquement dans la sortie. (GUIDES-38333)
- Lors de la publication d&#39;un plan DITA avec des éléments `processing-role=resource-only` sur AEM Sites (avec le mappage de composants hérité), des pages de site orphelines sont générées pour ces éléments dans des scénarios supplémentaires tels que des éléments `topicgroup` et des configurations de contenu spécifiques. (GUIDES-37650)
- Lorsqu’une carte avec un nom long est ajoutée à une collection de cartes, l’interface utilisateur de la collection de cartes s’affiche avec une disposition déformée. Ce problème a été résolu avec la collection New maps. (GUIDES-42062)
- Publication avec le moteur PDF natif v1 :
   - Lors de la génération d’une sortie Native PDF pour certains contenus, seule la première page est rendue dans PDF, malgré l’HTML intermédiaire contenant l’intégralité du contenu sur plusieurs pages. (GUIDES-28270)
   - L’ordre de lecture du contenu dans la sortie PDF native avec les paramètres d’accessibilité activés est incorrect. Les numéros de page des pieds de page sont lus avant le contenu principal et non à la fin. (GUIDES-27790)
   - La barre de couleurs dans la sortie Native PDF ne s’étend pas sur toute la largeur de la page et se chevauche lorsque la taille de la page est personnalisée, ce qui masque certaines zones de couleur. (GUIDES-15505)
   - Le sélecteur de pseudo-classe CSS `:is()` n’est pas respecté dans la sortie Native PDF, ce qui entraîne des différences de style par rapport au rendu du navigateur. (GUIDES-11328)

  >[!NOTE]
  >
  > Les problèmes susmentionnés ont été résolus avec le moteur PDF natif v2. Pour plus d’informations, consultez la section [Utilisation du moteur PDF natif v2](../native-pdf/new-pdf-engine.md).

## Traduction

- L’application d’une ligne de base à une carte avec de nombreuses ressources retarde le chargement du rapport de traduction pour la langue sélectionnée, ce qui entraîne parfois un délai d’expiration de la demande avant le rendu du rapport. (GUIDES-45508)
- Les groupes de langues de l’onglet Traduction dans les Paramètres Workspace ne sont pas conservés lorsque le dossier de langue sélectionné utilise un code de paramètre régional avec trait d’union (par exemple, `da-DK`) au lieu d’un format de trait de soulignement (`da_dk`). (GUIDES-37843)

## Révision

- L’info-bulle de l’icône **Historique des versions** est manquante dans le panneau de gauche de l’interface utilisateur de révision à côté du nom de la rubrique. (GUIDES-45511)
- Lors de la modification d’une tâche de révision active, si une rubrique qui fait déjà partie de la révision est supprimée puis ajoutée à nouveau sans sélectionner **Mettre à jour**, les informations du réviseur pour cette rubrique sont perdues. (GUIDES-38774)
- Le volet Contenu de l’interface utilisateur de révision affiche une barre de défilement horizontale dans certaines résolutions d’écran, notamment la résolution recommandée de 1 600 px, ce qui masque les commentaires de révision lorsque le contenu s’étend au-delà de la largeur du volet. (GUIDES-44082)

## Contenu d’apprentissage

- Lors de l’ajout de questions à un quiz à l’aide de l’option Insérer à partir de la banque de questions , les questions à réponse courte ne sont pas répertoriées malgré un ID de question valide. (GUIDES-44942)
- Lors de l’insertion de questions à l’aide de l’option Insérer à partir de la banque de questions , la boîte de dialogue Insérer à partir de la banque de questions scintille ou se redimensionne de manière inattendue à l’ouverture. (GUIDES-45524)
- Lors de l’insertion de questions à l’aide de l’option Insérer à partir de la banque de questions , une erreur se produit si le titre de la question contient une image. (GUIDES-45383)
- La sélection d’un modèle de sortie SCORM entraîne une erreur d’application lorsque le titre du modèle a été modifié. (GUIDES-45521)
- Les fichiers de sous-titres (`.vtt`) ne sont pas visibles dans la vue Référentiel ou Explorateur après avoir été chargés dans un dossier. (GUIDES-46014)
- Lors du chargement du contenu vidéo dans l’aperçu HTML, le chemin d’accès source (`src`) inclut un chemin de rendu ajouté au lieu de conserver le chemin d’accès au fichier d’origine, ce qui empêche le rendu correct de la vidéo. (GUIDES-41776)
- La publication d’une sortie SCORM à partir du navigateur Safari entraîne le téléchargement du package sous la forme d’un dossier au lieu d’un fichier zip, ainsi que des problèmes de rendu et de fonctionnalité dans le contenu généré (par exemple, contenu étiré, accordéon non fonctionnel, etc.). (GUIDES-45119)
- Un délai est observé avant que le bouton Suivant ne soit activé pour les cours, ce qui a un impact sur l’expérience de navigation de l’élève. (GUIDES-45113)
- Le style des questions à réponse courte ne s’affiche pas correctement dans la sortie de publication, même si elle s’affiche correctement en aperçu. (GUIDES-46478)
- Lors de la génération d’une sortie PDF pour les cours contenant des vidéos, le contenu vidéo n’est pas rendu et seul le chemin d’accès au fichier s’affiche au lieu d’une image d’espace réservé, telle qu’une miniature ou une image d’affiche vidéo. Ce problème a été résolu en activant l’option **Incorporer des fichiers multimédias** dans le paramètre prédéfini de sortie PDF natif.(GUIDES-45117)
- Les pseudo-classes et les éléments CSS sont rendus en blanc dans l’éditeur du guide, ce qui les rend invisibles ou difficiles à lire en arrière-plan de l’éditeur. (GUIDES-45116)

## Problèmes connus

Adobe a identifié les problèmes connus suivants pour la version 2026.06.0 :

## Éditeur 2.0

- Le passage entre les modes Source et Auteur entraîne des incohérences de contenu, certaines parties de la rubrique disparaissant ou n’étant pas reflétées entre les modes. (GUIDES-47432)

- Lorsque vous utilisez le suivi des modifications, le rejet d’une insertion de texte importé supprime tout le contenu de la balise au lieu de rejeter uniquement le contenu inséré spécifique. (GUIDES-48319)

- Le bouton **Exporter en tant que PDF** en mode Aperçu n’effectue aucune action lorsque la barre d’outils de l’éditeur est personnalisée à l’aide de `editor_toolbar.json` dans un profil de dossier. (GUIDES-47525)

- Lors des opérations de suppression, des incohérences mineures dans le mouvement et la navigation du curseur peuvent se produire sur les zones cliquables, les éléments structurés, les balises de formatage intégrées et les blocs non fusionnables, ce qui peut parfois entraîner un comportement inattendu du curseur ou de la suppression. (GUIDES-46756)

- L’utilisation de `Ctrl+click` sur un lien rompu dans un éditeur de cartes déclenche une erreur d’application. (GUIDES-45544)

- Appuyer sur la touche Retour arrière au début d’un paragraphe juste après un contenu en lecture seule (tel qu’un paragraphe `conref`) peut supprimer ou fusionner de manière inattendue le paragraphe modifiable, ce qui entraîne la suppression inattendue du paragraphe modifiable. (GUIDES-45049)

- Lorsque des indicateurs de condition sont appliqués à des éléments tels que `bodydiv`, les indicateurs débordent sur les balises adjacentes dans la vue Balises complètes, ce qui entraîne un rendu visuel incorrect. (GUIDES-44971)

- Lorsque vous travaillez dans l’éditeur, vous ne pouvez pas sélectionner de `keyrefs` ou de clés dérivés de mappages (y compris les entrées de glossaire dans les mappages référencés dans des éléments `term` ou `abbreviated-form`), ce qui entraîne une dégradation de l’expérience de création. (GUIDES-45790) <br> **Solution** : vous pouvez modifier la valeur de `keyref` dans le panneau de droite à l’aide des valeurs d’attributs.

- En mode Plan, la réactivation de la fonction **Afficher le texte** après la fermeture et la réouverture d&#39;une rubrique n&#39;affiche pas de texte à côté des balises d&#39;élément. (GUIDES-48320) <br> **Solution** : activez l’option **Afficher le texte**, puis rouvrez la rubrique. Après la réouverture, le texte s’affiche correctement à côté des balises d’élément.

- Lorsqu’une balise intégrée est renommée à l’aide de l’option **Renommer l’élément**, le chemin de navigation ne se met pas immédiatement à jour et ne reflète la modification qu’après le déplacement du curseur dans la balise ou la modification du mode d’affichage. (GUIDES-44993) <br> **Solution** : actualisez le navigateur après avoir renommé la balise intégrée pour mettre à jour le chemin de navigation.

- Lorsqu’une équation MathML est insérée en tant que `conref`, elle ne s’affiche pas correctement. (GUIDES-46601) <br> **Solution** : Encapsulez l’équation MathML dans un élément de `<p>` et utilisez cet élément de `<p>` comme source de conref.

## Révision

- Lorsqu’une tâche de révision est réaffectée à un utilisateur extérieur à l’équipe du projet, l’utilisateur peut effectuer des actions de révision malgré l’absence d’appartenance au projet, tandis que la visibilité des réviseurs, le suivi du statut de révision et les notifications de délégation ne fonctionnent pas correctement. (GUIDES-46602)

## Publication

- Lors de la publication de contenu avec le filtrage DITAVAL qui exclut tous les éléments de liste à puces par le biais du profilage conditionnel, la sortie conserve incorrectement une puce vide au lieu de supprimer l’ensemble de la structure de la liste. (GUIDES-47238)

- Lors de la publication d’une sortie de site AEM natif avec une nouvelle ligne de base, la liste des rubriques apparaît vide et n’affiche pas les rubriques incluses dans la ligne de base sélectionnée. (GUIDES-46480) <br> **Solution** : publiez la sortie native du site AEM à l’aide de l’ancienne ligne de base, qui peut être configurée via le gestionnaire de configuration.





