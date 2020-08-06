---
title: Supprimer un point de contrôle de l’utilitaire (utilitaire SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c048a416-900e-4c77-8243-e0f0d8b94068
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fe4ebb9de3f7644b4cff5c7dbfb34e50be7e8993
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614586"
---
# <a name="remove-a-utility-control-point-sql-server-utility"></a><span data-ttu-id="5de5e-102">Supprimer un point de contrôle de l'utilitaire (utilitaire SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5de5e-102">Remove a Utility Control Point (SQL Server Utility)</span></span>
  <span data-ttu-id="5de5e-103">Cette rubrique explique comment supprimer un point de contrôle de l'utilitaire (UCP) [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5de5e-103">This topic describes how to remove a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utility control point (UCP) from the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5de5e-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="5de5e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5de5e-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="5de5e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5de5e-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="5de5e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5de5e-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5de5e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5de5e-108">**Pour supprimer un point de contrôle de l'utilitaire, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="5de5e-108">**To remove a Utility Control Point, using:**</span></span>  
  
     [<span data-ttu-id="5de5e-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5de5e-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5de5e-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5de5e-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5de5e-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="5de5e-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="5de5e-112">Avant d'utiliser cette procédure pour supprimer le point de contrôle de l'utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , notez les conditions suivantes.</span><span class="sxs-lookup"><span data-stu-id="5de5e-112">Before you use this procedure to remove the UCP from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, note the following requirements.</span></span> <span data-ttu-id="5de5e-113">La procédure stockée effectuera des vérifications des conditions préalables dans le cadre de l'opération.</span><span class="sxs-lookup"><span data-stu-id="5de5e-113">The stored procedure will run prerequisite checks as part of the operation.</span></span>  
  
-   <span data-ttu-id="5de5e-114">Avant d'exécuter cette procédure, toutes les instances gérées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doivent être supprimées du point de contrôle de l'utilitaire.</span><span class="sxs-lookup"><span data-stu-id="5de5e-114">Before you run this procedure, all managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be removed from the UCP.</span></span> <span data-ttu-id="5de5e-115">Notez que le point de contrôle de l'utilitaire est une instance gérée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5de5e-115">Note that the UCP is a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5de5e-116">Pour plus d’informations, consultez [Supprimer une instance de SQL Server de l’utilitaire SQL Server](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="5de5e-116">From more information, see [Remove an Instance of SQL Server from the SQL Server Utility](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span></span>  
  
-   <span data-ttu-id="5de5e-117">Cette procédure doit être exécutée sur un ordinateur qui est un UCP.</span><span class="sxs-lookup"><span data-stu-id="5de5e-117">This procedure must be run on a computer that is a UCP.</span></span>  
  
-   <span data-ttu-id="5de5e-118">Si l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de laquelle le point de contrôle de l'utilitaire est supprimé comporte un jeu d'éléments de collecte de données qui n'est pas d'utilitaire, la base de données UMDW (sysutility_mdw) ne sera pas supprimée par la procédure.</span><span class="sxs-lookup"><span data-stu-id="5de5e-118">If the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the UCP was removed has a non-Utility data collection set, the UMDW database (sysutility_mdw) will not be dropped by the procedure.</span></span> <span data-ttu-id="5de5e-119">Si tel est le cas, la base de données UMDW (sysutility_mdw) doit être supprimée manuellement avant que le point de contrôle de l’utilitaire soit à nouveau créé.</span><span class="sxs-lookup"><span data-stu-id="5de5e-119">If this is the case, the UMDW database (sysutility_mdw) must be dropped manually before the UCP can be created again.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5de5e-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5de5e-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5de5e-121">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5de5e-121">Permissions</span></span>  
 <span data-ttu-id="5de5e-122">Cette procédure doit être exécutée par un utilisateur disposant d'autorisations `sysadmin` ; les mêmes autorisations sont requises pour créer un point de contrôle de l'utilitaire.</span><span class="sxs-lookup"><span data-stu-id="5de5e-122">This procedure must be run by a user with `sysadmin` permissions; the same permissions required to create a UCP.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5de5e-123">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5de5e-123">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-a-utility-control-point"></a><span data-ttu-id="5de5e-124">Pour supprimer un point de contrôle de l'utilitaire</span><span class="sxs-lookup"><span data-stu-id="5de5e-124">To remove a Utility Control Point</span></span>  
  
1.  <span data-ttu-id="5de5e-125">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5de5e-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5de5e-126">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5de5e-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5de5e-127">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5de5e-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
```  
EXEC msdb.dbo.sp_sysutility_ucp_remove;  
```  
  
## <a name="see-also"></a><span data-ttu-id="5de5e-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5de5e-128">See Also</span></span>  
 <span data-ttu-id="5de5e-129">[Fonctionnalités et tâches de l'utilitaire SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="5de5e-129">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 <span data-ttu-id="5de5e-130">[Utiliser l'Explorateur de l'utilitaire pour gérer l'Utilitaire SQL Server](use-utility-explorer-to-manage-the-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="5de5e-130">[Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="5de5e-131">Résolution des problèmes liés à l’utilitaire SQL Server</span><span class="sxs-lookup"><span data-stu-id="5de5e-131">Troubleshoot the SQL Server Utility</span></span>](../../database-engine/troubleshoot-the-sql-server-utility.md)  
  
  
