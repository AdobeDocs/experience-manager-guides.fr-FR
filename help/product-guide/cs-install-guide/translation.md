---
title: Traduction du contenu
description: Découvrir comment traduire le contenu
exl-id: 5af78233-343e-47ba-b60c-b7f4789e2406
feature: Translation
role: Admin
level: Experienced
source-git-commit: ea3083542e955a56c27cd833600370a7962c6b8d
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 13%

---

# Traduction du contenu {#id181GB0400UI}

Automatisez la traduction du contenu des pages, des ressources et du contenu créé par les utilisateurs pour créer et tenir à jour des sites web multilingues. Pour automatiser les workflows de traduction, vous intégrez des fournisseurs de services de traduction à AEM et vous créez des projets pour traduire le contenu dans plusieurs langues. AEM prend en charge les workflows de traduction humaine et automatique.

- Traduction humaine : le contenu est envoyé à votre fournisseur de traduction et traduit par des traducteurs professionnels. Une fois la traduction terminée, le contenu traduit est renvoyé et importé dans AEM. Lorsque votre fournisseur de traduction est intégré à AEM, le contenu est automatiquement échangé entre AEM et le fournisseur de traduction

- Traduction automatique : le service de traduction automatique traduit immédiatement votre contenu


La traduction du contenu implique les étapes suivantes :

1. Connectez AEM à votre [fournisseur de services de traduction](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) et créez des configurations de structure d’intégration de traduction.

1. Associez les pages de votre gabarit de langue au service de traduction et aux configurations de structure.

1. Identifiez le type de [contenu à traduire](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/rules.html?lang=en).

1. [Préparez le contenu à traduire](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html?lang=en) en créant le gabarit de langue et les pages racine des copies de langue.

1. Créez des [projets de traduction](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en) pour collecter le contenu à traduire et préparer le processus de traduction.

1. Utilisez les projets de traduction pour [gérer le processus de traduction ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en) contenu.


Lorsque votre fournisseur de services de traduction ne fournit pas de connecteur pour l’intégration à AEM, AEM prend en charge l’exportation et l’importation manuelles du contenu traduit au format XML.

>[!TIP]
>
> Voir la section *Traduction* dans le guide des bonnes pratiques pour connaître les bonnes pratiques en matière de traduction de contenu.

## Configuration de l&#39;onglet Traduction dans le tableau de bord du plan DITA

Pour masquer l&#39;onglet Traduction dans le tableau de bord du plan DITA, procédez comme suit :

1. Suivez les instructions fournies dans [Remplacements de la configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration.
1. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer l’onglet Traduction dans le tableau de bord de mappage :

   | PID | Clé de la propriété | Valeur de la propriété |
   |---|------------|--------------|
   | `com.adobe.fmdita.config.ConfigManager` | `tabs.translation` | Boolean \( true/ false\).<br> **Valeur par défaut** : `true` |

   >[!NOTE]
   >
   > Cette configuration est activée par défaut et l’onglet Traduction n’est pas disponible sur le tableau de bord des cartes.


## Configuration d’un workflow de traduction basé sur des composants

Si le connecteur du fournisseur de traduction ne prend pas en charge le contenu DITA, le workflow de traduction basé sur les composants doit être activé. Une fois activé, le contenu traduisible est envoyé en tant que métadonnées de ressource. Cependant, le connecteur doit prendre en charge la traduction des métadonnées de ressource pour que ce workflow fonctionne.

En fonction du workflow de traduction utilisé dans votre configuration, l’option de workflow de traduction basé sur les composants doit être configurée. Suivez les instructions fournies dans [Remplacements de la configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour configurer un workflow de traduction basé sur des composants :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `component.translation` | Booléen : <br> -   Si vous utilisez la traduction humaine, alors *Désactivez* \( `false`\) l’option **Workflow de traduction basé sur les composants**. <br> -   Si vous utilisez la traduction automatique, *Activez \( `true`\)* l’option **Workflow de traduction basé sur les composants**. |



## Configuration de l’ancien workflow de traduction

>[!IMPORTANT]
>
> Il est recommandé d’utiliser le dernier workflow de traduction, disponible dans AEM Guides 2024.06.0 et versions ultérieures, pour des performances améliorées. Cependant, si vous avez activé une personnalisation dans le processus de traduction et qu’elle est affectée par le nouveau workflow, pensez à revenir à l’ancien workflow de traduction comme solution.

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails (propriété) suivants pour configurer l’ancien workflow de traduction :


| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `translation.workflow.version.legacy` | Booléen : <br> - Si vous utilisez le dernier workflow de traduction, *Désactivez* \( `false`\) l’option **Exécuter le workflow de traduction hérité**.  <br> -   Si vous utilisez la traduction héritée, *Activez \( `true`\)* l’option **Exécuter le workflow de traduction hérité**. <br> **Valeur par défaut** : false |




>[!NOTE]
>
> Si vous utilisez le connecteur de traduction, assurez-vous d’avoir configuré le connecteur comme décrit dans la rubrique *[Configuration de la structure d’intégration de traduction ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en)* de la documentation Adobe Experience Manager.

>[!IMPORTANT]
>
> Après avoir configuré les configurations de traduction, assurez-vous de configurer la configuration cloud appropriée sur les dossiers de langue.

## Configuration du post-traitement des copies de langue temporaires

Lorsque vous lancez le workflow de traduction, le système crée des copies de langue temporaires du contenu source. Vous pouvez choisir d’activer ou de désactiver l’opération de post-traitement sur ces fichiers temporaires. Lors de l’opération de post-traitement, les références entrantes et sortantes des fichiers sont résolues, l’état du document est défini, ainsi que d’autres opérations. Si vous activez le post-traitement sur ces fichiers temporaires, le processus de traduction peut prendre plus de temps. Par conséquent, il est recommandé de conserver l’option de post-traitement désactivée.

Suivez les instructions fournies dans [Remplacements de la configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(property\) suivants pour configurer le post-traitement des copies de langue temporaires :

| PID | Clé de la propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `postprocess.temporary.langcopies` | Booléen : <br> -   Si vous ne souhaitez pas exécuter l’opération de post-traitement sur les fichiers temporaires, *Désactivez* \( false\) l’option **Post-traiter les copies de langue**.<br> -   Si vous souhaitez exécuter l’opération de post-traitement sur les fichiers temporaires, *Activez* \( true\) l’option **Post-traitement des copies de langue** <br>. **Valeur par défaut** : false |

