---
title: Activer les index et contraintes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], enabling
- nonclustered indexes [SQL Server], enabling a disabled index
- index enabling [SQL Server]
- disabled indexes [SQL Server], how to enable
- constraints [SQL Server], enabling
- clustered indexes, enabling disabled indexes
ms.assetid: c55c8865-322e-4ab0-ba04-ea1f56735353
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d4e79689b80a40d00958fa557fe51df2adf9c14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614060"
---
# <a name="enable-indexes-and-constraints"></a><span data-ttu-id="db569-102">Activer les index et contraintes</span><span class="sxs-lookup"><span data-stu-id="db569-102">Enable Indexes and Constraints</span></span>
  <span data-ttu-id="db569-103">Cette rubrique explique comment activer un index désactivé dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db569-103">This topic describes how to enable a disabled index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="db569-104">Lorsqu'un index est désactivé, il reste à l'état désactivé tant qu'il n'est pas reconstruit ou supprimé</span><span class="sxs-lookup"><span data-stu-id="db569-104">After an index is disabled, it remains in a disabled state until it is rebuilt or dropped</span></span>  
  
 <span data-ttu-id="db569-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="db569-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="db569-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="db569-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="db569-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="db569-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="db569-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="db569-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="db569-109">**Pour activer un index désactivé, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="db569-109">**To enable a disabled index, using:**</span></span>  
  
     [<span data-ttu-id="db569-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="db569-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="db569-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="db569-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="db569-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="db569-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="db569-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="db569-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="db569-114">Après la reconstruction de l'index, toutes les contraintes qui étaient désactivées du fait de la désactivation de l'index doivent être réactivées manuellement.</span><span class="sxs-lookup"><span data-stu-id="db569-114">After rebuilding the index, any constraints that were disabled because of disabling the index must be manually enabled.</span></span> <span data-ttu-id="db569-115">Les contraintes PRIMARY KEY et UNIQUE sont activées par la reconstruction de l'index associé.</span><span class="sxs-lookup"><span data-stu-id="db569-115">PRIMARY KEY and UNIQUE constraints are enabled by rebuilding the associated index.</span></span> <span data-ttu-id="db569-116">Cet index doit être reconstruit (activé) avant que les contraintes FOREIGN KEY qui font référence à la contrainte PRIMARY KEY ou UNIQUE puissent être activées.</span><span class="sxs-lookup"><span data-stu-id="db569-116">This index must be rebuilt (enabled) before you can enable FOREIGN KEY constraints that reference the PRIMARY KEY or UNIQUE constraint.</span></span> <span data-ttu-id="db569-117">Les contraintes FOREIGN KEY sont activées à l'aide de l'instruction ALTER TABLE CHECK CONSTRAINT.</span><span class="sxs-lookup"><span data-stu-id="db569-117">FOREIGN KEY constraints are enabled by using the ALTER TABLE CHECK CONSTRAINT statement.</span></span>  
  
-   <span data-ttu-id="db569-118">La reconstruction d'un index cluster désactivé n'est pas possible lorsque l'option ONLINE a la valeur ON.</span><span class="sxs-lookup"><span data-stu-id="db569-118">Rebuilding a disabled clustered index cannot be performed when the ONLINE option is set to ON.</span></span>  
  
-   <span data-ttu-id="db569-119">Lorsque l'index cluster est désactivé ou activé et que l'index non-cluster est désactivé, l'action sur l'index cluster produit les résultats ci-dessous sur l'index non-cluster désactivé.</span><span class="sxs-lookup"><span data-stu-id="db569-119">When the clustered index is disabled or enabled and the nonclustered index is disabled, the clustered index action has the following results on the disabled nonclustered index.</span></span>  
  
    |<span data-ttu-id="db569-120">Action sur l'index cluster</span><span class="sxs-lookup"><span data-stu-id="db569-120">Clustered Index Action</span></span>|<span data-ttu-id="db569-121">Index non cluster désactivé…</span><span class="sxs-lookup"><span data-stu-id="db569-121">Disabled Nonclustered Index ...</span></span>|  
    |----------------------------|-----------------------------------|  
    |<span data-ttu-id="db569-122">ALTER INDEX REBUILD</span><span class="sxs-lookup"><span data-stu-id="db569-122">ALTER INDEX REBUILD.</span></span>|<span data-ttu-id="db569-123">Reste désactivé.</span><span class="sxs-lookup"><span data-stu-id="db569-123">Remains disabled.</span></span>|  
    |<span data-ttu-id="db569-124">ALTER INDEX ALL REBUILD</span><span class="sxs-lookup"><span data-stu-id="db569-124">ALTER INDEX ALL REBUILD.</span></span>|<span data-ttu-id="db569-125">Est reconstruit et activé.</span><span class="sxs-lookup"><span data-stu-id="db569-125">Is rebuilt and enabled.</span></span>|  
    |<span data-ttu-id="db569-126">DROP INDEX</span><span class="sxs-lookup"><span data-stu-id="db569-126">DROP INDEX.</span></span>|<span data-ttu-id="db569-127">Reste désactivé.</span><span class="sxs-lookup"><span data-stu-id="db569-127">Remains disabled.</span></span>|  
    |<span data-ttu-id="db569-128">CREATE INDEX WITH DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="db569-128">CREATE INDEX WITH DROP_EXISTING.</span></span>|<span data-ttu-id="db569-129">Reste désactivé.</span><span class="sxs-lookup"><span data-stu-id="db569-129">Remains disabled.</span></span>|  
  
     <span data-ttu-id="db569-130">La création d'un nouvel index cluster suit le même comportement que ALTER INDEX ALL REBUILD.</span><span class="sxs-lookup"><span data-stu-id="db569-130">Creating a new clustered index, behaves the same as ALTER INDEX ALL REBUILD.</span></span>  
  
-   <span data-ttu-id="db569-131">Les actions autorisées sur les index non-cluster associés à un index cluster dépendent de l'état, désactivé ou activé, des deux types d'index.</span><span class="sxs-lookup"><span data-stu-id="db569-131">Allowed actions on nonclustered indexes associated with a clustered index depend on the state, whether disabled or enabled, of both index types.</span></span> <span data-ttu-id="db569-132">Le tableau ci-dessous récapitule les actions autorisées sur les index non-cluster.</span><span class="sxs-lookup"><span data-stu-id="db569-132">The following table summarizes the allowed actions on nonclustered indexes.</span></span>  
  
    |<span data-ttu-id="db569-133">Action sur l'index non cluster</span><span class="sxs-lookup"><span data-stu-id="db569-133">Nonclustered Index Action</span></span>|<span data-ttu-id="db569-134">Lorsque les index cluster et non cluster sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="db569-134">When both the clustered and nonclustered indexes are disabled.</span></span>|<span data-ttu-id="db569-135">Lorsque l'index cluster est activé et que l'index non cluster est activé ou désactivé.</span><span class="sxs-lookup"><span data-stu-id="db569-135">When the clustered index is enabled and the nonclustered index is in either state.</span></span>|  
    |-------------------------------|--------------------------------------------------------------------|----------------------------------------------------------------------------------------|  
    |<span data-ttu-id="db569-136">ALTER INDEX REBUILD</span><span class="sxs-lookup"><span data-stu-id="db569-136">ALTER INDEX REBUILD.</span></span>|<span data-ttu-id="db569-137">L'action échoue.</span><span class="sxs-lookup"><span data-stu-id="db569-137">The action fails.</span></span>|<span data-ttu-id="db569-138">L'action réussit.</span><span class="sxs-lookup"><span data-stu-id="db569-138">The action succeeds.</span></span>|  
    |<span data-ttu-id="db569-139">DROP INDEX</span><span class="sxs-lookup"><span data-stu-id="db569-139">DROP INDEX.</span></span>|<span data-ttu-id="db569-140">L'action réussit.</span><span class="sxs-lookup"><span data-stu-id="db569-140">The action succeeds.</span></span>|<span data-ttu-id="db569-141">L'action réussit.</span><span class="sxs-lookup"><span data-stu-id="db569-141">The action succeeds.</span></span>|  
    |<span data-ttu-id="db569-142">CREATE INDEX WITH DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="db569-142">CREATE INDEX WITH DROP_EXISTING.</span></span>|<span data-ttu-id="db569-143">L'action échoue.</span><span class="sxs-lookup"><span data-stu-id="db569-143">The action fails.</span></span>|<span data-ttu-id="db569-144">L'action réussit.</span><span class="sxs-lookup"><span data-stu-id="db569-144">The action succeeds.</span></span>|  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="db569-145">Sécurité</span><span class="sxs-lookup"><span data-stu-id="db569-145">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="db569-146">Autorisations</span><span class="sxs-lookup"><span data-stu-id="db569-146">Permissions</span></span>  
 <span data-ttu-id="db569-147">Nécessite une autorisation ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="db569-147">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="db569-148">S’il utilise DBCC DBREINDEX, l’utilisateur doit être propriétaire de la table ou être membre du rôle serveur fixe **sysadmin** ou des rôles de base de données fixes **db_ddladmin** et **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="db569-148">If using DBCC DBREINDEX, eser must either own the table or be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="db569-149">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="db569-149">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-a-disabled-index"></a><span data-ttu-id="db569-150">Pour activer un index désactivé</span><span class="sxs-lookup"><span data-stu-id="db569-150">To enable a disabled index</span></span>  
  
1.  <span data-ttu-id="db569-151">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer la base de données qui contient la table sur laquelle vous souhaitez activer un index.</span><span class="sxs-lookup"><span data-stu-id="db569-151">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to enable an index.</span></span>  
  
2.  <span data-ttu-id="db569-152">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="db569-152">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="db569-153">Cliquez sur le signe plus (+) pour développer la table sur laquelle vous souhaitez activer un index.</span><span class="sxs-lookup"><span data-stu-id="db569-153">Click the plus sign to expand the table on which you want to enable an index.</span></span>  
  
4.  <span data-ttu-id="db569-154">Cliquez sur le signe plus (+) pour développer le dossier **Index** .</span><span class="sxs-lookup"><span data-stu-id="db569-154">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="db569-155">Cliquez avec le bouton droit sur l’index que vous souhaitez activer et sélectionnez **Reconstruire**.</span><span class="sxs-lookup"><span data-stu-id="db569-155">Right-click the index you want to enable and select **Rebuild**.</span></span>  
  
6.  <span data-ttu-id="db569-156">Dans la boîte de dialogue **Reconstruire les index** , vérifiez que l'index correct figure dans la grille **Index à reconstruire** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="db569-156">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to rebuild** grid and click **OK**.</span></span>  
  
#### <a name="to-enable-all-indexes-on-a-table"></a><span data-ttu-id="db569-157">Pour activer tous les index d'une table</span><span class="sxs-lookup"><span data-stu-id="db569-157">To enable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="db569-158">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer la base de données qui contient la table sur laquelle vous souhaitez activer les index.</span><span class="sxs-lookup"><span data-stu-id="db569-158">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to enable the indexes.</span></span>  
  
2.  <span data-ttu-id="db569-159">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="db569-159">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="db569-160">Cliquez sur le signe plus (+) pour développer la table sur laquelle vous souhaitez activer les index.</span><span class="sxs-lookup"><span data-stu-id="db569-160">Click the plus sign to expand the table on which you want to enable the indexes.</span></span>  
  
4.  <span data-ttu-id="db569-161">Cliquez avec le bouton droit sur le dossier **Index** et sélectionnez **Tout reconstruire**.</span><span class="sxs-lookup"><span data-stu-id="db569-161">Right-click the **Indexes** folder and select **Rebuild All**.</span></span>  
  
5.  <span data-ttu-id="db569-162">Dans la boîte de dialogue **Reconstruire les index** , vérifiez que les index corrects figurent dans la grille **Index à reconstruire** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="db569-162">In the **Rebuild Indexes** dialog box, verify that the correct indexes are in the **Indexes to rebuild** grid and click **OK**.</span></span> <span data-ttu-id="db569-163">Pour supprimer un index de la grille **Index à reconstruire** , sélectionnez l'index et appuyez sur la touche SUPPR.</span><span class="sxs-lookup"><span data-stu-id="db569-163">To remove an index from the **Indexes to rebuild** grid, select the index and then press the Delete key.</span></span>  
  
 <span data-ttu-id="db569-164">Les informations suivantes sont disponibles dans la boîte de dialogue **Reconstruire les index** :</span><span class="sxs-lookup"><span data-stu-id="db569-164">The following information is available in the **Rebuild Indexes** dialog box:</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="db569-165">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="db569-165">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-a-disabled-index-using-alter-index"></a><span data-ttu-id="db569-166">Pour activer un index désactivé à l'aide de ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="db569-166">To enable a disabled index using ALTER INDEX</span></span>  
  
1.  <span data-ttu-id="db569-167">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db569-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="db569-168">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="db569-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="db569-169">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="db569-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Enables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table.  
  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    REBUILD;   
    GO  
    ```  
  
#### <a name="to-enable-a-disabled-index-using-create-index"></a><span data-ttu-id="db569-170">Pour activer un index désactivé à l'aide de CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="db569-170">To enable a disabled index using CREATE INDEX</span></span>  
  
1.  <span data-ttu-id="db569-171">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db569-171">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="db569-172">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="db569-172">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="db569-173">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="db569-173">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- re-creates the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    -- using the OrganizationLevel and OrganizationNode columns  
    -- and then deletes the existing IX_Employee_OrganizationLevel_OrganizationNode index  
    CREATE INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
       (OrganizationLevel, OrganizationNode)  
    WITH (DROP_EXISTING = ON);  
    GO  
    ```  
  
#### <a name="to-enable-a-disabled-index-using-dbcc-dbreindex"></a><span data-ttu-id="db569-174">Pour activer un index désactivé à l'aide de DBCC DBREINDEX</span><span class="sxs-lookup"><span data-stu-id="db569-174">To enable a disabled index using DBCC DBREINDEX</span></span>  
  
1.  <span data-ttu-id="db569-175">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db569-175">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="db569-176">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="db569-176">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="db569-177">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="db569-177">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- enables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    DBCC DBREINDEX ("HumanResources.Employee", IX_Employee_OrganizationLevel_OrganizationNode);  
    GO  
    ```  
  
#### <a name="to-enable-all-indexes-on-a-table-using-alter-index"></a><span data-ttu-id="db569-178">Pour activer tous les index d'une table à l'aide de ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="db569-178">To enable all indexes on a table using ALTER INDEX</span></span>  
  
1.  <span data-ttu-id="db569-179">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db569-179">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="db569-180">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="db569-180">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="db569-181">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="db569-181">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- enables all indexes  
    -- on the HumanResources.Employee table  
    ALTER INDEX ALL ON HumanResources.Employee  
    REBUILD;  
    GO  
    ```  
  
#### <a name="to-enable-all-indexes-on-a-table-using-dbcc-dbreindex"></a><span data-ttu-id="db569-182">Pour activer tous les index d'une table à l'aide de DBCC DBREINDEX</span><span class="sxs-lookup"><span data-stu-id="db569-182">To enable all indexes on a table using DBCC DBREINDEX</span></span>  
  
1.  <span data-ttu-id="db569-183">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db569-183">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="db569-184">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="db569-184">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="db569-185">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="db569-185">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- enables all indexes  
    -- on the HumanResources.Employee table  
    DBCC DBREINDEX ("HumanResources.Employee", " ");  
    GO  
    ```  
  
 <span data-ttu-id="db569-186">Pour plus d’informations, consultez [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql), [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) et [DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="db569-186">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql), [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql), and [DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql).</span></span>  
  
  
