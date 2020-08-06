---
title: Objet SQL Server User Settable | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- User Settable object
- SQLServer:User Settable
ms.assetid: 633de3ef-533c-4f0c-9c7b-c105129d8e94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7243ab4767c8de93dccf4556f136a94b47554d3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696751"
---
# <a name="sql-server-user-settable-object"></a><span data-ttu-id="954a1-102">Objet SQL Server User Settable</span><span class="sxs-lookup"><span data-stu-id="954a1-102">SQL Server, User Settable Object</span></span>
  <span data-ttu-id="954a1-103">L’objet **User Settable** de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vous permet de créer des instances de compteurs personnalisées.</span><span class="sxs-lookup"><span data-stu-id="954a1-103">The **User Settable** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows you to create custom counter instances.</span></span> <span data-ttu-id="954a1-104">La création de vos propres instances de compteurs est utile pour surveiller les aspects du serveur qui ne le sont pas par les compteurs existants, comme les composants propres à votre base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (par exemple, la détermination du nombre de commandes clients enregistrées ou l'inventaire des produits).</span><span class="sxs-lookup"><span data-stu-id="954a1-104">Use custom counter instances to monitor aspects of the server not monitored by existing counters, such as components unique to your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database (for example, the number of customer orders logged or the product inventory).</span></span>  
  
 <span data-ttu-id="954a1-105">L’objet **User Settable** contient 10 instances du compteur de requêtes : du **compteur utilisateur 1** au **compteur utilisateur 10**.</span><span class="sxs-lookup"><span data-stu-id="954a1-105">The **User Settable** object contains 10 instances of the query counter: **User counter 1** through **User counter 10**.</span></span> <span data-ttu-id="954a1-106">Ces compteurs correspondent aux procédures stockées [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**sp_user_counter1** à **sp_user_counter10**.</span><span class="sxs-lookup"><span data-stu-id="954a1-106">These counters map to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures **sp_user_counter1** through **sp_user_counter10**.</span></span> <span data-ttu-id="954a1-107">Comme ces procédures stockées sont exécutées par les applications de l'utilisateur, les valeurs définies par les procédures stockées sont affichées dans le Moniteur système.</span><span class="sxs-lookup"><span data-stu-id="954a1-107">As these stored procedures are executed by user applications, the values set by the stored procedures are displayed in System Monitor.</span></span> <span data-ttu-id="954a1-108">Un compteur peut surveiller toute valeur entière (par exemple une procédure stockée qui compte combien de fois un produit en particulier a été commandé en un jour).</span><span class="sxs-lookup"><span data-stu-id="954a1-108">A counter can monitor any single integer value (for example, a stored procedure that counts how many orders for a particular product have occurred in one day).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="954a1-109">Les procédures stockées des compteurs utilisateur ne sont pas automatiquement interrogées par le Moniteur système.</span><span class="sxs-lookup"><span data-stu-id="954a1-109">The user counter stored procedures are not polled automatically by System Monitor.</span></span> <span data-ttu-id="954a1-110">Pour que les valeurs d'un compteur soient mises à jour, les procédures doivent être explicitement exécutées par une application de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="954a1-110">They must be explicitly executed by a user application for the counter values to be updated.</span></span> <span data-ttu-id="954a1-111">Utilisez un déclencheur pour mettre automatiquement à jour la valeur du compteur.</span><span class="sxs-lookup"><span data-stu-id="954a1-111">Use a trigger to update the value of the counter automatically.</span></span> <span data-ttu-id="954a1-112">Par exemple, pour créer un compteur qui surveille le nombre de lignes d'une table, créez un déclencheur INSERT et DELETE sur la table qui exécute l'instruction suivante : `SELECT COUNT(*) FROM table`.</span><span class="sxs-lookup"><span data-stu-id="954a1-112">For example, to create a counter that monitors the number of rows in a table, create an INSERT and DELETE trigger on the table that executes the following statement: `SELECT COUNT(*) FROM table`.</span></span> <span data-ttu-id="954a1-113">Dès que le déclencheur est activé à la suite de l'exécution d'une opération INSERT ou DELETE sur la table, le compteur du Moniteur système est automatiquement mis à jour.</span><span class="sxs-lookup"><span data-stu-id="954a1-113">Whenever the trigger is fired because of an INSERT or DELETE operation occurring on the table, the System Monitor counter is automatically updated.</span></span>  
  
 <span data-ttu-id="954a1-114">Le tableau décrit l’objet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Définissable par l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="954a1-114">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **User Settable** object.</span></span>  
  
|<span data-ttu-id="954a1-115">Compteurs SQL Server User Settable</span><span class="sxs-lookup"><span data-stu-id="954a1-115">SQL Server User Settable counters</span></span>|<span data-ttu-id="954a1-116">Description</span><span class="sxs-lookup"><span data-stu-id="954a1-116">Description</span></span>|  
|---------------------------------------|-----------------|  
|<span data-ttu-id="954a1-117">**Requête**</span><span class="sxs-lookup"><span data-stu-id="954a1-117">**Query**</span></span>|<span data-ttu-id="954a1-118">L’objet **User Settable** contient le compteur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="954a1-118">The **User Settable** object contains the query counter.</span></span> <span data-ttu-id="954a1-119">Les utilisateurs configurent les **compteurs utilisateur** dans l’objet de requête.</span><span class="sxs-lookup"><span data-stu-id="954a1-119">Users configure the **User counters** within the query object.</span></span>|  
  
 <span data-ttu-id="954a1-120">Le tableau décrit les **instances** du compteur de **requêtes** .</span><span class="sxs-lookup"><span data-stu-id="954a1-120">This table describes the **instances** of the **Query** counter.</span></span>  
  
|<span data-ttu-id="954a1-121">Instances du compteur de requêtes</span><span class="sxs-lookup"><span data-stu-id="954a1-121">Query counter instances</span></span>|<span data-ttu-id="954a1-122">Description</span><span class="sxs-lookup"><span data-stu-id="954a1-122">Description</span></span>|  
|-----------------------------|-----------------|  
|<span data-ttu-id="954a1-123">**Compte utilisateur 1**</span><span class="sxs-lookup"><span data-stu-id="954a1-123">**User counter 1**</span></span>|<span data-ttu-id="954a1-124">Défini à l’aide de **sp_user_counter1**.</span><span class="sxs-lookup"><span data-stu-id="954a1-124">Defined using **sp_user_counter1**.</span></span>|  
|<span data-ttu-id="954a1-125">**Compteur utilisateur 2**</span><span class="sxs-lookup"><span data-stu-id="954a1-125">**User counter 2**</span></span>|<span data-ttu-id="954a1-126">Défini à l’aide de **sp_user_counter2**.</span><span class="sxs-lookup"><span data-stu-id="954a1-126">Defined using **sp_user_counter2**.</span></span>|  
|<span data-ttu-id="954a1-127">**Compteur utilisateur 3**</span><span class="sxs-lookup"><span data-stu-id="954a1-127">**User counter 3**</span></span>|<span data-ttu-id="954a1-128">Défini à l’aide de **sp_user_counter3**.</span><span class="sxs-lookup"><span data-stu-id="954a1-128">Defined using **sp_user_counter3**.</span></span>|  
|<span data-ttu-id="954a1-129">...</span><span class="sxs-lookup"><span data-stu-id="954a1-129">...</span></span>||  
|<span data-ttu-id="954a1-130">**Compte utilisateur 10**</span><span class="sxs-lookup"><span data-stu-id="954a1-130">**User counter 10**</span></span>|<span data-ttu-id="954a1-131">Défini à l’aide de **sp_user_counter10**.</span><span class="sxs-lookup"><span data-stu-id="954a1-131">Defined using **sp_user_counter10**.</span></span>|  
  
 <span data-ttu-id="954a1-132">Pour utiliser les procédures stockées du compteur utilisateur, exécutez-les à partir de votre propre application avec un seul paramètre entier qui représente la nouvelle valeur prise par le compteur.</span><span class="sxs-lookup"><span data-stu-id="954a1-132">To make use of the user counter stored procedures, execute them from your own application with a single integer parameter representing the new value for the counter.</span></span> <span data-ttu-id="954a1-133">Par exemple, pour faire passer le **compteur utilisateur 1** à la valeur 10, exécutez cette instruction Transact-SQL :</span><span class="sxs-lookup"><span data-stu-id="954a1-133">For example, to set **User counter 1** to the value 10, execute this Transact-SQL statement:</span></span>  
  
```  
EXECUTE sp_user_counter1 10  
```  
  
 <span data-ttu-id="954a1-134">Les procédures stockées du compteur utilisateur peuvent être appelées à partir de tout endroit où les autres procédures stockées peuvent être appelées, par exemple vos propres procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="954a1-134">The user counter stored procedures can be called from anywhere other stored procedures can be called, such as your own stored procedures.</span></span> <span data-ttu-id="954a1-135">Par exemple, vous pouvez créer la procédure stockée suivante pour compter le nombre de connexions et de tentatives de connexions qui ont eu lieu depuis qu'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a été lancée :</span><span class="sxs-lookup"><span data-stu-id="954a1-135">For example, you can create the following stored procedure to count the number of connections and attempted connections since an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was started:</span></span>  
  
```  
DROP PROC My_Proc  
GO  
CREATE PROC My_Proc  
AS   
   EXECUTE sp_user_counter1 @@CONNECTIONS  
GO  
```  
  
 <span data-ttu-id="954a1-136">La fonction @@CONNECTIONS retourne le nombre de connexions ou de tentatives de connexion depuis qu’une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a été lancée.</span><span class="sxs-lookup"><span data-stu-id="954a1-136">The @@CONNECTIONS function returns the number of connections or attempted connections since an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] started.</span></span> <span data-ttu-id="954a1-137">Cette valeur est transférée comme paramètre à la procédure stockée **sp_user_counter1** .</span><span class="sxs-lookup"><span data-stu-id="954a1-137">This value is passed to the **sp_user_counter1** stored procedure as the parameter.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="954a1-138">Les requêtes définies dans les procédures stockées du compteur utilisateur doivent être aussi simples que possible.</span><span class="sxs-lookup"><span data-stu-id="954a1-138">Make the queries defined in the user counter stored procedures as simple as possible.</span></span> <span data-ttu-id="954a1-139">Les requêtes sollicitant beaucoup de mémoire, comme les requêtes de tri ou de hachage, ou celles qui impliquent des volumes importants d'E/S sont d'une exécution coûteuse en ressources et peuvent affecter les performances.</span><span class="sxs-lookup"><span data-stu-id="954a1-139">Memory-intensive queries that perform substantial sort or hash operations or queries that perform large amounts of I/O are expensive to execute and can impact performance.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="954a1-140">Autorisations</span><span class="sxs-lookup"><span data-stu-id="954a1-140">Permissions</span></span>  
 <span data-ttu-id="954a1-141">**sp_user_counter** est disponible pour tous les utilisateurs, mais son utilisation peut être limitée pour chacun des compteurs de requêtes.</span><span class="sxs-lookup"><span data-stu-id="954a1-141">**sp_user_counter** is available for all users but can be restricted for any query counter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="954a1-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="954a1-142">See Also</span></span>  
 [<span data-ttu-id="954a1-143">Analyser l’utilisation des ressources &#40;Moniteur système&#41;</span><span class="sxs-lookup"><span data-stu-id="954a1-143">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
