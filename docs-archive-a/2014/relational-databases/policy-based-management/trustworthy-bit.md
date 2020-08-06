---
title: Bit de confiance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3198188a-2b59-4865-9560-10f760934b8e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 062a63dd52f4641a0ddfcbc20cb9bad3cce6dc61
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603447"
---
# <a name="trustworthy-bit"></a><span data-ttu-id="653e3-102">Bit de confiance</span><span class="sxs-lookup"><span data-stu-id="653e3-102">Trustworthy Bit</span></span>
  <span data-ttu-id="653e3-103">Cette règle détermine si le rôle dbo d'une base de données est affecté au rôle serveur fixe sysadmin et si le bit de confiance de la base de données a la valeur ON.</span><span class="sxs-lookup"><span data-stu-id="653e3-103">This rule determines whether the dbo role for a database is assigned to the sysadmin fixed server role and the database has its trustworthy bit set to ON.</span></span>  
  
 <span data-ttu-id="653e3-104">Si ces conditions sont réunies, un utilisateur de base de données doté de privilèges peut élever les privilèges au rôle sysadmin.</span><span class="sxs-lookup"><span data-stu-id="653e3-104">If these conditions are met, a privileged database user can elevate privileges to the sysadmin role.</span></span> <span data-ttu-id="653e3-105">Dans ce rôle, l'utilisateur peut créer et exécuter des assemblys non sécurisés qui compromettent le système.</span><span class="sxs-lookup"><span data-stu-id="653e3-105">In this role, the user can create and run unsafe assemblies that compromise the system.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="653e3-106">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="653e3-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="653e3-107">Désactivez le bit de confiance ou révoquez les autorisations sysadmin du rôle de base de données dbo.</span><span class="sxs-lookup"><span data-stu-id="653e3-107">Turn off the trustworthy bit or revoke sysadmin permissions from the dbo database role.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="653e3-108">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="653e3-108">For More Information</span></span>  
 [<span data-ttu-id="653e3-109">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="653e3-109">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="653e3-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="653e3-110">See Also</span></span>  
 [<span data-ttu-id="653e3-111">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="653e3-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
