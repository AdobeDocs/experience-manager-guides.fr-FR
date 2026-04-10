---
title: Configurer Dispatcher
description: Découvrez comment configurer Dispatcher
exl-id: 525de1c3-5a79-4d65-89b4-ca05ae660c2c
feature: Installation
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 6%

---

# Configurer Dispatcher {#id213BCM0M05U}

Si vous prévoyez d’utiliser une instance Dispatcher sur l’instance d’auteur AEM avec AEM Guides, vous devez effectuer les configurations supplémentaires suivantes pour terminer la configuration :

>[!NOTE]
>
> Dispatcher est l’outil de mise en cache et/ou d’équilibrage de charge d’Adobe Experience Manager. Pour plus d’informations sur l’utilisation de Dispatcher, consultez [Présentation de Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=fr).

## Activer AllowEncodedSlashes dans les URL

Les URL avec des barres obliques codées ne sont pas activées par défaut dans la configuration du Dispatcher AEM, mais lorsque vous travaillez dans AEM Guides, vous devez activer cette option. Pour ce faire, vous devez définir le paramètre AllowEncodedSlashes sur On dans la configuration Apache, comme illustré dans le fragment de code suivant :

```XML
<VirtualHost *:80>
                ServerName www.geometrixx-outdoors.com
                **AllowEncodedSlashes On**
                <Directory />
                <IfModule disp_apache2.c>
                SetHandler dispatcher-handler
                </IfModule>
                Options FollowSymLinks
                AllowOverride None
                </Directory>
                </VirtualHost>
            
```

## Configurer le fichier mime.types pour DITA

Lors de l’utilisation d’un Dispatcher avec AEM Guides, vous devez vous assurer que les fichiers de plan et de rubrique DITA sont générés en tant qu’HTML pour que les auteurs puissent afficher le contenu comme ils l’entendent \(au lieu du format de texte brut\).

Effectuez les étapes suivantes pour mettre à jour le fichier mime.types :

1. Connectez-vous au serveur Dispatcher à l’aide de SSH et accédez au fichier httpd.conf.

1. Vérifiez le chemin d’accès du fichier « mime.types ».

1. Ouvrez le fichier mime.types et recherchez « text/html ». Le mappage par défaut pour « text/html » est le suivant :

   `text/html html htm`

1. Mettez à jour le mappage en ajoutant les extensions ditamap et dita comme suit :

   `text/html html htm ditamap dita`

1. Enregistrez et fermez le fichier.


Cette mise à jour de la configuration garantit que les fichiers de plan et de rubrique DITA rendus par Dispatcher s&#39;affichent sous la forme HTML dans l&#39;interface utilisateur d&#39;Assets.

## URL de requête Autoriser les préférences utilisateur

Lors de l’utilisation d’un Dispatcher avec AEM Guides, si votre instance de création comporte un Dispatcher au premier plan, effectuez les deux modifications suivantes :

- Placez sur liste autorisée l’URL de la requête POST. Un exemple de règle « `/filters` » est fourni ci-dessous. Ajoutez cette règle au fichier de configurations du Dispatcher :

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

- Assurez-vous que le modèle d’URL « /libs/cq/security/userinfo.json » n’est pas mis en cache sur le Dispatcher de création. Ajoutez donc une règle \(comme ci-dessous\) dans author\_dispatcher.any.

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

**Rubrique parente :**[ Télécharger et installer](download-install.md)
