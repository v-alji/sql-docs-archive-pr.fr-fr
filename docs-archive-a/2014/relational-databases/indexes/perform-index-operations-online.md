---
title: Exécuter des opérations en ligne sur les index | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index online operations [SQL Server]
- online index operations
- ONLINE option
ms.assetid: 1e43537c-bf67-4db3-9908-3cb45c6fdaa1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d09bd99a0eaec5fdb433bd8c33351d7622957a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614044"
---
# <a name="perform-index-operations-online"></a><span data-ttu-id="5b418-102">Exécuter des opérations en ligne sur les index</span><span class="sxs-lookup"><span data-stu-id="5b418-102">Perform Index Operations Online</span></span>
  <span data-ttu-id="5b418-103">Cette rubrique explique comment créer, reconstruire ou supprimer des index en ligne dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b418-103">This topic describes how to create, rebuild, or drop indexes online in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5b418-104">L'option ONLINE permet l'accès simultané des utilisateurs aux tables sous-jacentes ou aux données des index cluster et aux index non-cluster associés pendant ces opérations sur les index.</span><span class="sxs-lookup"><span data-stu-id="5b418-104">The ONLINE option allows concurrent user access to the underlying table or clustered index data and any associated nonclustered indexes during these index operations.</span></span> <span data-ttu-id="5b418-105">Par exemple, pendant qu'un index cluster est reconstruit par un utilisateur, cet utilisateur et d'autres peuvent continuer de mettre à jour et d'interroger les données sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="5b418-105">For example, while a clustered index is being rebuilt by one user, that user and others can continue to update and query the underlying data.</span></span> <span data-ttu-id="5b418-106">Lorsque vous effectuez des opérations DDL (Data Definition Language) en mode hors connexion, comme la construction ou la reconstruction d'un index cluster, ces opérations posent des verrous exclusifs sur les données sous-jacentes et les index associés.</span><span class="sxs-lookup"><span data-stu-id="5b418-106">When you perform data definition language (DDL) operations offline, such as building or rebuilding a clustered index; these operations hold exclusive locks on the underlying data and associated indexes.</span></span> <span data-ttu-id="5b418-107">Ces verrous empêchent toute modification et toute interrogation des données sous-jacentes jusqu'à la fin de l'opération effectuée sur l'index.</span><span class="sxs-lookup"><span data-stu-id="5b418-107">This prevents modifications and queries to the underlying data until the index operation is complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b418-108">Les opérations d'index en ligne ne sont pas disponibles dans toutes les édition de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b418-108">Online index operations are not available in every [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition.</span></span> <span data-ttu-id="5b418-109">Pour plus d’informations, consultez [fonctionnalités prises en charge par les éditions de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="5b418-109">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="5b418-110">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="5b418-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5b418-111">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="5b418-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5b418-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="5b418-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5b418-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5b418-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5b418-114">**Pour reconstruire un index en ligne à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="5b418-114">**To rebuild an index online, using:**</span></span>  
  
     [<span data-ttu-id="5b418-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b418-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5b418-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b418-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5b418-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5b418-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5b418-118">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="5b418-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5b418-119">Il est recommandé d'effectuer les opérations sur les index en ligne dans les environnements qui sont opérationnels 24 heures sur 24 et 7 jours sur 7, dans lesquels il est vital de maintenir l'accès des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5b418-119">We recommend performing online index operations for business environments that operate 24 hours a day, seven days a week, in which the need for concurrent user activity during index operations is vital.</span></span>  
  
-   <span data-ttu-id="5b418-120">L'option ONLINE peut être utilisée dans les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes.</span><span class="sxs-lookup"><span data-stu-id="5b418-120">The ONLINE option is available in the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
    -   [<span data-ttu-id="5b418-121">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="5b418-121">CREATE INDEX</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
    -   [<span data-ttu-id="5b418-122">ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="5b418-122">ALTER INDEX</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
    -   [<span data-ttu-id="5b418-123">DROP INDEX</span><span class="sxs-lookup"><span data-stu-id="5b418-123">DROP INDEX</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
    -   <span data-ttu-id="5b418-124">[ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) (Pour ajouter ou supprimer des contraintes UNIQUE ou PRIMARY KEY avec l’option d’index CLUSTERED)</span><span class="sxs-lookup"><span data-stu-id="5b418-124">[ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) (To add or drop UNIQUE or PRIMARY KEY constraints with CLUSTERED index option)</span></span>  
  
-   <span data-ttu-id="5b418-125">Pour plus d’informations sur les limitations et les restrictions de création, reconstruction ou suppression d’index en ligne, consultez [Instructions pour les opérations d’index en ligne](guidelines-for-online-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="5b418-125">For more limitations and restrictions concerning creating, rebuilding, or dropping indexes online, see [Guidelines for Online Index Operations](guidelines-for-online-index-operations.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5b418-126">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5b418-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5b418-127">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5b418-127">Permissions</span></span>  
 <span data-ttu-id="5b418-128">Nécessite une autorisation ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="5b418-128">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5b418-129">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b418-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rebuild-an-index-online"></a><span data-ttu-id="5b418-130">Pour reconstruire un index en ligne</span><span class="sxs-lookup"><span data-stu-id="5b418-130">To rebuild an index online</span></span>  
  
1.  <span data-ttu-id="5b418-131">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer la base de données qui contient la table sur laquelle vous souhaitez reconstruire un index en ligne.</span><span class="sxs-lookup"><span data-stu-id="5b418-131">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rebuild an index online.</span></span>  
  
2.  <span data-ttu-id="5b418-132">Développez le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="5b418-132">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="5b418-133">Cliquez sur le signe plus (+) pour développer la table sur laquelle vous souhaitez reconstruire un index en ligne.</span><span class="sxs-lookup"><span data-stu-id="5b418-133">Click the plus sign to expand the table on which you want to rebuild an index online.</span></span>  
  
4.  <span data-ttu-id="5b418-134">Développez le dossier **Index** .</span><span class="sxs-lookup"><span data-stu-id="5b418-134">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="5b418-135">Cliquez avec le bouton droit sur l’index à reconstruire en ligne, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5b418-135">Right-click the index that you want to rebuild online and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="5b418-136">Sous **Sélectionner une page**, sélectionnez **Options**.</span><span class="sxs-lookup"><span data-stu-id="5b418-136">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="5b418-137">Sélectionnez **Autoriser le traitement des instructions DML en ligne**, puis sélectionnez **True** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="5b418-137">Select **Allow online DML processing**, and then select **True** from the list.</span></span>  
  
8.  <span data-ttu-id="5b418-138">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b418-138">Click **OK**.</span></span>  
  
9. <span data-ttu-id="5b418-139">Cliquez avec le bouton droit sur l’index à reconstruire en ligne, puis sélectionnez **Reconstruire**.</span><span class="sxs-lookup"><span data-stu-id="5b418-139">Right-click the index that you want to rebuild online and select **Rebuild**.</span></span>  
  
10. <span data-ttu-id="5b418-140">Dans la boîte de dialogue **Reconstruire les index** , vérifiez que l'index correct figure dans la grille **Index à reconstruire** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b418-140">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to rebuild** grid and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5b418-141">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b418-141">Using Transact-SQL</span></span>  
  
#### <a name="to-create-rebuild-or-drop-an-index-online"></a><span data-ttu-id="5b418-142">Pour créer, reconstruire ou supprimer un index en ligne</span><span class="sxs-lookup"><span data-stu-id="5b418-142">To create, rebuild, or drop an index online</span></span>  
  
1.  <span data-ttu-id="5b418-143">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b418-143">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5b418-144">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5b418-144">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5b418-145">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5b418-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5b418-146">L'exemple reconstruit un index en ligne existant.</span><span class="sxs-lookup"><span data-stu-id="5b418-146">The example rebuilds an existing online</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER INDEX AK_Employee_NationalIDNumber ON HumanResources.Employee  
    REBUILD WITH (ONLINE = ON);  
    GO  
    ```  
  
     <span data-ttu-id="5b418-147">L'exemple suivant supprime un index cluster en ligne et déplace la table résultante (segment de mémoire) vers le groupe de fichiers `NewGroup` en utilisant la clause `MOVE TO` .</span><span class="sxs-lookup"><span data-stu-id="5b418-147">The following example deletes a clustered index online and moves the resulting table (heap) to the filegroup `NewGroup` by using the `MOVE TO` clause.</span></span> <span data-ttu-id="5b418-148">Les affichages catalogue `sys.indexes`, `sys.tables`et `sys.filegroups` sont interrogés pour vérifier le placement de l'index et de la table dans les groupes de fichiers avant et après l'opération de déplacement.</span><span class="sxs-lookup"><span data-stu-id="5b418-148">The `sys.indexes`, `sys.tables`, and `sys.filegroups` catalog views are queried to verify the index and table placement in the filegroups before and after the move.</span></span>  
  
     [!code-sql[IndexDDL#DropIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/dropindex.sql#dropindex4)]  
  
 <span data-ttu-id="5b418-149">Pour plus d’informations, consultez [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5b418-149">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
