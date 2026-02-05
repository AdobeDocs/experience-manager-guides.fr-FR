---
title: Déploiement de l’indexation personnalisée
description: Découvrez comment créer un contenu d’index personnalisé
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 9a4f0391c464d69ea65ecfdaac6ecdcb17d1a3da
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 3%

---

# Déploiement de l’index personnalisé pour la fonction Rechercher et remplacer (vue Source)

## Vue d’ensemble

Ce guide fournit des instructions détaillées sur le déploiement de l’index personnalisé `guidesAssetLucene‑1‑custom‑1` sur Adobe Experience Manager (AEM) as a Cloud Service. Bien que la fonction de recherche et de remplacement standard de la vue Auteur fonctionne sans cet index, l’index personnalisé est spécifiquement requis pour activer la fonction de recherche et de remplacement dans la vue Source. La fonction Rechercher et remplacer (vue Source) vous permet de rechercher non seulement le contenu créé visible, mais également la structure XML sous-jacente, y compris les éléments, les balises et les valeurs d’attribut.

## Prérequis

Avant de poursuivre le déploiement de l’index, vérifiez que vous disposez des éléments suivants :

- **Environnement AEM as a Cloud Service** avec AEM Guides installé
- **Accès à la base de code de votre projet** (référentiel Git)
- Accès à **Cloud Manager** avec autorisations de déploiement

## Définition de l’index

Pour activer la fonction Rechercher et remplacer (vue Source), vous devez déployer un index personnalisé nommé **`guidesAssetLucene-1-custom-1`** dans votre environnement AEM Cloud Service.

### Nom de l’index

```
guidesAssetLucene-1-custom-1
```

### Définition d’index (.content.xml)

Créez la définition d’index suivante dans votre projet sur :

`ui.apps/src/main/content/jcr_root/_oak_index/guidesAssetLucene-1-custom-1/.content.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:dam="http://www.day.com/dam/1.0"
          xmlns:nt="http://www.jcp.org/jcr/nt/1.0" xmlns:oak="http://jackrabbit.apache.org/oak/ns/1.0"
          xmlns:rep="internal"
          jcr:mixinTypes="[rep:AccessControllable]"
          jcr:primaryType="oak:QueryIndexDefinition"
          async="[async,nrt]"
          compatVersion="{Long}2"
          evaluatePathRestrictions="{Boolean}true"
          includedPaths="[/content/dam]"
          selectionPolicy="tag"
          tags="[ditaSearch]"
          type="lucene">

    <aggregates jcr:primaryType="nt:unstructured">
        <dam:Asset jcr:primaryType="nt:unstructured">
            <include0
                    jcr:primaryType="nt:unstructured"
                    path="jcr:content/renditions/original/jcr:content"
                    relativeNode="{Boolean}true"/>
        </dam:Asset>
    </aggregates>

    <analyzers jcr:primaryType="nt:unstructured">
        <default jcr:primaryType="nt:unstructured">
            <tokenizer
                    jcr:primaryType="nt:unstructured"
                    name="Whitespace"/>
        </default>
    </analyzers>

    <indexRules jcr:primaryType="nt:unstructured">
        <dam:Asset
                jcr:primaryType="nt:unstructured"
                indexNodeName="{Boolean}true">
            <properties jcr:primaryType="nt:unstructured">
                <cqTags
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/cq:tags"
                        nodeScopeIndex="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        useInSpellcheck="{Boolean}true"
                        useInSuggest="{Boolean}true"/>
                <jcrLastModified
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/jcr:lastModified"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        type="Date"/>
                <jcrCreated
                        jcr:primaryType="nt:unstructured"
                        name="jcr:created"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        type="Date"/>
                <guidesParentMaps
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/guidesParentMaps"
                        propertyIndex="{Boolean}true"/>
                <guidesDirectParentMaps
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/guidesDirectParentMaps"
                        propertyIndex="{Boolean}true"/>
                <ditaClass
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/dita_class"
                        propertyIndex="{Boolean}true"/>
                <nodeNameLowerCase
                        jcr:primaryType="nt:unstructured"
                        function="fn:lower-case(fn:name())"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"/>
                <cqDriveLock
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/cq:driveLock"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <docState
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/docstate"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <jcrPath
                        jcr:primaryType="nt:unstructured"
                        function="fn:path()"
                        ordered="{Boolean}true"/>
                <dcTitleLowerCase
                        jcr:primaryType="nt:unstructured"
                        function="fn:lower-case(jcr:first(jcr:content/metadata/@dc:title))"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <dcTitle
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/dc:title"
                        propertyIndex="{Boolean}true"/>
            </properties>
        </dam:Asset>
    </indexRules>

    <tika jcr:primaryType="nt:unstructured">
        <mimeTypes jcr:primaryType="nt:unstructured">
            <application jcr:primaryType="nt:unstructured">
                <xml
                        jcr:primaryType="nt:unstructured"
                        mappedType="application/dita+xml"/>
            </application>
            <text jcr:primaryType="nt:unstructured">
                <markdown
                        jcr:primaryType="nt:unstructured"
                        mappedType="text/markdown+source"/>
            </text>
        </mimeTypes>
    </tika>
</jcr:root>
```

## Étapes de déploiement

Pour obtenir des instructions détaillées sur le déploiement d’index personnalisés vers AEM as a Cloud Service, consultez la page [Recherche et indexation de contenu - AEM as a Cloud Service](https://experienceleague.adobe.com/fr/docs/experience-manager-cloud-service/content/operations/indexing).

### Points importants pour cet index

Lorsque vous suivez le guide de déploiement, utilisez les informations suivantes pour l’index de recherche et de remplacement :

- **Nom de l’index** : `guidesAssetLucene-1-custom-1`
- **Type d’index** : index entièrement personnalisé (il ne s’agit pas d’une personnalisation de l’index OOTB)
- **Emplacement** : `ui.apps/src/main/content/jcr_root/_oak_index/guidesAssetLucene-1-custom-1/.content.xml`
- **Propriétés de package requises** :
   - `noIntermediateSaves=true`
   - `allowIndexDefinitions=true`

## Réindexation

La réindexation est gérée **automatiquement** par AEM as a Cloud Service lorsque vous déployez l’index via le pipeline CI/CD de Cloud Manager.

L’indexation est généralement gérée automatiquement. Cependant, si les anciennes données ne peuvent toujours pas faire l’objet de recherches, même après un déploiement correct et la fin du processus d’indexation, une réindexation manuelle de l’index doit être effectuée une seule fois.

### À quoi s’attendre ?

- La tâche d’indexation démarrera automatiquement après le déploiement.
- Vous pouvez surveiller la progression sur la page de création de Cloud Manager.
- L’environnement reste entièrement opérationnel pendant l’indexation.

## Vérification

Une fois le déploiement et l’indexation terminés, vérifiez que l’index fonctionne correctement.

### Vérifier le déploiement de l’index

Dans votre environnement de développement (si CRXDE Lite est disponible) :

1. Accédez à `/oak:index/guidesAssetLucene-1-custom-1`.
2. Vérifiez que le nœud existe avec la configuration attendue.

### Tester la fonction Rechercher et remplacer

La vérification principale consiste à tester la fonctionnalité :

1. Ouvrez AEM Guides.
2. Accédez à **Outils** > **Guides** > **Rechercher et remplacer dans le référentiel**.
3. Configurez une recherche de texte dans vos fichiers DITA ou Markdown.
4. Vérifiez que les résultats de la recherche sont correctement renvoyés.
5. Testez la fonctionnalité de remplacement sur un fichier de test.

## Ressources supplémentaires

- [Documentation sur l’indexation AEM as a Cloud Service](https://experienceleague.adobe.com/fr/docs/experience-manager-cloud-service/content/operations/indexing)
- [&#x200B; Guide d’indexation Apache Jackrabbit Oak &#x200B;](https://jackrabbit.apache.org/oak/docs/query/indexing.html)
- [Documentation AEM Guides](https://experienceleague.adobe.com/fr/docs/experience-manager-guides)
- [Documentation Cloud Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager)
