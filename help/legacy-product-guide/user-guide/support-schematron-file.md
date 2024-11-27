---
title: Prise en charge des fichiers de schéma
description: Découvrez comment importer et valider une rubrique DITA, utiliser l’insertion d’instructions de rapport pour rechercher des règles, utiliser des expressions regex et définir des modèles abstraits dans les fichiers de schéma d’AEM Guides.
feature: Authoring, Features of Web Editor
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 0%

---

# Prise en charge des fichiers de schéma

&quot;Schéma&quot; fait référence à un langage de validation basé sur des règles utilisé pour définir des tests pour un fichier XML. L’éditeur web prend en charge les fichiers de schéma. Vous pouvez importer les fichiers de schéma et les modifier dans l’éditeur web. À l’aide d’un fichier de schéma, vous pouvez définir certaines règles, puis les valider pour une rubrique DITA ou un mappage.

>[!NOTE]
>
> L’éditeur web prend en charge le schéma ISO.


## Importation des fichiers de schéma

Effectuez les étapes suivantes pour importer les fichiers de schéma :

![](images/scematron-panel-add.png){width="300" align="left"}

1. Accédez au dossier requis (où vous souhaitez charger les fichiers) dans *Repository View*.
1. Cliquez sur l’icône **Options** pour ouvrir le menu contextuel et sélectionnez **Télécharger Assets**.
1. Dans la boîte de dialogue **Télécharger Assets**, vous pouvez modifier le dossier de destination dans le champ **Sélectionner le dossier de ressources**.
1. Cliquez sur **Choose Files** (Choisir les fichiers) et accédez aux fichiers de schéma pour les sélectionner. Vous pouvez sélectionner un ou plusieurs fichiers de schéma, puis cliquer sur **Télécharger**.

## Validation d’une rubrique ou d’un mappage DITA avec Schematron

Après avoir importé des fichiers de schéma, vous pouvez les modifier dans l’éditeur web. Vous pouvez utiliser les fichiers de schéma pour valider les rubriques ou un mappage DITA. Par exemple, vous pouvez créer les règles suivantes pour un mappage ou une rubrique DITA :

* Un titre est défini pour un mappage DITA.
* Une brève description d’une certaine longueur a été ajoutée.
* Il doit y avoir au moins une référence de topicref dans la carte.

Lorsque vous ouvrez une rubrique dans l’éditeur web, un panneau Validation de schéma s’affiche à droite. Effectuez les étapes suivantes pour ajouter et valider une rubrique ou un mappage avec un fichier de schéma :
![](images/schematron-validate.png){width="300" align="left"}

1. Cliquez sur l’icône Schéma () pour ouvrir le panneau Schéma .
1. Utilisez Ajouter un fichier de schéma pour ajouter des fichiers de schéma.
1. Si le fichier de schéma ne comporte aucune erreur, il est ajouté et répertorié dans le panneau Validation. Un message d’erreur s’affiche pour le fichier de schéma contenant des erreurs.
   >[!NOTE]
   >
   >Vous pouvez utiliser l’icône croisée près du nom du fichier de schéma pour le supprimer.
1. Cliquez sur Valider avec le schéma pour valider la rubrique.

   * Si la rubrique ne enfreint aucune règle, le message de réussite de la validation s’affiche pour le fichier.
   * Si la rubrique rompt une règle, par exemple si elle ne contient pas de titre et est validée pour le schéma donné ci-dessus, elle affiche une erreur de validation.

1. Cliquez sur le message d’erreur pour mettre en surbrillance l’élément contenant l’erreur dans la rubrique/le mappage ouvert.

La prise en charge des schémas dans l’éditeur web vous aide à valider les fichiers par rapport à un ensemble de règles et à maintenir la cohérence et l’exactitude dans les rubriques.

## Utilisez des instructions d’insertion et de rapport pour rechercher des règles.{#schematron-assert-report}

AEM Guides prend également en charge les instructions d’insertion et de rapport dans le schéma. Ces instructions vous aident à valider vos rubriques DITA.

### Instruction d’affirmation

Une instruction sert génère un message lorsqu’une instruction test est évaluée comme false. Par exemple, si vous souhaitez que votre titre soit en gras, vous pouvez définir une instruction d’assertion pour celui-ci.

```XML
<sch:rule context="title"> 
    <sch:assert test = "b"> Title should be bold </sch:assert>
  </sch:rule>
```

Lorsque vous validez vos rubriques DITA avec le schéma, vous obtenez un message pour les rubriques dans lesquelles le titre n’est pas en gras.

### Instruction de rapport

Une instruction de rapport génère un message lorsqu’une instruction de test est évaluée comme vraie. Par exemple, si vous souhaitez que la brève description soit inférieure ou égale à 150 caractères, vous pouvez définir une instruction de rapport afin de vérifier les rubriques dont la brève description comporte plus de 150 caractères.
Lorsque vous validez vos rubriques DITA avec le schéma, vous obtenez un rapport complet des règles dans lesquelles l’instruction de rapport est vraie. Ainsi, vous obtenez un message pour les rubriques dont la brève description comporte plus de 150 caractères.


```XML
<sch:rule context="shortdesc"> 
        <sch:let name="characters" value="string-length(.)"/> 
        <sch:report test="$characters &gt; 150">  
        The short description has <sch:value-of select="$characters"/> characters. It should contain more than 150 characters.      
        </sch:report>   
    </sch:rule> 
```

>[!NOTE]
>
> Utilisez uniquement les expressions Xpath 2.0 lors de l’écriture des règles de schéma.

## Utilisation d’expressions Regex{#schematron-regex-espressions}

Vous pouvez également utiliser des expressions Regex pour définir une règle avec la fonction matches(), puis effectuer la validation à l’aide du fichier de schéma.

Par exemple, vous pouvez l’utiliser pour afficher un message si le titre contient un seul mot.

```XML
<assert test="not(matches(.,'^\w+$'))"> 
No one word titles.
</assert>  
```


## Définition de modèles abstraits{#schematron-abstract-patterns}

AEM Guides prend également en charge les modèles abstraits dans Schematron. Vous pouvez définir des modèles abstraits génériques qui réutilisent ces modèles abstraits.  Vous pouvez créer des paramètres d’espace réservé qui spécifient le modèle réel.


L’utilisation de modèles abstraits peut simplifier votre schéma de schéma en réduisant la duplication des règles et en facilitant la gestion et la mise à jour de votre logique de validation. Cela peut également faciliter la compréhension de votre schéma, car vous pouvez définir une logique de validation complexe dans un modèle abstrait unique qui peut être réutilisé dans l’ensemble du schéma.


Par exemple, le code XML suivant crée un modèle abstrait, auquel le modèle réel fait référence à l’aide de l’identifiant.

```XML
<sch:pattern abstract="true" id="LimitNoOfWords"> 

<sch:rule context="$parentElement"> 

<sch:let name="words" value="string-length(.)"/> 

<sch:assert test="$words &lt; $maxWords"> 

You have <sch:value-of select="$words"/> letters. This should be lesser than <sch:value-of select="$maxWords"/>. 

</sch:assert>  

<sch:assert test="$words &gt; $minWords"> 

You have <sch:value-of select="$words"/> letters. This should be greater than <sch:value-of select="$minWords"/>. 

</sch:assert>  

</sch:rule> 

</sch:pattern> 

<sch:pattern is-a="LimitNoOfWords" id="extend-LimitNoOfWords"> 

<sch:param name="parentElement" value="title"/> 

<param name="minWords" value="1"/> 

<param name="maxWords" value="8"/> 

</sch:pattern> 
```
