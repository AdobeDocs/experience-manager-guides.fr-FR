---
title: Réutilisation du contenu DITA dans AEM Guides
description: Ce bref article explique comment AEM Guides et DITA vous permettent de gagner du temps et des efforts lors de l’utilisation de la réutilisation du contenu.
role: User, Admin
exl-id: 1522ebf5-2aea-4d8f-ade7-367227b31dd9
source-git-commit: 12d7f9c3479d2fa8e8f0adad7cb89993cd17dec0
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---

# Réutilisation du contenu dans AEM Guides

Adobe AEM Guides tire parti des avantages de DITA pour offrir une interface conviviale pour la réutilisation du contenu.

Cet article abordera :

1. [Réutilisation à l’aide de la référence de rubrique (](#reusability-using-topic-referencestopicref)
2. [Réutilisation à l’aide de la référence de contenu (](#reusability-using-content-reference-conref--conkeyref)
3. [Conseil pour réutiliser le contenu par glisser-déposer dans AEM Guides](#reuse-content-with-a-single-click-in-aem-guides)

## Réutilisation à l’aide des références de rubrique (topicref)



Supposons que vous soyez une société de fabrication et que vous ayez des rubriques génériques pour les mesures de sécurité ou les techniques de dépannage.

Ils peuvent être référencés et adaptés dans des manuels d’utilisation spécifiques pour chaque modèle de machine, ce qui réduit la redondance et garantit la cohérence des informations de sécurité de base.

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

## Réutilisation à l’aide de la référence de contenu (conref &amp; conkeyref

L’attribut de référence de contenu (conref) vous permet de créer des liens vers d’autres parties de votre contenu. Cela favorise la réutilisation et réduit la redondance.

Par exemple :

Supposons que vous soyez une entreprise financière et que vous ayez un sujet générique pour KYC qui contient des procédures de KYC pour les individus, les entreprises, etc.

Vous souhaitez réutiliser un fragment de code de visite individuel pour les rubriques &quot;Enregistrement du compte&quot; et &quot;Compte de démonstration&quot;.

```
<section id="kyc_requirements_saving_account">
  <title>Know Your Customer (KYC) Requirements</title>
  <p>To comply with regulations and ensure customer identification, all individual applicants for savings  accounts must fulfill the KYC requirements as outlined below</p>
  <p conref=kyc_procedures.dita#individual_kyc></p>
</section>
```

`conref=kyc_procedures.dita#indvidual_kyc` kyc_processes.dita est l&#39;identifiant du fichier et #individual_kyc est l&#39;identifiant du fragment.

Kyc_process.dita reste la seule source d&#39;information. Si les modifications réglementaires nécessitent des mises à jour du processus de création de parcours, mettez à jour le chemin du sujet avec le nouveau. Les modifications seront automatiquement répercutées dans toutes les rubriques qui y font référence.

Avec AEM Guides, ses deux clics

Etape 1 : cliquez sur Insérer du contenu réutilisable
![toolbar](../../assets/publishing/content-reusability_image1.png)

<br>

Étape 2 : sélectionnez le fichier et le fragment qui doivent être réutilisés.
![conref](../../assets/publishing/content-reusability_image2.png)

Tout comme &quot;conref&quot;, vous pouvez utiliser &quot;conkeyref&quot; où, au lieu de donner un chemin de contenu, vous référencez le contenu par clé

Exemple de code :

```
<section conkeyref="kyc_procedure/individual_kyc_procedure" id="individual_kyc_procedure"></section>
```

La définition de clé se présente comme suit :

```
<map id="ABC_manual">
  <title>ABC_Manual</title>
  <topicref href="kyc_procedure_2020.dita" keys="kyc_procedure" processing-role="resource-only" type="concept">
  </topicref>
  <topicref href="savings_account.dita" type="concept">
  </topicref>
</map>
```

Clé : &quot;Kyc_process&quot; reste la source unique d’informations. S’il existe des modifications au processus de création de rapports d’expérience (KYC) requises par les réglementations, vous devez simplement mettre à jour un chemin de rubrique avec un nouveau chemin de rubrique. Ces modifications sont automatiquement répercutées dans toutes les rubriques qui y font référence.

```
<map id="ABC_manual">
  <title>ABC_Manual</title>
  <topicref href="kyc_procedure_2024.dita" keys="kyc_procedure" processing-role="resource-only" type="concept">
  </topicref>
  <topicref href="savings_account.dita" type="concept">
  </topicref>
</map>
```

Ici, le chemin d’accès à la rubrique est remplacé par &quot;kyc_process_2020.dita&quot; en raison de modifications récentes de la réglementation.

Avec AEM Guides, ses deux clics

Etape 1 : cliquez sur Insérer du contenu réutilisable
![toolbar](../../assets/publishing/content-reusability_image1.png)

Étape 2 : sélectionnez le mappage racine (facultatif), la clé et le fragment qui doivent être réutilisés.
![conkeyref](../../assets/publishing/content-reusability_image3.png)

Ici, la carte racine a été sélectionnée automatiquement, car elle était déjà ouverte dans la vue map.


## Réutilisation de contenu en un seul clic dans AEM Guides

AEM Guides offre une fonctionnalité &quot;Contenu réutilisable&quot; pour ajouter des références de contenu en un seul clic.

Étape 1 : Ajout d’une rubrique générique au contenu réutilisable

![Ajouter du contenu réutilisable](../../assets/publishing/content-reusability_image4.png)

Étape 2 : une fois ajouté, faites glisser et déposez le fragment que vous souhaitez réutiliser dans l’une de vos rubriques de destination.

![Ajouter un contenu réutilisable gif](../../assets/publishing/content-reusability_image5.gif)



## Questions fréquentes

- ### Tout le contenu ne s’affiche pas après la sélection d’un fichier/d’une clé dans la boîte de dialogue Réutiliser le contenu .

Attribuer des identifiants aux fragments (éléments Dita) que vous souhaitez réutiliser dans d’autres rubriques

- ## Les clés ne s’affichent pas dans la boîte de dialogue Réutiliser le contenu

  Assurez-vous d’avoir ouvert la carte racine/la carte parent dans map-view, qui comporte une définition de clé ou ajoutez le chemin de la carte racine manuellement dans la même boîte de dialogue.


<br>
<br>
<br>


Publiez sur le [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) de la communauté AEM Guides pour toutes les requêtes.
