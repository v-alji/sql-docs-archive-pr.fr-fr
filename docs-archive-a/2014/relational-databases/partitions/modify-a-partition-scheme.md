---
title: Modifier un schéma de partition | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 515de63f-dfc5-434d-9adb-f3b5992f745a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d57984228e23143d2061df6bf447f978f9bd3c46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611745"
---
# <a name="modify-a-partition-scheme"></a><span data-ttu-id="13598-102">Modifier un schéma de partition</span><span class="sxs-lookup"><span data-stu-id="13598-102">Modify a Partition Scheme</span></span>
  <span data-ttu-id="13598-103">Vous pouvez modifier un schéma de partition dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] en désignant un groupe de fichiers destiné à contenir la prochaine partition ajoutée à une table partitionnée à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13598-103">You can modify a partition scheme in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by designating a filegroup to hold the next partition that is added to a partitioned table using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="13598-104">Pour ce faire, vous affectez la propriété NEXT USED au groupe de fichiers en question.</span><span class="sxs-lookup"><span data-stu-id="13598-104">You do this by assigning the NEXT USED property to a filegroup.</span></span> <span data-ttu-id="13598-105">Vous pouvez affecter la propriété NEXT USED à un groupe de fichiers vide ou à un groupe de fichiers qui contient déjà une partition.</span><span class="sxs-lookup"><span data-stu-id="13598-105">You can assign the NEXT USED property to an empty filegroup or to one that already holds a partition.</span></span> <span data-ttu-id="13598-106">Autrement dit, un groupe de fichiers peut contenir plusieurs partitions.</span><span class="sxs-lookup"><span data-stu-id="13598-106">In other words, a filegroup can hold more than one partition.</span></span>  
  
 <span data-ttu-id="13598-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="13598-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="13598-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="13598-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="13598-109">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="13598-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="13598-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="13598-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="13598-111">**Pour créer une table ou un index partitionné(e), utilisez :**</span><span class="sxs-lookup"><span data-stu-id="13598-111">**To create a partitioned table or index, using:**</span></span>  
  
     [<span data-ttu-id="13598-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="13598-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="13598-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="13598-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="13598-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="13598-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="13598-115">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="13598-115">Limitations and Restrictions</span></span>  
 <span data-ttu-id="13598-116">Tout groupe de fichiers affecté par ALTER PARTITION SCHEME doit être en ligne.</span><span class="sxs-lookup"><span data-stu-id="13598-116">Any filegroup affected by ALTER PARTITION SCHEME must be online.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="13598-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="13598-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="13598-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="13598-118">Permissions</span></span>  
 <span data-ttu-id="13598-119">Les autorisations suivantes peuvent être utilisées pour exécuter ALTER PARTITION SCHEME :</span><span class="sxs-lookup"><span data-stu-id="13598-119">The following permissions can be used to execute ALTER PARTITION SCHEME:</span></span>  
  
-   <span data-ttu-id="13598-120">Autorisation ALTER ANY DATASPACE.</span><span class="sxs-lookup"><span data-stu-id="13598-120">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="13598-121">Cette autorisation est attribuée par défaut aux membres du rôle de serveur fixe **sysadmin** et des rôles de base de données fixes **db_owner** et **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="13598-121">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="13598-122">Autorisation CONTROL ou ALTER sur la base de données dans laquelle le schéma de partition a été créé.</span><span class="sxs-lookup"><span data-stu-id="13598-122">CONTROL or ALTER permission on the database in which the partition scheme was created.</span></span>  
  
-   <span data-ttu-id="13598-123">Autorisation CONTROL SERVER ou ALTER ANY DATABASE sur le serveur de la base de données dans laquelle le schéma de partition a été créé.</span><span class="sxs-lookup"><span data-stu-id="13598-123">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition scheme was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="13598-124">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="13598-124">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="13598-125">**Pour modifier un schéma de partition :**</span><span class="sxs-lookup"><span data-stu-id="13598-125">**To modify a partition scheme:**</span></span>  
  
 <span data-ttu-id="13598-126">Cette action spécifique ne peut pas être exécutée à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13598-126">This specific action cannot be performed using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="13598-127">Afin de modifier un schéma de partition, vous devez d'abord le supprimer puis en créer un nouveau avec les propriétés souhaitées à l'aide de l'Assistant Création de partition.</span><span class="sxs-lookup"><span data-stu-id="13598-127">In order to modify a partition scheme, you must first delete the scheme and then create a new one with the desired properties using the Create Partition Wizard.</span></span> <span data-ttu-id="13598-128">Pour plus d’informations, consultez [créer des tables et des index partitionnés à l’aide de SQL Server Management Studio](create-partitioned-tables-and-indexes.md#SSMSProcedure) sous **créer des tables et des index partitionnés**.</span><span class="sxs-lookup"><span data-stu-id="13598-128">For more information, see [Create Partitioned Tables and Indexes Using SQL Server Management Studio](create-partitioned-tables-and-indexes.md#SSMSProcedure) under **Create Partitioned Tables and Indexes**.</span></span>  
  
#### <a name="to-delete-a-partition-scheme"></a><span data-ttu-id="13598-129">Pour supprimer un schéma de partition</span><span class="sxs-lookup"><span data-stu-id="13598-129">To delete a partition scheme</span></span>  
  
1.  <span data-ttu-id="13598-130">Cliquez sur le signe plus (+) pour développer la base de données contenant le schéma de partition à supprimer.</span><span class="sxs-lookup"><span data-stu-id="13598-130">Click the plus sign to expand the database where you want to delete the partition scheme.</span></span>  
  
2.  <span data-ttu-id="13598-131">Cliquez sur le signe plus (+) pour développer le dossier **Stockage** .</span><span class="sxs-lookup"><span data-stu-id="13598-131">Click the plus sign to expand the **Storage** folder.</span></span>  
  
3.  <span data-ttu-id="13598-132">Cliquez sur le signe plus (+) pour développer le dossier **Schémas de partition** .</span><span class="sxs-lookup"><span data-stu-id="13598-132">Click the plus sign to expand the **Partition Schemes** folder.</span></span>  
  
4.  <span data-ttu-id="13598-133">Cliquez avec le bouton droit sur le schéma de partition à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="13598-133">Right-click the partition scheme you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="13598-134">Dans la boîte de dialogue **Supprimer un objet** , assurez-vous que le schéma de partition est sélectionné, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="13598-134">In the **Delete Object** dialog box, ensure that the correct partition scheme is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="13598-135">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="13598-135">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-partition-scheme"></a><span data-ttu-id="13598-136">Pour modifier un schéma de partition</span><span class="sxs-lookup"><span data-stu-id="13598-136">To modify a partition scheme</span></span>  
  
1.  <span data-ttu-id="13598-137">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13598-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="13598-138">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="13598-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="13598-139">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="13598-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- add five new filegroups to the AdventureWorks2012 database  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test1fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test2fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test3fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test4fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test5fg;  
    GO  
    -- if the "myRangePF1" partition function and the "myRangePS1" partition scheme exist,  
    -- drop them from the AdventureWorks2012 database  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
    DROP PARTITION FUNCTION myRangePF1;  
    GO  
    IF EXISTS (SELECT * FROM sys.partition_schemes  
        WHERE name = 'myRangePS1')  
    DROP PARTITION SCHEME myRangePS1;  
    GO  
    -- create the new partition function "myRangePF1" with four partition groups  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    -- create the new partition scheme "myRangePS1"that will use   
    -- the "myRangePF1" partition function with five file groups.  
    -- The last filegroup, "test5fg," will be kept empty but marked  
    -- as the next used filegroup in the partition scheme.  
    CREATE PARTITION SCHEME myRangePS1  
    AS PARTITION myRangePF1  
    TO (test1fg, test2fg, test3fg, test4fg, test5fg);  
    GO  
    --Split "myRangePS1" between boundary_values 100 and 1000  
    --to create two partitions between boundary_values 100 and 500  
    --and between boundary_values 500 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    SPLIT RANGE (500);  
    GO  
    -- Allow the "myRangePS1" partition scheme to use the filegroup "test5fg"  
    -- for the partition with boundary_values of 100 and 500  
    ALTER PARTITION SCHEME myRangePS1  
    NEXT USED test5fg;  
    GO  
    ```  
  
 <span data-ttu-id="13598-140">Pour plus d’informations, consultez [ALTER PARTITION SCHEME &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-scheme-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="13598-140">For more information, see [ALTER PARTITION SCHEME &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-scheme-transact-sql).</span></span>  
  
  
