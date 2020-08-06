---
title: Configurer des opérations d’index parallèles | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index parallel operations [SQL Server]
- processors [SQL Server], parallel index operations
- max degree of parallelism option
- MAXDOP index option, parallel index operations
- parallel index operations [SQL Server]
ms.assetid: 8ec8c71e-5fc1-443a-92da-136ee3fc7f88
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8831aadae15af03a05f4ab03cfe514e54566df1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600889"
---
# <a name="configure-parallel-index-operations"></a><span data-ttu-id="c9ab8-102">Configurer des opérations d'index parallèles</span><span class="sxs-lookup"><span data-stu-id="c9ab8-102">Configure Parallel Index Operations</span></span>
  <span data-ttu-id="c9ab8-103">Cette rubrique définit le degré maximal de parallélisme et explique comment modifier ce paramètre dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ab8-103">This topic defines max degree of parallelism and explains how to modify this setting in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c9ab8-104">Sur les ordinateurs multiprocesseurs qui exécutent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise ou une version ultérieure, les instructions d'index peuvent, à l'instar d'autres requêtes, utiliser des processeurs multiples pour réaliser les opérations d'analyse, de tri et d'indexation associées à l'instruction d'index.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-104">On multiprocessor computers that are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise or higher, index statements may use multiple processors to perform the scan, sort, and index operations associated with the index statement just like other queries do.</span></span> <span data-ttu-id="c9ab8-105">Le nombre de processeurs utilisés pour exécuter une instruction d’index est déterminé par l’option de configuration [Degré maximal de parallélisme](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md) , par la charge de travail actuelle et par les statistiques d’index.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-105">The number of processors used to run a single index statement is determined by the [max degree of parallelism](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md) configuration option, the current workload, and the index statistics.</span></span> <span data-ttu-id="c9ab8-106">L'option max degree of parallelism détermine le nombre maximal de processeurs à utiliser au cours de l'exécution d'un plan parallèle.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-106">The max degree of parallelism option determines the maximum number of processors to use in parallel plan execution.</span></span> <span data-ttu-id="c9ab8-107">Si le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] détecte que le système est occupé, le degré de parallélisme de l'opération d'index est automatiquement réduit avant l'exécution de l'instruction.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-107">If the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] detects that the system is busy, the degree of parallelism of the index operation is automatically reduced before statement execution starts.</span></span> <span data-ttu-id="c9ab8-108">Le [!INCLUDE[ssDE](../../includes/ssde-md.md)] peut également réduire le degré de parallélisme si la colonne clé principale d’un index non partitionné a un nombre limité de valeurs distinctes ou si la fréquence de chaque valeur distincte varie considérablement.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-108">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can also reduce the degree of parallelism if the leading key column of a non-partitioned index has a limited number of distinct values or the frequency of each distinct value varies significantly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9ab8-109">Les opérations d'index parallèles ne sont pas disponibles dans toutes les édition de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9ab8-109">Parallel index operations are not available in every [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition.</span></span> <span data-ttu-id="c9ab8-110">Pour plus d’informations, consultez [fonctionnalités prises en charge par les éditions de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="c9ab8-110">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="c9ab8-111">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="c9ab8-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c9ab8-112">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="c9ab8-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c9ab8-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="c9ab8-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c9ab8-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c9ab8-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c9ab8-115">**Pour configurer l'option Degré maximal de parallélisme à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="c9ab8-115">**To set the max degree of parallelism, using:**</span></span>  
  
     [<span data-ttu-id="c9ab8-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c9ab8-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c9ab8-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c9ab8-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c9ab8-118">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c9ab8-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c9ab8-119">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="c9ab8-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c9ab8-120">Le nombre de processeurs utilisés par l'optimiseur de requête garantit généralement des performances optimales.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-120">The number of processors that are used by the query optimizer typically provides optimal performance.</span></span> <span data-ttu-id="c9ab8-121">Toutefois, des opérations comme la création, la reconstruction ou la suppression d'index volumineux exigent beaucoup de ressources et peuvent, pendant leur exécution, entraîner un manque de ressources pour d'autres opérations d'applications ou de base de données.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-121">However, operations such as creating, rebuilding, or dropping very large indexes are resource intensive and can cause insufficient resources for other applications and database operations for the duration of the index operation.</span></span> <span data-ttu-id="c9ab8-122">Lorsque cette situation se produit, vous pouvez configurer manuellement le nombre maximal de processeurs utilisés pour exécuter l'instruction d'index en limitant le nombre de processeurs qui peuvent être utilisés par l'opération d'index.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-122">When this problem occurs, you can manually configure the maximum number of processors that are used to run the index statement by limiting the number of processors to use for the index operation.</span></span>  
  
-   <span data-ttu-id="c9ab8-123">L'option d'index MAXDOP remplace l'option de configuration max degree of parallelism uniquement pour la requête qui la spécifie.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-123">The MAXDOP index option overrides the max degree of parallelism configuration option only for the query specifying this option.</span></span> <span data-ttu-id="c9ab8-124">Le tableau suivant répertorie les valeurs entières valides qui peuvent être spécifiées au moyen de l'option de configuration max degree of parallelism et de l'option d'index MAXDOP.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-124">The following table lists the valid integer values that can be specified with the max degree of parallelism configuration option and the MAXDOP index option.</span></span>  
  
    |<span data-ttu-id="c9ab8-125">Valeur</span><span class="sxs-lookup"><span data-stu-id="c9ab8-125">Value</span></span>|<span data-ttu-id="c9ab8-126">Description</span><span class="sxs-lookup"><span data-stu-id="c9ab8-126">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="c9ab8-127">0</span><span class="sxs-lookup"><span data-stu-id="c9ab8-127">0</span></span>|<span data-ttu-id="c9ab8-128">Spécifie que le serveur détermine le nombre de processeurs utilisés, selon la charge système actuelle.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-128">Specifies that the server determines the number of CPUs that are used, depending on the current system workload.</span></span> <span data-ttu-id="c9ab8-129">Il s'agit de la valeur par défaut et recommandée.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-129">This is the default value and recommended setting.</span></span>|  
    |<span data-ttu-id="c9ab8-130">1</span><span class="sxs-lookup"><span data-stu-id="c9ab8-130">1</span></span>|<span data-ttu-id="c9ab8-131">Supprime la création de plans parallèles.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-131">Suppresses parallel plan generation.</span></span> <span data-ttu-id="c9ab8-132">L'opération est exécutée en série.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-132">The operation will be executed serially.</span></span>|  
    |<span data-ttu-id="c9ab8-133">2-64</span><span class="sxs-lookup"><span data-stu-id="c9ab8-133">2-64</span></span>|<span data-ttu-id="c9ab8-134">Limite le nombre de processeurs à la valeur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-134">Limits the number of processors to the specified value.</span></span> <span data-ttu-id="c9ab8-135">Un nombre moins élevé de processeurs peuvent être utilisés en fonction de la charge de travail actuelle.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-135">Fewer processors may be used depending on the current workload.</span></span> <span data-ttu-id="c9ab8-136">Si une valeur supérieure au nombre d'UC disponibles est spécifiée, c'est le nombre d'UC disponibles qui est utilisé.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-136">If a value larger than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>|  
  
-   <span data-ttu-id="c9ab8-137">L'exécution parallèle d'index et l'option d'index MAXDOP s'appliquent aux instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes :</span><span class="sxs-lookup"><span data-stu-id="c9ab8-137">Parallel index execution and the MAXDOP index option apply to the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    -   <span data-ttu-id="c9ab8-138">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="c9ab8-138">CREATE INDEX</span></span>  
  
    -   <span data-ttu-id="c9ab8-139">ALTER INDEX REBUILD</span><span class="sxs-lookup"><span data-stu-id="c9ab8-139">ALTER INDEX REBUILD</span></span>  
  
    -   <span data-ttu-id="c9ab8-140">DROP INDEX (index cluster uniquement.)</span><span class="sxs-lookup"><span data-stu-id="c9ab8-140">DROP INDEX (This applies to clustered indexes only.)</span></span>  
  
    -   <span data-ttu-id="c9ab8-141">ALTER TABLE ADD (index) CONSTRAINT</span><span class="sxs-lookup"><span data-stu-id="c9ab8-141">ALTER TABLE ADD (index) CONSTRAINT</span></span>  
  
    -   <span data-ttu-id="c9ab8-142">ALTER TABLE DROP (index cluster) CONSTRAINT</span><span class="sxs-lookup"><span data-stu-id="c9ab8-142">ALTER TABLE DROP (clustered index) CONSTRAINT</span></span>  
  
-   <span data-ttu-id="c9ab8-143">L'option d'index MAXDOP ne peut pas être spécifiée dans l'instruction ALTER INDEX REORGANIZE.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-143">The MAXDOP index option cannot be specified in the ALTER INDEX REORGANIZE statement.</span></span>  
  
-   <span data-ttu-id="c9ab8-144">Les besoins en mémoire des opérations d'index partitionné avec tri peuvent augmenter si l'optimiseur de requête applique des degrés de parallélisme à l'opération de construction.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-144">Memory requirements for partitioned index operations that require sorting can be greater if the query optimizer applies degrees of parallelism to the build operation.</span></span> <span data-ttu-id="c9ab8-145">Plus le degré de parallélisme est élevé, plus les besoins en mémoire sont importants.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-145">The higher the degrees of parallelism, the greater the memory requirement is.</span></span> <span data-ttu-id="c9ab8-146">Pour plus d’informations, consultez [Tables et index partitionnés](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="c9ab8-146">For more information, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c9ab8-147">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c9ab8-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c9ab8-148">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c9ab8-148">Permissions</span></span>  
 <span data-ttu-id="c9ab8-149">Nécessite une autorisation ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-149">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c9ab8-150">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c9ab8-150">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-max-degree-of-parallelism-on-an-index"></a><span data-ttu-id="c9ab8-151">Pour définir le degré maximal de parallélisme sur un index</span><span class="sxs-lookup"><span data-stu-id="c9ab8-151">To set max degree of parallelism on an index</span></span>  
  
1.  <span data-ttu-id="c9ab8-152">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer la base de données qui contient la table dans laquelle vous souhaitez spécifier un degré maximal de parallélisme pour un index.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to set max degree of parallelism for an index.</span></span>  
  
2.  <span data-ttu-id="c9ab8-153">Développez le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="c9ab8-153">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="c9ab8-154">Cliquez sur le signe plus (+) pour développer la table sur laquelle vous souhaitez définir le degré maximal de parallélisme pour un index.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-154">Click the plus sign to expand the table on which you want to set max degree of parallelism for an index.</span></span>  
  
4.  <span data-ttu-id="c9ab8-155">Développez le dossier **Index** .</span><span class="sxs-lookup"><span data-stu-id="c9ab8-155">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="c9ab8-156">Cliquez avec le bouton droit sur l’index où vous souhaitez définir le degré maximal de parallélisme et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-156">Right-click the index for which you want to set the max degree of parallelism and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="c9ab8-157">Sous **Sélectionner une page**, sélectionnez **Options**.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-157">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="c9ab8-158">Sélectionnez **Degré maximal de parallélisme**, puis entrez une valeur comprise entre 1 et 64.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-158">Select **Maximum degree of parallelism**, and then enter some value between 1 and 64.</span></span>  
  
8.  <span data-ttu-id="c9ab8-159">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-159">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c9ab8-160">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c9ab8-160">Using Transact-SQL</span></span>  
  
#### <a name="to-set-max-degree-of-parallelism-on-an-existing-index"></a><span data-ttu-id="c9ab8-161">Pour définir le degré maximal de parallélisme sur un index existant</span><span class="sxs-lookup"><span data-stu-id="c9ab8-161">To set max degree of parallelism on an existing index</span></span>  
  
1.  <span data-ttu-id="c9ab8-162">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ab8-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c9ab8-163">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-163">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c9ab8-164">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-164">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    /*Alters the IX_ProductVendor_VendorID index on the Purchasing.ProductVendor table so that, if the server has eight or more processors, the Database Engine will limit the execution of the index operation to eight or fewer processors.  
    */  
    ALTER INDEX IX_ProductVendor_VendorID ON Purchasing.ProductVendor  
    REBUILD WITH (MAXDOP=8);   
    GO  
    ```  
  
 <span data-ttu-id="c9ab8-165">Pour plus d’informations, consultez [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c9ab8-165">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
#### <a name="set-max-degree-of-parallelism-on-a-new-index"></a><span data-ttu-id="c9ab8-166">Définir le degré maximal de parallélisme sur un nouvel index</span><span class="sxs-lookup"><span data-stu-id="c9ab8-166">Set max degree of parallelism on a new index</span></span>  
  
1.  <span data-ttu-id="c9ab8-167">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9ab8-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c9ab8-168">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c9ab8-169">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c9ab8-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE INDEX IX_ProductVendor_NewVendorID   
    ON Purchasing.ProductVendor (BusinessEntityID)  
    WITH (MAXDOP=8);  
    GO  
    ```  
  
 <span data-ttu-id="c9ab8-170">Pour plus d’informations, consultez [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c9ab8-170">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
