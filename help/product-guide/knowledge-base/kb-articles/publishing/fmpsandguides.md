---
title: Publication à l’aide de FrameMaker Publishing Server (FMPS) dans AEM Guides
description: Publication à l’aide de FMPS à l’aide de AEM Guides
exl-id: 05d4d876-f83b-473c-bf31-14d6565e80e2
source-git-commit: c31a569c009155dacef00b6b3f1e6d64e556cf29
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 0%

---

# Publication à l’aide de FrameMaker Publishing Server (FMPS) dans AEM Guides

L’intégration d’AEM Guides à FrameMaker Publishing Server peut être votre solution si vous recherchez une publication automatisée de haute qualité.\
Cet article vous aide à configurer et à exécuter FMPS avec AEM Guides.

## Compatibilité de FMPS avec AEM Guides

- Compatibilité avec les AEM Guides 4.1 : [Tableau de compatibilité 4.1](/help/product-guide/release-info/release-notes-4.1.md#compatibility-matrix)
- Compatibilité avec les AEM Guides 4.0 : [Tableau de compatibilité 4.0](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html/#Compatibility%20matrix)
- Dernière version : [Dernières informations de mise à jour](/help/product-guide/release-info/latest-release-info.md)

## Installation

Reportez-vous aux guides d’AEM et à la configuration FMPS ci-dessous.

### Guides d’AEM

Installation et configuration : [4.1 installation et configurations](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

### FMPS

Pour l’installation FMPS, reportez-vous aux [Lien YouTube](https://www.youtube.com/watch?v=2deelyM5VA8&amp;t) ou [Installation et configuration de FMPS](https://help.adobe.com/en_US/framemaker/server/index.html#t=fmps-user-guide%2Finstall_config_fmps.html%23install_config_fmps&amp;rhtocid=_2)

## Configurations requises

FrameMaker Publishing Server (FMPS) peut être utilisé pour générer votre contenu DITA. FMPS prend en charge un large éventail de formats de sortie. Modifiez les propriétés suivantes du &quot;lot com.adobe.fmdita.config.ConfigManager&quot; dans la console web pour configurer AEM Guides afin d’utiliser FMPS.

Pour ouvrir la console web, accédez à l’URL http://\&lt;server name=&quot;&quot;>:\&lt;port>/system/console/configMgr

**Propriétés de configuration et leur description** [Installation et configuration 4.1](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf#page=89)

## Exécution du test :

Avec FMPS, vous pouvez publier automatiquement **PDF, HTML réactif5**, et **Epub** pour vos ressources DITA et FM.

Dans le menu &quot;Générer le PDF à l’aide de&quot;, choisissez FrameMaker Publishing Server.

L’utilisateur peut fournir &quot;settings File(.sts)&quot; et &quot;ditaval&quot;. Le filtrage est effectué à l’aide de ditaval en fonction des conditions que vous fournissez.

- **Définition du fichier**: fichier de paramètres de publication /FMPS FrameMaker qui contient tous les paramètres que vous souhaitez que FMPS respecte lors de la publication. Par exemple, la création d’une sortie avec un modèle personnalisé, la création de Marques et de Bleeds (PDF) et la création de PDF avec la table des matières.
- **Paramètre prédéfini FMPS :** Il s’agit d’une combinaison prédéfinie de ditaval et de fichier de paramètres. Au lieu de fournir des fichiers de paramètres et d’aval distincts, l’utilisateur peut précréer un paramètre prédéfini FMPS qui peut être réutilisé pour les besoins de publication.

**Remarque :** Le paramètre système par défaut est utilisé par FMPS pour la publication si vous ne sélectionnez aucun des paramètres ou paramètre prédéfini FMPS.

Il s’agit d’un conflit si vous choisissez le paramètre prédéfini FMPS et avez également fourni des paramètres personnalisés ou un fichier ditaval d’AEM. Dans ce cas, le paramètre prédéfini FMPS prévaut sur les paramètres personnalisés ou le fichier ditaval.

### Publication de base à l’aide de FMPS :

Vous pouvez publier vos lignes de base déjà créées avec FMPS2020.0.2 ou une version ultérieure.

**Exemple de fichier de paramètres FMPS (fichier .sts) pour commencer :** [Exemple de fichier de paramètres FMPS](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:ef750752-7a7e-4e51-923e-6b7d9861ed54) (décompressez ce fichier)

## FAQ et dépannage :

- ### Échec de publication FMPS avec &quot;Timeout Exception&quot;

>Vérifiez et augmentez la valeur du &quot;délai d’expiration FMPS&quot; (secondes) dans /system/console/configMgr/com.adobe.fmdita.config.ConfigManager&quot;.

- ### Impossible d’obtenir le paramètre prédéfini FMPS dans la liste déroulante

>Assurez-vous que vous disposez d’un paramètre prédéfini FMPS prédéfini créé sur le serveur et que vos paramètres de connexion sont corrects.

- ### Je deviens PDF vierge lors de la publication

>Si vous utilisez l’UUID, assurez-vous d’avoir coché &quot;Utiliser le référencement basé sur l’UUID&quot; dans les préférences d’édition de FrameMaker et inversement pour les guides d’AEM non UUID.

- ### Mes paramètres/ditaval ne sont pas appliqués dans la sortie publiée finale.

>Vérifiez que vous ne sélectionnez pas simultanément le paramètre prédéfini FMPS et le fichier de configuration/diaval. Utilisez FrameMaker pour vérifier manuellement la sortie.

- ### La ligne de base n’est pas publiée à partir de FMPS

>FMPS2020.0.2 ou versions ultérieures sont compatibles avec la publication de base.
>Assurez-vous que votre ligne de base a été correctement créée. Pour la vérifier, accédez au Tableau de bord des cartes - Rubriques - Carte de téléchargement et sélectionnez &quot;Utiliser la ligne de base&quot;.
- ### La publication des tâches à partir de FMPS prend plus de temps que les autres moteurs

>Lors de la publication à partir de FMPS, le temps d’en-tête fixe idéal est d’environ 3 à 4 minutes. Si vous pensez que c’est plus long, contactez votre administrateur FMPS ou contactez l’assistance Adobe.

## Autres ressources :

[Formation et assistance pour FMPS](https://helpx.adobe.com/support/framemaker-publishing-server.html)

[Formation et assistance pour AEM Guides](https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html)

[Communauté FrameMaker et FMPS](https://community.adobe.com/t5/framemaker/ct-p/ct-framemaker?page=1&amp;sort=latest_replies&amp;lang=all&amp;tabid=all)

[Communauté AEM Guides](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation)
