---
title: Définir l’option de base de données AUTO_SHRINK sur OFF | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 16403850-d745-4754-b84f-5f01aaecd24e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 42d79ed13a691c3d39a28e7ab35a740a9f613fac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708204"
---
# <a name="set-the-auto_shrink-database-option-to-off"></a><span data-ttu-id="aca23-102">Définir l'option de base de données AUTO_SHRINK sur OFF</span><span class="sxs-lookup"><span data-stu-id="aca23-102">Set the AUTO_SHRINK Database Option to OFF</span></span>
  <span data-ttu-id="aca23-103">Cette règle vérifie si l'option de base de données AUTO_SHRINK est définie avec la valeur OFF.</span><span class="sxs-lookup"><span data-stu-id="aca23-103">This rule checks whether the AUTO_SHRINK database option is set to OFF.</span></span> <span data-ttu-id="aca23-104">La réduction et le développement fréquents d'une base de données peuvent entraîner une fragmentation physique.</span><span class="sxs-lookup"><span data-stu-id="aca23-104">Frequently shrinking and expanding a database can lead to physical fragmentation.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="aca23-105">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="aca23-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="aca23-106">Définissez l'option de base de données AUTO_SHRINK avec la valeur OFF.</span><span class="sxs-lookup"><span data-stu-id="aca23-106">Set the AUTO_SHRINK database option to OFF.</span></span> <span data-ttu-id="aca23-107">Si vous savez que vous n'aurez pas besoin de l'espace que vous récupérez, vous pouvez le récupérer en réduisant manuellement la base de données.</span><span class="sxs-lookup"><span data-stu-id="aca23-107">If you know that the space that you are reclaiming will not be needed in the future, you can reclaim the space by manually shrinking the database.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="aca23-108">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="aca23-108">For More Information</span></span>  
 <span data-ttu-id="aca23-109">Article [315512](https://go.microsoft.com/fwlink/?linkid=117750)de la Base de connaissances Microsoft</span><span class="sxs-lookup"><span data-stu-id="aca23-109">Microsoft Knowledge Base article [315512](https://go.microsoft.com/fwlink/?linkid=117750)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aca23-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aca23-110">See Also</span></span>  
 [<span data-ttu-id="aca23-111">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="aca23-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
