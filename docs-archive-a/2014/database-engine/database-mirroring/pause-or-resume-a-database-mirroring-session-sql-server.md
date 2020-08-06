---
title: Suspendre ou reprendre une session de mise en miroir de bases de données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- resuming database mirroring
- database mirroring [SQL Server], sessions
- database mirroring [SQL Server], pausing
- database mirroring [SQL Server], resuming
- pausing database mirroring
ms.assetid: 05ede3b4-6abe-4442-abb7-9f5aee1d6bc0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b8a9e30bed3ff268fcfdc6e352ad15ebedfe4e8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701861"
---
# <a name="pause-or-resume-a-database-mirroring-session-sql-server"></a><span data-ttu-id="332b7-102">Suspendre ou reprendre une session de mise en miroir de bases de données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="332b7-102">Pause or Resume a Database Mirroring Session (SQL Server)</span></span>
  <span data-ttu-id="332b7-103">Cette rubrique explique comment suspendre ou reprendre la mise en miroir de bases de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="332b7-103">This topic describes how to pause or resume database mirroring in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="332b7-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="332b7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="332b7-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="332b7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="332b7-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="332b7-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="332b7-107">**Sur ReplaceThisText, à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="332b7-107">**To ReplaceThisText, using:**</span></span>  
  
     [<span data-ttu-id="332b7-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="332b7-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="332b7-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="332b7-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="332b7-110">**Suivi :**  [Après avoir suspendu ou repris la mise en miroir de bases de données](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="332b7-110">**Follow Up:**  [After Pausing or Resuming Database Mirroring](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="332b7-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="332b7-111">Before You Begin</span></span>  
 <span data-ttu-id="332b7-112">Vous pouvez à tout moment suspendre une session de mise en miroir de bases de données afin d'améliorer les performances pendant les goulots d'étranglement. De même, vous pouvez reprendre une session interrompue à tout moment.</span><span class="sxs-lookup"><span data-stu-id="332b7-112">At any time, you can suspend a database mirroring session, which might improve performance during bottlenecks, and you can resume a suspended session at any time.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="332b7-113">Après un service forcé, lorsque le serveur principal d'origine se reconnecte, la mise en miroir est suspendue.</span><span class="sxs-lookup"><span data-stu-id="332b7-113">After a forced service, when the original principal server reconnects, mirroring is suspended.</span></span> <span data-ttu-id="332b7-114">La reprise de la mise en miroir dans cette situation peut entraîner des pertes de données sur le serveur principal d'origine.</span><span class="sxs-lookup"><span data-stu-id="332b7-114">Resuming mirroring in this situation could possibly cause data loss on the original principal server.</span></span> <span data-ttu-id="332b7-115">Pour plus d’informations sur la gestion des problèmes éventuels de perte de données, consultez [Basculement de rôle durant une session de mise en miroir de bases de données &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="332b7-115">For information about managing the potential data loss, see [Role Switching During a Database Mirroring Session &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="332b7-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="332b7-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="332b7-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="332b7-117">Permissions</span></span>  
 <span data-ttu-id="332b7-118">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="332b7-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="332b7-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="332b7-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="332b7-120">Pour suspendre ou reprendre une session de mise en miroir de bases de données, utilisez la page **Mise en miroir** de la boîte de dialogue Propriétés de la base de données.</span><span class="sxs-lookup"><span data-stu-id="332b7-120">To pause or resume a database mirroring session use the **Database Properties Mirroring** page.</span></span>  
  
#### <a name="to-pause-or-resume-database-mirroring"></a><span data-ttu-id="332b7-121">Pour suspendre ou reprendre la mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="332b7-121">To pause or resume database mirroring</span></span>  
  
1.  <span data-ttu-id="332b7-122">Lors d'une session de mise en miroir de bases de données, connectez-vous à l'instance du serveur principal, puis, dans l'Explorateur d'objets, cliquez sur le nom du serveur pour développer l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="332b7-122">During a database mirroring session, connect to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="332b7-123">Développez le nœud **Bases de données**et sélectionnez la base de données.</span><span class="sxs-lookup"><span data-stu-id="332b7-123">Expand **Databases**, and select the database.</span></span>  
  
3.  <span data-ttu-id="332b7-124">Cliquez avec le bouton droit sur la base de données, sélectionnez **Tâches**, puis cliquez sur **Miroir**.</span><span class="sxs-lookup"><span data-stu-id="332b7-124">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="332b7-125">La page **Mise en miroir** de la boîte de dialogue **Propriétés de la base de données** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="332b7-125">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="332b7-126">Pour suspendre la session, cliquez sur **Suspendre**.</span><span class="sxs-lookup"><span data-stu-id="332b7-126">To pause the session, click **Pause**.</span></span>  
  
     <span data-ttu-id="332b7-127">Vous êtes invité à confirmer l'opération ; si vous cliquez sur **Oui**, la session est suspendue et le bouton devient **Reprendre**.</span><span class="sxs-lookup"><span data-stu-id="332b7-127">A prompt asks for confirmation; if you click **Yes**, the session is paused, and the button changes to **Resume**.</span></span>  
  
     <span data-ttu-id="332b7-128">Pour plus d’informations sur les effets de la suspension d’une session, consultez [Suspension et reprise de la mise en miroir de bases de données &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="332b7-128">For more information about the impact of pausing a session, see [Pausing and Resuming Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="332b7-129">Pour reprendre la session, cliquez sur **Reprendre**.</span><span class="sxs-lookup"><span data-stu-id="332b7-129">To resume the session, click **Resume**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="332b7-130">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="332b7-130">Using Transact-SQL</span></span>  
  
#### <a name="to-pause-database-mirroring"></a><span data-ttu-id="332b7-131">Pour suspendre la mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="332b7-131">To pause database mirroring</span></span>  
  
1.  <span data-ttu-id="332b7-132">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)] de l'un des partenaires.</span><span class="sxs-lookup"><span data-stu-id="332b7-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for either partner.</span></span>  
  
2.  <span data-ttu-id="332b7-133">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="332b7-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="332b7-134">Soumettez l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante :</span><span class="sxs-lookup"><span data-stu-id="332b7-134">Issue the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
     <span data-ttu-id="332b7-135">ALTER DATABASE *nom_base_de_données* SET PARTNER SUSPEND</span><span class="sxs-lookup"><span data-stu-id="332b7-135">ALTER DATABASE *database_name* SET PARTNER SUSPEND</span></span>  
  
     <span data-ttu-id="332b7-136">où *nom_base_de_données* est la base de données en miroir dont vous voulez suspendre la session.</span><span class="sxs-lookup"><span data-stu-id="332b7-136">where *database_name* is the mirrored database whose session you want to you want to suspend.</span></span>  
  
     <span data-ttu-id="332b7-137">L'exemple suivant suspend l'exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="332b7-137">The following example pauses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER SUSPEND;  
    ```  
  
##### <a name="to-resume-database-mirroring"></a><span data-ttu-id="332b7-138">Pour reprendre la mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="332b7-138">To resume database mirroring</span></span>  
  
1.  <span data-ttu-id="332b7-139">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)] de l'un des partenaires.</span><span class="sxs-lookup"><span data-stu-id="332b7-139">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for either partner.</span></span>  
  
2.  <span data-ttu-id="332b7-140">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="332b7-140">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="332b7-141">Émettez l'instruction Transact-SQL suivante :</span><span class="sxs-lookup"><span data-stu-id="332b7-141">Issue the following Transact-SQL statement:</span></span>  
  
     <span data-ttu-id="332b7-142">ALTER DATABASE *nom_base_de_données* SET PARTNER RESUME</span><span class="sxs-lookup"><span data-stu-id="332b7-142">ALTER DATABASE *database_name* SET PARTNER RESUME</span></span>  
  
     <span data-ttu-id="332b7-143">où *nom_base_de_données* est la base de données en miroir dont vous voulez reprendre la session.</span><span class="sxs-lookup"><span data-stu-id="332b7-143">where *database_name* is the mirrored database whose session you want to resume.</span></span>  
  
     <span data-ttu-id="332b7-144">L'exemple suivant suspend l'exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="332b7-144">The following example pauses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER RESUME;  
    ```  
  
##  <a name="follow-up-after-pausing-or-resuming-database-mirroring"></a><a name="FollowUp"></a> <span data-ttu-id="332b7-145">Suivi : après avoir suspendu ou repris la mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="332b7-145">Follow Up: After Pausing or Resuming Database Mirroring</span></span>  
  
-   <span data-ttu-id="332b7-146">**Après avoir suspendu la mise en miroir de bases de données**</span><span class="sxs-lookup"><span data-stu-id="332b7-146">**After pausing database mirroring**</span></span>  
  
     <span data-ttu-id="332b7-147">Sur la base de données primaire, prenez des précautions pour éviter la saturation du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="332b7-147">On the primary database, take precautions to avoid a full transaction log.</span></span> <span data-ttu-id="332b7-148">Pour plus d'informations, consultez [Journal des transactions &#40;SQL Server&#41;](../../relational-databases/logs/the-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="332b7-148">For more information, see [The Transaction Log &#40;SQL Server&#41;](../../relational-databases/logs/the-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="332b7-149">**Après avoir repris la mise en miroir de bases de données**</span><span class="sxs-lookup"><span data-stu-id="332b7-149">**After resuming database mirroring**</span></span>  
  
     <span data-ttu-id="332b7-150">La reprise de la mise en miroir de la base de données place la base de données miroir dans l'état Synchronisation.</span><span class="sxs-lookup"><span data-stu-id="332b7-150">Resuming database mirroring places the mirror database in the SYNCHRONIZING state.</span></span> <span data-ttu-id="332b7-151">Si le niveau de sécurité est FULL, le miroir récupère le principal et la base de données miroir entre dans l'état Synchronisé.</span><span class="sxs-lookup"><span data-stu-id="332b7-151">If the safety level is FULL, the mirror catches up with the principal and the mirror database enters the SYNCHRONIZED state.</span></span> <span data-ttu-id="332b7-152">À ce stade, le basculement devient possible.</span><span class="sxs-lookup"><span data-stu-id="332b7-152">At this point, failover becomes possible.</span></span> <span data-ttu-id="332b7-153">Si le serveur témoin est présent et activé, le basculement automatique est possible.</span><span class="sxs-lookup"><span data-stu-id="332b7-153">If the witness is present and ON, automatic failover is possible.</span></span> <span data-ttu-id="332b7-154">En l'absence de serveur témoin, le basculement manuel est possible.</span><span class="sxs-lookup"><span data-stu-id="332b7-154">In the absence of a witness, manual failover is possible.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="332b7-155">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="332b7-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="332b7-156">Supprimer une mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="332b7-156">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](remove-database-mirroring-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="332b7-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="332b7-157">See Also</span></span>  
 [<span data-ttu-id="332b7-158">Mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="332b7-158">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
