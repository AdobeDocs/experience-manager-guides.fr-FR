---
title: Recommendations pour l’optimisation des performances
description: Découvrez Recommendations pour l’optimisation des performances
exl-id: b2a836a0-de82-4d89-aae3-43276997da74
feature: Performance Optimization
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '967'
ht-degree: 0%

---

# Recommendations pour l’optimisation des performances {#id213BD0JG0XA}

## Configurer l’entrepôt de données \(obligatoire\)

**Quelle est la modification ?**
Définissez la propriété `minRecordLength` sur une valeur `100` sous la configuration `org.apache.jackrabbit.oak.plugins.blob.datastore.FileDataStore.` Pour plus d’informations sur le magasin de dates de fichier et le magasin de données S3, consultez l’article [Configuration des magasins de noeuds et des entrepôts de données dans AEM 6](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html) .

>[!NOTE]
>
> Pour l’entrepôt de données S3, le coût de maintenance du contenu dans l’entrepôt de données dépend également du nombre de requêtes. Par conséquent, lors de l’exécution de ce paramètre avec S3, le coût de configuration par requête et la taille du cache doivent également être pris en compte.

**Quand configurer ?**
Après la configuration initiale, mais avant la migration de tout contenu. Vous devez effectuer cette modification même sur un système existant, qui garantit que tout nouveau contenu est stocké dans l’entrepôt de données au lieu de l’entrepôt de segments.

**Résultat de cette modification**
Les fichiers DITA sont enregistrés dans l’entrepôt de données plutôt que dans l’entrepôt de segments. Cela permet de maintenir la taille de la banque de segments sous les limites recommandées, ce qui améliore la réactivité du système.

## Mise à jour de l’index Lucene \(obligatoire\)

**Quelle est la modification ?**
Excluez /var/dxml de oak:index/lucene.

>[!NOTE]
>
> AEM Guides n’utilise jamais les index Lucene pour rechercher du contenu dans le noeud /var/dxml .

**Quand configurer ?**
Si vous effectuez cette modification sur un nouveau système avant de migrer le contenu, seule la mise à jour oak:index/lucene est requise. Dans le cas contraire, sur un système existant où le contenu est déjà migré, après avoir apporté la modification dans oak:index/lucene, reconstruisez les index pour Lucene \(*qui peuvent prendre quelques heures pour se terminer*\).

**Résultat de cette modification**
Cette modification empêche le noeud /var/dxml d’être indexé et stocké dans le magasin de segments.

## Optimisation de la mémoire Java \(Obligatoire\)

**Quelle est la modification ?**
Les paramètres de démarrage de la JVM doivent être soigneusement réglés en fonction de l’infrastructure et de la taille du disque. Il est recommandé de consulter le support Adobe pour obtenir de l’aide afin d’accéder à la configuration idéale. Vous pouvez toutefois essayer vous-même les configurations suivantes :

- Définissez la taille du tas JVM sur un minimum de 1/4 de la quantité totale de mémoire disponible. Utilisez le paramètre `-Xmx<size>` pour définir la taille de la mémoire du tas. Définissez la valeur de -`Xms` égale à `-Xmx`.

- Activez `-XX:+HeapDumpOnOutOfMemoryError` et définissez le chemin pour `-XX:HeapDumpPath=</path/to/folder``>`.

- Activez le journal GC Java en tant que :

`* -XX:+PrintGCDateStamps`

`* -verbose:gc`

`* -XX:+PrintGCDetails`

`* -XX:+PrintTenuringDistribution`

`* -Xloggc:</path/to/gc.log>`

- En général, pour Java 11, utilisez G1GC \(`-XX:+UseG1GC`\) et pour Java 8, utilisez CMS \(-`XX:+UseConcMarkSweepGC`\).

- Utilisez `-XX:NewRatio` pour contrôler la taille de la taille de la mémoire de la jeune génération. La valeur par défaut est 2, ce qui signifie que 1/3 de la mémoire est utilisée pour la jeune génération. Comme de nombreux objets sont rapidement créés et détruits, l’utilisation d’une valeur de 1 allouera 1/2 de la mémoire à la jeune génération.

- Contrôlez le nombre d’objets convertis en anciennes générations à l’aide de `-XX:MaxTenuringThreshold`. Utilisez la valeur 15 \(default\) pour retarder la conversion d’objets en objets de l’ancienne génération.

**Quand configurer ?**
Si vous effectuez cette modification sur un système existant, vous devez redémarrer le système. Dans le cas d’une nouvelle installation, cette modification doit être effectuée dans le fichier de script de démarrage \(.bat ou .sh\) avant le démarrage du système.

**Résultat de cette modification**
Cela se traduit par une taille de tas optimale et une exécution réglementée du GC.

## Minimisation de la bibliothèque cliente sur l’instance d’auteur \(facultatif\)

**Quelle est la modification ?**
Les bibliothèques clientes doivent être définies pour être réduites dans les instances de création. Cela permet de s’assurer qu’il y a moins d’octets à télécharger lorsqu’un utilisateur navigue sur le système à partir de différents emplacements. Pour effectuer cette modification, définissez la configuration dans **HTML Library Manager** à partir de la console Felix.

**Quand configurer ?**
Cela peut être effectué au moment de l’exécution via la console Felix ou via le déploiement du code.

**Résultat de cette modification**
Cette modification améliore le temps de chargement des pages sur l’instance d’auteur, car moins d’octets sont transférés pour le chargement des bibliothèques clientes.

## Configuration de threads de publication simultanés \(obligatoire, selon le cas d’utilisation\)

**Quelle est la modification ?**
Cette modification est requise si vous utilisez DITA-OT pour publier la sortie et qu’un certain nombre de threads de publication simultanés sont également définis.

Par défaut, AEM Guides définit les threads de publication sur le nombre de processeurs+1. Cependant, il est recommandé de définir cette valeur sur la moitié \(1/2\) ou un tiers \(1/3\) du nombre total d’unités centrales. Pour ce faire, définissez la propriété **Generation Pool Size** sous la configuration `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl` conformément aux recommandations.

**Quand configurer ?**
Cela peut être effectué au moment de l’exécution via la console Felix ou via le déploiement du code.

**Résultat de cette modification**
Cette modification permet de s’assurer que toutes les ressources ne sont pas allouées pour les opérations de publication sur une instance d’auteur en cours d’exécution. Cela permet de conserver les ressources système disponibles pour les auteurs, ce qui se traduit par une meilleure expérience utilisateur.

## Configuration de la taille de lot des noeuds pour AEM génération de sortie de site \(obligatoire, selon le cas d’utilisation\)

**Quelle est la modification ?**
Cette modification est requise si vous générez une sortie AEM Sites.

Définissez la propriété **Limiter les pages AEM du site dans le tas** sous `com.adobe.fmdita.config.ConfigManager` sur un nombre en fonction de la configuration de votre système. Cette propriété définit la taille de lot des noeuds à valider lors de la génération des pages du site. Par exemple, sur un système avec un plus grand nombre de processeurs et une taille de tas plus importante, vous pouvez augmenter la valeur par défaut de `500` à un plus grand nombre. Vous devez tester l’exécution avec la valeur modifiée pour obtenir une valeur optimale pour cette propriété.

**Quand configurer ?**
Cela peut être effectué au moment de l’exécution via la console Felix ou via le déploiement du code.

**Résultat de cette modification**
Un nombre accru de la propriété **Limiter les pages du site AEM dans Heap** optimise le processus de génération de sortie AEM site.

## Optimiser le nombre de threads de post-traitement \(obligatoire, selon le cas d’utilisation\)

**Quelle est la modification ?**
Cette modification est requise si vous téléchargez du contenu DITA en masse.

Définissez la propriété **Post Process Threads** sous `com.adobe.fmdita.config.ConfigManager` sur `1`.

**Quand configurer ?**
Cela peut être effectué au moment de l’exécution.

**Résultat de cette modification**
Cette modification réduit le temps de post-traitement lors du téléchargement massif de fichiers DITA.

**Rubrique parente :**[ Télécharger et installer](download-install.md)
