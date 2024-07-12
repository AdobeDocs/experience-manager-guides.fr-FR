---
title: Notes de mise à jour pour la version de février 2022 de  [!DNL AEM Guides]
description: Version de février de [!DNL Adobe Experience Manager Guides] as a Cloud Service
exl-id: eb7ff475-bb5b-4d32-b291-024147fbfed1
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 0%

---

# Version de février de [!DNL Adobe Experience Manager Guides] as a Cloud Service

## Mise à niveau vers la version de février

Mettez à niveau votre configuration actuelle [!DNL Adobe Experience Manager Guides] as a Cloud Service (plus tard appelée [!DNL AEM Guides] as a Cloud Service) en procédant comme suit :
1. Extrayez le code Git des Cloud Service et passez à la branche configurée dans le pipeline Cloud Service correspondant à l’environnement que vous souhaitez mettre à niveau.
1. Mettez à jour la propriété `<dox.version>` du fichier `/dox/dox.installer/pom.xml` de votre code Git Cloud Service vers la version 2022.2.114.
1. Validez les modifications et exécutez le pipeline Cloud Service pour effectuer la mise à niveau vers la version de février de l’as a Cloud Service [!DNL AEM Guides].

## Matrice de compatibilité

Cette section répertorie la matrice de compatibilité des applications logicielles prises en charge par la version as a Cloud Service de février 2022 de [!DNL AEM Guides].

### FrameMaker et FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Non compatible | Mise à jour 4 et ultérieure 2020 |
| | |


### Connecteur Oxygen

| [!DNL AEM Guides] Version cloud | Fenêtres du connecteur Oxygen | Mac du connecteur Oxygen |
| --- | --- | --- |
| 2022.2.0 | 2.4.0 | 2.4.0 |
|  |  |  |


## Nouvelles fonctionnalités et améliorations

### Publication PDF native

La prise en charge de la création d’un PDF natif a également été ajoutée dans la version de février de l’as a Cloud Service [!DNL AEM Guides]. Un nouveau moteur de publication a été introduit avec les fonctionnalités suivantes :
* Création d’un modèle CSS
* Créer différents modèles de page
* Modèles de PDF de conception comprenant des modèles CSS et de page
* Mappage Publish et contenu de rubrique au format PDF

### Prise en charge du chemin du site de la base de connaissances dans la publication basée sur les articles

[!DNL AEM Guides] as a Cloud Service fournit la fonction de publication basée sur des articles pour générer de manière incrémentielle une sortie d’une ou de plusieurs rubriques ou publier votre contenu sur une plateforme de la base de connaissances. Avec la version de février, vous disposez d’une option supplémentaire pour choisir le chemin du site de la base de connaissances vers lequel la rubrique/le mappage doit être publiée. Une fois le chemin sélectionné, la sortie est générée à l’emplacement spécifié.

### Améliorations apportées à l’éditeur web

De nombreuses améliorations et nouvelles fonctionnalités ont été ajoutées à l’éditeur web :

* **Boîte de dialogue améliorée lors de la fermeture du fichier**

[!DNL AEM Guides] L’as a Cloud Service vous invite à enregistrer vos modifications et à déverrouiller vos fichiers verrouillés lorsque vous essayez de fermer un fichier ouvert dans l’éditeur web. Les invites sont affichées en fonction des paramètres **Demander l’archivage à la fermeture** et **Demander une nouvelle version à la fermeture** configurés par votre administrateur.

En fonction de la configuration, vous avez la possibilité d’enregistrer les modifications et de créer une nouvelle version de votre document. Vous pouvez également archiver le fichier et enregistrer les modifications apportées à la version actuelle.

![Fermeture du fichier](assets/file-close-save-changes-unlock.png)

Pour plus d’informations, voir *Scénarios de fermeture et d’enregistrement de fichier* dans le Guide de l’utilisateur.

* Un espace insécable a été ajouté à la palette des caractères.  Un espace **insécable** empêche un saut de ligne automatique à un point donné d’un document d’HTML. L’éditeur web prend en charge un espace insécable pour les sorties AEM Site et HTML5.

* Lorsque vous téléchargez une image à partir de l’éditeur Web, une boîte de dialogue de confirmation s’affiche si une image portant le même nom existe déjà. Vous pouvez conserver les deux fichiers (existant et nouveau fichier) ou remplacer le fichier existant et enregistrer uniquement le nouveau fichier.

* Si un utilisateur a verrouillé un fichier pour y apporter des modifications, un administrateur peut le déverrouiller et l’archiver. Cette fonctionnalité s’avère utile lorsque certains fichiers doivent être modifiés, mais ont été verrouillés par des utilisateurs qui ne sont pas disponibles pour archiver le fichier.

### Tableau de bord des cartes

Lorsque vous choisissez de télécharger le mappage DITA, la demande est mise en file d’attente et vous recevez une notification une fois que le mappage est prêt à être téléchargé. Vous pouvez choisir de télécharger le fichier de carte immédiatement ou plus tard à partir du lien fourni dans la boîte de réception de notifications AEM.

![Téléchargement de carte](assets/download-map-prompt.png)

### Révision

Vous pouvez mentionner les détails dans le champ de description de la tâche de révision, qui s’affiche dans l’e-mail envoyé au validant.

## Problèmes résolus

Les bogues résolus dans différentes zones sont répertoriés ci-dessous :

### Publication basée sur des articles

* La publication basée sur des articles ne publie pas d’articles en fonction de la ligne de base sélectionnée. (8771)
* Les fichiers DITAVAL ne sont pas honorés dans la publication basée sur un article. (8770)
* Impossible d’effectuer une publication basée sur un article pour le profil Salesforce lorsque le type d’enregistrement est FAQ et que le contenu du champ d’article est Question. (8448)
* Impossible d’effectuer une publication basée sur un article pour le profil Salesforce lorsque le type d’enregistrement est Manuel. (8447)

### Éditeur web

* Le fait de faire glisser et de déposer une condition ne fonctionne pas sur les rubriques DITA. (8761)
* Les attributs sont absents lors de l’ajout d’un chapitre dans un bookmap à l’aide de la fonction Glisser-déposer depuis la vue Favoris. (8746)
* La modification des propriétés d’une image (hauteur, largeur) entraîne une erreur d’application. (8722)
* Les liens rompus n’apparaissent pas dans le panneau Contour de la vue source. (8590)
* XML Editor supprime la balise de nouvelle ligne dans le bloc de code. (8522)
* Un Glossaire s’affiche sous la forme d’une note lors de la création d’un Glossentry. (8384)
* xref ne peut pas être inséré même à des emplacements valides. (8354)
* La liste des éléments (Alt+Entrée) apparaît en grisé dans le thème Sombre/Plus sombre. (7913)
* La liste des modèles de mappage dans l’option **Créer** (menu de points de suspension) du panneau Référentiel n’est pas conforme au **profil de dossier** dans les préférences utilisateur. (5918)
* Les identifiants d’élément ne sont pas générés automatiquement pour les éléments ajoutés à partir de la fonction Réutiliser le contenu de la barre d’outils principale. (5826)

### Interface utilisateur d’Assets

* La modification des images ne fonctionne pas comme prévu sur le serveur cloud. (8768)
* Dans le panneau Historique des versions, la section de version actuelle affiche un horodatage incorrect et modifié par informations. (8765)
* Le téléchargement du fichier DITAVAL sur le serveur cloud échoue lorsque l’outil de bureau AEM est utilisé. (8707)
* Le deuxième utilisateur administrateur ne peut pas être ajouté en tant que premier utilisateur administrateur à un dossier. (8430)
* Les propriétés non uniques d’une ressource ne sont pas copiées lorsque la ressource est copiée et collée. (8241)

### Modifications de la convivialité

* Dans le panneau Révision de l’éditeur web, si un nom d’utilisateur est long, les icônes à accepter/rejeter ne s’affichent pas clairement. (8793)
* Dans le panneau **Rechercher et remplacer**, une icône indésirable s’affiche lorsque vous pointez sur la souris dans la section de résultat. (8775)
* L’icône personnalisée n’est pas sélectionnée dans la propriété. Au lieu de cela, l’icône par défaut s’affiche pour les rapports générés à l’aide du bouton Générer le rapport . (8573)
