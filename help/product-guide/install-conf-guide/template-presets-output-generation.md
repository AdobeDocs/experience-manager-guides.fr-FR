---
title: Préréglages de modèles pour la génération de sortie
description: Découvrez comment créer et utiliser des paramètres prédéfinis de modèle pour la génération de sortie dans Adobe Experience Manager Guides.
source-git-commit: 0107a693c6d07c84f20dad7a9ffb53e8cb888d08
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 1%

---


# Configuration des paramètres prédéfinis de modèle pour la génération de sortie

>[!NOTE]
>
> Le paramètre prédéfini de modèle est disponible dans Experience Manager Guides as a Cloud Service à partir de la version 2026.08.0. Contactez votre équipe du succès client pour activer cette fonctionnalité.

Les paramètres prédéfinis de modèle permettent aux administrateurs de normaliser les configurations de paramètres prédéfinis de sortie sur plusieurs plans DITA. Au lieu de configurer le même paramètre prédéfini de sortie individuellement pour chaque mappage, vous pouvez définir un paramètre prédéfini en tant que modèle et l’appliquer à tous les mappages associés à un profil de dossier.

Cette fonctionnalité vous permet de maintenir des configurations de publication cohérentes entre les projets et de réduire les efforts de configuration manuelle.

## Avantages

L’utilisation des paramètres prédéfinis de modèle offre les avantages suivants :

- Garantit la cohérence des configurations de publication sur plusieurs mappages.
- Réduit les efforts manuels en éliminant la configuration répétitive des paramètres prédéfinis.
- Permet une gestion centralisée des paramètres prédéfinis de sortie.

## Types de sortie pris en charge

Les paramètres prédéfinis de modèle sont pris en charge pour tous les types de paramètres prédéfinis de sortie, à l’exception des suivants :

- Edge Delivery Services
- Knowledge Base
- SCORM

## Créer et gérer un paramètre prédéfini de modèle

>[!NOTE]
>
> - Les paramètres prédéfinis de modèle ne peuvent être créés et gérés que par **Administrateurs** et **Administrateurs de profil de dossier**.
> - Les paramètres prédéfinis de modèle sont destinés à la gestion de la configuration et ne sont pas utilisés directement pour la génération de sortie.

1. Configurez le Profil du dossier à utiliser pour les dossiers.
2. Ouvrez **Paramètres prédéfinis de sortie** à partir de la console Mappage pour le dossier associé.
3. Créez ou sélectionnez le paramètre prédéfini de sortie à utiliser comme modèle.

   >[!NOTE]
   >
   > Lors de la création ou de la sélection du paramètre prédéfini de sortie à utiliser comme modèle, assurez-vous qu’il est ajouté au profil du dossier actif.

4. Sélectionnez le **Définir comme modèle** dans le menu **Options** du paramètre prédéfini.

   ![](assets/template-preset.png){width="650"}

   Le paramètre prédéfini de sortie sélectionné est converti en paramètre prédéfini de modèle. Les paramètres prédéfinis de modèle sont identifiés par une icône de modèle qui les distingue des paramètres prédéfinis standard. Pour supprimer le statut du modèle, sélectionnez **Annuler en tant que modèle** à tout moment dans le menu **Options** du paramètre prédéfini de modèle.

   ![](assets/unset-as-template.png){width="650"}

5. Sélectionnez **Appliquer les modifications du paramètre prédéfini** dans le menu **Options** du paramètre prédéfini de modèle pour appliquer les paramètres prédéfinis mis à jour à tous les mappages existants dans le profil de dossier sélectionné.

   La boîte de dialogue **Appliquer les modifications de paramètre prédéfini** s’ouvre.

   ![](assets/apply-preset-change.png){width="350"}

6. Pour remplacer le paramètre prédéfini existant, cochez la case **Remplacer le paramètre prédéfini existant** et sélectionnez **OK**. Le remplacement met à jour le paramètre prédéfini, mais ne modifie pas les paramètres Ligne de base, Paramètre prédéfini de condition, DITAVAL, Liste de rubriques ou Contexte de publication dans le paramètre prédéfini cible. Ces paramètres restent inchangés.

   Une boîte de dialogue **Confirmer l’action** s’ouvre, indiquant le nombre de mappages auxquels s’appliquent les modifications du paramètre prédéfini.

   ![](assets/confirm-preset-change.png){width="350"}

7. **Cliquez sur OK**.

Les modifications sont appliquées à tous les paramètres prédéfinis de tous les mappages dans les dossiers associés.

>[!NOTE]
>
> Lors de la création d’un mappage dans le dossier associé, la copie locale du préréglage de modèle est également disponible pour ce mappage nouvellement créé.


## Comportement de la génération de sortie

Les paramètres prédéfinis de modèle sont des modèles de configuration et ne sont pas destinés à la publication directe. Lorsqu’un paramètre prédéfini est marqué comme modèle :

- La sortie générée n’est pas disponible.
- Le paramètre prédéfini de modèle ne peut pas être utilisé pour la publication.
- Les sorties générées existantes pour le paramètre prédéfini de modèle restent accessibles si elles ont été créées avant la conversion du paramètre prédéfini en modèle.



