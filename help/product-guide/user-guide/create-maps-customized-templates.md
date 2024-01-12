---
title: Création de cartes à partir de modèles personnalisés
description: Découvrez comment créer un modèle personnalisé, les utiliser pour créer des fichiers de mappage et transmettre le titre défini à un mappage DITA dans AEM Guides.
exl-id: 9cb0035f-bf81-4ab5-a575-53851bbff494
feature: Authoring, Map Editor
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 0%

---

# Création de cartes à partir de modèles personnalisés {#id225VF0808MP}

Vous pouvez créer des modèles de mappage personnalisés et les utiliser pour créer des mappages DITA avec les modèles de rubrique et de mappage référencés dans le modèle de mappage.

Vous pouvez vous référer à d’autres modèles de mappage et de rubriques à partir du modèle de mappage personnalisé. Les modèles de mappage référencés peuvent faire référence à divers modèles de mappage, modèles de rubrique, rubriques, cartes, images, vidéos et autres ressources. Le modèle de carte personnalisé peut vous aider à répliquer très facilement les modèles de carte et la structure de dossiers référencée entière. Ces modèles personnalisés sont particulièrement utiles pour créer et recréer plusieurs cartes qui comportent des structures et des références récursives.

>[!NOTE]
>
> Les modèles de rubrique ne sont pas créés de manière récursive. Seuls les modèles de rubrique situés directement dans le modèle de mappage sont générés et tout modèle de rubrique à l’intérieur d’un modèle de rubrique est simplement référencé directement dans le parent.

## Créer des modèles personnalisés

AEM Guides vous permet de créer des cartes et des rubriques personnalisées à partir du dossier dita-templates . Vous pouvez utiliser ces modèles personnalisés pour créer votre carte et votre rubrique. Vous pouvez également partager ces modèles avec vos auteurs et ils peuvent les utiliser pour créer leurs fichiers. Grâce à ces modèles, vous pouvez permettre aux auteurs de conserver des copies distinctes de certaines ressources qui se trouvent dans le dossier des modèles.

>[!NOTE]
>
> Toutes les ressources qui doivent uniquement être référencées et gérées doivent être conservées en dehors du dossier des modèles.


Vous pouvez créer des modèles de mappage et de rubrique de la manière suivante :
1. Volet Modèles de [Panneau gauche](./web-editor-features.md#left-panel-id2051ea0m0hs)
1. [Modèles dans l’interface utilisateur d’Assets](#templates-assets-ui)
1. [Menu Options](#templates-in-assets-ui)

### Modèles dans l’interface utilisateur d’Assets {#templates-assets-ui}

**Modèle de rubrique**

Pour créer un modèle de rubrique, procédez comme suit :

1. Dans le **Interface utilisateur des ressources**, accédez au dossier dita-templates .

   ![](images/dita-templates.png){width="800" align="left"}

1. Cliquez sur **rubriques** pour l’ouvrir.Cliquez sur **Créer \> modèle DITA**.
1. Sur la page Plan directeur, sélectionnez **Rubrique** puis cliquez sur **Suivant.**
1. Sur la page Propriétés, spécifiez le modèle de rubrique. **Titre**.
1. Spécification du fichier **Nom**

   >[!NOTE]
   >
   > Le nom de fichier doit avoir l’extension .dita .

1. \(Facultatif\) Ajoutez une description.
1. Cliquez sur **Créer**. Le message du modèle de rubrique créé s’affiche. Vous pouvez ensuite ouvrir le modèle de rubrique et le modifier.

**Modèle de carte**

Effectuez les étapes suivantes pour créer un modèle de mappage :

1. Dans le **Interface utilisateur des ressources**, accédez au dossier dita-templates .
1. Cliquez sur **maps** pour l’ouvrir.
1. Cliquez sur **Créez \> Modèle DITA.**

   ![](images/create-dita-template.png){width="300" align="left"}

1. Sur la page Plan directeur, sélectionnez **Carte** et cliquez sur **Suivant**.
1. Sur la page Propriétés , spécifiez le modèle de mappage. **Titre**.
1. Spécification du fichier **Nom**.

   >[!NOTE]
   >
   > Le nom de fichier doit avoir l’extension .ditamap .

1. (Facultatif\) Ajoutez une description. Cliquez sur **Créer**. Le message relatif au modèle de carte créé s’affiche. Vous pouvez ensuite ouvrir le modèle de carte et le modifier. Vous pouvez ajouter les références des modèles de rubrique, des modèles de mappage et d’autres ressources dans le modèle de mappage.

### Menu Options {#options-menu}

Pour créer un mappage ou un modèle de rubrique, procédez comme suit :

1. Sélectionnez la variable **Carte** ou **Rubrique** dans le dossier des modèles actuels. Par exemple, le dossier `dita-templates`.
1. Dans la **Options** menu, sélectionnez **Créer un modèle de carte** ou **Créer un modèle de rubrique**.

   La variable **Créer un modèle de carte** ou le **Créer un modèle de rubrique** s’ouvre.
1. Saisissez le titre et le nom du nouveau modèle.
1. Choisissez le type de modèle que vous souhaitez créer à partir du **Modèle** liste déroulante.

Le message relatif au modèle de carte créé s’affiche. Vous pouvez ajouter le modèle à votre profil global ou au niveau du dossier. Le nouveau modèle apparaît ensuite dans la rubrique ou le processus de création de mappage, et vous pouvez créer des mappages ou des rubriques à l’aide de celui-ci.


Votre administrateur peut également créer un dossier et le configurer pour qu’il soit le dossier dans lequel vous pouvez créer et enregistrer les modèles.

Selon votre configuration, apprenez à configurer le chemin d’accès au dossier de modèle DITA personnalisé :
<details>
    <summary> Services cloud </summary>

Découvrez comment [configuration du chemin d’accès au dossier de modèle DITA personnalisé](../install-guide/conf-template-tags-custom-dita-topic-template.md#configure-custom-dita-template-folder-path-id191lcf0095z) dans le Guide d&#39;installation et de configuration de Cloud Service.
</details>

<details>
    <summary> Logiciel On-Premise</summary>

Découvrez comment [configuration du chemin d’accès au dossier de modèle DITA personnalisé](../cs-install-guide/conf-template-tags-custom-dita-topic-template.md#configure-custom-dita-template-folder-path-id191lcf0095z) dans le Guide d&#39;installation et de configuration On-premise.
</details>

## Transmettre le titre défini dans les modèles

Si vous souhaitez transmettre le titre de la rubrique ou du mappage utilisé dans votre modèle aux mappages DITA créés à l’aide de ce modèle, utilisez des accolades autour du titre.

Exemple

```XML
<pubtitle>
   <mainpubtitle outputclass="booktitle">
   {title}
   </mainpubtitle>
   <subtitle>Subtitle</subtitle>
</pubtitle>

The resultant DITA map with title "Rootmap1" will look like as follows:
<pubtitle>
   <mainpubtitle outputclass="booktitle">Rootmap1
   </mainpubtitle>
   <subtitle>Subtitle</subtitle>
</pubtitle>
```

>[!NOTE]
> Seule la première occurrence de l’accolade sera remplacée par le titre.

Si vous n’utilisez pas de accolades autour du titre, seul le premier élément est sélectionné dans le mappage DITA qui en résulte, et l’imbrication du titre ne sera pas sélectionnée dans le modèle et se présentera comme suit :

```XML
<pubtitle> Rootmap1 </pubtitle>
```

>[!NOTE]
> Vous pouvez également utiliser les accolades autour du texte pour transmettre sa structure imbriquée des modèles personnalisés à vos mappages DITA.

Exemple

```XML
<title>    
    <sub>        
        <b>{title}</b>    
    </sub>
</title>
```




## Utiliser le modèle de carte pour créer de nouvelles cartes

>[!NOTE]
>
> Le modèle de carte doit être configuré et rendu disponible pour la création par votre administrateur. Pour plus d’informations, voir *Configuration de modèles de création* dans la section Installation et configuration de Adobe Experience Manager Guides as a Cloud Service.

Pour créer une carte à l’aide du modèle de carte personnalisé, procédez comme suit :

1. Dans le **Interface utilisateur d’Assets,** accédez au dossier dans lequel vous souhaitez créer la carte.
1. Cliquez sur **Créer \> Carte DITA**.
1. Sur la page Plan directeur, sélectionnez le modèle de carte à utiliser, puis cliquez sur **Suivant**. Par exemple, si vous avez créé un modèle de mappage &quot;test-template&quot;, sélectionnez-le.
1. Sur la page Propriétés, spécifiez la carte. **Titre**.
1. Spécification du fichier **Nom**.

   >[!NOTE]
   >
   > Le nom de fichier doit avoir l’extension .ditamap .

1. Cliquez sur **Créer**. Le message de mappage créé s’affiche.


La carte génère toutes les ressources auxquelles il est fait référence dans le dossier de modèles. Certains types de ressources qui sont référencés dans une carte peuvent être les suivants :

- Si le mappage contient la référence à un modèle de rubrique, une copie de celui-ci est créée dans le dossier, dans la même hiérarchie que dans le dossier de rubriques du `dita-templates` dossier.
- Si le mappage contient la référence à un modèle de mappage, une copie de celui-ci est créée dans le dossier, dans la même hiérarchie que dans le dossier des mappages dans la variable `dita-templates` dossier.
- Si la carte contient la référence générique à une rubrique ou à un mappage en dehors de la variable `dita-templates/topics` ou `dita-templates/maps` , il en est de même uniquement pour les références et aucune copie n’est créée.

  >[!NOTE]
  >
  > `dita-templates/topics` et `dita-templates/maps` sont les chemins par défaut dans les guides et peuvent être configurés.


  S’il existe une définition de clé de modèle de rubrique dans le modèle de mappage, une nouvelle clé \(par conséquent, nouvelle rubrique\) est créée et référencée dans le mappage.

- Si un autre mappage ou une autre rubrique est créé au même niveau dans le dossier, les noms des ressources nouvellement créées sont ajoutés avec 0,1,2, etc. Vous pouvez choisir d’ouvrir le mappage pour modifier ou enregistrer le fichier de mappage dans le référentiel.

**Rubrique parente :**[ Utilisation de l’éditeur de cartes](map-editor.md)
