---
title: Utilisation des paramètres de condition prédéfinis
description: Découvrez l’utilisation des paramètres prédéfinis de condition dans AEM Guides. Découvrez comment créer, modifier, copier et supprimer des paramètres prédéfinis de condition dans AEM.
exl-id: f6865a34-abdd-4d23-b903-0211bebd13b7
feature: Publishing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 2%

---

# Utilisation des paramètres de condition prédéfinis {#id1825FL004PN}

Vous pouvez définir des attributs dans vos rubriques DITA et utiliser le paramètre prédéfini de condition pour spécifier ce qui se passe avec l’attribut dans la sortie finale. Par exemple, vous pouvez ajouter des attributs comme version 1.0 et version 2.0 dans votre contenu, et utiliser un paramètre prédéfini de condition pour inclure la version 1.0 pour la version 1.0 et exclure la version 2.0. De même, vous pouvez ajouter des attributs sous OS Windows et OS Linux à votre contenu, puis inclure ou exclure le contenu correspondant à votre sortie finale en fonction du système d’exploitation.

Vous pouvez créer des paramètres de condition prédéfinis de deux manières différentes :

* À partir de l’éditeur web : vous permet de créer et de gérer les paramètres prédéfinis de condition pour un mappage DITA à partir de l’éditeur web.
* Depuis le tableau de bord de la carte : vous permet de créer et de gérer les paramètres prédéfinis de condition pour une carte DITA à partir du tableau de bord de la carte.


## Paramètres prédéfinis de condition de l’éditeur web

Experience Manager Guides vous permet de gérer les paramètres prédéfinis de condition à partir de l’éditeur web et de les utiliser dans les paramètres prédéfinis de sortie pour générer la sortie finale.
Vous pouvez créer et afficher les paramètres prédéfinis de condition, afficher les attributs et gérer les actions pour la carte active à partir de la vue **Paramètre prédéfini de condition** de l’éditeur web.

<img src="images//manage-condtions-presets.png" alt= "Paramètres prédéfinis de condition dans l’éditeur web" width="800" border="1px">



### Création d’un paramètre prédéfini de condition

La vue **Paramètres prédéfinis de condition** fournit des informations détaillées sur les paramètres prédéfinis de condition, tels que leurs attributs, valeurs et actions.
Vous pouvez créer un paramètre prédéfini de condition des rubriques en procédant comme suit :

1. Dans le panneau **Repository**, ouvrez le fichier de mappage DITA en mode Carte.
1. Sélectionnez l’onglet **Gérer** .
1. Sélectionnez **Paramètres prédéfinis de condition** sur la gauche. La liste des conditions prédéfinies définies pour le mappage DITA s’affiche.
1. Sélectionnez l’icône + en regard de **Paramètre prédéfini de condition** pour ouvrir la boîte de dialogue **Nouveau paramètre prédéfini de condition** .
1. Saisissez un nom unique pour le paramètre prédéfini.

   >[!NOTE]
   >
   > Vous affichez une erreur si le champ nom est vide ou si vous saisissez un caractère non valide ou un nom identique à un paramètre prédéfini de condition existant. Vous pouvez utiliser un trait d’union &quot;-&quot; ou un trait de soulignement &quot;_&quot; comme séparateur.

1. Sélectionnez **Créer**.
Le nouveau paramètre prédéfini de condition est ajouté à la liste.
1. Double-cliquez sur un paramètre prédéfini de condition pour afficher les attributs et les actions.
Le panneau **Attributs** affiche tous les attributs ajoutés à toutes les références présentes dans la carte. Le panneau de droite affiche uniquement les conditions que vous avez ajoutées aux paramètres prédéfinis de condition.
1. Pour ajouter les attributs, effectuez l’une des opérations suivantes :
   * Sélectionnez un ou plusieurs attributs pour ajouter toutes les valeurs sous-jacentes au paramètre prédéfini de condition. Par exemple, vous pouvez sélectionner l’attribut `platform` pour ajouter toutes ses valeurs.
   * Sélectionnez une ou plusieurs valeurs d’attribut pour les ajouter au paramètre prédéfini de condition. Par exemple, vous pouvez sélectionner les valeurs `Unix` et `Win` de l’attribut platform
   * Sélectionnez n’importe quelle paire d’attributs et de valeurs et faites-la glisser vers le panneau central. Par exemple, vous pouvez sélectionner la valeur `Unix` de l’attribut platform et la faire glisser.
   * **Sélectionnez all** pour ajouter tous les attributs et leurs valeurs au paramètre prédéfini de condition.
Par défaut, l’action d’un attribut est `Include`.

1. Sélectionnez **Ajouter**. Vous pouvez répéter cette étape pour ajouter d’autres attributs. Les attributs que vous ajoutez passent du central au panneau de droite.
1. Sélectionnez Supprimer dans la barre d’actions supérieure pour supprimer les attributs sélectionnés dans le panneau de droite.
1. (Facultatif) Si nécessaire, vous pouvez remplacer l’action appliquée aux attributs.
Utilisez l’une des méthodes suivantes :
   * Pour tout attribut, sélectionnez l’une des actions suivantes dans la liste déroulante Action .
      * Inclure
      * Exclure
      * Passage
      * Marquer
   * Sélectionnez plusieurs lignes d’attributs dans le panneau de droite et choisissez une action dans la barre d’actions située en haut. Par exemple, vous pouvez sélectionner Exclure l’action pour les attributs sélectionnés.
1. Sélectionnez **Enregistrer** pour enregistrer le paramètre prédéfini de condition.

   >[!NOTE]
   >
   > Un avertissement s’affiche si vous sélectionnez un autre paramètre prédéfini ou fermez-le sans l’enregistrer.

Une fois que vous avez créé un paramètre prédéfini de condition, il apparaît sous la liste déroulante **Paramètres prédéfinis de condition** des paramètres prédéfinis de sortie. En savoir plus sur la [sortie Publish PDF](../web-editor/native-pdf-web-editor.md).

### Renommer un paramètre prédéfini de condition

Pour renommer un paramètre de condition prédéfini, procédez comme suit :

1. Passez la souris sur un paramètre prédéfini de condition du panneau **Paramètres prédéfinis de condition** .
1. Sélectionnez **Renommer** dans le menu Options pour ouvrir la boîte de dialogue **Renommer le paramètre prédéfini de condition** .
1. Modifiez le nom du paramètre prédéfini de condition.
1. Cliquez sur **Renommer**.

### Duplication d’un paramètre prédéfini de condition

Effectuez les étapes suivantes pour dupliquer un paramètre prédéfini de condition :

1. Passez la souris sur un paramètre prédéfini de condition du panneau **Paramètres prédéfinis de condition** .
1. Sélectionnez **Dupliquer** dans le menu Options pour ouvrir la boîte de dialogue **Dupliquer le paramètre prédéfini de condition** .
   >[!NOTE]
   >
   > Le nom par défaut du paramètre prédéfini est `<selected condition preset name>_1`. Vous pouvez modifier le nom en fonction de vos besoins.

1. Cliquez sur **Dupliquer**.

### Supprimer le paramètre prédéfini de condition

Pour supprimer des paramètres prédéfinis de condition, procédez comme suit :

1. Passez la souris sur un paramètre prédéfini de condition du panneau **Paramètres prédéfinis de condition** .
1. Sélectionnez **Supprimer** dans le menu Options pour ouvrir la boîte de dialogue **Supprimer le paramètre de condition prédéfini**.
1. Cliquez sur **Supprimer**.



## Paramètres prédéfinis de condition du tableau de bord de la carte


### Création d’un paramètre prédéfini de condition

Pour créer un paramètre de condition prédéfini, procédez comme suit :

1. Sélectionnez l’onglet **Paramètres prédéfinis de condition** dans la console de mappage DITA.
1. Cliquez sur le bouton **Créer** .
1. Saisissez un nom pour le paramètre prédéfini dans **Condition de nom**.
1. Sélectionnez l’une des actions par défaut suivantes dans la liste déroulante **Définir l’action par défaut sur** :

   * Inclure
   * Exclure
   * Passage
   * Indicateur
L’action est définie comme action par défaut pour tous les attributs, qu’ils soient ajoutés ou non au paramètre prédéfini de condition.

   Par exemple, votre document contient 15 attributs de condition et vous en avez inclus quatre dans le paramètre prédéfini de condition. Si vous sélectionnez l’action par défaut **exclude** , elle est appliquée aux 15 attributs.

1. Pour ajouter les attributs, effectuez l’une des opérations suivantes :
   * Cliquez sur **Ajouter** à un attribut du paramètre de condition prédéfini. Vous pouvez répéter cette étape pour ajouter d’autres attributs.
   * Cliquez sur **Ajouter tout** pour ajouter tous les attributs au paramètre de condition prédéfini.
1. \(Facultatif\) Si nécessaire, vous pouvez remplacer l’action par défaut appliquée aux attributs à l’étape 4. Utilisez l’une des méthodes suivantes :
   * Sélectionnez plusieurs attributs, choisissez une action à partir de **Définissez l’action pour les conditions sélectionnées sur**, puis cliquez sur **Appliquer**.
   * Sélectionnez une action pour un attribut dans la liste déroulante **Action**.
1. Cliquez sur **Enregistrer**.

### Modifier un paramètre prédéfini de condition

Vous pouvez apporter des modifications à un paramètre prédéfini de condition existant afin de modifier les actions appliquées aux attributs dans le paramètre prédéfini de condition. Effectuez les étapes suivantes pour modifier un paramètre prédéfini de condition :

1. Sélectionnez l’onglet **Paramètres prédéfinis de condition** dans la console de mappage DITA.
1. Cliquez sur le bouton **Modifier** .
1. Apportez les modifications requises pour tous les attributs du paramètre prédéfini de condition.
1. Cliquez sur **Enregistrer**.

### Création d’une copie d’un paramètre prédéfini de condition

Vous pouvez créer une copie d’un paramètre prédéfini de condition, puis le modifier selon vos besoins. Effectuez les étapes suivantes pour créer une copie d’un paramètre prédéfini de condition :

1. Sélectionnez l’onglet **Paramètres prédéfinis de condition** dans la console de mappage DITA.
1. Cliquez sur le bouton **Dupliquer** .

   >[!NOTE]
   >
   > Le nom par défaut du paramètre prédéfini est `<selected condition preset name>_Duplicate`

   Vous pouvez modifier le nom en fonction de vos besoins.

1. \(Facultatif\) Apportez les modifications requises pour tous les attributs du paramètre prédéfini de condition.
1. Cliquez sur **Enregistrer**.

### Supprimer le paramètre prédéfini de condition

Vous pouvez supprimer un ou plusieurs paramètres prédéfinis de condition dans l’onglet **Paramètre prédéfini de condition** de la console de mappage DITA. Pour supprimer des paramètres prédéfinis de condition, procédez comme suit :

1. Sélectionnez l’onglet **Paramètres prédéfinis de condition** dans la console de mappage DITA.
1. Sélectionnez le ou les paramètres prédéfinis de condition que vous souhaitez supprimer.
1. Cliquez sur le bouton **Supprimer** .
1. Cliquez sur **Supprimer** pour confirmer l’action.

**Rubrique parente :**[ Génération de sortie](generate-output.md)
