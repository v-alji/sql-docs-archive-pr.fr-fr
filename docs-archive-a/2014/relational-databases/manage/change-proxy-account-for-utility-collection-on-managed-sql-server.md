---
title: Modifier le compte proxy pour le jeu d’collections de l’utilitaire sur un Managed Instance de SQL Server (Utilitaire SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ff37ba8b-a08c-4109-b6e2-5748c995a52c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19f60c607ed661ef42c1c1c0e48854cdfd69a912
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602143"
---
# <a name="change-the-proxy-account-for-the-utility-collection-set-on-a-managed-instance-of-sql-server-sql-server-utility"></a><span data-ttu-id="525d9-102">Modifier le compte proxy pour le jeu d'éléments de collecte de l'utilitaire sur une instance gérée de SQL Server (utilitaire SQL Server)</span><span class="sxs-lookup"><span data-stu-id="525d9-102">Change the Proxy Account for the Utility Collection Set on a Managed Instance of SQL Server (SQL Server Utility)</span></span>
  <span data-ttu-id="525d9-103">Cette rubrique explique comment modifier le compte proxy pour le jeu d'éléments de collecte de l'utilitaire sur une instance gérée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="525d9-103">This topic describes how to change the proxy account for the Utility Collection Set on a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="525d9-104">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="525d9-104">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-proxy-account-for-the-utility-collection-set-on-a-managed-instance-of-sql-server"></a><span data-ttu-id="525d9-105">Pour modifier le compte proxy pour le jeu d'éléments de collecte de l'utilitaire sur une instance gérée de SQL Server</span><span class="sxs-lookup"><span data-stu-id="525d9-105">To change the proxy account for the utility collection set on a managed instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="525d9-106">Supprimez l'instance gérée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de l'utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="525d9-106">Remove the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
    -   <span data-ttu-id="525d9-107">Dans l’ **Explorateur de l’utilitaire** dans SSMS, cliquez sur le nœud **Instances gérées** .</span><span class="sxs-lookup"><span data-stu-id="525d9-107">In **Utility Explorer** in SSMS, click on the **Managed Instances** node.</span></span>  
  
    -   <span data-ttu-id="525d9-108">Dans l’**Explorateur de l’utilitaire** en mode Liste, cliquez avec le bouton droit sur le nom de l’instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et sélectionnez **Supprimer une instance gérée…** . Pour plus d’informations, consultez [Supprimer une instance de SQL Server de l’utilitaire SQL Server](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="525d9-108">In the **Utility Explorer** list view, right-click the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name, and select **Remove Managed Instance...**. For more information, see [Remove an Instance of SQL Server from the SQL Server Utility](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span></span>  
  
2.  <span data-ttu-id="525d9-109">Réinscrivez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans l'utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="525d9-109">Enroll the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility again.</span></span>  
  
    -   <span data-ttu-id="525d9-110">Dans l’**Explorateur de l’utilitaire** dans SSMS, cliquez avec le bouton droit sur le nœud **Instances gérées** et sélectionnez **Ajouter une instance gérée…** .</span><span class="sxs-lookup"><span data-stu-id="525d9-110">In **Utility Explorer** in SSMS, right-click on the **Managed Instances** node, and select **Add Managed Instance...**.</span></span>  
  
    -   <span data-ttu-id="525d9-111">Suivez les indications de l'Assistant jusqu'au bout, en spécifiant le nouveau compte proxy.</span><span class="sxs-lookup"><span data-stu-id="525d9-111">Follow prompts to complete the wizard, specifying the new proxy account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="525d9-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="525d9-112">See Also</span></span>  
 <span data-ttu-id="525d9-113">[Fonctionnalités et tâches de l'utilitaire SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="525d9-113">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="525d9-114">Résolution des problèmes liés à l’utilitaire SQL Server</span><span class="sxs-lookup"><span data-stu-id="525d9-114">Troubleshoot the SQL Server Utility</span></span>](../../database-engine/troubleshoot-the-sql-server-utility.md)  
  
  
