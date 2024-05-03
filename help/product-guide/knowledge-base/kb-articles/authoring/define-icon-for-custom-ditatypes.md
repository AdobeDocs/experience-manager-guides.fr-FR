---
title: Icône de configuration pour les types DITA personnalisés
description: Découvrez comment définir des icônes pour les types de dictionnaire personnalisés afin d’afficher leur icône sur différentes interfaces utilisateur dans AEM
source-git-commit: ce2f5e4ab6b05fbce7b8384ff59091ebf9bab7be
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 0%

---

# Icône de configuration pour les types de dictionnaire de données personnalisés (rubrique ou mappage)


## Énoncé du problème

Avec le schéma personnalisé utilisé dans AEM Guides, vous pouvez créer des types de rubrique ou de mappage personnalisés. Vous remarquerez peut-être que les rubriques/mappages personnalisés n’affichent pas d’icône dans l’éditeur web ou l’interface utilisateur d’Assets. Voir la capture d’écran à titre de référence  (../assets/authoring/custom-ditatype-icon-notshown.png)

Pour affecter une icône aux types de rubrique/mappage personnalisés, procédez comme suit :
- Rechercher le type de rubrique/mappage personnalisé
- Écrire des styles pour ajouter l’icône de votre choix pour le type personnalisé


Nous pouvons mettre en oeuvre les étapes ci-dessus pour afficher l’icône dans l’éditeur web (affichage du référentiel) ainsi que dans l’interface utilisateur d’Assets. Vous trouverez ci-dessous les étapes pour les deux


## Affichage de l’icône pour une rubrique/un mappage personnalisé dans la vue de l’éditeur web

Étape 1 : Déterminer le type de dictionnaire de données pour la rubrique/l’application personnalisée - Ouvrez l’affichage du référentiel dans l’éditeur web > ouvrez la console de développement sur le navigateur - Inspect l’espace d’icône en regard de la rubrique/du mappage répertorié - Vérifiez la classe affectée à la rubrique personnalisée - Voir la capture d’écran  (../assets/authoring/custom-ditatype-icon-knowditatype.png) pour plus d’informations : nous utiliserons cette classe pour affecter des icônes et écrire des css pour cette classe.

Étape 2 : Création d’un css et affectation d’une icône à ce type de dita - Création d’une bibliothèque cliente sous /apps, permet de créer un dossier &quot;assets&quot; sous le chemin d’accès souhaité - ajout de catégories &quot;apps.fmdita.xml_editor.page&quot; - création d’un dossier &quot;assets&quot; sous ce répertoire et ajout de toutes les icônes que vous souhaitez utiliser pour les types de dita personnalisés - ajout d’un fichier CSS sous dossier client - ajout d’un dossier sous le dossier de bibliothèque cliente dossier, par exemple &quot;tree&quot; icons.css&quot; - Ajoutez le code suivant

```
            .tree-item-icon {
                &.custommaptype {
                    background-image: url('assets/custommap.svg')
                }
                &.customtopictype {
                    background-image: url('assets/customtopic.svg')
                }
            }
```

    - ajoutez css.txt sous le dossier de bibliothèque cliente et ajoutez une référence à &quot;tree-icon.css&quot; qui vient d’être créé.
    - enregistrer/déployer ces modifications
Reportez-vous à la capture d’écran  (../assets/authoring/custom-ditatype-icon-define-webeditor-styles.png) pour plus de détails.

Et le résultat final est affiché dans la capture d’écran.  (../assets/authoring/custom-ditatype-icon-webeditor-showstyles.png)


## Affichage de l’icône pour une rubrique/un mappage personnalisé dans l’interface utilisateur d’Assets

Étape 1 : détermination du type DITA de la rubrique/carte DITA personnalisée - ceci est expliqué dans l’étape 1 des méthodes précédentes

Étape 2 : Création de JavaScript pour définir les icônes à charger pour le type de dictionnaire de données personnalisé pour les types de rubrique/correspondance personnalisés - Création d’une bibliothèque cliente sous /apps, par exemple vous créez un cq:ClientLibraryFolder sous le chemin souhaité - lui ajoutez les propriétés suivantes : - valeur &quot;categories&quot;(chaîne à plusieurs valeurs) sous la forme &quot;dam.gui.admin.coral&quot; - valeur &quot;dependencies&quot; (chaîne à plusieurs valeurs) comme &quot;libfs.libs.libs.libs mdita.version.control&quot; - Créez une copie du fichier &quot;/libs/fmdita/clientlibs/clientlibs/xmleditor/clientlib-dam/topic_type.js&quot; dans ce répertoire /apps - modifiez le &quot;topic_type.js&quot; copié et modifiez/ajoutez customtopictype sous la variable &quot;typeImageNameMap&quot; - Vous pouvez également modifier le chemin du dossier images en modifiant la valeur de la variable &quot;parentImagePath&quot; en l’emplacement de stockage des icônes personnalisées - Créez un fichier nommé js.txt sous la bibliothèque cliente et ajouter une référence à &quot;topic_type.js&quot; - enregistrer/déployer ces modifications - Copie d’écran de référence  (../assets/authoring/custom-ditatype-icon-define-assetsui-styles.png) pour plus de détails.

Et la sortie finale apparaîtra comme illustré dans la capture d’écran  (../assets/authoring/custom-ditatype-icon-assetsui-showstyles.png)