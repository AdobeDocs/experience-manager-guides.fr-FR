---
title: Traduire le contenu dans AEM Guides
description: Découvrez comment traduire du contenu
exl-id: 0d3a909c-3499-4ef4-b033-02e412dae959
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 14%

---

# Traduction du contenu {#id181GB0400UI}

Automatisez la traduction du contenu des pages, des ressources et du contenu créé par les utilisateurs pour créer et tenir à jour des sites web multilingues. Pour automatiser les workflows de traduction, vous intégrez des fournisseurs de services de traduction à AEM et vous créez des projets pour traduire le contenu dans plusieurs langues. AEM prend en charge les workflows de traduction humaine et automatique.

- Traduction humaine : le contenu est envoyé à votre fournisseur de traduction et traduit par des traducteurs professionnels. Une fois la traduction terminée, le contenu traduit est renvoyé et importé dans AEM. Lorsque votre fournisseur de traduction est intégré à AEM, le contenu est automatiquement échangé entre AEM et le fournisseur de traduction.

- Traduction automatique : le service de traduction automatique traduit immédiatement votre contenu.


La traduction du contenu implique les étapes suivantes :

1. Connectez AEM à votre [fournisseur de services de traduction](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConnectingtoaTranslationServiceProvider) et créez [configurations de structure d’intégration de traduction](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#CreatingaTranslationIntegrationConfiguration).

1. Associez les pages de votre gabarit de langue à l’événement [configurations de structure et de service de traduction](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConfiguringPagesforTranslation).

1. Identifier le type de [contenu à traduire](https://experienceleague.adobe.com/docs/experience-manager-65/administering/introduction/tc-rules.html?lang=fr).

1. [Préparez le contenu à traduire](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-prep.html) en créant le gabarit de langue et les pages racine des copies de langue.

1. Créer [projets de traduction](https://experienceleague.adobe.com/docs/experience-manager-65/administering/introduction/tc-manage.html?lang=fr) pour rassembler le contenu à traduire et préparer le processus de traduction.

1. Utilisez les projets de traduction pour [gestion de la traduction du contenu](https://experienceleague.adobe.com/docs/experience-manager-65/administering/introduction/tc-manage.html?lang=fr) processus.


Lorsque votre fournisseur de services de traduction ne fournit pas de connecteur pour l’intégration avec AEM, AEM prend en charge l’exportation et l’importation manuelles de contenu traduit au format XML.

>[!TIP]
>
> Voir *Traduction* Consultez le guide des bonnes pratiques pour connaître les bonnes pratiques en matière de traduction de contenu.

## Configuration de l’onglet Traduction sur le tableau de bord de mappage DITA

L’option Masquer l’onglet Traduction n’est pas activée par défaut et vous devez l’activer à partir de configMgr. Pour masquer l’onglet Traduction sur le tableau de bord de mappage DITA, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le bouton **com.adobe.config.ConfigManager** du lot.

1. Sélectionnez la variable **Masquer l’onglet Traduction** pour masquer l’onglet traduction dans le tableau de bord de la carte.

   >[!NOTE]
   >
   > Cette propriété est désactivée par défaut et l’onglet Traduction est disponible dans le tableau de bord de la carte.

1. Cliquez sur **Enregistrer**.

## Configuration du processus de traduction basé sur des composants

Si le connecteur du fournisseur de traduction ne prend pas en charge le contenu DITA, le processus de traduction basé sur les composants doit être activé. Une fois activé, le contenu traduisible est envoyé en tant que métadonnées de ressource. Toutefois, le connecteur doit prendre en charge la traduction des métadonnées de ressource pour que ce processus fonctionne.

Selon le processus de traduction utilisé dans votre configuration, l’option de processus de traduction basé sur les composants doit être configurée comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le bouton **com.adobe.config.ConfigManager** du lot.

1. Configurez la variable **Processus de traduction DITA basé sur des composants** selon votre configuration :

   - Si vous utilisez la traduction humaine, alors *Désactiver* la valeur **Processus de traduction basé sur des composants** .

   - Si vous utilisez la traduction automatique, alors *Activer* la valeur **Processus de traduction basé sur des composants** .

   >[!NOTE]
   >
   > Si vous utilisez le connecteur de traduction, assurez-vous que vous avez configuré le connecteur comme décrit dans la section *[Configuration de la structure d’intégration de traduction](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html)* dans la documentation d’AEM.

1. Cliquez sur **Enregistrer**.


>[!IMPORTANT]
>
> Après avoir configuré les configurations de traduction, assurez-vous de configurer la configuration cloud appropriée sur les dossiers de langue.

## Configuration du post-traitement des copies de langue temporaires

Lorsque vous lancez le processus de traduction, le système crée des copies de langue temporaires du contenu source. Vous pouvez choisir d’activer ou de désactiver l’opération de post-traitement sur ces fichiers temporaires. Dans l’opération de post-traitement, les références entrantes et sortantes des fichiers sont résolues, l’état du document est défini, ainsi que d’autres opérations. Si vous activez le post-traitement sur ces fichiers temporaires, le processus de traduction peut prendre plus de temps. Par conséquent, il est recommandé de ne pas désactiver l’option de post-traitement.

Par défaut, l’option de post-traitement des fichiers temporaires est désactivée. Vous pouvez configurer cette option en procédant comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le bouton **com.adobe.config.ConfigManager** du lot.

1. Configurez la variable **Copies de langue de post-traitement** selon votre configuration :

   - \(*Par défaut*\) Si vous ne souhaitez pas exécuter l’opération de post-traitement sur les fichiers temporaires, *Désactiver* la valeur **Copies de langue de post-traitement** .

   - Si vous souhaitez exécuter l’opération de post-traitement sur les fichiers temporaires, *Activer* la valeur **Copies de langue de post-traitement** .

1. Cliquez sur **Enregistrer**.
