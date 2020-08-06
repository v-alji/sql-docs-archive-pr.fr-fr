---
title: Lier une base de données avec des tables optimisées en mémoire à un pool de ressources | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f222b1d5-d2fa-4269-8294-4575a0e78636
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: cd163c5d3bc7a2cd9051b8d37b8127a1cc88c30b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615142"
---
# <a name="bind-a-database-with-memory-optimized-tables-to-a-resource-pool"></a><span data-ttu-id="81892-102">Lier une base de données avec des tables optimisées en mémoire à un pool de ressources</span><span class="sxs-lookup"><span data-stu-id="81892-102">Bind a Database with Memory-Optimized Tables to a Resource Pool</span></span>
  <span data-ttu-id="81892-103">Un pool de ressources représente un sous-ensemble de ressources physiques qui peuvent être régies.</span><span class="sxs-lookup"><span data-stu-id="81892-103">A resource pool represents a subset of physical resources that can be governed.</span></span> <span data-ttu-id="81892-104">Par défaut, les bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont liées aux ressources du pool de ressources par défaut et consomment ces dernières.</span><span class="sxs-lookup"><span data-stu-id="81892-104">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases are bound to and consume the resources of the default resource pool.</span></span> <span data-ttu-id="81892-105">Pour empêcher que toutes les ressources de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] soient consommées par une ou plusieurs tables mémoire optimisées, et que d'autres utilisateurs consomment la mémoire requise par les tables mémoire optimisées, nous vous recommandons de créer un pool de ressources distinct afin de gérer la consommation de mémoire pour la base de données avec des tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="81892-105">To protect [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from having its resources consumed by one or more memory-optimized tables, and to prevent other memory users from consuming memory needed by memory-optimized tables, you should create a separate resource pool to manage memory consumption for the database with memory-optimized tables.</span></span>  
  
 <span data-ttu-id="81892-106">Une base de données ne peut être liée qu'à un seul pool de ressources.</span><span class="sxs-lookup"><span data-stu-id="81892-106">A database can be bound on only one resource pool.</span></span> <span data-ttu-id="81892-107">Toutefois, vous pouvez lier plusieurs bases de données au même pool.</span><span class="sxs-lookup"><span data-stu-id="81892-107">However, you can bind multiple databases to the same pool.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="81892-108">permet de lier une base de données sans tables optimisées en mémoire à un pool de ressources, mais cela n’a aucun effet.</span><span class="sxs-lookup"><span data-stu-id="81892-108">allows binding a database without memory-optimized tables to a resource pool but it has no effect.</span></span> <span data-ttu-id="81892-109">Vous pouvez lier une base de données à un pool de ressources nommé, si, à l'avenir, vous souhaitez créer des tables mémoire optimisées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="81892-109">You may want to bind a database to a named resource pool if, in future, you may want to create memory-optimized tables in the database.</span></span>  
  
 <span data-ttu-id="81892-110">Vous ne pouvez lier une base de données à un pool de ressources que si cette base de données et ce pool de ressources ont été créés au préalable.</span><span class="sxs-lookup"><span data-stu-id="81892-110">Before you can bind a database to a resource pool both the database and the resource pool must exist.</span></span> <span data-ttu-id="81892-111">La liaison prendra effet lors de la prochaine mise en ligne (ONLINE) de la base de données.</span><span class="sxs-lookup"><span data-stu-id="81892-111">The binding takes effect the next time the database is brought online.</span></span> <span data-ttu-id="81892-112">Pour plus d’informations, consultez [États d’une base de données](../databases/database-states.md) .</span><span class="sxs-lookup"><span data-stu-id="81892-112">See [Database States](../databases/database-states.md) for more information.</span></span>  
  
 <span data-ttu-id="81892-113">Pour plus d’informations sur les pools de ressources, consultez [Pool de ressources de Resource Governor](../resource-governor/resource-governor-resource-pool.md).</span><span class="sxs-lookup"><span data-stu-id="81892-113">For information about resource pools, see [Resource Governor Resource Pool](../resource-governor/resource-governor-resource-pool.md).</span></span>  
  
  
## <a name="create-the-database-and-resource-pool"></a><span data-ttu-id="81892-114">Créer la base de données et le pool de ressources</span><span class="sxs-lookup"><span data-stu-id="81892-114">Create the database and resource pool</span></span>  
 <span data-ttu-id="81892-115">Vous pouvez créer la base de données et le pool de ressources dans n'importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="81892-115">You can create the database and resource pool in any order.</span></span> <span data-ttu-id="81892-116">L'important est de créer les deux avant de procéder à leur liaison.</span><span class="sxs-lookup"><span data-stu-id="81892-116">What matters is that they both exist prior to binding the database to the resource pool.</span></span>  
  
### <a name="create-the-database"></a><span data-ttu-id="81892-117">Créer la base de données</span><span class="sxs-lookup"><span data-stu-id="81892-117">Create the database</span></span>  
 <span data-ttu-id="81892-118">Le code [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant crée la base de données IMOLTP_DB destinée à contenir une ou plusieurs tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="81892-118">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] creates a database named IMOLTP_DB which will contain one or more memory-optimized tables.</span></span> <span data-ttu-id="81892-119">Le chemin \<driveAndPath> doit exister avant d’exécuter cette commande.</span><span class="sxs-lookup"><span data-stu-id="81892-119">The path \<driveAndPath> must exist prior to running this command.</span></span>  
  
```sql  
CREATE DATABASE IMOLTP_DB  
GO  
ALTER DATABASE IMOLTP_DB ADD FILEGROUP IMOLTP_DB_fg CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE IMOLTP_DB ADD FILE( NAME = 'IMOLTP_DB_fg' , FILENAME = 'c:\data\IMOLTP_DB_fg') TO FILEGROUP IMOLTP_DB_fg;  
GO  
```  
  
### <a name="determine-the-minimum-value-for-min_memory_percent-and-max_memory_percent"></a><span data-ttu-id="81892-120">Déterminer la valeur minimale pour MIN_MEMORY_PERCENT et MAX_MEMORY_PERCENT</span><span class="sxs-lookup"><span data-stu-id="81892-120">Determine the minimum value for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT</span></span>  
 <span data-ttu-id="81892-121">Après avoir déterminé les besoins en mémoire des tables mémoire optimisées, vous devez déterminer le pourcentage de mémoire disponible dont vous avez besoin, et définir les pourcentages de mémoire sur cette valeur ou sur une valeur supérieure.</span><span class="sxs-lookup"><span data-stu-id="81892-121">Once you determine the memory needs for your memory-optimized tables, you need to determine what percentage of available memory you need, and set the memory percentages to that value or higher.</span></span>  
  
 <span data-ttu-id="81892-122">**Exemple :**  </span><span class="sxs-lookup"><span data-stu-id="81892-122">**Example:** </span></span>  
<span data-ttu-id="81892-123">Pour cet exemple, nous allons supposer que vos calculs ont déterminé que les tables et les index mémoire optimisés ont besoin de 16 Go de mémoire.</span><span class="sxs-lookup"><span data-stu-id="81892-123">For this example we will assume that from your calculations you determined that your memory-optimized tables and indexes need 16 GB of memory.</span></span> <span data-ttu-id="81892-124">Supposons que vous disposez de 32 Go de mémoire allouée.</span><span class="sxs-lookup"><span data-stu-id="81892-124">Assume that you have 32 GB of memory committed for your use.</span></span>  
  
 <span data-ttu-id="81892-125">À première vue, il semblerait que vous deviez définir MIN_MEMORY_PERCENT et MAX_MEMORY_PERCENT à 50 (16 est 50 % de 32).</span><span class="sxs-lookup"><span data-stu-id="81892-125">At first glance it could seem that you need to set MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT to 50 (16 is 50% of 32).</span></span>  <span data-ttu-id="81892-126">Cependant, cela ne permettrait pas de fournir à vos tables mémoire optimisées suffisamment de mémoire.</span><span class="sxs-lookup"><span data-stu-id="81892-126">However, that would not give your memory-optimized tables sufficient memory.</span></span> <span data-ttu-id="81892-127">En observant la table ci-dessous ([Pourcentage de mémoire disponible pour les tables et index mémoire optimisés](#percent-of-memory-available-for-memory-optimized-tables-and-indexes)), nous voyons que si vous disposez de 32 Go de mémoire allouée, seulement 80 % est disponible pour les tables et les index optimisés en mémoire.</span><span class="sxs-lookup"><span data-stu-id="81892-127">Looking at the table below ([Percent of memory available for memory-optimized tables and indexes](#percent-of-memory-available-for-memory-optimized-tables-and-indexes)) we see that if there is 32 GB of committed memory, only 80% of that is available for memory-optimized tables and indexes.</span></span>  <span data-ttu-id="81892-128">Par conséquent, il convient de calculer les pourcentages minimum et maximum en fonction de la mémoire, et non de la mémoire allouée.</span><span class="sxs-lookup"><span data-stu-id="81892-128">Therefore, we calculate the min and max percentages based upon the available memory, not the committed memory.</span></span>  
  
 `memoryNeedeed = 16`   
 `memoryCommitted = 32`   
 `availablePercent = 0.8`   
 `memoryAvailable = memoryCommitted * availablePercent`   
 `percentNeeded = memoryNeeded / memoryAvailable`  
  
 <span data-ttu-id="81892-129">Chiffres réels :</span><span class="sxs-lookup"><span data-stu-id="81892-129">Plugging in real numbes:</span></span>   
`percentNeeded = 16 / (32 * 0.8) = 16 / 25.6 = 0.625`  
  
 <span data-ttu-id="81892-130">Ainsi, vous avez besoin au moins de 62,5 % de la mémoire disponible pour obtenir les 16 Go requis pour vos tables et index mémoire optimisés.</span><span class="sxs-lookup"><span data-stu-id="81892-130">Thus you need at least 62.5% of the available memory to meet the 16 GB requirement of your memory-optimized tables and indexes.</span></span>  <span data-ttu-id="81892-131">Étant donné que les valeurs de MIN_MEMORY_PERCENT et MAX_MEMORY_PERCENT doivent être des entiers, nous devons les définir sur au moins 63 %.</span><span class="sxs-lookup"><span data-stu-id="81892-131">Since the values for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT must be integers, we set them to at least 63%.</span></span>  
  
### <a name="create-a-resource-pool-and-configure-memory"></a><span data-ttu-id="81892-132">Créer un pool de ressources et configurer la mémoire</span><span class="sxs-lookup"><span data-stu-id="81892-132">Create a resource pool and configure memory</span></span>  
 <span data-ttu-id="81892-133">Lors de la configuration de tables mémoire optimisées, la planification des capacités doit être effectuée sur MIN_MEMORY_PERCENT, et non sur MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="81892-133">When configuring memory for memory-optimized tables, the capacity planning should be done based on MIN_MEMORY_PERCENT, not on MAX_MEMORY_PERCENT.</span></span>  <span data-ttu-id="81892-134">Consultez [ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) pour des informations sur MIN_MEMORY_PERCENT et MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="81892-134">See [ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) for information on MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span> <span data-ttu-id="81892-135">Ce paramètre fournit une disponibilité de mémoire plus prédictible pour les tables mémoire optimisées, car MIN_MEMORY_PERCENT sollicite la mémoire d'autres pools de ressources pour s'assurer qu'il est servi.</span><span class="sxs-lookup"><span data-stu-id="81892-135">This provides more predictable memory availability for memory-optimized tables as MIN_MEMORY_PERCENT causes memory pressure to other resource pools to make sure it is honored.</span></span> <span data-ttu-id="81892-136">Pour garantir que la mémoire est disponible et éviter les conditions OOM (mémoire insuffisante), les valeurs de MIN_MEMORY_PERCENT et MAX_MEMORY_PERCENT doivent être identiques.</span><span class="sxs-lookup"><span data-stu-id="81892-136">To ensure that memory is available and help avoid out-of-memory conditions, the values for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT should be the same.</span></span> <span data-ttu-id="81892-137">Consultez [Pourcentage de mémoire disponible pour les tables et index mémoire optimisés](#percent-of-memory-available-for-memory-optimized-tables-and-indexes) ci-dessous pour obtenir le pourcentage de la mémoire disponible pour les tables optimisées en mémoire en fonction de la quantité de mémoire allouée.</span><span class="sxs-lookup"><span data-stu-id="81892-137">See [Percent of memory available for memory-optimized tables and indexes](#percent-of-memory-available-for-memory-optimized-tables-and-indexes) below for the percent of memory available for memory-optimized tables based on the amount of committed memory.</span></span>  
  
 <span data-ttu-id="81892-138">Consultez [Bonnes pratiques : Utilisation d'OLTP en mémoire dans un environnement de machine virtuelle](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) pour plus d’informations sur le fonctionnement dans un environnement de machine virtuelle.</span><span class="sxs-lookup"><span data-stu-id="81892-138">See [Best Practices: Using In-Memory OLTP in a VM environment](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) for more information when working in a VM environment.</span></span>  
  
 <span data-ttu-id="81892-139">Le code [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant crée un pool de ressources nommé Pool_IMOLTP avec la moitié de la mémoire disponible.</span><span class="sxs-lookup"><span data-stu-id="81892-139">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a resource pool named Pool_IMOLTP with half of the memory available for its use.</span></span>  <span data-ttu-id="81892-140">Une fois le pool créé, Resource Governor est reconfiguré afin d'inclure Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="81892-140">After the pool is created Resource Governor is reconfigured to include Pool_IMOLTP.</span></span>  
  
```sql  
-- set MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT to the same value  
CREATE RESOURCE POOL Pool_IMOLTP   
  WITH   
    ( MIN_MEMORY_PERCENT = 63,   
    MAX_MEMORY_PERCENT = 63 );  
GO  
  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="bind-the-database-to-the-pool"></a><span data-ttu-id="81892-141">Lier la base de données au pool</span><span class="sxs-lookup"><span data-stu-id="81892-141">Bind the database to the pool</span></span>  
 <span data-ttu-id="81892-142">Utilisez la fonction système `sp_xtp_bind_db_resource_pool` pour lier la base de données au pool de ressources.</span><span class="sxs-lookup"><span data-stu-id="81892-142">Use the system function `sp_xtp_bind_db_resource_pool` to bind the database to the resource pool.</span></span> <span data-ttu-id="81892-143">La fonction accepte deux paramètres : le nom de la base de données et le nom du pool de ressources.</span><span class="sxs-lookup"><span data-stu-id="81892-143">The function takes two parameters: the database name and the resource pool name.</span></span>  
  
 <span data-ttu-id="81892-144">Le code [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant définit une liaison de la base de données IMOLTP_DB au pool de ressources Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="81892-144">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] defines a binding of the database IMOLTP_DB to the resource pool Pool_IMOLTP.</span></span> <span data-ttu-id="81892-145">La liaison ne devient effective que lorsque vous mettez la base de données en ligne.</span><span class="sxs-lookup"><span data-stu-id="81892-145">The binding does not become effective until you bring the database online.</span></span>  
  
```sql  
EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'Pool_IMOLTP'  
GO  
```  
  
 <span data-ttu-id="81892-146">La fonction système sp_xtp_bind_db_resource_pool accepte deux paramètres de chaîne : database_name et pool_name.</span><span class="sxs-lookup"><span data-stu-id="81892-146">The system function sp_xtp_bind_db_resourece_pool takes two string parameters: database_name and pool_name.</span></span>  
  
## <a name="confirm-the-binding"></a><span data-ttu-id="81892-147">Confirmer la liaison</span><span class="sxs-lookup"><span data-stu-id="81892-147">Confirm the binding</span></span>  
 <span data-ttu-id="81892-148">Confirmez la liaison, en prenant soin de noter l'ID du pool de ressources pour IMOLTP_DB.</span><span class="sxs-lookup"><span data-stu-id="81892-148">Confirm the binding, noting the resource pool id for IMOLTP_DB.</span></span> <span data-ttu-id="81892-149">Cette valeur ne doit pas être NULL.</span><span class="sxs-lookup"><span data-stu-id="81892-149">It should not be NULL.</span></span>  
  
```sql  
SELECT d.database_id, d.name, d.resource_pool_id  
FROM sys.databases d  
GO  
```  
  
## <a name="make-the-binding-effective"></a><span data-ttu-id="81892-150">Rendre la liaison effective</span><span class="sxs-lookup"><span data-stu-id="81892-150">Make the binding effective</span></span>  
 <span data-ttu-id="81892-151">Vous devez mettre la base de données hors ligne, puis en ligne, après sa liaison au pool de ressources afin que la liaison prenne effet.</span><span class="sxs-lookup"><span data-stu-id="81892-151">You must take the database offline and back online after binding it to the resource pool for binding to take effect.</span></span> <span data-ttu-id="81892-152">Si votre base de données était déjà liée à un autre pool de ressources, cela supprime la mémoire allouée du pool précédent afin que les allocations de mémoire pour vos index et votre table mémoire optimisée émanent désormais du nouveau pool de ressources lié à la base de données.</span><span class="sxs-lookup"><span data-stu-id="81892-152">If your database was bound to an a different pool earlier, this removes the allocated memory from the previous resource pool and memory allocations for your memory-optimized table and indexes will now come from the resource pool newly bound with the database.</span></span>  
  
```sql  
USE master  
GO  
  
ALTER DATABASE IMOLTP_DB SET OFFLINE  
GO  
ALTER DATABASE IMOLTP_DB SET ONLINE  
GO  
  
USE IMOLTP_DB  
GO  
```  
  
 <span data-ttu-id="81892-153">Maintenant, la base de données est liée au pool de ressources.</span><span class="sxs-lookup"><span data-stu-id="81892-153">And now, the database is bound to the resource pool.</span></span>  
  
## <a name="change-min-memory-percent-and-max-memory-percent-on-an-existing-pool"></a><span data-ttu-id="81892-154">Modifier le pourcentage de mémoire minimal et le pourcentage de mémoire maximal sur un pool existant</span><span class="sxs-lookup"><span data-stu-id="81892-154">Change MIN MEMORY PERCENT and MAX MEMORY PERCENT on an existing pool</span></span>  
 <span data-ttu-id="81892-155">Si vous ajoutez de la mémoire supplémentaire au serveur ou si la quantité de mémoire requise pour vos tables mémoire optimisées change, il peut être nécessaire de remplacer la valeur de MIN_MEMORY_PERCENT et de MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="81892-155">If you add additional memory to the server or the amount of memory needed for your memory-optimized tables changes, you may need to alter the value of MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span> <span data-ttu-id="81892-156">Les étapes suivantes vous montrent comment modifier la valeur de MIN_MEMORY_PERCENT et de MAX_MEMORY_PERCENT sur un pool de ressources.</span><span class="sxs-lookup"><span data-stu-id="81892-156">The following steps show you how to alter the value of MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT on a resource pool.</span></span> <span data-ttu-id="81892-157">Consultez la section ci-dessous, pour des conseils sur les valeurs à utiliser pour MIN_MEMORY_PERCENT et MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="81892-157">See the section below, for guidance on what values to use for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span>  <span data-ttu-id="81892-158">Consultez la rubrique [Bonnes pratiques : Utilisation de l’OLTP en mémoire dans un environnement de machine virtuelle](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="81892-158">See the topic [Best Practices: Using In-Memory OLTP in a VM environment](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) for more information.</span></span>  
  
1.  <span data-ttu-id="81892-159">Utilisez `ALTER RESOURCE POOL` pour modifier à la fois la valeur de MIN_MEMORY_PERCENT et de MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="81892-159">Use `ALTER RESOURCE POOL` to change the value of both MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span>  
  
2.  <span data-ttu-id="81892-160">Utilisez `ALTER RESURCE GOVERNOR` pour reconfigurer Resource Governor avec les nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="81892-160">Use `ALTER RESURCE GOVERNOR` to reconfigure the Resource Governor with the new values.</span></span>  
  
 <span data-ttu-id="81892-161">**Exemple de Code**</span><span class="sxs-lookup"><span data-stu-id="81892-161">**Sample Code**</span></span>  
  
```sql  
ALTER RESOURCE POOL Pool_IMOLTP  
WITH  
     ( MIN_MEMORY_PERCENT = 70,  
       MAX_MEMORY_PERCENT = 70 )   
GO  
  
-- reconfigure the Resource Governor  
ALTER RESOURCE GOVERNOR RECONFIGURE  
GO  
```  
  
## <a name="percent-of-memory-available-for-memory-optimized-tables-and-indexes"></a><span data-ttu-id="81892-162">Pourcentage de mémoire disponible pour les tables et index mémoire optimisés</span><span class="sxs-lookup"><span data-stu-id="81892-162">Percent of memory available for memory-optimized tables and indexes</span></span>  
 <span data-ttu-id="81892-163">Si vous mappez une base de données avec des tables mémoire optimisées et une charge de travail [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] au même pool de ressources, Resource Governor définit un seuil interne pour l'utilisation de l' [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] afin que les utilisateurs du pool ne rencontrent aucun conflit au niveau de l'utilisation du pool.</span><span class="sxs-lookup"><span data-stu-id="81892-163">If you map a database with memory-optimized tables and a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] workload to the same resource pool, the Resource Governor sets an internal threshold for [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] use so that the users of the pool do not have conflicts over pool usage.</span></span> <span data-ttu-id="81892-164">D'une manière générale, le seuil d'utilisation de l' [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] représente environ 80 % du pool.</span><span class="sxs-lookup"><span data-stu-id="81892-164">Generally speaking, the threshold for [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] use is about 80% of the pool.</span></span> <span data-ttu-id="81892-165">Le tableau suivant montre les seuils réels pour différentes capacités de mémoire.</span><span class="sxs-lookup"><span data-stu-id="81892-165">The following table shows actual thresholds for various memory sizes.</span></span>  
  
 <span data-ttu-id="81892-166">Lorsque vous créez un pool de ressources dédié pour la base de données [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] , vous devez estimer la quantité de mémoire physique dont vous avez besoin pour les tables en mémoire compte tenu de la croissance des versions de ligne et des données.</span><span class="sxs-lookup"><span data-stu-id="81892-166">When you create a dedicated resource pool for the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] database, you need to estimate how much physical memory you need for the in-memory tables after accounting for row versions and data growth.</span></span> <span data-ttu-id="81892-167">Après avoir estimé la mémoire nécessaire, créez un pool de ressources avec un pourcentage de la mémoire cible allouée à l’instance SQL comme indiqué par la colonne « committed_target_kb » dans la DMV `sys.dm_os_sys_info` (reportez-vous à [sys.dm_os_sys_info](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-sys-info-transact-sql)).</span><span class="sxs-lookup"><span data-stu-id="81892-167">Once estimate the memory needed, you create a resource pool with a percent of the commit target memory for SQL Instance as reflected by column 'committed_target_kb' in the DMV `sys.dm_os_sys_info` (see [sys.dm_os_sys_info](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-sys-info-transact-sql)).</span></span> <span data-ttu-id="81892-168">Par exemple, créez un pool de ressources P1 avec 40 % de la mémoire totale disponible sur l'instance.</span><span class="sxs-lookup"><span data-stu-id="81892-168">For example, you can create a resource pool P1 with 40% of the total memory available to the instance.</span></span> <span data-ttu-id="81892-169">Parmi ces 40 %, le moteur [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] obtient un pourcentage plus petit pour enregistrer les données [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81892-169">Out of this 40%, the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine gets a smaller percent to store [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] data.</span></span>  <span data-ttu-id="81892-170">Cela a pour but de s'assurer que [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] ne consomme pas toute la mémoire de ce pool.</span><span class="sxs-lookup"><span data-stu-id="81892-170">This is done to make sure [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] does not consume all the memory from this pool.</span></span>  <span data-ttu-id="81892-171">Cette valeur de pourcentage inférieur dépend de la mémoire allouée cible.</span><span class="sxs-lookup"><span data-stu-id="81892-171">This value of the smaller percent depends upon the Target committed Memory.</span></span> <span data-ttu-id="81892-172">Le tableau suivant décrit la mémoire disponible pour la base de données [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] dans un pool de ressources (nommé ou par défaut) avant qu'une situation d'insuffisance de mémoire soit déclenchée.</span><span class="sxs-lookup"><span data-stu-id="81892-172">The following table describes memory available to [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] database in a resource pool (named or default) before an OOM error is raised.</span></span>  
  
|<span data-ttu-id="81892-173">Mémoire validée cible</span><span class="sxs-lookup"><span data-stu-id="81892-173">Target Committed Memory</span></span>|<span data-ttu-id="81892-174">Pourcentage disponible pour les tables en mémoire</span><span class="sxs-lookup"><span data-stu-id="81892-174">Percent available for in-memory tables</span></span>|  
|-----------------------------|---------------------------------------------|  
|<span data-ttu-id="81892-175"><= 8 Go</span><span class="sxs-lookup"><span data-stu-id="81892-175"><= 8 GB</span></span>|<span data-ttu-id="81892-176">70 %</span><span class="sxs-lookup"><span data-stu-id="81892-176">70%</span></span>|  
|<span data-ttu-id="81892-177"><= 16 Go</span><span class="sxs-lookup"><span data-stu-id="81892-177"><= 16 GB</span></span>|<span data-ttu-id="81892-178">75 %</span><span class="sxs-lookup"><span data-stu-id="81892-178">75%</span></span>|  
|<span data-ttu-id="81892-179"><= 32 Go</span><span class="sxs-lookup"><span data-stu-id="81892-179"><= 32 GB</span></span>|<span data-ttu-id="81892-180">80 %</span><span class="sxs-lookup"><span data-stu-id="81892-180">80%</span></span>|  
|<span data-ttu-id="81892-181">\<= 96 Go</span><span class="sxs-lookup"><span data-stu-id="81892-181">\<= 96 GB</span></span>|<span data-ttu-id="81892-182">85 %</span><span class="sxs-lookup"><span data-stu-id="81892-182">85%</span></span>|  
|<span data-ttu-id="81892-183">>96 Go</span><span class="sxs-lookup"><span data-stu-id="81892-183">>96 GB</span></span>|<span data-ttu-id="81892-184">90%</span><span class="sxs-lookup"><span data-stu-id="81892-184">90%</span></span>|  
  
 <span data-ttu-id="81892-185">Par exemple, si votre « mémoire allouée cible » est de 100 Go et vous estimez que les tables et les index à mémoire optimisée ont besoin de 60 Go de mémoire, créez un pool de ressources avec MAX_MEMORY_PERCENT = 67 (60 Go nécessaires/0,90 = 66,667 Go – arrondi à 67 Go ; 67 Go/100 Go installés = 67 %) pour vous assurer que vos objets [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] ont les 60 Go dont ils ont besoin.</span><span class="sxs-lookup"><span data-stu-id="81892-185">For example, if your 'target committed memory' is 100 GB, and you estimate your memory-optimized tables and indexes need 60GBof memory, then you can create a resource pool with MAX_MEMORY_PERCENT = 67 (60GB needed / 0.90 = 66.667GB - round up to 67GB; 67GB / 100GB installed = 67%) to ensure that your [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] objects have the 60GB they need.</span></span>  
  
 <span data-ttu-id="81892-186">Une fois qu'une base de données a été liée à un pool de ressources nommé, utilisez la requête suivante pour afficher les allocations de mémoire sur les différents pools de ressources.</span><span class="sxs-lookup"><span data-stu-id="81892-186">Once a database has been bound to a named resource pool, use the following query to see memory allocations across different resource pools.</span></span>  
  
```sql  
SELECT pool_id  
     , Name  
     , min_memory_percent  
     , max_memory_percent  
     , max_memory_kb/1024 AS max_memory_mb  
     , used_memory_kb/1024 AS used_memory_mb   
     , target_memory_kb/1024 AS target_memory_mb  
   FROM sys.dm_resource_governor_resource_pools  
```  
  
 <span data-ttu-id="81892-187">Les résultats indiquent que la mémoire consommée par les objets mémoire optimisés est de 1356 Mo dans le pool de ressources, PoolIMOLTP, avec une limite supérieure de 2307 Mo.</span><span class="sxs-lookup"><span data-stu-id="81892-187">This sample output shows that the memory taken by memory-optimized objects is 1356 MB in resource pool, PoolIMOLTP, with an upper bound of 2307 MB.</span></span> <span data-ttu-id="81892-188">Cette limite supérieure contrôle la mémoire totale pouvant être consommée par les objets mémoire optimisés système et utilisateur mappés à ce pool.</span><span class="sxs-lookup"><span data-stu-id="81892-188">This upper bound controls the total memory that can be taken by user and system memory-optimized objects mapped to this pool.</span></span>  
  
 <span data-ttu-id="81892-189">**Résultat de l'exemple** </span><span class="sxs-lookup"><span data-stu-id="81892-189">**Sample Output** </span></span>  
<span data-ttu-id="81892-190">Ce résultat concerne la base de données et les tables créées précédemment.</span><span class="sxs-lookup"><span data-stu-id="81892-190">This output is from the database and tables we created above.</span></span>  
  
```  
pool_id     Name        min_memory_percent max_memory_percent max_memory_mb used_memory_mb target_memory_mb  
----------- ----------- ------------------ ------------------ ------------- -------------- ----------------   
1           internal    0                  100                3845          125            3845  
2           default     0                  100                3845          32             3845  
259         PoolIMOLTP 0                  100                3845          1356           2307  
```  
  
 <span data-ttu-id="81892-191">Pour plus d’informations consultez [sys.dm_resource_governor_resource_pools (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-resource-pools-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="81892-191">For more information see [sys.dm_resource_governor_resource_pools (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-resource-pools-transact-sql).</span></span>  
  
 <span data-ttu-id="81892-192">Si vous ne liez pas votre base de données à un pool de ressources nommé, elle est liée au pool « par défaut ».</span><span class="sxs-lookup"><span data-stu-id="81892-192">If you do not bind your database to a named resource pool, it is bound to the 'default' pool.</span></span> <span data-ttu-id="81892-193">Étant donné que le pool de ressources par défaut est utilisé par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour la plupart des autres allocations, vous ne pourrez pas surveiller la mémoire consommée par les tables mémoire optimisées à l'aide de la DMV sys.dm_resource_governor_resource_pools précisément pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="81892-193">Since default resource pool is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for most other allocations, you will not be able to monitor memory consumed by memory-optimized tables using the DMV sys.dm_resource_governor_resource_pools accurately for the database of interest.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81892-194">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="81892-194">See Also</span></span>  
 <span data-ttu-id="81892-195">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="81892-195">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="81892-196">[sys.sp_xtp_unbind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="81892-196">[sys.sp_xtp_unbind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="81892-197">[Resource Governor](../resource-governor/resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="81892-197">[Resource Governor](../resource-governor/resource-governor.md) </span></span>  
 <span data-ttu-id="81892-198">[Pool de ressources de Resource Governor](../resource-governor/resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="81892-198">[Resource Governor Resource Pool](../resource-governor/resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="81892-199">[Créer un pool de ressources](../resource-governor/create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="81892-199">[Create a Resource Pool](../resource-governor/create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="81892-200">[Modifier les paramètres de pool de ressources](../resource-governor/change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="81892-200">[Change Resource Pool Settings](../resource-governor/change-resource-pool-settings.md) </span></span>  
 [<span data-ttu-id="81892-201">Supprimer un pool de ressources</span><span class="sxs-lookup"><span data-stu-id="81892-201">Delete a Resource Pool</span></span>](../resource-governor/delete-a-resource-pool.md)  
  
  
