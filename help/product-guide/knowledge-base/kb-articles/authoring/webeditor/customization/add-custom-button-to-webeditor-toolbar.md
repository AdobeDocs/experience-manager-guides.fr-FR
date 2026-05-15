---
title: Ajouter un nouveau bouton exploitable personnalisé dans la barre d’outils de l’éditeur web
description: Découvrez comment ajouter un nouveau bouton personnalisé dans la barre d’outils de l’éditeur web et appeler javascript pour l’utiliser de manière personnalisée.
exl-id: 34999db6-027a-4d93-944f-b285b4a44288
feature: Web Editor
role: User, Admin
TQID: https://experienceleague.adobe.com/7NqswCerJdfej5j4XqnPhHzvvAkhlThHAUY3iQYL3t0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 553
ht-degree: 0%

---

# Ajouter un nouveau bouton exploitable personnalisé dans la barre d’outils de l’éditeur web

Dans cet article, nous allons découvrir comment ajouter un nouveau bouton personnalisé dans la barre d’outils de l’éditeur web et appeler javascript pour effectuer l’opération personnalisée souhaitée.

L’ajout d’un bouton exploitable à l’éditeur web implique les étapes suivantes :
- Ajout du bouton dans le fichier *ui_config.json* à l’emplacement où il est nécessaire
- Enregistrement de l’événement bouton-clic dans l’éditeur web pour que l’utilisateur ou l’utilisatrice effectue une action lorsqu’il ou elle clique dessus


## Implémentation en prenant un exemple

Comprenons ceci avec un exemple où un auteur souhaite ajouter une référence Jira à une section de prologue de rubrique. La section de prologue avec l’ID de référence jira incorporé peut se présenter comme suit :

![Section Prolog avec référence d’identifiant JIRA](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-sample.png)

L’élément « change-request-id » contenant l’ID JIRA doit être récupéré dans l’API (par exemple en fonction d’une requête JIRA spécifique représentée par l’application). Lorsque l’utilisateur crée la section de prologue, il doit pouvoir cliquer sur un bouton et insérer un identifiant de référence jira dans la barre d’outils de l’éditeur web, par exemple :

![Section Prolog - Ajouter une référence JIRA](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-insertjirareference.png)

Et lorsque l’utilisateur clique sur le bouton, une boîte de dialogue doit s’afficher. Elle doit extraire les options possibles et permettre à l’utilisateur de sélectionner l’identifiant JIRA souhaité, par exemple :

![Boîte de dialogue Ajouter un ID JIRA à la section Prologue](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-insertjirareference-dialog.png)

qui doit ensuite ajouter le « change-request-id » au prologue :

![Section Prolog avec référence d’identifiant JIRA](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-sample.png)



## Mise en œuvre de ceci


### Ajoutez le bouton dans l’éditeur web en le configurant dans *ui_config.json*

Utilisez les profils de dossier pour vérifier le fichier *ui_config.json* sous l’onglet « Configuration de l’éditeur XML » et ajoutez le fichier JSON de configuration des boutons dans la section souhaitée du groupe « toolbar »

```
{
    "on-click":"insertJIRARef",
    "icon":"linkCheck",
    "variant":"quiet",
    "type":"button",
    "title":"Insert JIRA Reference"
}
```

[Utilisez ce lien pour en savoir plus sur le profil de dossier et la configuration du fichier ui_config.json](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=en)


### Gérer l’événement on-click pour le nouveau bouton

REMARQUE : les étapes mentionnées ci-dessous sont disponibles en tant que package joint à cette publication


- Après avoir enregistré le profil du dossier, créez un « cq :ClientLibraryFolder » sous un répertoire de projet (qui peut se trouver sous */apps*) et ajoutez des propriétés comme illustré dans la capture d’écran ci-dessous :
  ![Paramètres de bibliothèque cliente pour l’éditeur web](../../../assets/authoring/webeditor-add-customtoolbarbutton-clientlibrarysettings.png)

```
This example uses "coralui3" library to show a dialog as it is used in the Javascript sample we presented.
You may use different library of your choice.
```

- Sous ce dossier de bibliothèque cliente, créez deux fichiers comme indiqué ci-dessous :
   - *overrides.js* : qui disposera du code javascript pour gérer l’événement on-click pour « insertJIRARef » (utilisez le package joint pour obtenir le contenu de ce javascript)
   - *js.txt* : qui contiendra le fichier « overrides.js » pour activer ce javascript

- Enregistrez les modifications et vous devriez être prêt à les tester.


### Tests

- Ouvrir l’éditeur web
- Dans les préférences utilisateur , choisissez le profil de dossier dans lequel vous avez ajouté le fichier personnalisé *ui_config.json*. Si vous l’avez ajouté au profil global, vous l’utilisez probablement déjà.
- Ouvrez une rubrique, vous remarquerez que la barre d’outils comporte un nouveau bouton « Insérer une référence Jira »
- Vous pouvez ensuite ajouter la section de prologue comme indiqué ci-dessous à la rubrique et essayer de cliquer sur le bouton « Insérer une référence Jira » à l’intérieur de l’élément de prologue « change-request-reference »

```
<prolog>
    <change-historylist>
        <change-item>
            <change-request-reference>
            </change-request-reference>
            <change-completed></change-completed>
            <change-summary></change-summary>
        </change-item>
    </change-historylist>
</prolog>
```

Consultez la capture d’écran ci-dessous pour savoir à quoi elle ressemblera :

![Tester le nouveau bouton](../../../assets/authoring/webeditor-add-customtoolbarbutton-testing.png)


### Pièces jointes

- Exemple de package clientlibs qui installera la bibliothèque cliente webeditor avec le code javascript pour l’action du bouton de la barre d’outils : [télécharger à l’aide de ce lien](../../../assets/authoring/webeditor-addbuttonontoolbar-insertjira-clientlib.zip)
- Exemple *ui_config.json* que vous pouvez charger vers un profil de dossier : [télécharger l’exemple ui_config.json](../../../assets/authoring/sample_ui_config_Guides4.2-InsertJiraReference.json)

```
Please note this is compatible to AEM 6.5 and AEM Guides version 4.2.
If you are using a different version please add the toolbar button to the ui_config.json manually.
```
