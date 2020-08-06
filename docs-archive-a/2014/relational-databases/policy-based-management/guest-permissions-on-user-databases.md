---
title: Autorisations Invité sur les bases de données utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 540f1c6d-df51-497e-958a-3a0f429d2920
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 344c5fd0639876998f1585c32fac5f7599f664e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601434"
---
# <a name="guest-permissions-on-user-databases"></a><span data-ttu-id="e407b-102">Autorisations Invité sur les bases de données utilisateur</span><span class="sxs-lookup"><span data-stu-id="e407b-102">Guest Permissions on User Databases</span></span>
  <span data-ttu-id="e407b-103">Cette règle détermine si l'utilisateur invité a l'autorisation d'accéder à la base de données.</span><span class="sxs-lookup"><span data-stu-id="e407b-103">This rule determines whether the guest user has permission to access the database.</span></span> <span data-ttu-id="e407b-104">Cette règle s'applique uniquement aux bases de données utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e407b-104">This rule applies to user databases only.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="e407b-105">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="e407b-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="e407b-106">Révoquez l'autorisation d'accès à la base de données octroyée à l'utilisateur invité si elle n'est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e407b-106">Revoke the guest user permission to access the database if it is not required.</span></span>  
  
 <span data-ttu-id="e407b-107">Vous ne pouvez pas supprimer l’utilisateur guest, mais vous pouvez le désactiver en révoquant son autorisation CONNECT. Pour ce faire, vous devez exécuter REVOKE CONNECT FROM GUEST dans toute base de données autre que la base master, tempdb ou msdb.</span><span class="sxs-lookup"><span data-stu-id="e407b-107">The guest user cannot be dropped, but guest user can be disabled by revoking its CONNECT permission by executing REVOKE CONNECT FROM GUEST within any database other than master, tempdb, or msdb.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="e407b-108">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="e407b-108">For More Information</span></span>  
 [<span data-ttu-id="e407b-109">Sécurisation de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e407b-109">Securing SQL Server</span></span>](../security/securing-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="e407b-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e407b-110">See Also</span></span>  
 [<span data-ttu-id="e407b-111">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="e407b-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
