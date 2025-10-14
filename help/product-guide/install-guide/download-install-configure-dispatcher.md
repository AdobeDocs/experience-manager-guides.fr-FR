---
title: Configuration du Dispatcher
description: Découvrez comment configurer Dispatcher
exl-id: 525de1c3-5a79-4d65-89b4-ca05ae660c2c
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 6%

---

# Configuration du Dispatcher {#id213BCM0M05U}

Si vous prévoyez d’utiliser une instance Dispatcher sur l’instance d’auteur AEM avec AEM Guides, vous devez effectuer les configurations supplémentaires suivantes pour terminer la configuration :

>[!NOTE]
>
> Dispatcher est l’outil de mise en cache et/ou d’équilibrage de charge d’Adobe Experience Manager. Pour plus d’informations sur l’utilisation de Dispatcher, voir [Présentation de Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=fr).

## Activation de AllowEncodedSlashes dans les URL

Les URL avec des barres obliques codées ne sont pas activées par défaut dans AEM configuration du Dispatcher, mais lorsque vous travaillez dans AEM Guides, vous devez activer cette fonctionnalité. Pour ce faire, vous devez définir le paramètre AllowEncodedSlashes sur Activé dans la configuration Apache, comme illustré dans le fragment de code suivant :

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

## Configuration du fichier mime.types pour DITA

Lors de l’utilisation d’un Dispatcher avec AEM Guides, vous devez vous assurer que le mappage DITA et les fichiers de rubrique sont rendus comme HTML pour que les auteurs puissent afficher le contenu comme ils le souhaitent \(au lieu du format de texte brut\).

Effectuez les étapes suivantes pour mettre à jour le fichier mime.types :

1. Connectez-vous au serveur Dispatcher à l’aide de SSH et accédez au fichier httpd.conf .

1. Vérifiez le chemin d’accès au fichier &quot;mime.types&quot;.

1. Ouvrez le fichier mime.types et recherchez &quot; text/html&quot;. Le mappage par défaut pour &quot; text/html&quot; est le suivant :

   `text/html html htm`

1. Mettez à jour le mappage en ajoutant les extensions ditamap et dita comme suit :

   `text/html html htm ditamap dita`

1. Enregistrez et fermez le fichier.


Cette mise à jour de la configuration garantit que le mappage DITA et les fichiers de rubrique rendus par Dispatcher sont affichés comme HTML dans l’interface utilisateur d’Assets.

## Autoriser l’URL de requête des préférences utilisateur

Lors de l’utilisation d’un Dispatcher avec AEM Guides, si votre instance d’auteur dispose d’un dispatcher au premier plan, effectuez les deux modifications suivantes :

- Placez l’URL de demande du POST sur liste blanche. Un exemple de règle &quot; `/filters`&quot; est donné ci-dessous - Ajoutez cette règle au fichier de configurations du Dispatcher :

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

- Assurez-vous que le modèle d’URL &quot; /libs/cq/security/userinfo.json&quot; n’est pas mis en cache sur le Dispatcher de l’auteur. Par conséquent, ajoutez une règle \(comme ci-dessous\) dans author\_dispatcher.any.

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

**Rubrique parente :**&#x200B;[&#x200B; Télécharger et installer](download-install.md)
