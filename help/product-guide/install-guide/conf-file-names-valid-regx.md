---
title: Configuration de Regx pour les caractères de nom de fichier valides
description: Découvrez comment configurer la regx pour les caractères de nom de fichier valides
exl-id: 876dfc77-078f-4341-b99d-02a453d2e065
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 0%

---

# Configuration de Regx pour les caractères de nom de fichier valides {#id214BD0550E8}

À compter de la version 3.8 d’AEM Guides, en tant qu’administrateur, vous pouvez définir une liste de caractères spéciaux valides autorisés dans les noms de fichier. Dans les versions antérieures, les utilisateurs étaient autorisés à définir des noms de fichier contenant des caractères spéciaux, tels que `@`, `$`, `>`, etc. Ces caractères spéciaux entraînaient des problèmes lors de l’ouverture de rubriques à partir du tableau de bord de la carte DITA ou d’un clic sur le lien de la rubrique dans la table des matières, ce qui entraînait souvent l’ouverture de la page en raison de caractères spéciaux dans l’URL.

En utilisant la configuration qui vous permet de définir une regx pour les caractères de nom de fichier valides, vous avez un contrôle total sur la manière dont les fichiers sont nommés en interne dans le système. Vous pouvez définir une liste de caractères spéciaux autorisés dans les noms de fichier. Par défaut, la configuration de nom de fichier valide contient &quot;`a-z A-Z 0-9 - _`&quot;. Lors de la création d’un fichier, vous pouvez avoir n’importe quel caractère spécial dans le titre du fichier, mais en interne, il sera remplacé par &quot;&quot;.`-`&quot; dans le nom du fichier. Par exemple, le titre du fichier peut être &quot;Introduction 1&quot; ou &quot;Introduction@1&quot;, le nom de fichier correspondant généré pour ces deux cas serait &quot;Introduction-1&quot;.

Lorsque vous définissez une liste de caractères valides, n’oubliez pas que ces caractères &quot;`*/:[\]|#%{}?&<>"/+`&quot; sera toujours remplacé par un &quot;`-`&quot;.

Si vous ne configurez pas la liste des caractères spéciaux valides, le processus de création de fichier peut vous donner des résultats inattendus. Pour éviter de telles erreurs, il est vivement recommandé d&#39;effectuer cette modification de configuration immédiatement après la mise à niveau de votre version vers la version 3.8.

Pour configurer une expression régulière pour les caractères \(ou autorisés\) valides dans les noms de fichier, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le bouton *com.adobe.config.ConfigManager* du lot.

1. Dans le **Expression régulière pour les caractères valides** , assurez-vous que la propriété est définie sur \[-a-zA-Z0-9\_\]. Vous pouvez ajouter d’autres caractères à cette liste, mais elle doit contenir ces caractères de base et la liste doit commencer par un trait d’union &quot;-&quot;.

   >[!NOTE]
   >
   > Cette propriété s’applique uniquement aux noms de fichiers, et non aux noms de dossiers.

1. Cliquez sur **Enregistrer**.


>[!NOTE]
>
> Tout comme la liste des caractères de nom de fichier valides, vous pouvez également spécifier une liste de caractères de nom de fichier valides pour AEM sortie Site. Pour plus d’informations, voir [Configuration de noms de fichier valides pour AEM sortie Site](conf-file-names-valid-regx-aem-site-output.md#).

**Rubrique parente :**[ Configuration des noms de fichier](conf-file-names.md)
