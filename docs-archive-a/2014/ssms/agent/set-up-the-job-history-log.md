---
title: Configurer le journal d’historique des travaux | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: 018e5c49-d3a0-4504-851a-f70996a34bb7
author: stevestein
ms.author: sstein
ms.openlocfilehash: cb42e1daaee8a3a9e5ae9cc3c09a8cc42dcbff56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695251"
---
# <a name="set-up-the-job-history-log"></a><span data-ttu-id="7e807-102">Configurer le journal d'historique des travaux</span><span class="sxs-lookup"><span data-stu-id="7e807-102">Set Up the Job History Log</span></span>
  <span data-ttu-id="7e807-103">Cette rubrique décrit comment configurer le journal d' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] historique des travaux de l’agent.</span><span class="sxs-lookup"><span data-stu-id="7e807-103">This topic describes how to set up the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log.</span></span>  
  
-   <span data-ttu-id="7e807-104">**Avant de commencer :**  [Sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="7e807-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="7e807-105">**Pour configurer le journal d’historique des travaux, avec :**  [SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="7e807-105">**To setup the job history log, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7e807-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="7e807-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7e807-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7e807-107">Security</span></span>  
 <span data-ttu-id="7e807-108">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="7e807-108">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="7e807-109">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7e807-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="7e807-110">**Pour définir le journal d'historique des travaux**</span><span class="sxs-lookup"><span data-stu-id="7e807-110">**To set up the job history log**</span></span>  
  
1.  <span data-ttu-id="7e807-111">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="7e807-111">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7e807-112">Cliquez avec le bouton droit sur **SQL Server Agent**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7e807-112">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7e807-113">Dans la boîte de dialogue **Propriétés de l'Agent SQL Server** , sélectionnez la page **Historique** .</span><span class="sxs-lookup"><span data-stu-id="7e807-113">In the **SQL Server Agent Properties** dialog box, select the **History** page.</span></span>  
  
4.  <span data-ttu-id="7e807-114">Choisissez parmi les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="7e807-114">Choose from the following options:</span></span>  
  
    1.  <span data-ttu-id="7e807-115">Activez la case à cocher **Limiter la taille de l'historique des travaux**, puis tapez le nombre maximal de lignes pour le journal de l'historique des travaux, ainsi que le nombre maximal de lignes par travail.</span><span class="sxs-lookup"><span data-stu-id="7e807-115">Check **Limit size of job history log**, and then type the maximum number of rows for the job history log, and the maximum number of rows per job.</span></span>  
  
    2.  <span data-ttu-id="7e807-116">Activez la case à cocher **Supprimer automatiquement l'historique de l'agent**, puis spécifiez une période de temps, de telle façon que l'historique antérieur à cette période soit purgé du journal.</span><span class="sxs-lookup"><span data-stu-id="7e807-116">Check **Automatically remove agent history**, and specify a time period, such that history older than this period will be purged from the log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e807-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7e807-117">See Also</span></span>  
 <span data-ttu-id="7e807-118">[Implémenter des travaux](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="7e807-118">[Implement Jobs](implement-jobs.md) </span></span>  
 <span data-ttu-id="7e807-119">[Surveiller l’activité des travaux](monitor-job-activity.md) </span><span class="sxs-lookup"><span data-stu-id="7e807-119">[Monitor Job Activity](monitor-job-activity.md) </span></span>  
 [<span data-ttu-id="7e807-120">Créer des travaux</span><span class="sxs-lookup"><span data-stu-id="7e807-120">Create Jobs</span></span>](create-jobs.md)  
  
  
