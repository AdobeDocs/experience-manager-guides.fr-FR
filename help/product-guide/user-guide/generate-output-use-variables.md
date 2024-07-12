---
title: Utilisez des variables pour définir le chemin de destination, le nom du site ou le nom de fichier.
description: Découvrez comment utiliser les variables pour définir les options Chemin de destination, Nom du site ou Nom de fichier. Variables prêtes à l’emploi connues prises en charge dans AEM Guides.
exl-id: 3396c971-6332-45b5-b2ef-b07f0abf97f7
feature: Publishing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Utilisez des variables pour définir le chemin de destination, le nom du site ou le nom de fichier.


Lors de la génération de sorties dans AEM site ou les PDF, vous pouvez utiliser des variables pour définir les options Chemin de destination, AEM Nom de site ou Nom de fichier du PDF. Vous pouvez utiliser une seule ou une combinaison de variables pour définir ces options.

Le tableau suivant répertorie les variables prises en charge par défaut :

| Variable | Chemin de destination final | Exemple |
| --- | --- | --- |
| `${map_filename}` | Utilise le nom des fichiers de mappage DITA pour créer le chemin de destination. | **Nom de fichier de mappage DITA** :<br>`AEMGuides.ditamap`<br><br>**Chemin de destination** configuré comme suit :<br>`/content/output/sites/${map_filename}`<br><br>**Emplacement de sortie final**:<br>`/content/output/sites/aemGuides/AEMGuides.html` |
| `${map_title}` | Utilise le titre du mappage DITA pour créer le chemin de destination. | **Nom de fichier de mappage DITA** :<br>`AEMGuides.ditamap`<br><br>**Titre de mappage DITA** :<br>`AEMGuides`<br><br>**Chemin de destination** configuré comme suit :<br>`/content/output/sites/${map_title}`<br><br>**Emplacement de sortie final** :<br>`/content/output/sites/AEMGuides/AEMGuides.html` |
| `${preset_name}` | Utilise le nom du paramètre prédéfini de sortie pour créer le chemin de destination. | **Nom du paramètre prédéfini de sortie** :<br>`AEM Guides PDF Output`<br><br>**Nom du fichier de mappage DITA** :<br>`SampleDita.ditamap`<br><br>**Chemin de destination** configuré comme suit :<br>`/content/output/sites/${preset_name}`<br><br>**Emplacement de sortie final** :<br>`/content/output/sites/AEM Guides PDF Output/SampleDita.html` |
| `${language_code}` | Utilise le code de langue où se trouve le fichier de mappage pour créer le chemin d’accès de destination. | **Nom du fichier de mappage DITA** :<br>`SampleDita.ditamap`<br><br>**Chemin du fichier de mappage DITA** :<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Chemin de destination** configuré comme suit :<br>`/content/output/sites/${language_code}`<br><br>**Emplacement de sortie final** :<br>`/content/output/sites/en/SampleDita.html` |
| `${map_parentpath}` | Utilise le chemin d’accès complet du fichier de mappage pour créer le chemin d’accès de destination.<br><br>**Remarque** : Cette variable ne peut pas être utilisée pour spécifier le nom de site AEM ou le nom de fichier du PDF. | **Nom de fichier de mappage DITA** :<br>`SampleDita.ditamap`<br><br>**Chemin du fichier de mappage DITA** :<br>`/content/dam/projects/AEM-Guides/en/user-guide`/<br><br>**Chemin de destination** configuré comme suit :<br>`/content/output/sites/${map_parentpath}`<br><br>**Emplacement de sortie final**:<br>`/content/output/sites/content/dam/projects/AEM-Guides/en/user-guide/SampleDita.html` |
| `${path_after_langfolder}` | Utilise le chemin d’accès du fichier map après le dossier language pour créer le chemin d’accès de destination.<br><br>**Remarque** : Cette variable ne peut pas être utilisée pour spécifier le nom de site AEM ou le nom de fichier du PDF. | **Nom du fichier de mappage DITA** :<br>`SampleDita.ditamap`<br><br>**Chemin du fichier de mappage DITA** :<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Chemin de destination** configuré comme suit :<br>`/content/output/sites/${path\_after\_langfolder}`<br><br>**Emplacement de sortie final** :<br>`/content/output/sites/user-guide/SampleDita.html` |
| `${system_date}` | Utilise la date courante du serveur pour créer le chemin de destination. | **Nom de fichier de mappage DITA** : <br> `SampleDita.ditamap` <br><br> **Chemin du fichier de mappage DITA :** <br> `/content/dam/projects/AEM-Guides/en/user-guide/` <br><br> **Chemin de destination** configuré comme suit : <br> `/content/output/sites/${system_date}` <br> <br> **Emplacement de sortie final :** <br> /`content/output/sites/08252023/SampleDita.html` |
| `${system_time}` | Utilise l’heure actuelle du serveur pour créer le chemin de destination. | **Nom du fichier de mappage DITA :** <br>`SampleDita.ditamap` <br> <br> **Chemin du fichier de mappage DITA :** <br>`/content/dam/projects/AEM-Guides/en/user-guide/` <br><Br>**Chemin de destination** configuré comme suit : <br> `/content/output/sites/${system_time}`<br><br>**Emplacement de sortie final :**<br>`/content/output/sites/055612/SampleDita.html` |

En outre, vous pouvez également utiliser les métadonnées définies pour le mappage DITA ou le fichier bookmap comme variables. Les métadonnées se trouvent sous le noeud `/jcr:content/metadata` du mappage DITA ou du fichier bookmap. Par exemple, l’une des propriétés de métadonnées définies dans le noeud `/jcr:content/metadata` est `dc:title`. Vous pouvez spécifier `${dc:title}` et la valeur de titre est utilisée dans la sortie finale.
**Rubrique parente :**[ Génération de sortie](generate-output.md)
