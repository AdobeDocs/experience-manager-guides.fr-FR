---
title: Ouvrir la rubrique DITA ou mapper des fichiers dans le même onglet
description: Découvrez comment ouvrir une rubrique DITA ou mapper des fichiers dans le même onglet
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 1%

---

# Ouvrir la rubrique DITA ou mapper des fichiers dans le même onglet {#id223HI0P202H}

Dans certains workflows, lorsque vous cliquez sur un lien d’une rubrique ou d’un fichier de mappage, il s’ouvre dans un nouvel onglet. Cela peut entraîner l’ouverture de nombreux onglets dans votre navigateur, ce qui peut avoir un impact sur votre productivité. Vous pouvez modifier ce comportement d&#39;ouverture d&#39;une rubrique ou d&#39;un fichier de mappage dans un nouvel onglet, et forcer son ouverture dans l&#39;onglet actuel.

Les onglets suivants fournissent des instructions pour ouvrir la rubrique DITA ou mapper un fichier dans le même onglet en fonction de votre configuration Experience Manager Guides : Cloud Service ou On-Premise.

>[!BEGINTABS]

>[!TAB Tab]

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour ouvrir une rubrique ou mapper un fichier dans un nouvel onglet :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinsametab` | Booléen \(true/false\). <br> **Valeur par défaut** : `false` |

>[!TAB  On-Premise ]

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** et cliquez dessus.

1. Sélectionnez l&#39;option **Ouvrir la rubrique/le plan DITA dans le même onglet**.

1. Cliquez sur **Enregistrer**.

>[!ENDTABS]

Ce paramètre affecte les emplacements suivants à partir desquels vous pouvez accéder aux fichiers de rubrique ou de mappage :

- Créer une rubrique DITA \(à la fin du workflow, lorsque vous cliquez sur le bouton **Ouvrir la rubrique**\)

- Créer un plan DITA \(à la fin du workflow, lorsque vous cliquez sur le bouton **Ouvrir le plan**\)

- Onglet Rubriques dans la console de plan DITA

- Onglet Lignes de base dans la console de plan DITA

- Onglet Rapports dans la console de mappage DITA

**Rubrique parente :**&#x200B;[&#x200B; Personnaliser l’éditeur web](customize-overview.md)
