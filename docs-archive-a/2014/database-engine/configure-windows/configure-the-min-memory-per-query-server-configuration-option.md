---
title: Configurer l’option de configuration de serveur min memory per query | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- memory [SQL Server], queries
- minimum query memory
- queries [SQL Server], memory
- min memory per query option
ms.assetid: ecd3fb79-b4a6-432f-9ef5-530e0d42d5a6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 56d85f36840f0900c8b5e986334a99ba610d3930
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611292"
---
# <a name="configure-the-min-memory-per-query-server-configuration-option"></a><span data-ttu-id="234fd-102">Configurer l'option de configuration de serveur min memory per query</span><span class="sxs-lookup"><span data-stu-id="234fd-102">Configure the min memory per query Server Configuration Option</span></span>
  <span data-ttu-id="234fd-103">Cette rubrique explique comment configurer l' `min memory per query` option de configuration de serveur dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="234fd-103">This topic describes how to configure the `min memory per query` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="234fd-104">L' `min memory per query` option spécifie la quantité minimale de mémoire (en kilo-octets) qui sera allouée à l’exécution d’une requête.</span><span class="sxs-lookup"><span data-stu-id="234fd-104">The `min memory per query` option specifies the minimum amount of memory (in kilobytes) that will be allocated for the execution of a query.</span></span> <span data-ttu-id="234fd-105">Par exemple, si `min memory per query` a la valeur 2 048 Ko, la requête est garantie d’obtenir au moins cette quantité de mémoire totale.</span><span class="sxs-lookup"><span data-stu-id="234fd-105">For example, if `min memory per query` is set to 2,048 KB, the query is guaranteed to get at least that much total memory.</span></span> <span data-ttu-id="234fd-106">La valeur par défaut est 1 024 Ko.</span><span class="sxs-lookup"><span data-stu-id="234fd-106">The default value is 1,024 KB.</span></span> <span data-ttu-id="234fd-107">La valeur minimale est de 512 Ko et la valeur maximale de 2 147 483 647 Ko (2 Go).</span><span class="sxs-lookup"><span data-stu-id="234fd-107">The minimum value 512 KB, and the maximum is 2,147,483,647 KB (2 GB).</span></span>  
  
 <span data-ttu-id="234fd-108">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="234fd-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="234fd-109">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="234fd-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="234fd-110">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="234fd-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="234fd-111">Recommandations</span><span class="sxs-lookup"><span data-stu-id="234fd-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="234fd-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="234fd-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="234fd-113">**Pour configurer l'option min memory per query, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="234fd-113">**To configure the min memory per query option, using:**</span></span>  
  
     [<span data-ttu-id="234fd-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="234fd-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="234fd-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="234fd-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="234fd-116">**Suivi :**  [Après avoir configuré l’option min memory per query](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="234fd-116">**Follow Up:**  [After you configure the min memory per query option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="234fd-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="234fd-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="234fd-118">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="234fd-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="234fd-119">La quantité de mémoire minimale par requête est prioritaire sur l' [option index create memory](configure-the-index-create-memory-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="234fd-119">The amount of min memory per query has precedence over the [index create memory Option](configure-the-index-create-memory-server-configuration-option.md).</span></span> <span data-ttu-id="234fd-120">Si vous modifiez ces deux options et que le paramètre index create memory est inférieur au paramètre min memory per query, un message d’avertissement s’affiche, mais la valeur définie est acceptée.</span><span class="sxs-lookup"><span data-stu-id="234fd-120">If you modify both options and the index create memory is less than min memory per query, you receive a warning message, but the value is set.</span></span> <span data-ttu-id="234fd-121">Vous obtenez un avertissement similaire lors de l'exécution de requêtes.</span><span class="sxs-lookup"><span data-stu-id="234fd-121">During query execution you receive another similar warning.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="234fd-122">Recommandations</span><span class="sxs-lookup"><span data-stu-id="234fd-122">Recommendations</span></span>  
  
-   <span data-ttu-id="234fd-123">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="234fd-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="234fd-124">Le processeur de requêtes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tente de déterminer la quantité de mémoire optimale à allouer à une requête.</span><span class="sxs-lookup"><span data-stu-id="234fd-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query processor tries to determine the optimal amount of memory to allocate to a query.</span></span> <span data-ttu-id="234fd-125">L'option min memory per query permet à l'administrateur de spécifier la quantité minimale de mémoire que reçoit n'importe quelle requête.</span><span class="sxs-lookup"><span data-stu-id="234fd-125">The min memory per query option lets the administrator specify the minimum amount of memory any single query receives.</span></span> <span data-ttu-id="234fd-126">Les requêtes reçoivent généralement une quantité de mémoire supérieure si elles doivent effectuer des opérations de hachage et de tri sur un volume de données important.</span><span class="sxs-lookup"><span data-stu-id="234fd-126">Queries generally receive more memory than this if they have hash and sort operations on a large volume of data.</span></span> <span data-ttu-id="234fd-127">L'attribution d'une valeur supérieure à min memory per query peut améliorer les performances pour certaines requêtes de taille petite à moyenne, mais cela risque de donner lieu à une concurrence accrue pour les ressources mémoire.</span><span class="sxs-lookup"><span data-stu-id="234fd-127">Increasing the value of min memory per query may improve performance for some small to medium-sized queries, but doing so could lead to increased competition for memory resources.</span></span> <span data-ttu-id="234fd-128">L’option min memory per query inclut la mémoire allouée au tri.</span><span class="sxs-lookup"><span data-stu-id="234fd-128">The min memory per query option includes memory allocated for sorting.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="234fd-129">Sécurité</span><span class="sxs-lookup"><span data-stu-id="234fd-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="234fd-130">Autorisations</span><span class="sxs-lookup"><span data-stu-id="234fd-130">Permissions</span></span>  
 <span data-ttu-id="234fd-131">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="234fd-131">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="234fd-132">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="234fd-132">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="234fd-133">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="234fd-133">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="234fd-134">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="234fd-134">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-min-memory-per-query-option"></a><span data-ttu-id="234fd-135">Pour configurer l'option min memory per query</span><span class="sxs-lookup"><span data-stu-id="234fd-135">To configure the min memory per query option</span></span>  
  
1.  <span data-ttu-id="234fd-136">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="234fd-136">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="234fd-137">Cliquez sur le nœud **Mémoire** .</span><span class="sxs-lookup"><span data-stu-id="234fd-137">Click the **Memory** node.</span></span>  
  
3.  <span data-ttu-id="234fd-138">Dans la zone **Mémoire minimum par requête** , entrez la quantité minimale de mémoire (en kilo-octets) allouée pour l’exécution d’une requête.</span><span class="sxs-lookup"><span data-stu-id="234fd-138">In the **Minimum memory per query** box, enter the minimum amount of memory (in kilobytes) that will be allocated for the execution of a query.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="234fd-139">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="234fd-139">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-min-memory-per-query-option"></a><span data-ttu-id="234fd-140">Pour configurer l'option min memory per query</span><span class="sxs-lookup"><span data-stu-id="234fd-140">To configure the min memory per query option</span></span>  
  
1.  <span data-ttu-id="234fd-141">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="234fd-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="234fd-142">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="234fd-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="234fd-143">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="234fd-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="234fd-144">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `min memory per query` la valeur `3500` Ko.</span><span class="sxs-lookup"><span data-stu-id="234fd-144">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `min memory per query` option to `3500` KB.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'min memory per query', 3500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
##  <a name="follow-up-after-you-configure-the-min-memory-per-query-option"></a><a name="FollowUp"></a> <span data-ttu-id="234fd-145">Suivi : Après avoir configuré l’option min memory per query</span><span class="sxs-lookup"><span data-stu-id="234fd-145">Follow Up: After you configure the min memory per query option</span></span>  
 <span data-ttu-id="234fd-146">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="234fd-146">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="234fd-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="234fd-147">See Also</span></span>  
 <span data-ttu-id="234fd-148">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="234fd-148">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="234fd-149">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="234fd-149">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="234fd-150">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="234fd-150">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="234fd-151">Configurer l’option de configuration Création d’index en mémoire.</span><span class="sxs-lookup"><span data-stu-id="234fd-151">Configure the index create memory Server Configuration Option</span></span>](configure-the-index-create-memory-server-configuration-option.md)  
  
  
