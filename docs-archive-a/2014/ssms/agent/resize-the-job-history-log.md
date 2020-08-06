---
title: Redimensionner le journal d’historique des travaux | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- resizing job history log
- size [SQL Server], job history log
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: ddee1ce8-9d1b-4017-9894-bf7256aed95d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4c25cc43295d47b2bc19d48b5b257dbbe6bcfe9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603775"
---
# <a name="resize-the-job-history-log"></a><span data-ttu-id="d5541-102">Resize the Job History Log</span><span class="sxs-lookup"><span data-stu-id="d5541-102">Resize the Job History Log</span></span>
  <span data-ttu-id="d5541-103">Cette rubrique explique comment définir des limites de taille pour les [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] journaux d’historique des travaux de l’agent dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5541-103">This topic describes how to set size limits for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history logs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="d5541-104">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="d5541-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d5541-105">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d5541-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d5541-106">**Pour définir des limites de taille pour les journaux d'historique des travaux, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="d5541-106">**To set size limits for job history logs, using:**</span></span>  
  
     [<span data-ttu-id="d5541-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d5541-107">SQL Server Management Studio</span></span>](#SSMS)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d5541-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d5541-108">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d5541-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d5541-109">Security</span></span>  
 <span data-ttu-id="d5541-110">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="d5541-110">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="d5541-111">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d5541-111">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-resize-the-job-history-log-based-on-raw-size"></a><span data-ttu-id="d5541-112">Pour redimensionner le journal d'historique des travaux en fonction de sa taille brute</span><span class="sxs-lookup"><span data-stu-id="d5541-112">To resize the job history log based on raw size</span></span>  
  
1.  <span data-ttu-id="d5541-113">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="d5541-113">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d5541-114">Cliquez avec le bouton droit sur **SQL Server Agent**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d5541-114">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="d5541-115">Sélectionnez la page **Historique** , puis vérifiez que la case **Limiter la taille du journal d’historique des travaux**est cochée.</span><span class="sxs-lookup"><span data-stu-id="d5541-115">Select the **History** page, and then confirm that **Limit size of job history log**is checked.</span></span>  
  
4.  <span data-ttu-id="d5541-116">Dans la zone **Taille maximale du journal d'historique des travaux** , entrez le nombre maximal de lignes autorisées dans le journal d'historique des travaux.</span><span class="sxs-lookup"><span data-stu-id="d5541-116">In the **Maximum job history log size** box, enter the maximum number of rows the job history log should allow.</span></span>  
  
5.  <span data-ttu-id="d5541-117">Dans la zone **Nombre maximal de lignes d'historique des travaux par travail** , entrez le nombre maximal de lignes d'historique des travaux autorisées pour un travail.</span><span class="sxs-lookup"><span data-stu-id="d5541-117">In the **Maximum job history rows per job** box, enter the maximum number of job history rows to allow for a job.</span></span>  
  
#### <a name="to-resize-the-job-history-log-based-on-time"></a><span data-ttu-id="d5541-118">Pour redimensionner le journal d'historique des travaux en fonction du temps</span><span class="sxs-lookup"><span data-stu-id="d5541-118">To resize the job history log based on time</span></span>  
  
1.  <span data-ttu-id="d5541-119">Dans **l’Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], puis développez-la.</span><span class="sxs-lookup"><span data-stu-id="d5541-119">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d5541-120">Cliquez avec le bouton droit sur **SQL Server Agent**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d5541-120">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="d5541-121">Sélectionnez la page **Historique** , puis cliquez sur **Supprimer automatiquement l'historique de l'agent**.</span><span class="sxs-lookup"><span data-stu-id="d5541-121">Select the **History** page, and then click **Automatically remove agent history**.</span></span>  
  
4.  <span data-ttu-id="d5541-122">Sélectionnez le nombre approprié de **Jour(s)**, **Semaine(s)** ou **Mois(s)**.</span><span class="sxs-lookup"><span data-stu-id="d5541-122">Select the appropriate number of **Days(s)**, **Week(s)**, or **Month(s)**.</span></span>  
  
  
