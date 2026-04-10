---
title: Charger le contenu DITA existant
description: Découvrez comment télécharger du contenu DITA existant dans Experience Manager Guides à l’aide de l’outil WebDAV et de FrameMaker
feature: Migration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 0%

---

# Charger le contenu DITA existant à l&#39;aide de l&#39;outil WebDAV et de FrameMaker for On-Premise

Il est probable que vous disposiez d&#39;un référentiel de contenu DITA existant que vous souhaitez utiliser avec AEM Guides. Pour ce type de contenu existant, vous pouvez utiliser l’une des approches suivantes pour charger en bloc votre contenu dans le référentiel AEM.

- [Utilisation d’un outil WebDAV](#use-a-webdav-tool)
- [Utilisation de FrameMaker](#use-framemaker)

## Utilisation d’un outil WebDAV

Si vous créez vos rubriques et mappages dans un autre éditeur DITA, vous pouvez utiliser n&#39;importe quel outil WebDAV pour charger vos fichiers. La procédure décrite dans cette section utilise WinSCP comme outil WebDAV pour télécharger du contenu.

Effectuez les étapes suivantes pour utiliser WinSCP pour charger des fichiers :

1. Télécharger et installer WinSCP sur votre ordinateur.

1. Lancez l&#39;application WinSCP.

   La boîte de dialogue Connexion s’affiche.

1. Dans la boîte de dialogue Connexion, spécifiez un paramètre Nouveau site en choisissant WebDAV comme **Protocole de fichier** et en fournissant d’autres détails de connexion, tels que :

   - l’URL d’hébergement de votre serveur AEM,

   - le numéro de port `\(default is 4502\)`, et

   - le nom d’utilisateur et le mot de passe pour accéder à votre serveur AEM.

1. Sélectionnez **Connexion**.

   Une fois la connexion établie, le contenu d&#39;AEM Assets s&#39;affiche dans l&#39;interface utilisateur WinSCP. Vous pouvez facilement parcourir, créer, mettre à jour ou supprimer du contenu en utilisant l&#39;explorateur de fichiers WinSCP.

## Télécharger du contenu avec UUID à l’aide d’un outil WebDav {#id201MI0I04Y4}

Vous pouvez utiliser l’une des méthodes suivantes pour charger votre contenu avec l’UUID :

- Glissez-déposez du contenu à partir de votre système local.
- Utilisez le workflow **Créer** \> **Fichiers** à partir de l’interface utilisateur d’AEM Assets.
- Utilisez un outil comme WinSCP.

Si vous utilisez un outil tel que WinSCP, vous pouvez définir l&#39;action à effectuer sur un fichier dupliqué en définissant l&#39;option **Déplacer l&#39;ancien fichier avec le même UUID vers le nouveau dossier** dans configMgr. Cette option définit l’action à effectuer sur un fichier disponible à un autre emplacement du référentiel AEM. Ce paramètre est disponible dans le lot `*com.adobe.fmdita.config.ConfigManager*` de configMgr.

Par défaut, l’option **Déplacer l’ancien fichier avec le même UUID vers le nouveau dossier** est activée. Cela signifie que lorsque le fichier en cours de chargement se trouve dans un autre dossier du référentiel, le fichier existant est déplacé vers l’emplacement actuel et remplacé par le fichier en cours de chargement. Si vous ne sélectionnez pas cette option, le fichier est remplacé à son emplacement existant.

**Remarques supplémentaires sur l’utilisation des fichiers basés sur UUID** :

Lors du déplacement ou de la copie de contenu dans le référentiel AEM, tenez compte des points suivants :

- Lors de la copie d&#39;un ou plusieurs fichiers d&#39;un emplacement à un autre, un nouvel UUID est généré pour les fichiers sans UUID. Cet UUID est ajouté dans les métadonnées du fichier.

- Si un fichier est en conflit ou en double, un nom de fichier unique est généré pour le nouveau fichier copié ou déplacé.

- Deux fichiers ne peuvent pas avoir le même UUID. Un UUID unique est affecté à tous les nouveaux fichiers.


Lors du déplacement ou de la copie de contenu de votre système local vers le référentiel AEM, tenez compte des points suivants :

- Si un fichier est chargé par deux utilisateurs différents en même temps, le fichier qui est traité ultérieurement remplace le fichier précédent. Cependant, une telle pratique est rare et doit être évitée.

- Lorsque vous extrayez du contenu du référentiel AEM et apportez des modifications à votre système local, assurez-vous que le nom du fichier n’est pas modifié au moment du téléchargement du fichier.

## Utilisation de FrameMaker

Adobe FrameMaker s’accompagne d’un puissant connecteur AEM qui vous permet de charger facilement vos documents DITA et autres documents FrameMaker existants `\(.book and .fm\)`dans AEM). Vous pouvez utiliser diverses fonctionnalités de chargement de fichier, telles que le chargement d’un seul fichier ou d’un dossier complet avec ou sans dépendances \(comme les références de contenu, les références croisées et les graphiques\).

Effectuez les étapes suivantes pour utiliser le connecteur AEM FrameMaker afin de charger du contenu :

1. Lancez FrameMaker.

1. Ouvrez la boîte de dialogue **Gestionnaire de connexions**.

   ![](assets/fm-aem-connector.png){width="550" align="left"}

1. Saisissez les informations suivantes pour vous connecter au référentiel AEM :

   - **Nom** : saisissez un nom explicite pour identifier la connexion à votre serveur AEM.
   - **Serveur** : saisissez l’URL et le numéro de port de votre serveur AEM.

   - **Nom d’utilisateur**/**Mot de passe** : saisissez le nom d’utilisateur et le mot de passe pour accéder au serveur AEM.

1. Sélectionnez **Connexion**.

   Une fois la connexion établie, les Assets du référentiel AEM s’affichent dans la fenêtre Gestionnaire de référentiel .

   ![](assets/fm-repo-manager.png){width="550" align="left"}

   Cliquez avec le bouton droit de la souris sur un fichier ou un dossier pour effectuer les opérations associées. Par exemple, si vous cliquez avec le bouton droit de la souris sur un dossier, vous obtenez des options pour charger un fichier , charger un fichier avec des dépendances, charger un dossier entier, etc.






**Rubrique parente :**[ Migrer le contenu existant](migrate-content.md)
