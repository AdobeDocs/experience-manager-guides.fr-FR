---
title: Configurer Regx pour les caractères de nom de fichier valides
description: Découvrez comment configurer la regx pour les caractères de nom de fichier valides
exl-id: 876dfc77-078f-4341-b99d-02a453d2e065
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/STMaIE3mkqhAwXB7dz-3pmROSQjqPO5EVC9e2cC0nlE
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 397
ht-degree: 0%

---

# Configurer Regx pour les caractères de nom de fichier valides {#id214BD0550E8}

À partir de la version 3.8 d’AEM Guides, en tant qu’administrateur, vous pouvez définir une liste de caractères spéciaux valides autorisés dans les noms de fichier. Dans les versions antérieures, les utilisateurs étaient autorisés à définir des noms de fichier contenant des caractères spéciaux tels que `@`, `$`, `>`, etc. Ces caractères spéciaux entraînaient des problèmes lors de l&#39;ouverture de rubriques à partir du tableau de bord de plan DITA ou du clic sur le lien de la rubrique dans la table des matières, ce qui empêchait souvent l&#39;ouverture de la page en raison de caractères spéciaux dans l&#39;URL.

En utilisant la configuration qui vous permet de définir une regx pour les caractères de nom de fichier valides, vous avez un contrôle total sur la manière dont les fichiers sont nommés en interne dans le système. Vous pouvez définir une liste de caractères spéciaux autorisés dans les noms de fichier. Par défaut, la configuration du nom de fichier valide contient « `a-z A-Z 0-9 - _` ». Lors de la création d’un fichier, vous pouvez avoir n’importe quel caractère spécial dans le titre du fichier, mais en interne, il sera remplacé par « `-` » dans le nom du fichier. Par exemple, si le titre du fichier est « Introduction 1 » ou « Introduction@1 », le nom de fichier correspondant généré pour ces deux cas est « Introduction-1 ».

Lorsque vous définissez une liste de caractères valides, n&#39;oubliez pas que ces caractères « `*/:[\]|#%{}?&<>"/+` » seront toujours remplacés par un « `-` ».

Si vous ne configurez pas la liste de caractères spéciaux valide, le processus de création de fichier peut vous donner des résultats inattendus. Pour éviter de telles erreurs, il est vivement recommandé d’effectuer cette modification de configuration immédiatement après la mise à niveau de votre build vers la version 3.8.

Pour configurer regx pour des caractères \(ou autorisés\) valides dans les noms de fichier, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot *com.adobe.fmdita.config.ConfigManager* et cliquez dessus.

1. Dans la propriété **Regex pour les caractères valides**, assurez-vous que la propriété est définie sur \[-a-zA-Z0-9\_\]. Vous pouvez ajouter d’autres caractères à cette liste. Toutefois, elle doit comporter ces caractères de base et la liste doit commencer par un trait d’union « - ».

   >[!NOTE]
   >
   > Cette propriété s’applique uniquement aux noms de fichier, et non aux noms de dossier.

1. Cliquez sur **Enregistrer**.


>[!NOTE]
>
> Tout comme la liste des caractères de nom de fichier valides, vous pouvez également spécifier une liste de caractères de nom de fichier valide pour la sortie du site AEM. Pour plus d’informations, voir [Configurer des noms de fichier valides pour la sortie de site AEM](conf-file-names-valid-regx-aem-site-output.md#).

**Rubrique parente :**[ Configurer les noms de fichier](conf-file-names.md)
