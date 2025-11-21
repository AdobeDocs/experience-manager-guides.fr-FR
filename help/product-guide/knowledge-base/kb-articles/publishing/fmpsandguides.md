---
title: Publication à l’aide de FrameMaker Publishing Server (FMPS) dans AEM Guides
description: Publication avec FMPS à l’aide d’AEM Guides
exl-id: 05d4d876-f83b-473c-bf31-14d6565e80e2
feature: AEM Guides FrameMaker Publishing Server
author: Pulkit Nagpal(punagpal)
role: User, Admin
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Publication à l’aide de FrameMaker Publishing Server (FMPS) dans AEM Guides

L’intégration d’AEM Guides à FrameMaker Publishing Server peut être votre solution si vous recherchez une publication automatisée de haute qualité.\
Cet article vous aide à configurer et à exécuter FMPS avec AEM Guides.

## Compatibilité de FMPS avec AEM Guides

- Compatibilité avec la version 4.1 d’AEM Guides : matrice de compatibilité [4.1](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html?lang=en/#compatibility-matrix)
- Compatibilité avec AEM Guides 4.0 : matrice de compatibilité [4.0](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html/#Compatibility%20matrix)
- Dernière version : [dernières informations de mise à jour](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/latest-release-info.html?lang=en)

## Installation

Consultez les sections suivantes pour l’installation et la configuration d’AEM Guides et de FMPS

### AEM Guides

Référencez l’installation et la configuration : installation et configurations [4.1](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

### FMPS

Pour l&#39;installation FMPS, vous pouvez vous référer au lien [YouTube donné](https://www.youtube.com/watch?v=2deelyM5VA8&t) ou [Installation et configuration FMPS](https://help.adobe.com/en_US/framemaker/server/index.html#t=fmps-user-guide%2Finstall_config_fmps.html%23install_config_fmps&rhtocid=_2)

## Configurations requises

FrameMaker Publishing Server (FMPS) peut être utilisé pour générer votre contenu DITA. FMPS prend en charge un large éventail de formats de sortie. Modifiez les propriétés suivantes du « lot com.adobe.fmdita.config.ConfigManager » dans la console web pour configurer AEM Guides pour utiliser FMPS.

Pour ouvrir la console web, accédez à l’URL Accès http://\&lt;nom du serveur\>:\&lt;port\>/system/console/configMgr.

**Propriétés de configuration et leur description** installation et configuration [4.1](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf#page=89)

## Exécution du test :

En utilisant FMPS, vous pouvez publier automatiquement **PDF** Responsive HTML5 et **Epub** pour vos Assets DITA et FM.

Dans le menu « Générer PDF à l’aide de », choisissez FrameMaker Publishing Server.

L’utilisateur peut indiquer « settings File(.sts) » et « ditaval ». Le filtrage s’effectue à l’aide de ditaval en fonction des conditions que vous fournissez.

- **Fichier de configuration** : fichier de configuration FrameMaker /FMPS Publish qui contient tous les paramètres que vous souhaitez que FMPS respecte lors de la publication. Par exemple, vous pouvez créer une sortie avec un modèle personnalisé, créer des repères et des fonds perdus (PDF) et créer un PDF avec la table des matières.
- **Préréglage FMPS :** il s&#39;agit d&#39;une combinaison prédéfinie de fichiers ditaval et settings. Au lieu de fournir des fichiers de paramètres et de dérangement distincts, l&#39;utilisateur peut précréer un paramètre prédéfini FMPS qui peut être réutilisé pour les besoins de publication.

**Remarque :** le paramètre système par défaut est utilisé par FMPS pour la publication si vous ne choisissez aucun des paramètres ou du paramètre prédéfini FMPS.

Il s’agit d’un conflit si vous avez choisi le paramètre prédéfini FMPS et avez également fourni des paramètres personnalisés ou un fichier déroulant d’AEM. Dans ce cas, le paramètre prédéfini FMPS est prioritaire par rapport aux paramètres personnalisés ou au fichier Daval.

### Publication de référence à l&#39;aide de FMPS :

Vous pouvez publier les lignes de base déjà créées avec la version FMPS2020.0.2 ou une version ultérieure.

**Exemple de fichier de paramètres FMPS (fichier .sts) pour commencer :** [Exemple de fichier de paramètres FMPS](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:ef750752-7a7e-4e51-923e-6b7d9861ed54) (décompressez ce fichier)

## Questions fréquentes et dépannage :

- ### Échec de la publication FMPS avec « Exception de délai d’expiration »

>Vérifiez et augmentez la valeur de « Délai d’expiration FMPS » (secondes) dans /system/console/configMgr/com.adobe.fmdita.config.ConfigManager »

- ### Impossible d’obtenir le préréglage FMPS dans la liste déroulante

>Assurez-vous qu&#39;un paramètre prédéfini FMPS est créé sur le serveur et que vos paramètres de connexion sont corrects.

- ### J’obtiens des PDF vierges lors de la publication

>Si vous utilisez UUID, assurez-vous d’avoir coché la case « Utiliser le référencement basé sur UUID » dans les préférences d’édition de FrameMaker et inversement pour les guides AEM non-UUID.

- ### Mes paramètres/perturbations ne sont pas appliqués à la sortie publiée finale

>Vérifiez que vous ne choisissez pas simultanément le paramètre prédéfini FMPS et le fichier de paramètre/division. Utilisez FrameMaker pour vérifier manuellement la sortie.

- ### La ligne de base n&#39;est pas publiée à partir de FMPS

>Les versions FMPS2020.0.2 ou ultérieures sont compatibles avec la publication de base.
>Assurez-vous que votre ligne de base a été correctement créée ; pour vérifier, accédez au tableau de bord des cartes— Rubriques— Télécharger  Mappez et choisissez Utiliser niveau de référence.

- ### La publication des tâches à partir de FMPS prend plus de temps que les autres moteurs

>Lors de la publication à partir de FMPS, le temps d’en-tête fixe idéal est d’environ 3 à 4 minutes ; si vous pensez qu’il est plus long, contactez votre administrateur FMPS ou l’assistance Adobe.

## Autres ressources :

[Formation et assistance FMPS](https://helpx.adobe.com/support/framemaker-publishing-server.html)

[Formation et assistance AEM Guides](https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html)

[Communauté FrameMaker et FMPS](https://community.adobe.com/t5/framemaker/ct-p/ct-framemaker?page=1&sort=latest_replies&lang=all&tabid=all)

[Communauté AEM Guides](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation)
