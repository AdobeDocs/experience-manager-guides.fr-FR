---
title: Configurer d’autres paramètres
description: Découvrez comment configurer des dossiers, des dossiers de ressources, des variables, des fragments de code, des conditions, etc. pour différents services dans Experience Manager Guides.
feature: Authoring
role: Admin
level: Experienced
source-git-commit: 5f42540a32da6e85a5c8aa0831582ce871c9088a
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---

# Configurer d’autres paramètres

En tant qu’administrateur, vous pouvez également configurer les paramètres suivants pour les auteurs et éditeurs des cours de formation :

- **Paramètres des dossiers**
   - **Créer des dossiers différents** : vous pouvez créer des dossiers pour les auteurs et les éditeurs travaillant dans différents services ou produits de votre entreprise. Ces dossiers peuvent être associés à des profils de dossier spécifiques, chacun configuré avec différents modèles de création et de sortie pour prendre en charge la création de cours d’apprentissage spécifiques au service et une administration décentralisée.

     Vous pouvez créer un dossier à partir du panneau Référentiel.

     ![](assets/create-new-folder.png){width="350" align="left"}
   - **Créer des dossiers de langue** : si vous traduisez du contenu dans différentes langues, vous devez créer des dossiers correspondant à chaque langue. Chacun de ces dossiers de langue contient le contenu correspondant à cette langue.

     Pour plus d’informations, consultez [Bonnes pratiques pour la traduction de contenu](../user-guide/translation-first-time.md).
   - **Gestion d’Assets** : comme pour les dossiers, vous pouvez également créer différents dossiers Assets pour répondre aux besoins de différents services. Ainsi, vous vous assurez également que les auteurs et les éditeurs ont accès au CSS correct configuré dans leurs modèles, images et autres ressources.

     ![](assets/configure-assets-folder.png){width="350" align="left"}
- **Fragments de code** : vous pouvez configurer les fragments de code au niveau du dossier pour vous assurer que les auteurs ont accès aux fragments de code appropriés. Seuls les administrateurs peuvent créer des fragments de code dans Experience Manager Guides, qui peuvent ensuite être utilisés par les auteurs dans l’éditeur.

  Vous pouvez accéder à Fragments de code à partir du panneau de gauche dans l’éditeur.

  ![](assets/create-snippets.png){width="350" align="left"}
- **Conditions** : en tant qu&#39;administrateur, vous pouvez configurer des attributs conditionnels standard pris en charge par DITA au niveau global ou au niveau du dossier. Les auteurs utilisent ensuite les conditions configurées en faisant simplement glisser et en déposant la condition souhaitée sur leur contenu.

  Vous pouvez accéder aux Conditions dans le panneau de gauche de l’éditeur.

  ![](assets/create-conditions.png){width="350" align="left"}
- **Variables** : vous pouvez définir des variables pour rendre votre contenu plus portable, cohérent et facile à mettre à jour. Lors de la génération de la sortie, les variables sont remplacées par les valeurs de l’ensemble de variables sélectionné, ce qui vous permet de produire efficacement des sorties personnalisées.

  Pour plus d’informations, consultez la section [Créer une variable](../native-pdf/native-pdf-variables.md#create-a-new-variable)

- **Barre d’outils de l’éditeur** : vous pouvez personnaliser la barre d’outils de l’éditeur en fonction des besoins de votre organisation. Par exemple, vous pouvez préférer modifier le nom d’un bouton de barre d’outils, changer son emplacement, etc.

  Pour plus d’informations, consultez [Configuration et personnalisation de l’éditeur XML](../cs-install-guide/conf-folder-level.md#configure-and-customize-the-xml-editor-id2065g300o5z).
