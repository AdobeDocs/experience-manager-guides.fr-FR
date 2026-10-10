---
title: Configuration de caractères spéciaux supplémentaires dans la barre d’outils de l’éditeur
description: Découvrez comment configurer des caractères spéciaux supplémentaires dans l’éditeur d’AEM Guides.
feature: Web Editor
role: User
exl-id: 4007eb03-c100-4892-b293-f22b3f0082e2
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
subfeature_v2:
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 0%
---
# Comment configurer des caractères spéciaux supplémentaires dans la barre d’outils de l’éditeur pour On-Premise

Il existe une option de raccourci dans la barre d’outils de l’éditeur web pour permettre à l’auteur d’insérer déjà les caractères spéciaux.
Vous pouvez voir la même chose dans la capture d’écran ci-dessous :

![Caractères spéciaux](assets/special-chars.png)


Cette liste de caractères peut être configurée ici. Si vous devez y ajouter d’autres caractères, procédez comme suit :

+ Connectez-vous à AEM et ouvrez le mode CRXDE Lite .

+ Créez le fichier symbols.json à l’emplacement suivant : &#39;/apps/fmdita/xmleditor/&#39; (Vous pouvez copier le fichier par défaut depuis - &#39;/libs/fmdita/clientlibs/clientlibs/xmleditor/symbols.json&#39; location)

+ Ajoutez la définition de caractères spéciaux dans le fichier symbols.json en tant que :

```
{
      "label": "Logical Symbols",
      "items": [
        {
          "name": "≥",
          "title": "Greater-Than or Equal To"
        },
        {
          "name": "≤",
          "title": "Smaller-Than or Equal To"
        }
      ]
}
```

La structure du fichier symbols.json est expliquée ci-dessous :

+ « label » : « Symboles logiques » : permet de spécifier la catégorie des caractères spéciaux. Dans le fragment de code, une catégorie portant le nom « Symbole logique » est définie.

+ « items » : définit l&#39;ensemble des caractères spéciaux de la catégorie.

+ « name »: « ≥ », « title »: « Greater-Than or Equal To »: C&#39;est la définition du caractère spécial. Il commence par le libellé « nom », qui ne doit pas être modifié. Le nom est suivi du caractère spécial. Le « titre » est le nom ou le titre du caractère spécial qui s’affiche en tant qu’info-bulle pour ce caractère spécial.

Vous pouvez définir plusieurs définitions de caractères spéciaux au sein d’une catégorie.

Vous ajouterez ainsi une autre catégorie dans la boîte de dialogue des caractères spéciaux :

![Catégorie de symbole spécial](assets/special-char-category.png)

![Insérer un caractère spécial](assets/insert-special-char.png)

>[!MORELIKETHIS]
>
>+ [ Guide d’installation et de configuration ](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-6/XML-Documentation-for-Adobe-Experience-Manager_Installation-Configuration-Guide_EN.pdf)
