---
title: Supprimer le témoin d’une session de mise en miroir de bases de données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], turning off
- witness [SQL Server], removing
- database mirroring [SQL Server], witness
ms.assetid: f3ce7afc-8936-4d35-80ce-d0f8fbc318d3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d5ede54aca3588a6fcd7cee8759112b606eac752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701796"
---
# <a name="remove-the-witness-from-a-database-mirroring-session-sql-server"></a><span data-ttu-id="08acd-102">Supprimer le témoin d'une session de mise en miroir de bases de données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="08acd-102">Remove the Witness from a Database Mirroring Session (SQL Server)</span></span>
  <span data-ttu-id="08acd-103">Cette rubrique explique comment supprimer un témoin depuis une session de mise en miroir de bases de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08acd-103">This topic describes how to remove a witness from a database mirroring session in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="08acd-104">À tout moment au cours d'une session de mise en miroir d'une base de données, le propriétaire de cette dernière peut désactiver le témoin pour cette session.</span><span class="sxs-lookup"><span data-stu-id="08acd-104">At any time during a database mirroring session, the database owner can turn off the witness for a database mirroring session.</span></span>  
  
 <span data-ttu-id="08acd-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="08acd-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="08acd-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="08acd-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="08acd-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="08acd-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="08acd-108">**Pour supprimer le témoin, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="08acd-108">**To Replace remove the witness, using:**</span></span>  
  
     [<span data-ttu-id="08acd-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="08acd-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="08acd-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="08acd-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="08acd-111">**Suivi :**  [Après avoir supprimé le témoin](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="08acd-111">**Follow Up:**  [After Removing the Witness](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="08acd-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="08acd-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="08acd-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="08acd-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="08acd-114">Autorisations</span><span class="sxs-lookup"><span data-stu-id="08acd-114">Permissions</span></span>  
 <span data-ttu-id="08acd-115">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="08acd-115">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="08acd-116">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="08acd-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-the-witness"></a><span data-ttu-id="08acd-117">Pour supprimer le témoin</span><span class="sxs-lookup"><span data-stu-id="08acd-117">To remove the witness</span></span>  
  
1.  <span data-ttu-id="08acd-118">Connectez-vous à l'instance du serveur principal puis, dans le volet **Explorateur d'objets** , cliquez sur le nom du serveur pour développer l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="08acd-118">Connect to the principal server instance and, in the **Object Explorer** pane, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="08acd-119">Développez **Bases de données**, puis sélectionnez la base de données dont vous souhaitez supprimer le témoin.</span><span class="sxs-lookup"><span data-stu-id="08acd-119">Expand **Databases**, and select the database whose witness you want to remove.</span></span>  
  
3.  <span data-ttu-id="08acd-120">Cliquez avec le bouton droit sur la base de données, sélectionnez **Tâches**, puis cliquez sur **Miroir**.</span><span class="sxs-lookup"><span data-stu-id="08acd-120">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="08acd-121">La page **Mise en miroir** de la boîte de dialogue **Propriétés de la base de données** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="08acd-121">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="08acd-122">Pour supprimer le témoin, supprimez son adresse réseau de serveur du champ **Témoin** .</span><span class="sxs-lookup"><span data-stu-id="08acd-122">To remove the witness, delete its server network address from the **Witness** field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="08acd-123">Si vous passez du mode de sécurité élevée avec basculement automatique au mode haute performance, le champ **Témoin** est automatiquement supprimé.</span><span class="sxs-lookup"><span data-stu-id="08acd-123">If you switch from high-safety mode with automatic failover to high-performance mode, the **Witness** field is automatically cleared.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="08acd-124">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="08acd-124">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-the-witness"></a><span data-ttu-id="08acd-125">Pour supprimer le témoin</span><span class="sxs-lookup"><span data-stu-id="08acd-125">To remove the witness</span></span>  
  
1.  <span data-ttu-id="08acd-126">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)] sur l'une des instances de serveur partenaire.</span><span class="sxs-lookup"><span data-stu-id="08acd-126">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on either partner server instance.</span></span>  
  
2.  <span data-ttu-id="08acd-127">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="08acd-127">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="08acd-128">Émettez l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="08acd-128">Issue the following statement:</span></span>  
  
     <span data-ttu-id="08acd-129">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *nom_base_de_données* SET WITNESS OFF</span><span class="sxs-lookup"><span data-stu-id="08acd-129">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET WITNESS OFF</span></span>  
  
     <span data-ttu-id="08acd-130">où *nom_base_de_données* est le nom de la base de données en miroir.</span><span class="sxs-lookup"><span data-stu-id="08acd-130">where *database_name* is the name of the mirrored database.</span></span>  
  
     <span data-ttu-id="08acd-131">L'exemple suivant supprime le témoin de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08acd-131">The following example removes the witness from the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET WITNESS OFF ;  
    ```  
  
##  <a name="follow-up-after-removing-the-witness"></a><a name="FollowUp"></a><span data-ttu-id="08acd-132">Suivi : après avoir supprimé le témoin</span><span class="sxs-lookup"><span data-stu-id="08acd-132">Follow Up: After Removing the Witness</span></span>  
 <span data-ttu-id="08acd-133">La désactivation du témoin modifie le [mode d’opération](database-mirroring-operating-modes.md)conformément au paramètre de sécurité des transactions :</span><span class="sxs-lookup"><span data-stu-id="08acd-133">Turning off the witness changes the [operating mode](database-mirroring-operating-modes.md)in accordance with the transaction-safety setting:</span></span>  
  
-   <span data-ttu-id="08acd-134">Si la sécurité des transactions a la valeur FULL (valeur par défaut), la session utilise le mode synchrone haute sécurité sans basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="08acd-134">If transaction safety is set to FULL (the default), the session uses high-safety, synchronous mode without automatic failover.</span></span>  
  
-   <span data-ttu-id="08acd-135">Si la sécurité des transactions a la valeur OFF (désactivée), la session agit de manière asynchrone (en mode hautes performances) sans nécessiter de quorum.</span><span class="sxs-lookup"><span data-stu-id="08acd-135">If transaction safety is set to OFF, the session operates asynchronously (in high-performance mode) without requiring quorum.</span></span> <span data-ttu-id="08acd-136">Lorsque la sécurité des transactions est désactivée, il est vivement recommandé de désactiver également le témoin.</span><span class="sxs-lookup"><span data-stu-id="08acd-136">Whenever transaction safety is turned off, we strongly recommend also turning the witness off.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="08acd-137">Le paramètre de sécurité des transactions de la base de données est enregistré pour chaque serveur partenaire dans la vue de catalogue [sys.database_mirroring](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql) des colonnes **mirroring_safety_level** et **mirroring_safety_level_desc**.</span><span class="sxs-lookup"><span data-stu-id="08acd-137">The transaction safety setting of the database is recorded on each partner in the [sys.database_mirroring](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql) catalog view in the **mirroring_safety_level** and **mirroring_safety_level_desc** columns.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="08acd-138">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="08acd-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="08acd-139">Ajouter un témoin de mise en miroir de bases de données à l’aide de l’authentification Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="08acd-139">Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="08acd-140">Ajouter ou remplacer un témoin de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="08acd-140">Add or Replace a Database Mirroring Witness &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/add-or-replace-a-database-mirroring-witness-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="08acd-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="08acd-141">See Also</span></span>  
 <span data-ttu-id="08acd-142">[Mise en miroir de bases de données ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="08acd-142">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="08acd-143">[Modifier la sécurité des transactions dans une session de mise en miroir de bases de données &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="08acd-143">[Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md) </span></span>  
 <span data-ttu-id="08acd-144">[Ajouter un témoin de mise en miroir de bases de données à l’aide de l’authentification Windows &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="08acd-144">[Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md) </span></span>  
 [<span data-ttu-id="08acd-145">Témoin de mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="08acd-145">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
