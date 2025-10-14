---
title: Utilisez des variables pour définir les options Chemin de destination, Nom du site ou Nom de fichier
description: Découvrez comment utiliser des variables pour définir les options Chemin de destination, Nom du site ou Nom de fichier. Connaître les variables prêtes à l’emploi prises en charge dans AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: 19d9121f-6b72-445c-a7d9-07f00026b654
source-git-commit: 1426cdaecdd358f06e76908b09330e65997e8452
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Utilisez des variables pour définir les options Chemin de destination, Nom du site ou Nom de fichier


Lors de la génération de sorties dans les fichiers PDF ou de site AEM, vous pouvez utiliser des variables pour définir les options Chemin de destination, Nom du site AEM ou Nom du fichier PDF . Vous pouvez utiliser une seule variable ou une combinaison de variables pour définir ces options.

Le tableau suivant répertorie les variables prêtes à l’emploi prises en charge :

| Variable | Chemin de destination final | Exemple |
| --- | --- | --- |
| `${map_filename}` | Utilise le nom des fichiers DITA map pour créer le chemin de destination. | **Nom du fichier de mappage DITA**:<br>`AEMGuides.ditamap`<br><br>**Chemin de destination** configuré comme : <br>`/content/output/sites/${map_filename}`<br><br>**Emplacement de sortie final**:<br>`/content/output/sites/aemGuides/AEMGuides.html` |
| `${map_title}` | Utilise le titre du plan DITA pour créer le chemin de destination. | **Nom du fichier de mappage DITA**:<br>`AEMGuides.ditamap`<br><br>**Titre de mappage DITA**:<br>`AEMGuides`<br><br>**Chemin de destination** configuré comme :<br>`/content/output/sites/${map_title}`<br><br>**Emplacement de sortie final**:<br>`/content/output/sites/AEMGuides/AEMGuides.html` |
| `${preset_name}` | Utilise le nom du préréglage de sortie pour créer le chemin de destination. | **Nom du paramètre prédéfini de sortie**:<br>`AEM Guides PDF Output`<br><br>**Nom du fichier de mappage DITA**:<br>`SampleDita.ditamap`<br><br>**Chemin de destination** configuré comme :<br>`/content/output/sites/${preset_name}`<br><br>**Emplacement de sortie final**:<br>`/content/output/sites/AEM Guides PDF Output/SampleDita.html` |
| `${language_code}` | Utilise le code de langue dans lequel se trouve le fichier de mappage pour créer le chemin de destination. | **Nom du fichier de mappage DITA**:<br>`SampleDita.ditamap`<br><br>**Chemin d&#39;accès du fichier de mappage DITA**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Chemin de destination** configuré comme : <br>`/content/output/sites/${language_code}`<br><br>**Emplacement de sortie final**:<br>`/content/output/sites/en/SampleDita.html` |
| `${map_parentpath}` | Utilise le chemin d’accès complet du fichier de mappage pour créer le chemin d’accès de destination.<br><br>**Remarque** : cette variable ne peut pas être utilisée pour spécifier le nom du site AEM ou le nom du fichier PDF. | **Nom du fichier de mappage DITA**:<br>`SampleDita.ditamap`<br><br>**Chemin d&#39;accès du fichier de mappage DITA**:<br>`/content/dam/projects/AEM-Guides/en/user-guide`/<br><br>**Chemin de destination** configuré comme : <br>`/content/output/sites/${map_parentpath}`<br><br>**Emplacement de sortie final**:<br>`/content/output/sites/content/dam/projects/AEM-Guides/en/user-guide/SampleDita.html` |
| `${path_after_langfolder}` | Utilise le chemin d’accès du fichier de mappage après le dossier de langue pour créer le chemin d’accès de destination.<br><br>**Remarque** : cette variable ne peut pas être utilisée pour spécifier le nom du site AEM ou le nom du fichier PDF. | **Nom du fichier de mappage DITA**:<br>`SampleDita.ditamap`<br><br>**Chemin d&#39;accès du fichier de mappage DITA**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Chemin de destination** configuré comme : <br>`/content/output/sites/${path\_after\_langfolder}`<br><br>**Emplacement de sortie final**:<br>`/content/output/sites/user-guide/SampleDita.html` |
| `${system_date}` | Utilise la date actuelle du serveur pour créer le chemin de destination. | **Nom de fichier de mappage DITA** : <br> `SampleDita.ditamap` <br><br> **Chemin d&#39;accès du fichier de mappage DITA :** <br> `/content/dam/projects/AEM-Guides/en/user-guide/` <br><br> **Chemin de destination** configuré comme suit : <br> `/content/output/sites/${system_date}` <br> <br> **Emplacement de sortie final :** <br> /`content/output/sites/08252023/SampleDita.html` |
| `${system_time}` | Utilise l’heure actuelle du serveur pour créer le chemin de destination. | **Nom de fichier de mappage DITA :** <br>`SampleDita.ditamap` <br> <br> **Chemin d&#39;accès du fichier de mappage DITA :** <br>`/content/dam/projects/AEM-Guides/en/user-guide/` <br><Br>**Chemin de destination** configuré comme suit : <br> `/content/output/sites/${system_time}`<br><br>**Emplacement de sortie final :**<br>`/content/output/sites/055612/SampleDita.html` |

En outre, vous pouvez également utiliser les métadonnées définies pour le plan DITA ou le fichier de plan de livre comme variables. Les métadonnées se trouvent sous le nœud `/jcr:content/metadata` du fichier de plan DITA ou de bookmap. Par exemple, l’une des propriétés de métadonnées définies dans le nœud `/jcr:content/metadata` est `dc:title`. Vous pouvez indiquer `${dc:title}` et la valeur du titre est utilisée dans la sortie finale.
**Rubrique parente :**&#x200B;[&#x200B; Génération de sortie](generate-output.md)
