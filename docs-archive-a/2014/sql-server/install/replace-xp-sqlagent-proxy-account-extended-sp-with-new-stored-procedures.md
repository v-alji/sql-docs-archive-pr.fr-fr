---
title: Remplacer l’utilisation de la procédure stockée étendue xp_sqlagent_proxy_account par de nouvelles procédures stockées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- xp_sqlagent_proxy_account
ms.assetid: 0e3cc931-6237-41dd-bf0d-0c03f4d8fff2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d124ab73f4b4315550134f28ffad232b4a1c0ec2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612092"
---
# <a name="replace-usage-of-the-xp_sqlagent_proxy_account-extended-stored-procedure-with-new-stored-procedures"></a><span data-ttu-id="5a831-102">Utiliser de nouvelles procédures stockées à la place de la procédure stockée étendue xp_sqlagent_proxy_account</span><span class="sxs-lookup"><span data-stu-id="5a831-102">Replace usage of the xp_sqlagent_proxy_account extended stored procedure with new stored procedures</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5a831-103">Agent prend en charge plusieurs proxies.</span><span class="sxs-lookup"><span data-stu-id="5a831-103">Agent supports multiple proxies.</span></span> <span data-ttu-id="5a831-104">Vous définissez ces proxies à l'aide d'un nouvel ensemble de procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="5a831-104">You define these proxies by using a new set of stored procedures.</span></span> <span data-ttu-id="5a831-105">Pour plus d'informations sur les nouvelles procédures stockées de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez les rubriques suivantes dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="5a831-105">For more information about the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stored procedures, see the following topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   <span data-ttu-id="5a831-106">« sp_add_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)]) »</span><span class="sxs-lookup"><span data-stu-id="5a831-106">"sp_add_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="5a831-107">« sp_delete_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)]) »</span><span class="sxs-lookup"><span data-stu-id="5a831-107">"sp_delete_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="5a831-108">« sp_enum_login_for_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)]) »</span><span class="sxs-lookup"><span data-stu-id="5a831-108">"sp_enum_login_for_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="5a831-109">« sp_enum_proxy_for_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)]) »</span><span class="sxs-lookup"><span data-stu-id="5a831-109">"sp_enum_proxy_for_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="5a831-110">« sp_enum_sqlagent_subsystems ([!INCLUDE[tsql](../../includes/tsql-md.md)]) »</span><span class="sxs-lookup"><span data-stu-id="5a831-110">"sp_enum_sqlagent_subsystems ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="5a831-111">« sp_grant_proxy_to_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)]) »</span><span class="sxs-lookup"><span data-stu-id="5a831-111">"sp_grant_proxy_to_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="5a831-112">« sp_grant_login_to_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)]) »</span><span class="sxs-lookup"><span data-stu-id="5a831-112">"sp_grant_login_to_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="5a831-113">« sp_help_proxy" ([!INCLUDE[tsql](../../includes/tsql-md.md)]) »</span><span class="sxs-lookup"><span data-stu-id="5a831-113">"sp_help_proxy" ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="5a831-114">« sp_revoke_login_from_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)]) »</span><span class="sxs-lookup"><span data-stu-id="5a831-114">"sp_revoke_login_from_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="5a831-115">« sp_revoke_proxy_from_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)]) »</span><span class="sxs-lookup"><span data-stu-id="5a831-115">"sp_revoke_proxy_from_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
-   <span data-ttu-id="5a831-116">« sp_update_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)]) »</span><span class="sxs-lookup"><span data-stu-id="5a831-116">"sp_update_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])"</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5a831-117">Après la mise à niveau vers [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] , toutes les instructions qui utilisent le **xp_sqlagent_proxy_account** procédure stockée étendue ne fonctionneront pas.</span><span class="sxs-lookup"><span data-stu-id="5a831-117">After you upgrade to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], any statements that use the **xp_sqlagent_proxy_account** extended stored procedure will not work.</span></span> <span data-ttu-id="5a831-118">Utilisez **sp_xp_cmdshell_proxy_account** au lieu de **xp_sqlagent_proxy_account** pour définir le proxy pour **xp_cmdshell**.</span><span class="sxs-lookup"><span data-stu-id="5a831-118">Use **sp_xp_cmdshell_proxy_account** instead of **xp_sqlagent_proxy_account** to set the proxy for **xp_cmdshell**.</span></span>  
  
## <a name="component"></a><span data-ttu-id="5a831-119">Composant</span><span class="sxs-lookup"><span data-stu-id="5a831-119">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5a831-120">Agent</span><span class="sxs-lookup"><span data-stu-id="5a831-120">Agent</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a831-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5a831-121">See Also</span></span>  
 [<span data-ttu-id="5a831-122">Problèmes de mise à niveau de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="5a831-122">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
