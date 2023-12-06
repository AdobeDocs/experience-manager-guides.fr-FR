---
title: Configuration d’une invite pour l’enregistrement en tant que nouvelle version à la fermeture
description: Découvrez comment configurer une invite pour enregistrer en tant que nouvelle version à la fermeture
exl-id: 9029b671-8ff8-45eb-b27e-ab89bd09e7ed
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 1%

---

# Configuration d’une invite pour l’enregistrement en tant que nouvelle version à la fermeture {#id222HBI00XXA}

Lorsque l’utilisateur tente de fermer un fichier ouvert dans l’éditeur Web à l’aide de la fonction **Fermer** dans l’onglet du fichier ou dans la fonction **Fermer** dans le menu Options, une boîte de dialogue s’affiche si le fichier contient des données non enregistrées ou une version non enregistrée. L’utilisateur est invité à enregistrer le fichier en tant que nouvelle version si la version n’est pas enregistrée.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer une invite d’enregistrement en tant que nouvelle version à la fermeture :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.savenewversion` | Booléen \( true/ false\). <br>  **Valeur par défaut**: true |

Lorsque cette configuration est activée, la variable **Enregistrer comme nouvelle version** est sélectionnée par défaut dans la boîte de dialogue.

Pour plus d’informations, voir *Fermeture du fichier et enregistrement des scénarios* dans le guide as a Cloud Service Utilisation des guides Adobe Experience Manager .

**Rubrique parente :**[ Personnalisation de l’éditeur web](conf-web-editor.md)
