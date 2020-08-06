---
title: Modifier une fonction de partition | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: ae5bfc09-f27a-4ea9-9518-485278b11674
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: bf14e633e62839b1abca7f38f833efab933c18f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696780"
---
# <a name="modify-a-partition-function"></a><span data-ttu-id="6fd54-102">Modifier une fonction de partition</span><span class="sxs-lookup"><span data-stu-id="6fd54-102">Modify a Partition Function</span></span>
  <span data-ttu-id="6fd54-103">Vous pouvez modifier le partitionnement d'une table ou d'un index dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] en ajoutant ou supprimant le nombre de partitions spécifié (par incréments de 1) dans la fonction de partition de la table ou de l'index à l'aide de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fd54-103">You can change the way a table or index is partitioned in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by adding or subtracting the number of partitions specified, in increments of 1, in the partition function of the partitioned table or index by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6fd54-104">Lorsque vous ajoutez une partition, vous fractionnez une partition existante en deux partitions dont vous redéfinissez les limites.</span><span class="sxs-lookup"><span data-stu-id="6fd54-104">When you add a partition, you do so by "splitting" an existing partition into two partitions and redefining the boundaries of the new partitions.</span></span> <span data-ttu-id="6fd54-105">Lorsque vous supprimez une partition, vous fusionnez les limites de deux partitions pour n'en définir qu'une.</span><span class="sxs-lookup"><span data-stu-id="6fd54-105">When you drop a partition, you do so by "merging" the boundaries of two partitions into one.</span></span> <span data-ttu-id="6fd54-106">Cette action a pour effet de remplir à nouveau une partition et de laisser l'autre non affectée.</span><span class="sxs-lookup"><span data-stu-id="6fd54-106">This last action repopulates one partition and leaves the other partition unassigned.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="6fd54-107">Une même fonction de partition peut être utilisée par plusieurs tables ou index.</span><span class="sxs-lookup"><span data-stu-id="6fd54-107">More than one table or index can use the same partition function.</span></span> <span data-ttu-id="6fd54-108">Lorsque vous modifiez une fonction de partition, vous affectez toutes les fonctions dans une transaction unique.</span><span class="sxs-lookup"><span data-stu-id="6fd54-108">When you modify a partition function, you affect all of them in a single transaction.</span></span> <span data-ttu-id="6fd54-109">Vérifiez les dépendances de la fonction de partition avant de la modifier.</span><span class="sxs-lookup"><span data-stu-id="6fd54-109">Check the partition function's dependencies before modifying it.</span></span>  
  
 <span data-ttu-id="6fd54-110">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="6fd54-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6fd54-111">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="6fd54-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6fd54-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="6fd54-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6fd54-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="6fd54-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6fd54-114">**Pour modifier une fonction de partition à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="6fd54-114">**To modify a partition function, using:**</span></span>  
  
     [<span data-ttu-id="6fd54-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6fd54-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6fd54-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6fd54-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6fd54-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="6fd54-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6fd54-118">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="6fd54-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6fd54-119">Vous ne pouvez utiliser ALTER PARTITION FUNCTION que pour diviser une partition en deux ou pour fusionner deux partitions en une seule.</span><span class="sxs-lookup"><span data-stu-id="6fd54-119">ALTER PARTITION FUNCTION can only be used for splitting one partition into two, or for merging two partitions into one.</span></span> <span data-ttu-id="6fd54-120">Pour modifier le mode de partitionnement d'une table ou d'un index (par exemple, pour passer de 10 à 5 partitions), vous disposez de plusieurs options :</span><span class="sxs-lookup"><span data-stu-id="6fd54-120">To change the way a table or index is partitioned (from 10 partitions to 5, for example), you can use any one of the following options:</span></span>  
  
    -   <span data-ttu-id="6fd54-121">Créez une nouvelle table partitionnée avec la fonction de partition de votre choix, puis insérez les données de l'ancienne table dans la nouvelle à l'aide de l'instruction INSERT INTO ... SELECT FROM [!INCLUDE[tsql](../../includes/tsql-md.md)] ou de **l’Assistant gestion de partition** dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fd54-121">Create a new partitioned table with the desired partition function, and then insert the data from the old table into the new table by using either an INSERT INTO ... SELECT FROM [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or the **Manage Partition Wizard** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
    -   <span data-ttu-id="6fd54-122">Créez un index cluster partitionné sur un segment.</span><span class="sxs-lookup"><span data-stu-id="6fd54-122">Create a partitioned clustered index on a heap.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="6fd54-123">La suppression d'un index cluster partitionné engendre un segment partitionné.</span><span class="sxs-lookup"><span data-stu-id="6fd54-123">Dropping a partitioned clustered index results in a partitioned heap.</span></span>  
  
    -   <span data-ttu-id="6fd54-124">Supprimez et reconstruisez un index partitionné existant à l'aide de l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE INDEX avec la clause DROP EXISTING = ON.</span><span class="sxs-lookup"><span data-stu-id="6fd54-124">Drop and rebuild an existing partitioned index by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE INDEX statement with the DROP EXISTING = ON clause.</span></span>  
  
    -   <span data-ttu-id="6fd54-125">Exécutez une séquence d'instructions ALTER PARTITION FUNCTION.</span><span class="sxs-lookup"><span data-stu-id="6fd54-125">Perform a sequence of ALTER PARTITION FUNCTION statements.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6fd54-126">n'assure pas la prise en charge de la réplication lors de la modification d'une fonction de partition.</span><span class="sxs-lookup"><span data-stu-id="6fd54-126">does not provide replication support for modifying a partition function.</span></span> <span data-ttu-id="6fd54-127">Si vous voulez apporter des modifications à une fonction de partition dans la base de données de publication, vous devez le faire manuellement dans la base d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="6fd54-127">If you want to make changes to a partition function in the publication database, you must do this manually in the subscription database.</span></span>  
  
-   <span data-ttu-id="6fd54-128">Tous les groupes de fichiers concernés par l’instruction ALTER PARTITION FUNCTION doivent être en ligne.</span><span class="sxs-lookup"><span data-stu-id="6fd54-128">All filegroups that are affected by ALTER PARTITION FUNCTION must be online.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6fd54-129">Sécurité</span><span class="sxs-lookup"><span data-stu-id="6fd54-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6fd54-130">Autorisations</span><span class="sxs-lookup"><span data-stu-id="6fd54-130">Permissions</span></span>  
 <span data-ttu-id="6fd54-131">L'instruction ALTER PARTITION FUNCTION peut être exécutée avec les autorisations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6fd54-131">Any one of the following permissions can be used to execute ALTER PARTITION FUNCTION:</span></span>  
  
-   <span data-ttu-id="6fd54-132">Autorisation ALTER ANY DATASPACE.</span><span class="sxs-lookup"><span data-stu-id="6fd54-132">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="6fd54-133">Cette autorisation est attribuée par défaut aux membres du rôle de serveur fixe **sysadmin** et des rôles de base de données fixes **db_owner** et **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="6fd54-133">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="6fd54-134">Autorisation CONTROL ou ALTER sur la base de données dans laquelle la fonction de partition a été créée.</span><span class="sxs-lookup"><span data-stu-id="6fd54-134">CONTROL or ALTER permission on the database in which the partition function was created.</span></span>  
  
-   <span data-ttu-id="6fd54-135">Autorisation CONTROL SERVER ou ALTER ANY DATABASE sur le serveur de la base de données dans laquelle la fonction de partition a été créée.</span><span class="sxs-lookup"><span data-stu-id="6fd54-135">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition function was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6fd54-136">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6fd54-136">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="6fd54-137">**Pour modifier une fonction de partition :**</span><span class="sxs-lookup"><span data-stu-id="6fd54-137">**To modify a partition function:**</span></span>  
  
 <span data-ttu-id="6fd54-138">Cette action spécifique ne peut pas être exécutée à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fd54-138">This specific action cannot be performed using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="6fd54-139">Afin de modifier une fonction de partition, vous devez d'abord supprimer la fonction puis en créer une nouvelle avec les propriétés souhaitées à l'aide de l'Assistant Création de partition.</span><span class="sxs-lookup"><span data-stu-id="6fd54-139">In order to modify a partition function, you must first delete the function and then create a new one with the desired properties using the Create Partition Wizard.</span></span> <span data-ttu-id="6fd54-140">Pour plus d'informations, consultez la rubrique</span><span class="sxs-lookup"><span data-stu-id="6fd54-140">For more information, see</span></span>  
  
#### <a name="to-delete-a-partition-function"></a><span data-ttu-id="6fd54-141">Pour supprimer une fonction de partition</span><span class="sxs-lookup"><span data-stu-id="6fd54-141">To delete a partition function</span></span>  
  
1.  <span data-ttu-id="6fd54-142">Développez la base de données dans laquelle vous souhaitez supprimer la fonction de partition, puis développer le dossier **Stockage** .</span><span class="sxs-lookup"><span data-stu-id="6fd54-142">Expand the database where you want to delete the partition function and then expand the **Storage** folder.</span></span>  
  
2.  <span data-ttu-id="6fd54-143">Développez le dossier **Fonctions de partition** .</span><span class="sxs-lookup"><span data-stu-id="6fd54-143">Expand the **Partition Functions** folder.</span></span>  
  
3.  <span data-ttu-id="6fd54-144">Cliquez avec le bouton droit sur la fonction de partition à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="6fd54-144">Right-click the partition function you want to delete and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="6fd54-145">Dans la boîte de dialogue **Supprimer un objet** , assurez-vous que la fonction de partition est sélectionnée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6fd54-145">In the **Delete Object** dialog box, ensure that the correct partition function is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6fd54-146">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6fd54-146">Using Transact-SQL</span></span>  
  
#### <a name="to-split-a-single-partition-into-two-partitions"></a><span data-ttu-id="6fd54-147">Pour fractionner une partition unique en deux partitions</span><span class="sxs-lookup"><span data-stu-id="6fd54-147">To split a single partition into two partitions</span></span>  
  
1.  <span data-ttu-id="6fd54-148">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fd54-148">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6fd54-149">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="6fd54-149">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6fd54-150">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="6fd54-150">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Look for a previous version of the partition function "myRangePF1" and deletes it if it is found.  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
        DROP PARTITION FUNCTION myRangePF1;  
    GO  
    -- Create a new partition function called "myRangePF1" that partitions a table into four partitions.  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    --Split the partition between boundary_values 100 and 1000  
    --to create two partitions between boundary_values 100 and 500  
    --and between boundary_values 500 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    SPLIT RANGE (500);  
    ```  
  
#### <a name="to-merge-two-partitions-into-one-partition"></a><span data-ttu-id="6fd54-151">Pour fusionner deux partitions dans une partition</span><span class="sxs-lookup"><span data-stu-id="6fd54-151">To merge two partitions into one partition</span></span>  
  
1.  <span data-ttu-id="6fd54-152">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fd54-152">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6fd54-153">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="6fd54-153">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6fd54-154">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="6fd54-154">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Look for a previous version of the partition function "myRangePF1" and deletes it if it is found.  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
        DROP PARTITION FUNCTION myRangePF1;  
    GO  
    -- Create a new partition function called "myRangePF1" that partitions a table into four partitions.  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    --Merge the partitions between boundary_values 1 and 100  
    --and between boundary_values 100 and 1000 to create one partition  
    --between boundary_values 1 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    MERGE RANGE (100);  
    ```  
  
 <span data-ttu-id="6fd54-155">Pour plus d’informations, consultez [ALTER PARTITION FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6fd54-155">For more information, see [ALTER PARTITION FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-function-transact-sql).</span></span>  
  
  
