---
title: Réutilisation du contenu DITA dans les guides AEM
description: Ce court article explique comment les guides AEM et DITA vous aident à gagner du temps et à économiser des efforts lors de l’utilisation de la réutilisation du contenu
role: User, Admin
exl-id: 1522ebf5-2aea-4d8f-ade7-367227b31dd9
source-git-commit: 4160c990bafe41611714ef66ee361aba0ef47c0a
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 0%

---

# Réutilisation du contenu dans les guides AEM

Adobe AEM Guides exploite les points forts de DITA pour fournir une interface conviviale pour la réutilisation du contenu.

Dans cet article, nous aborderons les sujets suivants :

1. [Réutilisation à l’aide de la référence de rubrique (](#reusability-using-topic-referencestopicref)
2. [Réutilisation à l’aide de la référence de contenu (](#reusability-using-content-reference-conref--conkeyref)
3. [Conseil bonus pour réutiliser du contenu par glisser-déposer dans les guides AEM](#reuse-content-with-a-single-click-in-aem-guides)

## Réutilisation à l’aide de références de rubrique (topicref)



Supposons que vous êtes un fabricant et que vous ayez des rubriques génériques pour les précautions de sécurité ou les techniques de dépannage.

Ils peuvent être référencés et adaptés dans des manuels d’utilisation spécifiques pour chaque modèle de machine, ce qui réduit la redondance et garantit que les informations de sécurité de base restent cohérentes.

```
<map id="user_manual_model 100" title="ABC Model 100 User Manual ">


<topicref href="Safety_Information.dita" format="dita">
</topicref>
.
.
.
.
.
</map>
```


De même pour le modèle 200

```
<map id="user_manual_model 200" title="ABC Model 200 User Manual ">

<topicref href="Safety_Information.dita" format="dita">
</topicref>
.
.
.
.
.
  
</map>
```

## Réutilisation à l’aide de la référence de contenu (conref et conkeyref)

L’attribut référence de contenu (conref) vous permet d’établir un lien vers d’autres parties de votre contenu. Cela favorise la réutilisation et réduit la redondance.

Par exemple :

Supposons que vous êtes une entreprise financière et que vous ayez un sujet générique pour KYC qui contient des procédures KYC pour les individus, les entreprises, etc.

Vous souhaitez réutiliser un fragment de clé USB individuel pour vos rubriques « Enregistrement du compte » et « Compte de démonstration ».

```
<section id="kyc_requirements_saving_account">
  <title>Know Your Customer (KYC) Requirements</title>
  <p>To comply with regulations and ensure customer identification, all individual applicants for savings  accounts must fulfill the KYC requirements as outlined below</p>
  <p conref=kyc_procedures.dita#individual_kyc></p>
</section>
```

Ici `conref=kyc_procedures.dita#indvidual_kyc` kyc_procédures.dita est l’identifiant du fichier et #individual_kyc est l’identifiant du fragment.

Kyc_Procedure.dita reste la seule source d&#39;information. Si des modifications sont apportées au processus de vérification des connaissances comme l’exige la réglementation, il vous suffit de mettre à jour une rubrique, et ces modifications sont automatiquement répercutées dans toutes les rubriques qui y font référence.

À l’aide des guides AEM, ses deux clics

Étape 1 : cliquez sur Insérer du contenu réutilisable
![barre d’outils](../../assets/publishing/content-reusability_image1.png)

<br>

Étape 2 : sélectionnez le fichier et le fragment qui doivent être réutilisés.
![conref](../../assets/publishing/content-reusability_image2.png)

Tout comme « conref », vous pouvez également utiliser « conkeyref » où, au lieu de donner un chemin de contenu, vous pouvez référencer du contenu par le biais de clés.

Exemple de code :

```
<section conkeyref="kyc_procedure/individual_kyc_procedure" id="individual_kyc_procedure"></section>
```

La définition de clé ressemble à ceci :

```
<map id="ABC_manual">
  <title>ABC_Manual</title>
  <topicref href="kyc_procedure_2020.dita" keys="kyc_procedure" processing-role="resource-only" type="concept">
  </topicref>
  <topicref href="savings_account.dita" type="concept">
  </topicref>
</map>
```

Clé - « Kyc_Procedure » restera la seule source d’information. Si des modifications sont apportées au processus de création des clés de connaissance comme l’exige la réglementation, vous devez simplement mettre à jour un chemin de rubrique avec un nouveau chemin de rubrique. Ces modifications seront répercutées automatiquement dans toutes les rubriques qui y font référence.

```
<map id="ABC_manual">
  <title>ABC_Manual</title>
  <topicref href="kyc_procedure_2024.dita" keys="kyc_procedure" processing-role="resource-only" type="concept">
  </topicref>
  <topicref href="savings_account.dita" type="concept">
  </topicref>
</map>
```

Ici, le chemin d&#39;accès au sujet est modifié de « kyc_PROCEDURE_2020.dita » à « kyc_PROCEDURE_2024.dita » en raison de modifications récentes de la réglementation.

À l’aide des guides AEM, ses deux clics

Étape 1 : cliquez sur Insérer du contenu réutilisable
![barre d’outils](../../assets/publishing/content-reusability_image1.png)

Étape 2 : sélectionnez la carte racine (facultative), la clé et le fragment qui doivent être réutilisés.
![conkeyref](../../assets/publishing/content-reusability_image3.png)

Ici, le mappage racine a été sélectionné automatiquement, car il était déjà ouvert dans la vue de mappage.


## Réutilisation du contenu en un seul clic dans les AEM Guides

AEM Guides offre une fonctionnalité « Contenu réutilisable » permettant d’ajouter des références de contenu en un seul clic.

Étape 1 : ajouter une rubrique générique aux contenus réutilisables

![Ajouter du contenu réutilisable](../../assets/publishing/content-reusability_image4.png)

Étape 2 : une fois ajouté, faites glisser et déposez le fragment que vous souhaitez réutiliser dans l’une de vos rubriques de destination.

![Ajouter un gif de contenu réutilisable](../../assets/publishing/content-reusability_image5.gif)



## Questions fréquentes

- ### Tout le contenu ne s’affiche pas après la sélection du fichier/de la clé dans la boîte de dialogue Réutiliser le contenu .

Vous devez attribuer des identifiants aux fragments (éléments de la diapositive ) que vous souhaitez réutiliser dans d’autres rubriques

- ## Les clés ne s’affichent pas dans la boîte de dialogue Réutiliser le contenu .

Assurez-vous d’avoir ouvert la carte racine/le mappage parent dans map-view qui comporte une définition de clé ou ajoutez le chemin de la carte racine manuellement dans la même boîte de dialogue.


<br>


Publication sur la communauté AEM Guides [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) pour toutes les requêtes.
