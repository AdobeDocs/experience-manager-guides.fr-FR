---
title: Configurer la politique de sécurité du contenu pour la prévisualisation SCORM
description: Découvrez comment configurer la politique de sécurité du contenu pour l’aperçu SCORM à l’aide d’une variable d’environnement dans Cloud Manager
feature: Authoring
role: User
source-git-commit: 730fe6021aa20aa2b57801807da0f471f84a7718
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 3%

---


# Configurer la politique de sécurité du contenu (CSP) pour l’aperçu SCORM

L’aperçu Experience Manager Guides SCORM est géré par le biais d’une variable d’environnement dédiée qui régit la politique de sécurité du contenu (CSP) appliquée à l’expérience d’aperçu. Une fois le paramètre activé, les administrateurs et administratrices peuvent l’étendre en ajoutant d’autres sources approuvées. Ces sources peuvent inclure des scripts, des styles, des polices, des images, des médias, des images, etc., nécessaires pour que les packages SCORM chargent et effectuent correctement le rendu des aperçus dans Experience Manager Guides.

Cet article explique comment ajouter et configurer la variable d’environnement dans Cloud Manager, répartit les fonctions de chaque champ dans la valeur JSON et montre comment mettre à jour la valeur ultérieurement si vos besoins changent.

## Champs de configuration

La variable accepte `GUIDES_SCORM_PREVIEW_CONFIG` l’objet JSON comme valeur. Chaque valeur contrôle un aspect spécifique de la CSP appliquée lors de la prévisualisation SCORM :

| Champs | Type | Description |
|---|---|---|
| `CSP_ENABLED` | Booléen | Active (`true`) ou désactive (`false`) l’application de la CSP pour l’aperçu SCORM. |
| `ALLOW_UNSAFE_EVAL` | Booléen | Autorise l’utilisation de `eval()` et de méthodes d’évaluation JavaScript non sécurisées similaires lorsqu’elles sont définies sur `true`. |
| `ADDITIONAL_SCRIPT_SRC` | Tableau | Autres sources approuvées autorisées à servir JavaScript. |
| `ADDITIONAL_STYLE_SRC` | Tableau | Autres sources approuvées autorisées à servir des feuilles de style. |
| `ADDITIONAL_FONT_SRC` | Tableau | Autres sources approuvées autorisées à diffuser des polices. |
| `ADDITIONAL_FRAME_SRC` | Tableau | Le chargement d’autres sources approuvées dans des éléments `<iframe>` est autorisé. |
| `ADDITIONAL_IMG_SRC` | Tableau | Autres sources approuvées autorisées à diffuser des images. |
| `ADDITIONAL_MEDIA_SRC` | Tableau | Autres sources approuvées autorisées à diffuser du contenu audio/vidéo. |
| `ADDITIONAL_WORKER_SRC` | Tableau | D’autres sources approuvées ont été autorisées pour les programmes de travail web. |
| `ADDITIONAL_CONNECT_SRC` | Tableau | Autres sources approuvées auxquelles l’aperçu peut se connecter (par exemple, appels XHR/fetch). |
| `ADDITIONAL_MANIFEST_SRC` | Tableau | Autres sources approuvées autorisées à servir des manifestes d’applications web. |
| `ADDITIONAL_OBJECT_SRC` | Tableau | Autres sources approuvées pouvant être chargées via `<object>`, `<embed>` ou `<applet>`. |


## Valeurs par défaut des champs de configuration

```json
{
  "CSP_ENABLED": true,
  "ALLOW_UNSAFE_EVAL": false,
  "ADDITIONAL_STYLE_SRC": ["https://fonts.googleapis.com"],
  "ADDITIONAL_FONT_SRC": ["https://fonts.gstatic.com"],
  "ADDITIONAL_FRAME_SRC": ["https://www.youtube-nocookie.com", "https://www.youtube.com"],
  "ADDITIONAL_SCRIPT_SRC": [],
  "ADDITIONAL_WORKER_SRC": [],
  "ADDITIONAL_IMG_SRC": [],
  "ADDITIONAL_MEDIA_SRC": [],
  "ADDITIONAL_CONNECT_SRC": [],
  "ADDITIONAL_MANIFEST_SRC": [],
  "ADDITIONAL_OBJECT_SRC": []
}
```

Selon vos besoins, il n’est pas nécessaire de renseigner chaque valeur ; laissez n’importe quel type de source comme un tableau vide si vous n’avez pas besoin d’autoriser d’autres origines pour celui-ci.

>[!NOTE]
>
> Si vous souhaitez désactiver l’application des CSP pour l’aperçu SCORM, définissez `"CSP_ENABLED": false` dans la valeur JSON.

## Ajouter la variable dans Cloud Manager

1. Connectez-vous à Cloud Manager et sélectionnez l’environnement dans lequel vous souhaitez appliquer la configuration.
2. Accédez à l’onglet **Configuration** de l’environnement.
3. Sélectionnez **Ajouter/Mettre à jour** pour ajouter une variable d’environnement.

   ![Ajout d’une nouvelle variable au ](assets/add-new-variable.png){width="650"} Cloud Manager

4. Saisissez le nom de la variable (`GUIDES_SCORM_PREVIEW_CONFIG`) dans le champ **Nom**.

   ![Ajout du nom de la variable dans le champ du nom](assets/variable-name.png){width="650"}

5. Saisissez votre configuration JSON complète, y compris la liste autorisée source de vos besoins de cours, dans le champ **Valeur**.
6. Sélectionnez le **Service appliqué** pour choisir si la variable doit s’appliquer à **Auteur**, **Publication** ou aux deux. Pour la création Experience Manager Guides, sélectionnez **Auteur**.
7. Sélectionnez **Variable** dans le champ **Type**.
8. Sélectionnez **Ajouter**.
9. Sélectionnez **Enregistrer**.

   ![Enregistrement de la variable en vue de son application à l’environnement](assets/save.png){width="650"}

Une fois l’enregistrement effectué, Cloud Manager applique la configuration à l’environnement sélectionné. La propagation prend généralement entre 10 et 12 minutes, ce qui laisse le temps à la mise à jour de se terminer. Une fois cette opération terminée, la nouvelle configuration sera active pour l’aperçu SCORM sur cet environnement.

## Mise à jour des valeurs de variable

Si vos exigences changent, vous pouvez à tout moment consulter à nouveau la variable `GUIDES_SCORM_PREVIEW_CONFIG` à partir du même onglet Configuration dans Cloud Manager. Recherchez la variable existante et sélectionnez son option **Ajouter/Mettre à jour** pour l’ouvrir afin de la modifier, puis révisez la valeur si nécessaire.