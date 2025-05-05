---
title: Remplacements de configuration
description: Découvrez comment remplacer des configurations
exl-id: dc5f81f7-5b0a-4d12-a944-ba66b0239d5c
feature: Installation
role: Admin
level: Experienced
source-git-commit: dae38cf948b99c8b89c61472938ce97b571f9366
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---

# Remplacements de configuration {#id216IFC003XA}

Pour effectuer les mises à jour de configuration, l’approche générique suivante doit être utilisée :

1. Accédez à votre référentiel Git Cloud Manager.

1. Créez un fichier JSON à l’emplacement suivant :

   src/main/content/jcr\_root/apps/fmditaCustom/config/

1. Nommez le fichier au format suivant :

   $\{PID\}.cfg.json

   Ici, le PID est l’identifiant de processus de la configuration.

1. Ajoutez des propriétés dans le fichier JSON à l’aide du format suivant :

   ```
   {
      "aem.adminuname": "updatedUserjson",
      "valid.characters": "[-a-zA-Z0-9_@$]",
      "dita.serialization": true
   }
   ```

1. Validez les modifications et exécutez le pipeline Cloud Manager pour déployer la configuration mise à jour.

## Configuration de l’interface utilisateur de Experience Manager Guides

La version 2025.02.0 d’Adobe Experience Manager Guides propose une interface utilisateur repensée et des fonctionnalités améliorées pour vous aider à travailler plus rapidement et plus efficacement que jamais auparavant. Cela comprend une toute nouvelle page d’accueil, une barre d’outils d’éditeur plus propre et plus organisée, une console de mappage dédiée et des fonctionnalités améliorées.

Pour garantir une transition fluide et minimiser les perturbations, Experience Manager Guides fournit une option de configuration qui vous permet de revenir à l’ancienne interface utilisateur ( et vice versa) si nécessaire.

>[!IMPORTANT]
>
> Cette option de configuration permettant de basculer entre la nouvelle et l’ancienne interface utilisateur sera disponible jusqu’à la version 2025.4.0. Ensuite, la nouvelle interface utilisateur devient la valeur par défaut et l’option permettant de revenir à l’interface utilisateur précédente n’est plus prise en charge.

Effectuez les étapes suivantes pour configurer l’interface utilisateur de Experience Manager Guides :

1. Ouvrez Adobe Experience Manager, puis sélectionnez votre programme contenant l’environnement à configurer.
2. Passez à l’onglet **Environnements**.
3. Sélectionnez le nom de l’environnement à configurer. Vous devriez y accéder à la page **Informations sur l’environnement**.
4. Passez à l’onglet **Configuration**.
5. Sélectionnez **Ajouter/Mettre à jour**.
6. Ajoutez les détails de configuration de l’interface utilisateur. Assurez-vous que vous utilisez le même nom et la même configuration que dans la capture d’écran suivante.

   ![](assets/enable-penultimate-ui.png){width="800" align="left"}

   La définition de la valeur sur **true** conserve l’ancienne IU, tandis que **false** active la nouvelle IU.



**Rubrique parente :**&#x200B;[ Télécharger et installer](download-install.md)
