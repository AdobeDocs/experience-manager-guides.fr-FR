---
title: Traduire le contenu dans AEM Guides
description: Découvrez comment traduire du contenu
exl-id: 0d3a909c-3499-4ef4-b033-02e412dae959
feature: Translation
role: Admin
level: Experienced
source-git-commit: bc2348ae3342addf9ab05a3e3898fa485dba9bcf
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 14%

---

# Traduction du contenu {#id181GB0400UI}

Automatisez la traduction du contenu des pages, des ressources et du contenu créé par les utilisateurs pour créer et tenir à jour des sites web multilingues. Pour automatiser les workflows de traduction, vous intégrez des fournisseurs de services de traduction à AEM et vous créez des projets pour traduire le contenu dans plusieurs langues. AEM prend en charge les workflows de traduction humaine et automatique.

- Traduction humaine : le contenu est envoyé à votre fournisseur de traduction et traduit par des traducteurs professionnels. Une fois la traduction terminée, le contenu traduit est renvoyé et importé dans AEM. Lorsque votre fournisseur de traduction est intégré à AEM, le contenu est automatiquement échangé entre AEM et le fournisseur de traduction.

- Traduction automatique : le service de traduction automatique traduit immédiatement votre contenu.


La traduction du contenu implique les étapes suivantes :

1. Connectez AEM à votre [fournisseur de services de traduction](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConnectingtoaTranslationServiceProvider) et créez des [ configurations de structure d’intégration de traduction](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#CreatingaTranslationIntegrationConfiguration).

1. Associez les pages de votre gabarit de langue aux [ configurations de structure et de service de traduction](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConfiguringPagesforTranslation).

1. Identifiez le type de [contenu à traduire](https://experienceleague.adobe.com/docs/experience-manager-65/administering/introduction/tc-rules.html?lang=fr).

1. [Préparez le contenu à traduire](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-prep.html) en créant le gabarit de langue et les pages racine des copies de langue.

1. Créez des [projets de traduction](https://experienceleague.adobe.com/docs/experience-manager-65/administering/introduction/tc-manage.html?lang=fr) pour rassembler le contenu à traduire et préparer le processus de traduction.

1. Utilisez les projets de traduction pour [gérer le processus de traduction de contenu](https://experienceleague.adobe.com/docs/experience-manager-65/administering/introduction/tc-manage.html?lang=fr).


Lorsque votre fournisseur de services de traduction ne fournit pas de connecteur pour l’intégration avec AEM, AEM prend en charge l’exportation et l’importation manuelles de contenu traduit au format XML.

>[!TIP]
>
> Consultez la section *Traduction* du guide Bonnes pratiques pour connaître les bonnes pratiques en matière de traduction de contenu.

## Configuration de l’onglet Traduction sur le tableau de bord de mappage DITA

L’option Masquer l’onglet Traduction n’est pas activée par défaut et vous devez l’activer à partir de configMgr. Pour masquer l’onglet Traduction sur le tableau de bord de mappage DITA, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L&#39;URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.config.ConfigManager**.

1. Sélectionnez l’option **Masquer l’onglet Traduction** pour masquer l’onglet Traduction dans le tableau de bord de la carte.

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

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.config.ConfigManager**.

1. Configurez l’option **Workflow de traduction DITA basé sur les composants** en fonction de votre configuration :

   - Si vous utilisez la traduction humaine, alors *Désactivez* l’option **Workflow de traduction basé sur les composants** .

   - Si vous utilisez la traduction automatique, *Activez* l’option **Workflow de traduction basé sur les composants** .

   >[!NOTE]
   >
   > Si vous utilisez le connecteur de traduction, assurez-vous d’avoir configuré le connecteur comme décrit dans la rubrique *[Configuration de la structure d’intégration de traduction](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html)* de la documentation d’AEM.

1. Cliquez sur **Enregistrer**.

<!---

This was added for 2406 CS IG

## Configure the legacy translation workflow 

It is recommended that you use the latest translation workflow, which provides enhanced performance. However, you can configure the legacy translation workflow if necessary.

Based on the translation workflow used in your setup, provide the following (property) details to configure the legacy translation workflow: the component-based translation workflow option should be configured as follows:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ! Add the syntax of http as given in previous config

    Note: Configure htttp code as given in previous sample
    

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.



1.  Configure the **Run legacy translation workflow** option as per your setup:

    -   If you use the latest translation workflow, then *Disable* \( `false`\) the **Run legacy translation workflow** option. The latest translation workflow is enabled by default. <br> 

    -   If you use the legacy translation, then *Enable \( `true`\)* the **Run legacy translation workflow** option.

1.  Click **Save**.


--->
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

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.config.ConfigManager**.

1. Configurez l’option **Copies de langue de processus Post** en fonction de votre configuration :

   - \(*Par défaut*\) Si vous ne souhaitez pas exécuter l’opération de post-traitement sur les fichiers temporaires, *Désactivez* l’option **Copies de langue de processus Post**.

   - Si vous souhaitez exécuter l’opération de post-traitement sur les fichiers temporaires, alors *Activez* l’option **Copies de langue de processus Post** .

1. Cliquez sur **Enregistrer**.
