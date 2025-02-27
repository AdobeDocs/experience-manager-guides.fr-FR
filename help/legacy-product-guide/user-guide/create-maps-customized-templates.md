---
title: Création de mappages à partir de modèles personnalisés
description: Découvrez comment créer un modèle personnalisé, les utiliser pour créer des fichiers de mappage et transmettre le titre défini à un mappage DITA dans AEM Guides.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: 0f86ac98-7ba4-4e15-8a1f-83456afa7570
source-git-commit: 4801f0d327b4bd0641aa195d39ec2c4be2a2ce74
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 0%

---

# Création de mappages à partir de modèles personnalisés {#id225VF0808MP}

Vous pouvez créer des modèles de carte personnalisés et les utiliser pour créer des cartes DITA avec les modèles de rubrique et les modèles de carte référencés dans le modèle de carte

Vous pouvez vous reporter à d’autres modèles de carte et modèles de rubrique à partir du modèle de carte personnalisé. Les modèles de mappage référencés peuvent faire référence à divers modèles de mappage, modèles de rubrique, rubriques, mappages, images, vidéos et autres ressources. Le modèle de mappage personnalisé peut vous aider à répliquer très facilement les modèles de mappage et l’ensemble de la structure de dossiers à laquelle il est fait référence. Ces modèles personnalisés sont particulièrement utiles pour créer et recréer plusieurs mappings dotés de structures et de références récursives.

>[!NOTE]
>
> Les modèles de rubrique ne sont pas créés de manière récursive. Seuls les modèles de rubrique directement à l&#39;intérieur du modèle de carte sont générés et tout modèle de rubrique à l&#39;intérieur d&#39;un modèle de rubrique est simplement référencé directement dans le parent.

## Création de modèles personnalisés

AEM Guides vous permet de créer des cartes et des rubriques personnalisées à partir du dossier dita-templates . Vous pouvez utiliser ces modèles personnalisés pour créer votre carte et votre rubrique. Vous pouvez également partager ces modèles avec vos auteurs et les utiliser pour créer leurs fichiers. Grâce à ces modèles, vous pouvez permettre aux auteurs de conserver des copies distinctes de certaines ressources qui se trouvent dans le dossier des modèles.

>[!NOTE]
>
> Toutes les ressources qui ne doivent être référencées et conservées que sur doivent être conservées en dehors du dossier des modèles.


Vous pouvez créer des modèles de carte et de rubrique des manières suivantes :
1. Volet Modèles du [panneau de gauche](./web-editor-features.md#left-panel-id2051ea0m0hs)
1. [Modèles de l’interface utilisateur d’Assets](#templates-assets-ui)
1. [Menu Options](#templates-in-assets-ui)

### Modèles de l’interface utilisateur d’Assets {#templates-assets-ui}

**Modèle de rubrique**

Pour créer un modèle de rubrique, procédez comme suit :

1. Dans l’**interface utilisateur d’Assets**, accédez au dossier dita-templates .

   ![](images/dita-templates.png){width="800" align="left"}

1. Cliquez sur le dossier **topics** pour l&#39;ouvrir.Cliquez sur **Create \> DITA Template**.
1. Sur la page Plan directeur, sélectionnez **Rubrique** puis cliquez sur **Suivant.**
1. Sur la page Propriétés , spécifiez le modèle de rubrique **Titre**.
1. Spécifiez le fichier **Nom**

   >[!NOTE]
   >
   > Le nom de fichier doit avoir l’extension .dita.

1. \(Facultatif\) Ajoutez une description.
1. Cliquez sur **Créer**. Le message de création du modèle de rubrique s’affiche. Vous pouvez ensuite ouvrir le modèle de rubrique et le modifier.

**Modèle de carte**

Pour créer un modèle de mappage, procédez comme suit :

1. Dans l’**interface utilisateur d’Assets**, accédez au dossier dita-templates .
1. Cliquez sur le dossier **mappages** pour l’ouvrir.
1. Cliquez sur **Créer \> Modèle DITA.**

   ![](images/create-dita-template.png){width="300" align="left"}

1. Sur la page Plan directeur, sélectionnez **Map** et cliquez sur **Suivant**.
1. Sur la page Propriétés , spécifiez le modèle de mappage **Titre**.
1. Spécifiez le fichier **Nom**.

   >[!NOTE]
   >
   > Le nom du fichier doit avoir l’extension .ditamap.

1. (Facultatif\) Ajoutez une description. Cliquez sur **Créer**. Le message de création du modèle de mappage s’affiche. Vous pouvez ensuite ouvrir le modèle de carte et le modifier. Vous pouvez ajouter les références des modèles de rubrique et de mappage, ainsi que d’autres ressources dans le modèle de mappage.

### Menu Options {#options-menu}

Pour créer un mappage ou un modèle de rubrique, procédez comme suit :

1. Sélectionnez le dossier **Map** ou **Topic** dans le dossier des modèles actifs. Par exemple, le dossier `dita-templates`.
1. Dans le menu **Options**, sélectionnez **Créer un modèle de carte** ou **Créer un modèle de rubrique**.

   La boîte de dialogue **Créer un modèle de carte** ou **Créer un modèle de rubrique** s’ouvre.
1. Saisissez le titre et le nom du nouveau modèle.
1. Sélectionnez le type de modèle à créer dans la liste déroulante **Modèle**.

Le message de création du modèle de mappage s’affiche. Vous pouvez ajouter le modèle à votre profil global ou au niveau du dossier. Le nouveau modèle apparaît ensuite dans le processus de création de rubrique ou de carte, et vous pouvez créer des cartes ou des rubriques à l’aide de celui-ci.


Votre administrateur peut également créer un dossier et le configurer pour qu’il soit le dossier dans lequel vous pouvez créer et enregistrer les modèles.

En fonction de votre configuration, apprenez à configurer le chemin d&#39;accès au dossier du modèle DITA personnalisé :
<details>
    <summary> Services cloud </summary>

Découvrez comment [configurer le chemin d’accès au dossier du modèle DITA personnalisé](/help/product-guide/install-guide/conf-template-tags-custom-dita-topic-template.md#configure-custom-dita-template-folder-path-id191lcf0095z) dans le Guide d’installation et de configuration des services cloud.
</details>

<details>
    <summary> Logiciel On-Premise</summary>

Découvrez comment [configurer le chemin d&#39;accès au dossier du modèle DITA personnalisé](/help/product-guide/cs-install-guide/conf-template-tags-custom-dita-topic-template.md#configure-custom-dita-template-folder-path-id191lcf0095z) dans le Guide d&#39;installation et de configuration On-premise.
</details>

## Transmission du titre défini dans les modèles

Si vous souhaitez transmettre le titre du sujet ou du plan utilisé dans votre modèle aux plans DITA créés à l&#39;aide de ce modèle, utilisez des crochets autour du titre.

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

Si vous n&#39;utilisez pas d&#39;accolades autour du titre, seul le premier élément sera sélectionné dans le plan DITA résultant et l&#39;imbrication du titre ne sera pas sélectionnée dans le modèle. Il se présentera comme suit :

```XML
<pubtitle> Rootmap1 </pubtitle>
```

>[!NOTE]
> Vous pouvez également utiliser les accolades autour du texte pour transmettre sa structure imbriquée des modèles personnalisés à vos plans DITA.

Exemple

```XML
<title>    
    <sub>        
        <b>{title}</b>    
    </sub>
</title>
```




## Utiliser le modèle de mappage pour créer de nouveaux mappages

>[!NOTE]
>
> Le modèle de mappage doit être configuré et mis à disposition pour la création par votre administrateur. Pour plus d’informations, consultez la section *Configurer les modèles de création* dans la section Installation et configuration d’Adobe Experience Manager Guides as a Cloud Service.

Pour créer une carte à l’aide du modèle de carte personnalisé, procédez comme suit :

1. Dans l’interface utilisateur d’**Assets** accédez au dossier dans lequel vous souhaitez créer le mappage.
1. Cliquez sur **Créer \> DITA Map**.
1. Sur la page Plan directeur, sélectionnez le modèle de carte à utiliser, puis cliquez sur **Suivant**. Par exemple, si vous avez créé un modèle de mappage « test-template », sélectionnez-le.
1. Sur la page Propriétés , spécifiez le mappage **Titre**.
1. Spécifiez le fichier **Nom**.

   >[!NOTE]
   >
   > Le nom du fichier doit avoir l’extension .ditamap.

1. Cliquez sur **Créer**. Le message Mappage créé s’affiche.


La carte génère toutes les ressources qui sont référencées à l’intérieur du dossier de modèles. Certains types de ressources référencés dans un mappage peuvent être les suivants :

- Si la carte contient la référence à un modèle de rubrique, une copie de celui-ci est créée dans le dossier , dans la même hiérarchie que dans le dossier des rubriques dans le dossier des `dita-templates`.
- Si le mappage contient la référence à un modèle de mappage, une copie de celui-ci est créée dans le dossier , dans la même hiérarchie que dans le dossier des mappages dans le dossier `dita-templates` .
- Si la carte contient la référence générique à une rubrique ou à une carte en dehors du dossier `dita-templates/topics` ou `dita-templates/maps`, la même référence est uniquement faite et aucune copie n&#39;est créée.

  >[!NOTE]
  >
  > `dita-templates/topics` et `dita-templates/maps` sont les chemins d’accès par défaut dans les guides et peuvent être configurés.


  S’il existe une définition de clé de modèle de rubrique dans le modèle de carte, une nouvelle clé \(par conséquent, nouvelle rubrique\) est créée et référencée dans la carte.

- Si un autre mappage ou une autre rubrique est créé au même niveau dans le dossier, les noms des ressources nouvellement créées sont ajoutés avec 0,1,2, etc. Vous pouvez choisir d’ouvrir le mappage pour le modifier ou d’enregistrer le fichier de mappage dans le référentiel.

**Rubrique parente :**[ Utilisation de l’éditeur de cartes](map-editor.md)
