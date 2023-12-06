---
title: Traduction du contenu
description: Découvrez comment traduire du contenu
exl-id: 5af78233-343e-47ba-b60c-b7f4789e2406
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 15%

---

# Traduction du contenu {#id181GB0400UI}

Automatisez la traduction du contenu des pages, des ressources et du contenu créé par les utilisateurs pour créer et tenir à jour des sites web multilingues. Pour automatiser les workflows de traduction, vous intégrez des fournisseurs de services de traduction à AEM et vous créez des projets pour traduire le contenu dans plusieurs langues. AEM prend en charge les workflows de traduction humaine et automatique.

- Traduction humaine : le contenu est envoyé à votre fournisseur de traduction et traduit par des traducteurs professionnels. Une fois la traduction terminée, le contenu traduit est renvoyé et importé dans AEM. Lorsque votre fournisseur de traduction est intégré à AEM, le contenu est automatiquement échangé entre AEM et le fournisseur de traduction.

- Traduction automatique : le service de traduction automatique traduit immédiatement votre contenu.


La traduction du contenu implique les étapes suivantes :

1. Connectez AEM à votre [fournisseur de services de traduction](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) et créer des configurations de structure d’intégration de traduction.

1. Associez les pages de votre gabarit de langue aux configurations de structure et de service de traduction.

1. Identifier le type de [contenu à traduire](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/rules.html?lang=en).

1. [Préparez le contenu à traduire](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html?lang=en) en créant le gabarit de langue et les pages racine des copies de langue.

1. Créer [projets de traduction](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en) pour rassembler le contenu à traduire et préparer le processus de traduction.

1. Utilisez les projets de traduction pour [gestion de la traduction du contenu](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en) processus.


Lorsque votre fournisseur de services de traduction ne fournit pas de connecteur pour l’intégration avec AEM, AEM prend en charge l’exportation et l’importation manuelles de contenu traduit au format XML.

>[!TIP]
>
> Voir *Traduction* dans le guide des bonnes pratiques pour connaître les bonnes pratiques en matière de traduction de contenu.

## Configuration de l’onglet Traduction sur le tableau de bord de mappage DITA

Pour masquer l’onglet Traduction sur le tableau de bord de mappage DITA, procédez comme suit :

1. Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration.
1. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer l’onglet de traduction sur le tableau de bord de la carte :

   | PID | Clé de propriété | Valeur de la propriété |
   |---|------------|--------------|
   | `com.adobe.fmdita.config.ConfigManager` | `tabs.translation` | Booléen \( true/ false\).<br> **Valeur par défaut**: `true` |

   >[!NOTE]
   >
   > Cette configuration est activée par défaut et l’onglet Traduction n’est pas disponible dans le tableau de bord de la carte.


## Configuration du processus de traduction basé sur des composants

Si le connecteur du fournisseur de traduction ne prend pas en charge le contenu DITA, le processus de traduction basé sur les composants doit être activé. Une fois activé, le contenu traduisible est envoyé en tant que métadonnées de ressource. Toutefois, le connecteur doit prendre en charge la traduction des métadonnées de ressource pour que ce processus fonctionne.

Selon le processus de traduction utilisé dans votre configuration, l’option de processus de traduction basé sur les composants doit être configurée. Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer le processus de traduction basé sur les composants :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `component.translation` | Booléen : <br> - Si vous utilisez la traduction humaine, alors *Désactiver* \( `false`\) la variable **Processus de traduction basé sur des composants** . <br> - Si vous utilisez la traduction automatique, alors *Activez \( `true`\)* la valeur **Processus de traduction basé sur des composants** . |

>[!NOTE]
>
> Si vous utilisez le connecteur de traduction, assurez-vous que vous avez configuré le connecteur comme décrit dans la section *[Configuration de la structure d’intégration de traduction](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en)* dans la documentation d’AEM.

>[!IMPORTANT]
>
> Après avoir configuré les configurations de traduction, assurez-vous de configurer la configuration cloud appropriée sur les dossiers de langue.

## Configuration du post-traitement des copies de langue temporaires

Lorsque vous lancez le processus de traduction, le système crée des copies de langue temporaires du contenu source. Vous pouvez choisir d’activer ou de désactiver l’opération de post-traitement sur ces fichiers temporaires. Dans l’opération de post-traitement, les références entrantes et sortantes des fichiers sont résolues, l’état du document est défini, ainsi que d’autres opérations. Si vous activez le post-traitement sur ces fichiers temporaires, le processus de traduction peut prendre plus de temps. Par conséquent, il est recommandé de ne pas désactiver l’option de post-traitement.

Suivez les instructions de la section [Remplacements de configuration](download-install-additional-config-override.md#) pour créer le fichier de configuration. Dans le fichier de configuration, fournissez les détails \(propriété\) suivants pour configurer le post-traitement des copies de langue temporaires :

| PID | Clé de propriété | Valeur de la propriété |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `postprocess.temporary.langcopies` | Booléen : <br> - Si vous ne souhaitez pas exécuter l’opération de post-traitement sur les fichiers temporaires, *Désactiver* \( false\) la variable **Copies de langue de post-traitement** .<br> - Si vous souhaitez exécuter l’opération de post-traitement sur les fichiers temporaires, *Activer* \( true\) la variable **Copies de langue de post-traitement** .<br> **Valeur par défaut**: false |
