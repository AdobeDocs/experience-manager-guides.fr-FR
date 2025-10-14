---
title: Traduction de contenu dans AEM Guides
description: Découvrir comment traduire le contenu
exl-id: 0d3a909c-3499-4ef4-b033-02e412dae959
feature: Translation
role: Admin
level: Experienced
source-git-commit: ea3083542e955a56c27cd833600370a7962c6b8d
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 12%

---

# Traduction du contenu {#id181GB0400UI}

Automatisez la traduction du contenu des pages, des ressources et du contenu créé par les utilisateurs pour créer et tenir à jour des sites web multilingues. Pour automatiser les workflows de traduction, vous intégrez des fournisseurs de services de traduction à AEM et vous créez des projets pour traduire le contenu dans plusieurs langues. AEM prend en charge les workflows de traduction humaine et automatique.

- Traduction humaine : le contenu est envoyé à votre fournisseur de traduction et traduit par des traducteurs professionnels. Une fois la traduction terminée, le contenu traduit est renvoyé et importé dans AEM. Lorsque votre fournisseur de traduction est intégré à AEM, le contenu est automatiquement échangé entre AEM et le fournisseur de traduction

- Traduction automatique : le service de traduction automatique traduit immédiatement votre contenu


La traduction du contenu implique les étapes suivantes :

1. Connectez AEM à votre [fournisseur de services de traduction](https://helpx.adobe.com/fr/experience-manager/6-5/sites/administering/using/tc-tic.html#ConnectingtoaTranslationServiceProvider) et créez [&#x200B; configurations de structure d’intégration de traduction](https://helpx.adobe.com/fr/experience-manager/6-5/sites/administering/using/tc-tic.html#CreatingaTranslationIntegrationConfiguration).

1. Associez les pages de votre gabarit de langue au [service de traduction et aux configurations de structure](https://helpx.adobe.com/fr/experience-manager/6-5/sites/administering/using/tc-tic.html#ConfiguringPagesforTranslation).

1. Identifiez le type de [contenu à traduire](https://experienceleague.adobe.com/docs/experience-manager-65/administering/introduction/tc-rules.html?lang=fr).

1. [Préparez le contenu à traduire](https://helpx.adobe.com/fr/experience-manager/6-5/sites/administering/using/tc-prep.html) en créant le gabarit de langue et les pages racine des copies de langue.

1. Créez des [projets de traduction](https://experienceleague.adobe.com/docs/experience-manager-65/administering/introduction/tc-manage.html?lang=fr) pour collecter le contenu à traduire et préparer le processus de traduction.

1. Utilisez les projets de traduction pour [gérer le processus de traduction &#x200B;](https://experienceleague.adobe.com/docs/experience-manager-65/administering/introduction/tc-manage.html?lang=fr) contenu.


Lorsque votre fournisseur de services de traduction ne fournit pas de connecteur pour l’intégration à AEM, AEM prend en charge l’exportation et l’importation manuelles du contenu traduit au format XML.

>[!TIP]
>
> Voir la section *Traduction* dans le guide des bonnes pratiques pour connaître les bonnes pratiques en matière de traduction de contenu.

## Configuration de l&#39;onglet Traduction dans le tableau de bord du plan DITA

L’option Masquer l’onglet de traduction n’est pas activée par défaut et vous devez l’activer à partir de configMgr. Pour masquer l&#39;onglet Traduction dans le tableau de bord du plan DITA, procédez comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.config.ConfigManager** et cliquez dessus.

1. Sélectionnez l’option **Masquer l’onglet de traduction** pour masquer l’onglet de traduction dans le tableau de bord de mappage.

   >[!NOTE]
   >
   > Cette propriété est désactivée par défaut et l’onglet Traduction est disponible dans le tableau de bord des cartes.

1. Cliquez sur **Enregistrer**.

## Configuration d’un workflow de traduction basé sur des composants

Si le connecteur du fournisseur de traduction ne prend pas en charge le contenu DITA, le workflow de traduction basé sur les composants doit être activé. Une fois activé, le contenu traduisible est envoyé en tant que métadonnées de ressource. Cependant, le connecteur doit prendre en charge la traduction des métadonnées de ressource pour que ce workflow fonctionne.

En fonction du workflow de traduction utilisé dans votre configuration, l’option de workflow de traduction basé sur les composants doit être configurée comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.config.ConfigManager** et cliquez dessus.

1. Configurez l&#39;option **Workflow de traduction DITA basé sur les composants** en fonction de votre configuration :

   - Si vous utilisez la traduction humaine, désactivez l’option *Désactiver* **le workflow de traduction basé sur les composants**.

   - Si vous utilisez la traduction automatique, sélectionnez l’option *Activer* le **Workflow de traduction basé sur les composants**.

   >[!NOTE]
   >
   > Si vous utilisez le connecteur de traduction, vérifiez que vous avez configuré le connecteur comme décrit dans la rubrique *[Configuration de la structure d’intégration de traduction &#x200B;](https://helpx.adobe.com/fr/experience-manager/6-5/sites/administering/using/tc-tic.html)* de la documentation AEM.

1. Cliquez sur **Enregistrer**.

>[!IMPORTANT]
>
> Après avoir configuré les configurations de traduction, assurez-vous de configurer la configuration cloud appropriée sur les dossiers de langue.

## Configuration de l’ancien workflow de traduction

>[!IMPORTANT]
> 
> Il est recommandé d’utiliser le dernier workflow de traduction, disponible dans AEM Guides 4.6.0 et les versions ultérieures, pour des performances améliorées. Cependant, si vous avez activé une personnalisation dans le processus de traduction et qu’elle est affectée par le nouveau workflow, pensez à revenir à l’ancien workflow de traduction comme solution.



Par défaut, l’option de workflow de traduction héritée est désactivée. Vous pouvez configurer cette option en procédant comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.config.ConfigManager** et cliquez dessus.

1. Configurez l’option de workflow de traduction héritée en fonction de votre configuration :

   - (*Par défaut*) Si vous souhaitez utiliser le dernier workflow de traduction, désactivez l’option **Exécuter le workflow de traduction hérité**.
   - Si vous souhaitez utiliser le processus de traduction hérité, activez l’option **Exécuter le processus de traduction hérité**.

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


## Configuration du post-traitement des copies de langue temporaires

Lorsque vous lancez le workflow de traduction, le système crée des copies de langue temporaires du contenu source. Vous pouvez choisir d’activer ou de désactiver l’opération de post-traitement sur ces fichiers temporaires. Lors de l’opération de post-traitement, les références entrantes et sortantes des fichiers sont résolues, l’état du document est défini, ainsi que d’autres opérations. Si vous activez le post-traitement sur ces fichiers temporaires, le processus de traduction peut prendre plus de temps. Par conséquent, il est recommandé de conserver l’option de post-traitement désactivée.

Par défaut, l’option post-traitement des fichiers temporaires est désactivée. Vous pouvez configurer cette option en procédant comme suit :

1. Ouvrez la page de configuration de la console web Adobe Experience Manager .

   L’URL par défaut pour accéder à la page de configuration est :

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Recherchez et cliquez sur le lot **com.adobe.fmdita.config.ConfigManager** et cliquez dessus.

1. Configurez l’option **Post-traitement des copies de langue** en fonction de votre configuration :

   - \(*Par défaut*\) Si vous ne souhaitez pas exécuter l’opération de post-traitement sur les fichiers temporaires, *Désactivez* l’option **Post-traitement des copies de langue**.

   - Si vous souhaitez exécuter l’opération de post-traitement sur les fichiers temporaires, *Activez* l’option **Post-traitement des copies de langue**.

1. Cliquez sur **Enregistrer**.
