---
title: Prise en charge des schémas dans l’éditeur web
description: Utilisation de Schematron dans l’éditeur web
exl-id: 3e61432f-d81e-446e-b0ad-560f5b9fa91a
feature: Web Editor
role: User, Admin
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---

# Contrôle de la qualité du contenu dans l’éditeur web

Cet article donne un aperçu des possibilités de validation dans l’éditeur web d’AEM Guides.
Par défaut, l&#39;éditeur web exploite la configuration du schéma DITA dans le système pour obliger les utilisateurs à créer du contenu compatible DITA. Ainsi, tout le contenu stocké dans le système est structuré, réutilisable et valide dans le contenu DITA.

Outre la prise en charge des règles DITA, l’éditeur web prend également en charge la validation du contenu en fonction des règles « *Schematron* ».

« *Schematron* » fait référence à un langage de validation basé sur des règles utilisé pour définir des tests pour un fichier XML. Vous pouvez importer les fichiers Schematron et les modifier également dans l&#39;éditeur Web. A l&#39;aide d&#39;un fichier « Schematron », vous pouvez définir certaines règles, puis les valider pour une rubrique DITA ou un mappage. Les règles de schéma peuvent assurer la cohérence de la structure XML en imposant des restrictions définies sous la forme de règles. Ces restrictions sont imposées par les PME qui sont propriétaires de la qualité et de la cohérence du contenu.

REMARQUE : l&#39;éditeur Web prend en charge le schéma ISO.


## Savoir comment fonctionne « Schematron » dans un éditeur web

### Configuration des règles de schéma

Reportez-vous à la section « Prise en charge des fichiers Schematron » du [Guide de l’utilisateur](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=148)


### Application des règles de validation lors de l’enregistrement du fichier

Les paramètres de l’éditeur web permettent aux utilisateurs expérimentés de configurer des règles/fichiers Schematron qui seront exécutés chaque fois qu’un utilisateur met à jour le contenu. Pour plus d’informations, consultez la section « Validation » du [Guide de l’utilisateur](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=58)

![Définissez des règles à partir des paramètres de l’éditeur web](../../../assets/authoring/schematron-editorsettings-validation-tab.png)


### Pouvez-vous exécuter la validation manuellement ?

Oui, en tant qu’auteur/utilisateur lors de la création de contenu, vous pouvez utiliser le panneau Schéma dans l’éditeur web pour charger un fichier de schéma et exécuter des validations sur le fichier ouvert dans l’éditeur.

Pour que cela fonctionne, l’administrateur de profils de dossiers doit autoriser tous les utilisateurs à ajouter des fichiers Schemtron dans le panneau Validation. Voir les paramètres de l’éditeur (capture d’écran ci-dessus)

![Choisir le fichier Schematron](../../../assets/authoring/schematron-rightpanel-validation-addsch.png)
![Exécuter la validation](../../../assets/authoring/schematron-rightpanel-validation-runsch.png)


### Règles prises en charge

La version actuelle d’AEM Guides prend uniquement en charge la validation à l’aide de règles basées sur « Assertion ». (voir [rapport sur les ressources](https://schematron.com/document/205.html))
Les règles basées sur « Rapports » ne sont pas encore prises en charge.


### Exemples et plus d’aide sur les règles Schematron

#### Exemples de cas d’utilisation

- Vérifier si un lien est externe et s’il a une portée « externe »

  ```
  <sch:pattern>
      <sch:rule context="xref[contains(@href, 'http') or contains(@href, 'https')]">
          <sch:assert test="@scope = 'external' and @format = 'html'">
              All external xref links must be with scope='external' and format='html'
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

- Vérifiez s&#39;il y a au moins un « topicref » dans une carte ou au moins un « li » sous un « ul »

  ```
  <sch:pattern>
      <sch:rule context="map">
          <sch:assert test="count(topicref) > 0">
              There should be atleast one topicref in map
          </sch:assert>
      </sch:rule>
  
      <sch:rule context="ul">
          <sch:assert test="count(li) > 1" >
              A list must have more than one item.
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

- L’élément « indexterm » doit toujours être présent dans un « prologue »

  ```
  <sch:pattern>
      <sch:rule context="*[contains(@class, ' topic/indexterm ')]">
          <sch:assert test="ancestor::node()/local-name() = 'prolog'">
              The indexterm element should be in a prolog.
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

#### Ressources

- Présentation des [principes de base de Schematron](https://da2022.xatapult.com/#what-is-schematron)
- En savoir plus sur [Règles d’assertion dans Schematron](https://www.xml.com/pub/a/2003/11/12/schematron.html#Assertions)
- [Exemple de fichier Schematron](../../../assets/authoring/sample_schematron.sch)
