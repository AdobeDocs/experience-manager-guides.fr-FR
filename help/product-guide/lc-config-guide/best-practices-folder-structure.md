---
title: Bonnes pratiques pour configurer la structure de dossiers
description: Découvrez les bonnes pratiques pour configurer la structure des dossiers lors de l’utilisation du contenu d’apprentissage et de formation dans Experience Manager Guides.
feature: Authoring
role: Admin
level: Experienced
exl-id: 1b99ade0-0eee-42c3-a383-0c3774b6c1f6
TQID: https://experienceleague.adobe.com/jfoPbeASfVpgWYR2-cKacAdhWKPw-2j6qliqzjEzgFw
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: b1210526-416b-4ef6-bcc0-1692e99f30e9id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
subfeature_v2: id: a7a242db-c88c-4e44-818b-bfb4ef92efdfid: c8841798-1a28-4264-a46a-984860f8e6f6id: dc1f7602-db3c-4ad4-a440-ff999bb16455id: f7774ebe-aec9-42b6-97e4-5002acdc712eid: f9dbea21-a714-40dd-bc90-080d8046c93fid: fd456af4-cb12-4a34-8cc4-b74adf885626
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 625
ht-degree: 0%

---

# Bonnes pratiques pour configurer la structure de dossiers

Cet article décrit les étapes essentielles et les bonnes pratiques pour que les administrateurs puissent configurer des structures de dossiers dans Adobe Experience Manager Guides. Une hiérarchie de dossiers bien organisée garantit des workflows de création, de publication et de traduction fluides pour le contenu d’apprentissage et de formation.

## Configurer la structure de dossiers

Pour autoriser l’accès à diverses fonctionnalités de création, de publication et de traduction de Experience Manager Guides, assurez-vous de configurer les dossiers dans la bonne hiérarchie, comme expliqué ci-dessous.

**Créer un dossier de niveau racine**

Commencez par créer un dossier racine pour votre organisation. Il sert de base pour tous les dossiers au niveau du service et les ressources partagées couramment.

Exemple : `/content/dam/ABC-Corp/`

Dans ce dossier racine, créez un dossier dédié pour gérer les ressources qui seront utilisées dans plusieurs services. Par exemple, créez un dossier **Commun** pour inclure des ressources partagées telles que des images, des vidéos, etc.

![](assets/root-level-folder.png)

**Créer des dossiers au niveau du service**

Créez des dossiers distincts pour chaque service, comme les ressources humaines, les finances et le service juridique, afin qu’ils puissent gérer leur propre contenu.

![](assets/department-level-folders.png)
*Légende : Structure de dossiers distincte créée pour le service des ressources humaines dans le dossier racine*

**Bonnes pratiques pour définir des dossiers au niveau du service**

- Créez un dossier **Commun** > **ressources** dédié sous chaque service pour les ressources communes au niveau du service (si nécessaire).
- Si vous souhaitez partager du contenu pour la traduction, créez des dossiers spécifiques à une langue (par exemple, en, de, fr). Les auteurs doivent créer ou mettre à jour le contenu uniquement dans le dossier de langue source (comme en), car le contenu situé en dehors du dossier de langue source n’est pas inclus dans le workflow de traduction. Les autres dossiers de langue peuvent être laissés vides sous forme d’espaces réservés. En savoir plus sur la [ traduction de contenu ](../user-guide/translation.md).
- Les autorisations peuvent être utilisées pour limiter l’accès de services ou d’utilisateurs spécifiques à la structure de dossiers nouvellement créée. Par exemple, attribuez des autorisations pour vous assurer que seuls les utilisateurs du service des ressources humaines peuvent créer ou modifier du contenu dans le dossier désigné.

Répétez la même structure pour d&#39;autres ministères comme les Finances, les Services juridiques, etc.

## Configurer la structure de dossiers de sortie

Le dossier `fm-ditaoutputs` sert d’emplacement de stockage par défaut pour les sorties générées à partir du contenu de formation. Ces sorties incluent généralement des packages SCORM (fichiers ZIP) dans le dossier **alm** et des fichiers PDF dans le dossier **pdf**.Si nécessaire, vous pouvez modifier ce chemin de sortie par défaut au niveau du paramètre prédéfini dans la **console Carte**.

![](assets/fmdita-output-lc.png)

Lorsque vous travaillez avec plusieurs services, pensez à créer des dossiers spécifiques au service dans la structure de dossiers `fm-ditaoutputs` afin de vous assurer que les utilisateurs d’un service spécifique ont accès aux dossiers de sortie appropriés.

## Créer des utilisateurs et les affecter à des groupes appropriés

Une fois la hiérarchie de dossiers établie, vous pouvez commencer à créer des utilisateurs et à les ajouter à des groupes afin qu’ils aient accès aux fonctionnalités pertinentes de Experience Manager Guides. Experience Manager Guides fournit trois groupes prêts à l’emploi : auteurs, réviseurs et éditeurs. Selon le groupe auquel un utilisateur est associé, il est autorisé à effectuer des tâches spécifiques. Par exemple, une tâche de publication ne peut être effectuée que par un éditeur, mais pas par un auteur.

Pour créer des utilisateurs et les ajouter à des groupes, accédez à **Outils** > **Sécurité** > **Utilisateurs**.

Sur la page User Management, sélectionnez **Créer** pour créer un utilisateur. Ajoutez des détails d’utilisateur et affectez-les à un groupe.

![](assets/create-users-page.png)

Pour plus d’informations, consultez [Administration et sécurité des utilisateurs](../cs-install-guide/user-admin-sec.md)


## Attribuer des autorisations à chaque groupe d’utilisateurs

Une fois que les utilisateurs ont été ajoutés aux groupes appropriés, configurez des autorisations au niveau du groupe pour vous assurer qu’ils ont accès aux dossiers de création et de sortie appropriés dans le référentiel.

Pour attribuer des autorisations, accédez à **Outils** > **Sécurité** > **Autorisations**.

Ces autorisations permettent de s’assurer que les utilisateurs peuvent créer ou modifier du contenu uniquement dans les dossiers qu’ils ont désignés.

Pour plus d’informations, voir [Autorisations dans AEM](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/security/security#permissions-in-aem).
