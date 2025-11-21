---
title: Ajouter un nouveau bouton exploitable personnalisé dans la barre d’outils de l’éditeur web
description: Découvrez comment ajouter un nouveau bouton personnalisé dans la barre d’outils de l’éditeur web et appeler javascript pour l’utiliser de manière personnalisée.
exl-id: 34999db6-027a-4d93-944f-b285b4a44288
feature: Web Editor
role: User, Admin
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '527'
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

[utilisez ce lien pour en savoir plus sur le profil de dossier et la configuration du fichier ui_config.json](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=fr)


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
