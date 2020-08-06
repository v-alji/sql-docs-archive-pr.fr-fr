---
title: Clés symétriques sur les bases de données utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3333ab5b-2518-4753-a0a8-57df5e5af74f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ca0fb62ccb32ce244e1087281997dcd9929df89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603449"
---
# <a name="symmetric-keys-on-user-databases"></a><span data-ttu-id="558f9-102">Clés symétriques sur les bases de données utilisateur</span><span class="sxs-lookup"><span data-stu-id="558f9-102">Symmetric Keys on User Databases</span></span>
  <span data-ttu-id="558f9-103">Cette règle vérifie que les clés dont la longueur est inférieure à 128 octets n'utilisent pas l'algorithme de chiffrement RC2 ou RC4.</span><span class="sxs-lookup"><span data-stu-id="558f9-103">This rule checks whether keys that have a length of less than 128 bytes do not use the RC2 or RC4 encryption algorithm.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="558f9-104">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="558f9-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="558f9-105">Utilisez AES 128 bits ou supérieur pour créer des clés symétriques pour le chiffrement de données.</span><span class="sxs-lookup"><span data-stu-id="558f9-105">Use AES 128 bit or larger to create symmetric keys for data encryption.</span></span> <span data-ttu-id="558f9-106">Si AES n'est pas pris en charge par votre système d'exploitation, utilisez 3DES.</span><span class="sxs-lookup"><span data-stu-id="558f9-106">If AES is not supported by your operating system, use 3DES.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="558f9-107">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="558f9-107">For More Information</span></span>  
 [<span data-ttu-id="558f9-108">Choisir un algorithme de chiffrement</span><span class="sxs-lookup"><span data-stu-id="558f9-108">Choose an Encryption Algorithm</span></span>](../security/encryption/choose-an-encryption-algorithm.md)  
  
## <a name="see-also"></a><span data-ttu-id="558f9-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="558f9-109">See Also</span></span>  
 [<span data-ttu-id="558f9-110">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="558f9-110">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
