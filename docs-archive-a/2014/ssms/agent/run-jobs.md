---
title: Exécuter des travaux | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, manually running
- multiserver job processing [SQL Server]
- jobs [SQL Server Agent], manually running
- manual job processing [SQL Server]
ms.assetid: cd445949-dc10-42fc-8785-4db74c9723ad
author: stevestein
ms.author: sstein
ms.openlocfilehash: 652399f44888852d7263020de0fc7e44f3f942e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603774"
---
# <a name="run-jobs"></a><span data-ttu-id="ac2b1-102">Exécuter des travaux</span><span class="sxs-lookup"><span data-stu-id="ac2b1-102">Run Jobs</span></span>
  <span data-ttu-id="ac2b1-103">Pour gérer des travaux de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous pouvez utiliser [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], des procédures stockées [!INCLUDE[tsql](../../includes/tsql-md.md)] ou des Objets de gestion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac2b1-103">To manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures, or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ac2b1-104">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ac2b1-104">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ac2b1-105">**Description**</span><span class="sxs-lookup"><span data-stu-id="ac2b1-105">**Description**</span></span>|<span data-ttu-id="ac2b1-106">**Rubrique**</span><span class="sxs-lookup"><span data-stu-id="ac2b1-106">**Topic**</span></span>|  
|<span data-ttu-id="ac2b1-107">Explique comment lancer l'exécution d'un travail de l'Agent [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac2b1-107">Describes how to start running a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="ac2b1-108">Démarrer un travail</span><span class="sxs-lookup"><span data-stu-id="ac2b1-108">Start a Job</span></span>](start-a-job.md)|  
|<span data-ttu-id="ac2b1-109">Explique comment arrêter un travail de l'Agent [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac2b1-109">Describes how to stop a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="ac2b1-110">Arrêter un travail</span><span class="sxs-lookup"><span data-stu-id="ac2b1-110">Stop a Job</span></span>](stop-a-job.md)|  
|<span data-ttu-id="ac2b1-111">Explique comment désactiver ou activer un travail [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="ac2b1-111">Describes how to disable or enable a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>|[<span data-ttu-id="ac2b1-112">Disable or Enable a Job</span><span class="sxs-lookup"><span data-stu-id="ac2b1-112">Disable or Enable a Job</span></span>](disable-or-enable-a-job.md)|  
  
## <a name="see-also"></a><span data-ttu-id="ac2b1-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ac2b1-113">See Also</span></span>  
 [<span data-ttu-id="ac2b1-114">dbo.sysdownloadlist &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ac2b1-114">dbo.sysdownloadlist &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysdownloadlist-transact-sql)  
  
  
