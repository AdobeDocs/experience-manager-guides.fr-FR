---
title: Configuration de l’environnement AEM pour la publication native de PDF
description: Configuration de l’environnement AEM pour la publication native de PDF
exl-id: 40266ca0-0b0b-4418-b606-f70270addbaa
feature: Native PDF Output
role: User, Admin
TQID: https://experienceleague.adobe.com/SLuPn9YigAcHvcSEdrbbQOz29Y6DeWGYnWktWY9L9nQ
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 911
ht-degree: 1%

---

# Configuration de l’environnement AEM pour la publication native de PDF

AEM Guides comprend un moteur de publication PDF natif qui permet aux utilisateurs et utilisatrices de concevoir, développer et publier le contenu au format PDF.

Il permet de créer différentes mises en page et différents modèles CSS, ainsi que de concevoir les modèles PDF en combinaison avec les mises en page et CSS.

Les étapes de configuration de ce PDF natif dans AEM Guides varient en fonction du système d’exploitation. Suivez les étapes de configuration ci-dessous en fonction du système d’exploitation sur lequel AEM est installé.

## Conditions préalables

Configuration minimale requise pour le PDF natif :

- Plateforme Java installée, JDK Standard Edition 8 ou 11 (kit de développement Java SE) et JRE (environnement d’exécution Java SE)
- AEM 6.5 SP13, SP12, SP11 ou SP10
- Guides 4.1 et versions ultérieures (non-UUID ou UUID)

Le moteur de publication natif de PDF a besoin du JDK Oracle pour générer les modules de nœud dans le dossier crx-quickstart d’AEM. Il prend en charge les systèmes d’exploitation suivants par défaut :

- Windows 10, Windows 2019 Server et versions ultérieures.
- Linux - (RHEL 8 et versions ultérieures, CentOS 7 et versions ultérieures, Ubuntu 18 et versions ultérieures)
- Système d’exploitation Mac (basé sur Intel)

## Étapes de configuration pour Windows Server (JAVA 11/8)

1. Vérifiez que le serveur AEM est hors service.
2. Dans la barre des tâches de Windows, cliquez avec le bouton droit de la souris sur l&#39;icône Windows et sélectionnez Système.
3. Dans la fenêtre Paramètres, sous Paramètres associés, cliquez sur Paramètres système avancés.
4. Dans l’onglet Avancé , cliquez sur Variables d’environnement.
5. Dans la section des variables système, cliquez sur « _Nouveau_ » pour créer une variable d’environnement.
6. Saisissez le nom de variable JAVA_HOME.
7. Dans le champ de valeur, indiquez le chemin d’installation Java et cliquez sur OK.

   Par exemple :

   JAVA 11 :

   11.0.15.1

   JAVA 8 :

   C:\Program Files\JAVA\ jdk1.8.0_144

8. Ajoutez et sélectionnez Chemin d’accès à partir des variables système, puis cliquez sur Modifier.

9. Désormais, dans Chemin d’accès , les variables indiquent la valeur du Chemin du serveur et cliquez sur OK.

   Par exemple :

   JAVA 11 :

   %JAVA_HOME%\bin\server\

   JAVA 8 :

   %JAVA_HOME%\jre\bin\server\

10. Cliquez de nouveau sur « OK » dans la boîte de dialogue Variables d’environnement .
11. Cliquez de nouveau sur OK dans la boîte de dialogue Propriétés du système.
12. Démarrez à présent le serveur AEM.
13. Générez un PDF natif à partir de paramètres prédéfinis dans l’éditeur.

## Etapes de configuration pour Linux Server (RHEL7/centOS 7)

1. Vérifiez que le serveur AEM est hors service.
2. Vérifiez la variable JAVA_HOME en faisant écho à $JAVA_HOME.
3. Si la variable JAVA_HOME n’est pas définie, suivez l’étape 4. Sinon, passez directement à l’étape 5.
4. Définissez la variable JAVA_HOME à l’aide des commandes ci-dessous en fonction de la version Java installée

   Par exemple :

   JAVA 11 :

   1. export JAVA\_HOME=/usr/lib/jvm/java-11.0.15.1
   2. CHEMIN D’ACCÈS À L’EXPORTATION=$PATH: $JAVA\_HOME/bin
   3. export LD\_LIBRARY\_PATH=/usr/lib/jvm/jdk-11.0.15.1/lib/server:/usr/java/jdk-11.0.15.1/lib/server

   JAVA 8 :

   1. export JAVA\_HOME=/usr/lib/jvm/java-11.0.15.1
   2. CHEMIN D’ACCÈS À L’EXPORTATION=$PATH: $JAVA\_HOME/bin

5. Redémarrez le serveur AEM et passez à l’étape 12, si vous utilisez les versions 4.2 et ultérieures de Guides.
6. Copiez le fichier « _node_ modules.zip_ » joint au bas de cet article dans le répertoire crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166/ .
7. Ouvrez le terminal dans crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166/ location.
8. Supprimez le répertoire node_modules à l’aide de la commande ci-dessous

   **rm -rf node_modules**

9. Décompressez node_modules.zip à l’aide de la commande ci-dessous

   **unzip node_modules.zip**

10. Si la commande unzip n’est pas installée/reconnue, elle peut être installée à l’aide de la commande suivante

    **yum install unzip**

11. Installez le package fontconfig.
Commande : yum install fontconfig
12. Générez un PDF natif à partir de paramètres prédéfinis dans l’éditeur.

**REMARQUE** : le package node_modules.zip peut être téléchargé [ici] (:aaid:scds:US:295d8f03-41e1-429b-8465-2761ce3c2fb3).

L’importation manuelle des modules de nœud téléchargés pour le système d’exploitation Linux est une solution de contournement pour les utilisateurs qui utilisent Guides 4.1 ou des versions antérieures (étapes 6 à 12)

## Étapes de configuration de la machine Mac (JAVA 11/8)

1. Installez Oracle JAVA 11 ou Oracle JAVA 8.
2. Définissez la variable d’environnement JAVA_HOME sur le répertoire JAVA installé.
3. Ouvrez un shell Unix.
(Bash est utilisé ici pour configurer)

   Commande : nano ~/.bashrc

4. Définissez la variable JAVA_HOME à l’aide des commandes ci-dessous en fonction de la version Java installée

   Par exemple :

   JAVA 11 :

   export JAVA\_HOME= /Library/Java/JavaVirtualMachines/jdk-11.0.15.1.jdk/Contents/Home

5. Recharger la base

   Commande : source ~/.bashrc.

6. Vérifiez que JAVA_HOME est défini à l’aide de la commande echo $JAVA_HOME.

7. Exécutez les trois commandes ci-dessous à partir du chemin d’installation AEM

   C:/{aem-installation-folder}/crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166

   i) rechercher . -type d -exec chmod 0755 {} \;
ii) rechercher . -type f -exec chmod 0755 {} \;
iii) ./node-darwin/bin/node node-darwin/lib/node_modules/npm/bin/npm-cli.js —prefix . install —unsafe-perm —scripts-prepend-node-path

8. Vérifiez si Java est installé à l’aide de la commande ci-dessous

   i) Exécutez la commande **./node-darwin/bin/node** à partir du dossier /crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166.

   ![mac](../assets/publishing/mac.png)

   ii) a = required(&#39;java&#39;)

9. Installez le package fontconfig.
Commande : apt install fontconfig

10. Générez un PDF natif à partir de paramètres prédéfinis dans l’éditeur.

## Résolution des problèmes

Vous trouverez ci-dessous les erreurs courantes qui peuvent se produire pendant la génération du PDF lorsque les variables d’environnement ne sont pas définies correctement.

### Exception pointeur nul dans Windows/Mac OS

![exception de pointeur nul](../assets/publishing/null-pointer-exception.png)

Si le problème persiste même après la correction des paramètres de l’environnement Java, veuillez revalider les éléments suivants :

1. Vérifiez si le paramètre prédéfini de sortie est défini correctement ou créez un nouveau paramètre prédéfini de sortie sans espaces.

2. Vérifiez le répertoire des ressources de nœud sous /libs/fmdta/node_resources pour vous assurer que toutes les bibliothèques requises sont installées pendant l’installation.

### Bibliothèques manquantes dans RHEL 7 Linux OS

![bibliothèques manquantes &#x200B;](../assets/publishing/missing-libraries.png)

### Délai d’expiration du processus de publication. Le processus ne s&#39;est pas terminé dans le délai donné de 0ms

![délai d’expiration du processus de publication](../assets/publishing/publish-process-timeout.png)

Validez la valeur de la propriété timeout pour le nœud nodejs dans /var/dxml/profiles/b1aad0a7-9079-e56c-1ed8-6fcababe8166/nodejs dans le référentiel CRX. La valeur par défaut est 300.



Si vous rencontrez des problèmes lors de l’exécution des étapes ci-dessus, publiez votre question sur le [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) de la communauté AEM Guides pour obtenir de l’aide.
