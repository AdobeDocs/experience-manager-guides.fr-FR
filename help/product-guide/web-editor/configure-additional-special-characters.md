---
title: Configuration de caractères spéciaux supplémentaires dans la barre d’outils de l’éditeur web
description: Découvrez comment configurer des caractères spéciaux supplémentaires dans l’éditeur web d’AEM Guides.
feature: Web Editor
role: User
exl-id: 0fbc05a5-a6b0-4f6b-bbc4-8fca03581d90
TQID: https://experienceleague.adobe.com/7InE1R4lpkq7cQ6xptqVIyjG4b-2i9klObtxf2y7Cw8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 265
ht-degree: 0%

---

# Comment configurer des caractères spéciaux supplémentaires dans la barre d’outils de l’éditeur web pour On-Premise

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
>+ [&#x200B; Guide d’installation et de configuration &#x200B;](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-6/XML-Documentation-for-Adobe-Experience-Manager_Installation-Configuration-Guide_EN.pdf)
