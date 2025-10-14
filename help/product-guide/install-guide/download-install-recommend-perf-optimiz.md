---
title: Recommendations pour l’optimisation des performances
description: Découvrir le Recommendations pour l’optimisation des performances
exl-id: b2a836a0-de82-4d89-aae3-43276997da74
feature: Performance Optimization
role: Admin
level: Experienced
source-git-commit: b28b7d96cce69f677b0bcf891b94d7ac84eb1eb0
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 0%

---

# Recommendations pour l’optimisation des performances {#id213BD0JG0XA}

## Configuration du magasin de données \(Obligatoire\)

**Quel est le changement ?**
Définissez la propriété `minRecordLength` sur une valeur de `100` sous le `org.apache.jackrabbit.oak.plugins.blob.datastore.FileDataStore.` de configuration. Pour plus d’informations sur le magasin de dates de fichiers et le magasin de données S3, consultez l’article [Configuration des magasins de nœuds et de données dans AEM 6](https://helpx.adobe.com/fr/experience-manager/6-5/sites/deploying/using/data-store-config.html) .

>[!NOTE]
>
> Pour le magasin de données S3, le coût de maintenance du contenu du magasin de données dépend également du nombre de requêtes. Par conséquent, lorsque vous définissez ce paramètre avec S3, le coût de configuration par requête et la taille du cache doivent également être pris en compte.

**Quand configurer ?**
Après la configuration initiale, mais avant la migration d’un contenu. Vous devez effectuer cette modification même sur un système existant, ce qui garantit que tout nouveau contenu est stocké dans l’entrepôt de données plutôt que dans l’entrepôt de segments.

**Résultat de cette modification**
Les fichiers DITA sont enregistrés dans l&#39;entrepôt de données plutôt que dans l&#39;entrepôt de segments. Cela permet de maintenir la taille de la banque de segments sous les limites recommandées, ce qui améliore la réactivité du système.

## Mettre à jour l’index Lucene \(Obligatoire\)

**Quel est le changement ?**
Excluez /var/dxml de oak:index/lucene.

>[!NOTE]
>
> AEM Guides n’utilise jamais les index Lucene pour rechercher du contenu dans le nœud /var/dxml.

**Quand configurer ?**
Si vous apportez cette modification à un nouveau système avant de migrer le contenu, seule la mise à jour de oak:index/lucene est requise. Sinon, sur un système existant où le contenu est déjà migré, après avoir effectué la modification dans oak:index/lucene, recréez les index pour Lucene \(*ce qui peut prendre quelques heures*\).

**Résultat de cette modification**
Cette modification empêche le nœud /var/dxml d’être indexé et stocké dans le magasin de segments.

## Optimisation de la mémoire Java \(Obligatoire\)

**Quel est le changement ?**
Les paramètres de démarrage de la JVM doivent être soigneusement réglés en fonction de l’infrastructure et de la taille du disque. Il est recommandé de consulter le support technique d’Adobe pour obtenir de l’aide afin d’accéder à la configuration idéale. Vous pouvez toutefois essayer les configurations suivantes vous-même :

- Définissez la taille du tas JVM sur un minimum de 1/4 de la mémoire totale disponible. Utilisez le paramètre `-Xmx<size>` pour définir la taille de la mémoire de tas. Définissez la valeur de -`Xms` est égale à `-Xmx`.

- Activez `-XX:+HeapDumpOnOutOfMemoryError` et définissez le chemin d’accès pour `-XX:HeapDumpPath=</path/to/folder` `>`.

- Activez le journal Java GC en tant que :

`* -XX:+PrintGCDateStamps`

`* -verbose:gc`

`* -XX:+PrintGCDetails`

`* -XX:+PrintTenuringDistribution`

`* -Xloggc:</path/to/gc.log>`

- En général, pour Java 11, utilisez G1GC \(`-XX:+UseG1GC`\) et pour Java 8, utilisez CMS \(-`XX:+UseConcMarkSweepGC`\).

- Utilisez `-XX:NewRatio` pour contrôler la taille de la mémoire de la jeune génération. La valeur par défaut est 2, ce qui signifie que 1/3 de la mémoire est utilisé pour la jeune génération. Comme de nombreux objets sont créés et détruits rapidement, l’utilisation d’une valeur de 1 allouera 1/2 de la mémoire à la jeune génération.

- Contrôlez le nombre d’objets promus vers l’ancienne génération à l’aide de `-XX:MaxTenuringThreshold`. Utilisez la valeur 15 \(default\) pour retarder le passage des objets à l&#39;ancienne génération.

**Quand configurer ?**
Si vous apportez cette modification à un système existant, vous devez redémarrer le système. Dans le cas d’une nouvelle installation, cette modification doit être effectuée dans le fichier de script de démarrage \(.bat ou .sh\) avant le démarrage du système.

**Résultat de cette modification**
Cela permet d’obtenir une taille de tas optimale et une exécution régulée du GC.

## Minimisation de la bibliothèque cliente sur l’instance d’auteur \(Facultatif\)

**Quel est le changement ?**
Les bibliothèques clientes doivent être définies pour être réduites dans les instances de création. Cela permet de s’assurer qu’il y a moins d’octets à télécharger lorsqu’un utilisateur ou une utilisatrice parcourt le système à partir de différents emplacements. Pour effectuer cette modification, définissez la configuration dans **HTML Library Manager** à partir de la console Felix.

**Quand configurer ?**
Cela peut être effectué au moment de l’exécution via la console Felix ou via le déploiement du code.

**Résultat de cette modification**
Cette modification réduit le temps de chargement des pages sur l’instance d’auteur, car moins d’octets sont transférés pour charger les bibliothèques clientes.

## Configuration des threads de publication simultanée \(obligatoire, selon le cas d’utilisation\)

**Quel est le changement ?**
Cette modification est requise si vous utilisez DITA-OT pour publier la sortie et qu’un certain nombre de threads de publication simultanés sont également définis.

Par défaut, AEM Guides définit les threads de publication sur le nombre de processeurs+1. Cependant, il est recommandé de définir cette valeur sur la moitié \(1/2\) ou sur le tiers \(1/3\) du nombre total de processeurs. Pour ce faire, définissez la propriété **Taille du pool de génération** sous le `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl` de configuration en fonction des recommandations.

**Quand configurer ?**
Cela peut être effectué au moment de l’exécution via la console Felix ou via le déploiement du code.

**Résultat de cette modification**
Cette modification garantit que sur une instance de création en cours d’exécution, toutes les ressources ne sont pas allouées pour les opérations de publication. Cela permet aux auteurs et autrices de disposer des ressources système, ce qui se traduit par une meilleure expérience utilisateur.

## Configurez la taille de lot des nœuds pour la génération de sortie AEM Site \(Obligatoire, selon le cas d’utilisation\)

**quel est le changement ?**
Cette modification est requise si vous générez une sortie AEM Sites.

Définissez la propriété **Limiter les pages du site AEM dans le tas** sous `com.adobe.fmdita.config.ConfigManager` sur un nombre en fonction de la configuration de votre système. Cette propriété définit la taille du lot des nœuds à valider lors de la génération des pages du site. Par exemple, sur un système avec un plus grand nombre de processeurs et une taille de tas plus importante, vous pouvez augmenter la valeur par défaut de `500` à un plus grand nombre. Vous devez tester l’exécution avec la valeur modifiée pour obtenir une valeur optimale pour cette propriété.

**Quand configurer ?**
Cela peut être effectué au moment de l’exécution via la console Felix ou via le déploiement du code.

**Résultat de cette modification**
Un nombre accru de la propriété **Limiter les pages du site AEM dans le tas** optimise le processus de génération de sortie du site AEM.


**Rubrique parente :**&#x200B;[&#x200B; Télécharger et installer](download-install.md)
