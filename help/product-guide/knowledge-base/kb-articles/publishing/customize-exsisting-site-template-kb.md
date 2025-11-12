---
title: Personnaliser les modèles de site AEM existants pour AEM Guides
description: Découvrez comment personnaliser les modèles de site AEM existants pour AEM Guides
feature: Installation
role: Admin
level: Experienced
exl-id: d48709b8-f5b2-4545-ac65-838c5d8b1bae
source-git-commit: 4c564a0ffaa8f287bcaf012634d49dbf1e0682b4
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 1%

---

# Personnaliser les modèles de site AEM existants pour AEM Guides

Ce guide fournit des instructions détaillées pour personnaliser les modèles de site AEM existants à utiliser avec AEM Guides afin de générer AEM Sites à partir de cartes et de rubriques DITA.

Si vous utilisez le modèle prêt à l’emploi AEM Guides (AEMG Docs) , les configurations et les composants sont déjà en place et peuvent être utilisés en l’état pour publier votre contenu AEM Guides. Cependant, si vous souhaitez utiliser vos modèles AEM Sites existants avec une valorisation de marque personnalisée pour publier du contenu AEM Guides, suivez les étapes ci-dessous pour aligner vos modèles de sites sur les exigences de rendu AEM Guides.


## Conditions préalables

- Vous disposez des autorisations appropriées et de l’accès aux modèles AEM.
- Vous comprenez les modèles modifiables AEM et la structure du site AEM.
- Une hiérarchie de site existante est créée à l’aide de modèles modifiables.
- Votre projet existant contient au moins deux modèles :

   - **Modèle de page de conteneur de documentation** utilisé pour effectuer le rendu du plan DITA en tant que racine de documentation.
   - **Modèle de page de rubrique** utilisé pour effectuer le rendu de pages de rubrique DITA individuelles.

## Considérations relatives aux noms de modèles

Les noms des modèles varient en fonction de la configuration du projet. Par exemple, dans la configuration des documents AEM prêts à l’emploi :

- Page Conteneur de documentation : `/conf/AEMG-Docs-Site/settings/wcm/templates/kb-content`

- Page de sujet : `/conf/AEMG-Docs-Site/settings/wcm/templates/topic-content`

**Personnalisation :** le processus de personnalisation comprend deux étapes principales :

1. Paramétrage des modèles : identifiez et paramétrez les deux modèles (conteneur et rubrique).
2. Composants des guides de rendu : incorporez les composants AEM Guides requis pour activer des fonctionnalités telles que la table des matières, la navigation et l’affichage des métadonnées.

## Configuration du modèle

Choisissez et configurez deux modèles modifiables à partir de votre site AEM.

### Modèle de page du conteneur de documentation

Le modèle de page Conteneur de documentation est utilisé pour créer la page Conteneur de documentation de produit , qui effectue le rendu du contenu d&#39;un plan DITA.

- Il sert de point d’entrée ou de page d’accueil pour un ensemble spécifique de documentation (par exemple, un manuel ou un guide du produit).
- Ajoutez la propriété id=« category-page » au jcr:content du nœud initial du modèle. Cela permet de s’assurer que toutes les pages créées à partir de ce modèle sont automatiquement traitées comme des conteneurs de documentation par AEM Guides.

  ![Ajout de id=« category-page »](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-id-category-page.png){width="650" align="left"}

- Ajoutez un composant Texte avec la propriété obligatoire : text=« $category.html$ ».

  ![Ajout d’un composant de texte](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-text-component.png){width="650" align="left"}

- Inclut généralement des éléments de navigation, tels que des liens vers des sections ou des rubriques de la documentation.
- Il peut être personnalisé pour inclure l’identité graphique, les en-têtes, les pieds de page et d’autres éléments de conception.

**Exemple de cas d’utilisation :**
Si vous disposez d&#39;un plan DITA pour un manuel de produit, le modèle de page conteneur de documentation génère la page d&#39;accueil de ce manuel, affichant un aperçu et des liens vers des rubriques individuelles.

### Modèle de page de rubrique

- Le **modèle de page de rubrique** permet de créer des pages pour des **rubriques DITA** individuelles.
- Chaque rubrique d&#39;un plan DITA est rendue en tant que page distincte à l&#39;aide de ce modèle.
- Contient un **composant de texte** avec la propriété obligatoire : text=« $topic.content$ ».

  ![Ajout d’un composant de texte avec la propriété mandatory](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-text-component-mandatory-property.png){width="650" align="left"}

- Cet espace réservé est remplacé par le contenu réel de la rubrique DITA lors de la génération du site.
   - Le composant de texte est généralement placé à l’intérieur d’un **composant de conteneur** pour garantir une mise en page et un style appropriés.
   - Peut être personnalisé pour inclure des en-têtes, des pieds de page et des éléments de navigation cohérents sur toutes les pages de rubrique.

**Exemple de cas d’utilisation :**
Si vous disposez d&#39;une rubrique DITA sur les « Instructions d&#39;installation », le modèle de page de rubrique génère une page affichant le contenu de cette rubrique.

**Composant de conteneur :**

![Ajouter un composant de conteneur](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-container-component.png){width="650" align="left"}

>[!NOTE]
>
> Assurez-vous que les composants qui utilisent sling:resourceType sous `wcm/foundation/components` sont migrés vers les `core/wcm/components` correspondants.

Ajoutez le même (composant de conteneur et de texte) dans la structure du même modèle :

![Ajout d’un composant de conteneur et de texte](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-container-and-text-component.png){width="650" align="left"}

## Composants des guides de rendu dans des modèles personnalisés

Pour activer les fonctionnalités des composants AEM Guides principaux tels que la table des matières, la redirection de page, la navigation et l’affichage des métadonnées, vous devez inclure des composants AEM Guides spécifiques dans vos modèles personnalisés. Ces composants doivent être explicitement ajoutés aux modèles modifiables correspondants (page Conteneur de documentation ou page de rubrique) pour garantir que la fonctionnalité prévue est disponible pendant la génération et l’exécution du site.

Consultez le tableau ci-dessous pour obtenir la liste des composants et leur utilisation :

| Fonctionnalité | Nom du composant | Description | Modèle recommandé |
|---|---|---|---|
| Table des matières | guidessidenavigation | Rend la table des matières complète à partir du plan DITA | Conteneur de documentation |
| Redirection de page | child-direct | Redirige vers la première page de rubrique de la carte | Conteneur de documentation |
| Mini table des matières | minitoc | Affiche la table des matières pour la rubrique actuelle | Page Rubrique |
| Date de la dernière mise à jour | pageproperty | Affiche la date de dernière modification | Page Rubrique |
| Récepteur d&#39;appel | récepteur de radiomessagerie | Permet la navigation entre les pages de sujets précédentes et suivantes | Page Rubrique |
| Navigation par langue | languagenavigation | Permet de basculer entre différentes versions linguistiques | Modèle : |


## Cas d’utilisation de composants

- **Composant de redirection (redirection enfant) :** ajoutez-le au modèle de page du conteneur de documentation afin que la page d&#39;accueil du produit générée à partir du plan DITA redirige automatiquement vers la première page de rubrique. Si votre page de conteneur de documentation est conçue pour agir en tant que page d’accueil autonome avec des composants et une disposition personnalisés, ce composant n’est pas nécessaire.

- **Table des matières (guidessidenavigation) :** ajoutez-la au modèle de page de rubrique pour effectuer le rendu d’une table des matières navigable avec le contenu de rubrique. La table des matières est dérivée du plan DITA et permet aux utilisateurs de naviguer entre les rubriques frères.


## Activation des bibliothèques clientes Guides

Par défaut, les bibliothèques clientes (clientlibs) fournies dans le package de composants AEM Guides ne sont pas appliquées aux modèles personnalisés. Pour les activer :

1. **Modifier le modèle :**

   1. Ouvrez la **page produit** en **mode Éditeur**.
   2. Sélectionnez **Modifier le modèle** (une URL telle que conf/settings/wcm/templates/structure.html s’ouvre alors).

      ![Modifier le modèle](/help/product-guide/knowledge-base/kb-articles/assets/publishing/edit-template.png){width="650" align="left"}

2. **Mettre à jour la politique de page :**

   1. Accédez au bouton **Informations sur la page** et sélectionnez **Politique de page**.
   2. Ajoutez les bibliothèques clientes suivantes :
      - **Bibliothèques clientes**
      - **En-tête de page JavaScript des bibliothèques clientes**

3. **Enregistrer les modifications :** enregistrez le modèle après l’ajout des bibliothèques clientes requises.

   ![Ajout de bibliothèques clientes](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-client-libraries.png){width="650" align="left"}


>[!NOTE]
>
> Assurez-vous que les modèles sont testés dans un environnement hors production avant le déploiement en production.<br><br>Pour plus d’informations[&#x200B; consultez la documentation officielle de &#x200B;](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/overview)AEM Guides et [AEM Sites](https://experienceleague.adobe.com/fr/docs/experience-manager-core-components/using/get-started/authoring).
