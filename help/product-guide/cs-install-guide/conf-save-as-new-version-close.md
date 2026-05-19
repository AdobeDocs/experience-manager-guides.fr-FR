---
title: Configurer l'invite pour enregistrer en tant que nouvelle version à la fermeture
description: Découvrez comment Configurer une invite pour enregistrer en tant que nouvelle version à la fermeture
exl-id: 9029b671-8ff8-45eb-b27e-ab89bd09e7ed
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/t42Tf7hh9Sm-yu05OGGmEx-hF1gYRkDeCnCiEEoqNDE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 185
ht-degree: 1%

---

# Configurer l&#39;invite pour enregistrer en tant que nouvelle version à la fermeture {#id222HBI00XXA}

Lorsque l’utilisateur tente de fermer un fichier ouvert dans l’éditeur web à l’aide du bouton **Fermer** de l’onglet du fichier ou de l’option **Fermer** du menu Options, une boîte de dialogue s’affiche si le fichier contient des données non enregistrées ou une version non enregistrée. L’utilisateur est invité à enregistrer le fichier en tant que nouvelle version si celle-ci n’est pas enregistrée.

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour configurer une invite d’enregistrement en tant que nouvelle version à la fermeture :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.savenewversion` | Booléen \( true/ false\). <br>  **Valeur par défaut** : true |

Lorsque cette configuration est activée, la case **Enregistrer en tant que nouvelle version** est cochée par défaut dans la boîte de dialogue.

Pour plus d’informations, voir la section *Scénarios de fermeture et d’enregistrement de fichier* dans le guide Utilisation d’Adobe Experience Manager Guides as a Cloud Service .

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](conf-web-editor.md)
