---
title: Définir l’option de base de données AUTO_CLOSE sur OFF | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: e6b03364-263a-4ec4-9794-de9869d396ce
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: db6cf5a3f82c3493a8732958594743104fccc968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708207"
---
# <a name="set-the-auto_close-database-option-to-off"></a><span data-ttu-id="6fd12-102">Définir l'option de base de données AUTO_CLOSE sur OFF</span><span class="sxs-lookup"><span data-stu-id="6fd12-102">Set the AUTO_CLOSE Database Option to OFF</span></span>
  <span data-ttu-id="6fd12-103">Cette règle vérifie si l'option AUTO_ CLOSE est désactivée (OFF).</span><span class="sxs-lookup"><span data-stu-id="6fd12-103">This rule checks whether the AUTO_ CLOSE option is set OFF.</span></span> <span data-ttu-id="6fd12-104">Lorsqu'elle est définie sur ON, cette option peut entraîner une dégradation des performances sur les bases de données fréquemment sollicitées en raison de la surcharge causée par l'ouverture et la fermeture de la base de données après chaque connexion.</span><span class="sxs-lookup"><span data-stu-id="6fd12-104">When AUTO_CLOSE is set ON, this option can cause performance degradation on frequently accessed databases because of the increased overhead of opening and closing the database after each connection.</span></span> <span data-ttu-id="6fd12-105">AUTO_CLOSE vide également le cache de procédure après chaque connexion.</span><span class="sxs-lookup"><span data-stu-id="6fd12-105">AUTO_CLOSE also flushes the procedure cache after each connection.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="6fd12-106">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="6fd12-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="6fd12-107">En cas d'accès fréquent à une base de données, définissez l'option AUTO_CLOSE sur OFF pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="6fd12-107">If a database is accessed frequently, set the AUTO_CLOSE option to OFF for the database.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="6fd12-108">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="6fd12-108">For More Information</span></span>  
 [<span data-ttu-id="6fd12-109">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6fd12-109">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
## <a name="see-also"></a><span data-ttu-id="6fd12-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6fd12-110">See Also</span></span>  
 [<span data-ttu-id="6fd12-111">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="6fd12-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
