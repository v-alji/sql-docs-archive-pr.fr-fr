---
title: Configurer l’option de configuration de serveur index create memory | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- index create memory option
ms.assetid: 3d722d9b-bada-4bf5-a9d7-bfc556bb4915
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6cd0aeb93d3fb68089338335068fdaaae19919fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700217"
---
# <a name="configure-the-index-create-memory-server-configuration-option"></a><span data-ttu-id="073d0-102">Configurer l'option de configuration de serveur index create memory</span><span class="sxs-lookup"><span data-stu-id="073d0-102">Configure the index create memory Server Configuration Option</span></span>
  <span data-ttu-id="073d0-103">Cette rubrique explique comment configurer l'option de configuration de serveur **index create memory** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="073d0-103">This topic describes how to configure the **index create memory** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="073d0-104">L'option **index create memory** contrôle la quantité maximale de mémoire initialement allouée pour la création d'index.</span><span class="sxs-lookup"><span data-stu-id="073d0-104">The **index create memory** option controls the maximum amount of memory initially allocated for creating indexes.</span></span> <span data-ttu-id="073d0-105">La valeur par défaut de cette option est 0 (auto-configuration).</span><span class="sxs-lookup"><span data-stu-id="073d0-105">The default value for this option is 0 (self-configuring).</span></span> <span data-ttu-id="073d0-106">Si une quantité supplémentaire de mémoire est requise ultérieurement pour créer les index et que cette quantité de mémoire est disponible, le serveur l'utilisera, outrepassant ainsi le paramétrage de cette option.</span><span class="sxs-lookup"><span data-stu-id="073d0-106">If more memory is later needed for index creation and the memory is available, the server will use it; thereby, exceeding the setting of this option.</span></span> <span data-ttu-id="073d0-107">Si la mémoire supplémentaire requise n'est pas disponible, la création d'index se poursuivra en utilisant la mémoire déjà allouée.</span><span class="sxs-lookup"><span data-stu-id="073d0-107">If additional memory is not available, the index creation will continue using the memory already allocated.</span></span>  
  
 <span data-ttu-id="073d0-108">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="073d0-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="073d0-109">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="073d0-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="073d0-110">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="073d0-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="073d0-111">Recommandations</span><span class="sxs-lookup"><span data-stu-id="073d0-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="073d0-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="073d0-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="073d0-113">**Pour configurer l'option index create memory, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="073d0-113">**To configure the index create memory option, using:**</span></span>  
  
     [<span data-ttu-id="073d0-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="073d0-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="073d0-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="073d0-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="073d0-116">**Suivi :**  [Après avoir configuré l’option index create memory](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="073d0-116">**Follow Up:**  [After you configure the index create memory option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="073d0-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="073d0-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="073d0-118">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="073d0-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="073d0-119">Le paramétrage de l’option **min memory per query** prévaut par rapport à celui de l’option **index create memory**.</span><span class="sxs-lookup"><span data-stu-id="073d0-119">The setting of the **min memory per query** option has precedence over the **index create memory** option.</span></span> <span data-ttu-id="073d0-120">Si vous modifiez ces deux options et que l’option **index create memory** est inférieur au paramètre **min memory per query**, un message d'avertissement s'affiche, mais la valeur définie est acceptée.</span><span class="sxs-lookup"><span data-stu-id="073d0-120">If you change both options and the **index create memory** is less than **min memory per query**, you receive a warning message, but the value is set.</span></span> <span data-ttu-id="073d0-121">Au cours de l'exécution d'une requête, un message d'avertissement similaire s'affiche.</span><span class="sxs-lookup"><span data-stu-id="073d0-121">During query execution, you receive a similar warning.</span></span>  
  
-   <span data-ttu-id="073d0-122">Lorsque vous utilisez des tables et des index partitionnés, la quantité minimale de mémoire requise pour la création d'index peut croître significativement en présence d'index partitionnés non alignés et d'un haut niveau de parallélisme.</span><span class="sxs-lookup"><span data-stu-id="073d0-122">When using partitioned tables and indexes, the minimum memory requirements for index creation may increase significantly if there are non-aligned partitioned indexes and a high degree of parallelism.</span></span> <span data-ttu-id="073d0-123">Cette option contrôle la quantité totale initiale de mémoire allouée pour toutes les partitions d'index, au sein d'une opération de création d'index.</span><span class="sxs-lookup"><span data-stu-id="073d0-123">This option controls the total initial amount of memory allocated for all index partitions in a single index creation operation.</span></span> <span data-ttu-id="073d0-124">La requête se terminera par l'apparition d'un message d'erreur si la quantité définie par cette option est inférieure au minimum requis pour exécuter cette requête.</span><span class="sxs-lookup"><span data-stu-id="073d0-124">The query will terminate with an error message if the amount set by this option is less than the minimum required to run the query.</span></span>  
  
-   <span data-ttu-id="073d0-125">La valeur d'exécution de cette option n'excédera pas la quantité réelle de mémoire pouvant être utilisée par le système d'exploitation et la plateforme matérielle sur lesquels [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute.</span><span class="sxs-lookup"><span data-stu-id="073d0-125">The run value for this option will not exceed the actual amount of memory that can be used for the operating system and hardware platform on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span> <span data-ttu-id="073d0-126">Sur les systèmes d'exploitation 32 bits, la valeur d'exécution sera inférieure à 3 gigaoctets (Go).</span><span class="sxs-lookup"><span data-stu-id="073d0-126">On 32-bit operating systems, the run value will be less than 3 gigabytes (GB).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="073d0-127">Recommandations</span><span class="sxs-lookup"><span data-stu-id="073d0-127">Recommendations</span></span>  
  
-   <span data-ttu-id="073d0-128">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="073d0-128">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="073d0-129">L’option **index create memory** est configurée automatiquement et fonctionne habituellement sans besoin de modification.</span><span class="sxs-lookup"><span data-stu-id="073d0-129">The **index create memory** option is self-configuring and usually works without requiring adjustment.</span></span> <span data-ttu-id="073d0-130">Cependant, si vous rencontrez des difficultés dans la création d'index, envisagez d'augmenter la valeur de cette option par rapport à sa valeur d'exécution.</span><span class="sxs-lookup"><span data-stu-id="073d0-130">However, if you experience difficulties creating indexes, consider increasing the value of this option from its run value.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="073d0-131">Sécurité</span><span class="sxs-lookup"><span data-stu-id="073d0-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="073d0-132">Autorisations</span><span class="sxs-lookup"><span data-stu-id="073d0-132">Permissions</span></span>  
 <span data-ttu-id="073d0-133">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="073d0-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="073d0-134">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="073d0-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="073d0-135">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="073d0-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="073d0-136">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="073d0-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-index-create-memory-option"></a><span data-ttu-id="073d0-137">Pour configurer l'option index create memory</span><span class="sxs-lookup"><span data-stu-id="073d0-137">To configure the index create memory option</span></span>  
  
1.  <span data-ttu-id="073d0-138">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="073d0-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="073d0-139">Cliquez sur le nœud **Mémoire** .</span><span class="sxs-lookup"><span data-stu-id="073d0-139">Click the **Memory** node.</span></span>  
  
3.  <span data-ttu-id="073d0-140">Sous **Mémoire de création de l'index**, tapez ou sélectionnez la valeur que vous souhaitez attribuer à l'option index create memory.</span><span class="sxs-lookup"><span data-stu-id="073d0-140">Under **Index creation memory**, type or select the desired value for the index create memory option.</span></span>  
  
     <span data-ttu-id="073d0-141">L'option **index create memory** permet de contrôler la quantité de mémoire utilisée par les tris de création d'index.</span><span class="sxs-lookup"><span data-stu-id="073d0-141">Use the **index create memory** option to control the amount of memory used by index creation sorts.</span></span> <span data-ttu-id="073d0-142">L’option **index create memory** est configurée automatiquement et doit fonctionner dans la plupart des cas sans besoin de modification.</span><span class="sxs-lookup"><span data-stu-id="073d0-142">The **index create memory** option is self-configuring and should work in most cases without requiring adjustment.</span></span> <span data-ttu-id="073d0-143">Cependant, si vous rencontrez des difficultés dans la création d'index, envisagez d'augmenter la valeur de cette option par rapport à sa valeur d'exécution.</span><span class="sxs-lookup"><span data-stu-id="073d0-143">However, if you experience difficulties creating indexes, consider increasing the value of this option from its run value.</span></span> <span data-ttu-id="073d0-144">Les tris de requête sont contrôlés au moyen de l'option **min memory per query** .</span><span class="sxs-lookup"><span data-stu-id="073d0-144">Query sorts are controlled through the **min memory per query** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="073d0-145">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="073d0-145">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-index-create-memory-option"></a><span data-ttu-id="073d0-146">Pour configurer l'option index create memory</span><span class="sxs-lookup"><span data-stu-id="073d0-146">To configure the index create memory option</span></span>  
  
1.  <span data-ttu-id="073d0-147">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="073d0-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="073d0-148">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="073d0-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="073d0-149">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="073d0-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="073d0-150">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `index create memory` la valeur `4096`.</span><span class="sxs-lookup"><span data-stu-id="073d0-150">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `index create memory` option to `4096`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
EXEC sp_configure 'index create memory', 4096  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="073d0-151">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="073d0-151">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-index-create-memory-option"></a><a name="FollowUp"></a> <span data-ttu-id="073d0-152">Suivi : Après avoir configuré l’option index create memory</span><span class="sxs-lookup"><span data-stu-id="073d0-152">Follow Up: After you configure the index create memory option</span></span>  
 <span data-ttu-id="073d0-153">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="073d0-153">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="073d0-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="073d0-154">See Also</span></span>  
 <span data-ttu-id="073d0-155">[sys.configurations &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="073d0-155">[sys.configurations &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) </span></span>  
 <span data-ttu-id="073d0-156">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="073d0-156">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="073d0-157">[Mémoire du serveur (option de configuration de serveur)](server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="073d0-157">[Server Memory Server Configuration Options](server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="073d0-158">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="073d0-158">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="073d0-159">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="073d0-159">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
