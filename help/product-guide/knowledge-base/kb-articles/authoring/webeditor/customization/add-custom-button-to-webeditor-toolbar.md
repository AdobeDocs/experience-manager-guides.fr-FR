---
title: Ajout d’un bouton interactif personnalisé dans la barre d’outils de l’éditeur de webeans
description: Découvrez comment ajouter un nouveau bouton personnalisé dans la barre d’outils de l’éditeur de weets et appeler javascript pour l’utiliser de manière personnalisée.
exl-id: 34999db6-027a-4d93-944f-b285b4a44288
feature: Web Editor
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---

# Ajout d’un bouton interactif personnalisé dans la barre d’outils de l’éditeur de webeans

Dans cet article, nous allons apprendre comment ajouter un nouveau bouton personnalisé dans la barre d’outils de l’éditeur de weeter et appeler javascript pour effectuer l’opération personnalisée souhaitée.

L’ajout d’un bouton exploitable à l’éditeur Web implique les étapes suivantes :
- Ajout du bouton dans le *ui_config.json* à l’emplacement où il est nécessaire
- Enregistrement de l’événement &quot;onclick&quot; de bouton dans l’éditeur web pour que l’utilisateur effectue une action lorsqu’il clique dessus.


## Mise en oeuvre en prenant un exemple

Comprenons cela avec un exemple où un auteur souhaite ajouter une référence jira à une section de prolog de rubrique. La section prolog avec l’ID de référence jira incorporé peut se présenter comme suit :

![Section Prolog avec référence d’ID JIRA](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-sample.png)

L’élément &quot;change-request-id&quot; qui contient l’identifiant JIRA doit être récupéré à partir de l’API (par exemple, en fonction d’une requête JIRA spécifique qui est représentée par l’application). Lorsque l’utilisateur crée la section prolog, il doit pouvoir cliquer sur un bouton et insérer un identifiant de référence jira dans la barre d’outils de l’éditeur web, par exemple :

![Section Prolog - Ajouter une référence JIRA](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-insertjirareference.png)

Lorsque l’utilisateur clique sur le bouton, une boîte de dialogue s’affiche. Celle-ci doit extraire les options possibles et permettre à l’utilisateur de sélectionner l’identifiant JIRA souhaité, par exemple :

![Ajout de la section Prolog à la boîte de dialogue JIRA ID](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-insertjirareference-dialog.png)

qui doit ensuite ajouter &quot;change-request-id&quot; au prolog :

![Section Prolog avec référence d’ID JIRA](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-sample.png)



## Implémenter


### Ajoutez le bouton dans l’éditeur Web en le configurant dans *ui_config.json*

Utilisez les profils de dossier pour vérifier le fichier *ui_config.json* sous l’onglet &quot;Configuration de l’éditeur XML&quot; et ajoutez la configuration de bouton JSON dans la section souhaitée du groupe &quot;barre d’outils&quot;.

```
{
    "on-click":"insertJIRARef",
    "icon":"linkCheck",
    "variant":"quiet",
    "type":"button",
    "title":"Insert JIRA Reference"
}
```

[ utilisez ce lien pour en savoir plus sur le profil de dossier et la configuration ui_config.json](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=fr)


### Gérer l’événement &quot;onclick&quot; pour le nouveau bouton

    REMARQUE : les étapes mentionnées ci-dessous sont disponibles sous forme de package joint à cette publication


- Après avoir enregistré le profil de dossier, créez un &quot;cq:ClientLibraryFolder&quot; sous un répertoire de projet (qui peut se trouver sous */apps*) et ajoutez des propriétés comme illustré dans la capture d’écran ci-dessous :
  ![ Paramètres de bibliothèque cliente pour webeditor](../../../assets/authoring/webeditor-add-customtoolbarbutton-clientlibrarysettings.png)

```
This example uses "coralui3" library to show a dialog as it is used in the Javascript sample we presented.
You may use different library of your choice.
```

- Sous ce dossier de bibliothèque cliente, créez deux fichiers comme indiqué ci-dessous :
   - *overrides.js* : qui disposera du code JavaScript pour gérer l’événement &quot;insertJIRARef&quot; en cas de clic (utilisez le package joint pour obtenir le contenu de ce JavaScript)
   - *js.txt* : qui inclura &quot;overrides.js&quot; pour activer ce javascript

- Enregistrez les modifications et vous devriez être prêt à les tester.


### Tests

- Ouvrir l’éditeur web
- Dans les préférences de l’utilisateur, choisissez le profil de dossier dans lequel vous avez ajouté le *ui_config.json* personnalisé. Si vous l’avez ajouté au profil Global, vous l’utilisez probablement déjà.
- Ouvrez une rubrique, vous remarquerez que la barre d’outils comporte un nouveau bouton &quot;Insérer une référence Jira&quot;.
- Vous pouvez ensuite ajouter la section prolog comme indiqué ci-dessous à la rubrique et essayer de cliquer sur le bouton &quot;Insérer une référence Jira&quot; à l’intérieur de l’élément prolog &quot;change-request-reference&quot;.

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

Reportez-vous à la capture d’écran ci-dessous pour savoir à quoi elle ressemblera :

![Tester le nouveau bouton](../../../assets/authoring/webeditor-add-customtoolbarbutton-testing.png)


### Pièces jointes

- Exemple de package clientlibs qui installera la bibliothèque cliente webeditor avec du code JavaScript pour l’action de bouton de barre d’outils : [télécharger à l’aide de ce lien](../../../assets/authoring/webeditor-addbuttonontoolbar-insertjira-clientlib.zip)
- Exemple *ui_config.json* que vous pouvez télécharger dans un profil de dossier : [téléchargez exemple ui_config.json](../../../assets/authoring/sample_ui_config_Guides4.2-InsertJiraReference.json)

```
Please note this is compatible to AEM 6.5 and AEM Guides version 4.2.
If you are using a different version please add the toolbar button to the ui_config.json manually.
```
