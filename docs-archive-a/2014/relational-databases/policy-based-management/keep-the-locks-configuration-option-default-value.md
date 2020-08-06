---
title: Conserver la valeur par défaut de l’option de configuration locks | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: f214f05b-5f0b-4786-b2ad-b8b4b6e58d72
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a1d1dcf82d9cd0ef8ef2c15cb68ef78b53a8a54a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601419"
---
# <a name="keep-the-locks-configuration-option-default-value"></a><span data-ttu-id="139e2-102">Conserver la valeur par défaut de l'option de configuration locks</span><span class="sxs-lookup"><span data-stu-id="139e2-102">Keep the Locks Configuration Option Default Value</span></span>
  <span data-ttu-id="139e2-103">Cette règle vérifie la valeur de l'option de configuration locks (verrous).</span><span class="sxs-lookup"><span data-stu-id="139e2-103">This rule checks the value of the locks configuration option.</span></span> <span data-ttu-id="139e2-104">Cette option détermine le nombre maximal de verrous disponibles</span><span class="sxs-lookup"><span data-stu-id="139e2-104">This option determines the maximum number of available locks.</span></span> <span data-ttu-id="139e2-105">et limite ainsi la quantité de mémoire utilisée par le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] pour les verrous.</span><span class="sxs-lookup"><span data-stu-id="139e2-105">This limits how much memory the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses for locks.</span></span> <span data-ttu-id="139e2-106">La valeur par défaut 0 permet à [!INCLUDE[ssDE](../../includes/ssde-md.md)] d’allouer et de libérer des structures de verrous de manière dynamique en fonction des modifications de la configuration requise.</span><span class="sxs-lookup"><span data-stu-id="139e2-106">The default setting of 0 enables the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to allocate and deallocate lock structures dynamically based on changing system requirements.</span></span>  
  
 <span data-ttu-id="139e2-107">Si la valeur de l'option locks est différente de zéro, les programmes de traitement par lots s'arrêtent et un message d'erreur indiquant un nombre de verrous insuffisant est généré lorsque la valeur spécifiée est dépassée.</span><span class="sxs-lookup"><span data-stu-id="139e2-107">If locks is nonzero, batch jobs will stop, and an "out of locks" error message will be generated, if the value specified is exceeded.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="139e2-108">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="139e2-108">Best Practices Recommendations</span></span>  
 <span data-ttu-id="139e2-109">Utilisez la procédure stockée système sp_configure pour rétablir la valeur par défaut de l'option locks à l'aide de l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="139e2-109">Use the sp_configure system stored procedure to change the value of locks to its default setting by using the following statement:</span></span>  
  
```  
EXEC sp_configure 'locks', 0;  
```  
  
## <a name="for-more-information"></a><span data-ttu-id="139e2-110">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="139e2-110">For More Information</span></span>  
 [<span data-ttu-id="139e2-111">Configurer l'option de configuration du serveur locks</span><span class="sxs-lookup"><span data-stu-id="139e2-111">Configure the locks Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-locks-server-configuration-option.md)  
  
 [<span data-ttu-id="139e2-112">sys.dm_tran_locks &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="139e2-112">sys.dm_tran_locks &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql)  
  
 [<span data-ttu-id="139e2-113">sys.dm_os_wait_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="139e2-113">sys.dm_os_wait_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-wait-stats-transact-sql)  
  
 [<span data-ttu-id="139e2-114">Article 271509 de la Base de connaissances Microsoft</span><span class="sxs-lookup"><span data-stu-id="139e2-114">Microsoft Knowledge Base article 271509</span></span>](https://go.microsoft.com/fwlink/?linkid=117788)  
  
## <a name="see-also"></a><span data-ttu-id="139e2-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="139e2-115">See Also</span></span>  
 [<span data-ttu-id="139e2-116">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="139e2-116">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
