---
title: Notes de mise à jour | Correction de problèmes dans Adobe Experience Manager Guides 4.6.0 Service Pack 4
description: Découvrez les correctifs de bugs dans la version 4.6.0 Service Pack 4 d’Adobe Experience Manager Guides
role: Leader
exl-id: ad69ea47-7880-43d1-8567-cd608fedb462
TQID: https://experienceleague.adobe.com/4ILARUO5umX41xE3Lcie-FsP396sgSqfbrWlMqdjsQ4
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 234
ht-degree: 4%

---

# Correction de problèmes dans la version 4.6.0 Service Pack 4 (avril 2025)


Cet article couvre les bugs corrigés dans différentes zones de la version 4.6.0 Service Pack 4 d’Adobe Experience Manager Guides.

Découvrez les [instructions de mise à niveau pour le pack de services 4.6.0 d’](upgrade-instructions-4-6-0-sp4.md).

## Création

- Faire glisser et déposer une image dans une rubrique en mode **Auteur** rompt la référence de l’image, ce qui entraîne une perte de données. (25769)
- Faire glisser et déposer un `topicref` dans un mappage dans la vue **Auteur** ne permet pas d’effectuer l’opération prévue et supprime le `topicref` en regard du `topicref` déplacé. (19460)
- Si vous ne fermez pas les connexions de session JCR lors de la mise à jour ou de la création de rubriques, des fuites de mémoire et des temps d’arrêt du service surviennent. (26282)

## Publication

- La publication native de PDF se poursuit indéfiniment si le contenu DITA comporte un lien web sans que la portée soit définie comme `external`. (26434)
- Lors de la création d&#39;une nouvelle ligne de base avec un grand nombre de libellés, le chargeur de libellés échoue et les libellés ne sont pas récupérés. (16232)
- La publication des PDF natifs et des sites AEM est bloquée et mise en file d’attente en cas d’erreur dans le contenu. (26516)

## Problèmes connus

Adobe a identifié le problème connu suivant pour cette version :

- La publication native de PDF sous Windows rencontre des échecs lorsque le contenu DITA contient un lien externe qui n&#39;inclut pas l&#39;attribut `scope`.
