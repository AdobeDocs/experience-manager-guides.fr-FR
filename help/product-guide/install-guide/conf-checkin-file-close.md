---
title: Configurer l'invite pour archiver un fichier à la fermeture
description: Découvrez comment Configurer une invite pour archiver un fichier à la fermeture
exl-id: d184c97f-8405-4bcd-963d-635f17584897
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/mK01xE-ysqIXm9YL5xkvp1dz1-3hGr63kvt-cePEHSA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 196
ht-degree: 1%

---

# Configurer l&#39;invite pour archiver un fichier à la fermeture {#id222HC040PE8}

Lorsque l’utilisateur tente de fermer un fichier ouvert dans l’éditeur à l’aide du bouton **Fermer** de l’onglet du fichier ou de l’option **Fermer** du menu Options, une boîte de dialogue s’affiche si le fichier contient des données non enregistrées ou une version non enregistrée. L’utilisateur est invité à déverrouiller le fichier s’il est verrouillé.

La case **Déverrouiller le fichier** n’est pas cochée par défaut et vous devez l’activer à partir de configMgr. Effectuez les étapes suivantes pour activer l’option par défaut dans l’éditeur :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** et cliquez dessus.

1. Sélectionnez l’option **Demander l’enregistrement à la fermeture**.

1. Cliquez sur **Enregistrer**.


Lorsque cette configuration est activée, la case **Déverrouiller le fichier** est cochée par défaut dans la boîte de dialogue.

Pour plus d’informations, voir la section *Scénarios de fermeture et d’enregistrement de fichier* dans le guide Utilisation d’Adobe Experience Manager Guides as a Cloud Service .

**Rubrique parente :**[ Personnaliser l’éditeur](conf-web-editor.md)
