---
title: Considérations relatives à l’exécution de jeux d’éléments de collecte de l’utilitaire et non-utilitaire sur la même instance de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ca7ee9b3-ef9a-4ba4-83d0-9ee9f80dab27
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67df2d65cc9da4026377e77c152c0d78f3749932
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611066"
---
# <a name="considerations-for-running-utility-and-non-utility-collection-sets-on-the-same-instance-of-sql-server"></a><span data-ttu-id="9ec60-102">Considérations sur l'exécution de jeux d'éléments de collecte de l'utilitaire et non-utilitaire sur la même instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ec60-102">Considerations for Running Utility and non-Utility Collection Sets on the Same Instance of SQL Server</span></span>
  <span data-ttu-id="9ec60-103">Le jeu d'éléments de collecte de l'utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est pris en charge côte à côte avec les jeux d'éléments de collecte d'utilitaires non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ec60-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection set is supported side-by-side with non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets.</span></span> <span data-ttu-id="9ec60-104">Autrement dit, une instance gérée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut être surveillée par d'autres jeux d'éléments de collecte bien qu'elle soit membre d'un utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ec60-104">That is, a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be monitored by other collection sets while it is a member of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="9ec60-105">Toutefois, vous devez désactiver les fonctionnalités du jeu d'éléments de collecte de l'utilitaire non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pendant que l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est inscrite dans l'utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ec60-105">However, you must disable non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility data collection functionality while the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is being enrolled into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
 <span data-ttu-id="9ec60-106">Une fois l'instance inscrite avec l'UCP, vous pouvez redémarrer le jeu d'éléments de collecte de l'utilitaire non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ec60-106">After the instance is enrolled with the UCP, you can restart non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets.</span></span> <span data-ttu-id="9ec60-107">Notez, toutefois, que tous les jeux d'éléments de collecte sur l'instance gérée téléchargeront leurs données dans l'entrepôt de données de gestion de l'utilitaire (UMDW). Le nom de fichier UMDW est sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="9ec60-107">Note, however, that all collection sets on the managed instance will upload their data to the utility management data warehouse (UMDW); the UMDW file name is sysutility_mdw.</span></span>  
  
 <span data-ttu-id="9ec60-108">Pour exécuter des jeux d'éléments de collecte d'utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] côte à côte avec des jeux d'éléments de collecte d'utilitaire non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , prenez en considération les points suivants :</span><span class="sxs-lookup"><span data-stu-id="9ec60-108">To run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets side-by-side with non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets, consider the following points:</span></span>  
  
-   <span data-ttu-id="9ec60-109">Les jeux d'éléments de collecte côte à côte sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="9ec60-109">Side-by-side collection sets are supported.</span></span>  
  
-   <span data-ttu-id="9ec60-110">Vous devez désactiver les collecteurs de données existants en inscrivant des instances dans l'utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ec60-110">You must disable existing data collectors while enrolling instances into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
-   <span data-ttu-id="9ec60-111">Pour satisfaire aux exigences de validation, vous devez exécuter les procédures stockées suivantes sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avant de créer un UCP, et sur une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avant de l'inscrire dans l'utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="9ec60-111">To pass validation requirements, you must run the following stored procedures on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you create a UCP, and on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you enroll it into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility:</span></span>  
  
    ```  
    exec msdb.dbo.sp_syscollector_set_warehouse_database_name NULL  
    exec msdb.dbo.sp_syscollector_set_warehouse_instance_name NULL  
    ```  
  
     <span data-ttu-id="9ec60-112">Si vous n'exécutez pas ces procédures stockées avant de lancer l'Assistant Créer un UCP ou l'Assistant Ajouter une instance gérée, l'opération échouera.</span><span class="sxs-lookup"><span data-stu-id="9ec60-112">If you do not run these stored procedures before you launch the Create UCP Wizard or Add Managed Instance Wizard, the operation will fail.</span></span>  
  
-   <span data-ttu-id="9ec60-113">Vous devez utiliser l'UMDW (sysutility_mdw) de l'utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour tous les jeux d'éléments de collecte sur une instance gérée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ec60-113">You must use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility UMDW (sysutility_mdw) for all collection sets on a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ec60-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9ec60-114">See Also</span></span>  
 <span data-ttu-id="9ec60-115">[Fonctionnalités et tâches de l'utilitaire SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="9ec60-115">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="9ec60-116">Configurer votre entrepôt de données de point de contrôle de l’utilitaire &#40;utilitaire SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9ec60-116">Configure Your Utility Control Point Data Warehouse &#40;SQL Server Utility&#41;</span></span>](configure-your-utility-control-point-data-warehouse-sql-server-utility.md)  
  
  
