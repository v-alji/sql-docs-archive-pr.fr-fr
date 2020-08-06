---
title: Configurer l’option de configuration de serveur cursor threshold | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cursor threshold option
ms.assetid: 189f2067-c6c4-48bd-9bd9-65f6b2021c12
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0d7fd9ecafda270a02f1fba9f5dd74adc9e299d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614844"
---
# <a name="configure-the-cursor-threshold-server-configuration-option"></a><span data-ttu-id="ef95e-102">Configurer l'option de configuration de serveur cursor threshold</span><span class="sxs-lookup"><span data-stu-id="ef95e-102">Configure the cursor threshold Server Configuration Option</span></span>
  <span data-ttu-id="ef95e-103">Cette rubrique explique comment configurer l'option de configuration de serveur **cursor threshold** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef95e-103">This topic describes how to configure the **cursor threshold** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ef95e-104">L'option **cursor threshold** spécifie le nombre de lignes du jeu de curseurs à partir desquelles les jeux de clés de curseurs sont générés de façon asynchrone.</span><span class="sxs-lookup"><span data-stu-id="ef95e-104">The **cursor threshold** option specifies the number of rows in the cursor set at which cursor keysets are generated asynchronously.</span></span> <span data-ttu-id="ef95e-105">Lorsque le curseur génère un jeu de clés pour un jeu de résultats, l'optimiseur de requête évalue le nombre de lignes renvoyées pour ce jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="ef95e-105">When cursors generate a keyset for a result set, the query optimizer estimates the number of rows that will be returned for that result set.</span></span> <span data-ttu-id="ef95e-106">Si l'optimiseur de requête estime que le nombre de lignes renvoyées est plus élevé que ce seuil, le curseur est généré de façon asynchrone, ce qui permet à l'utilisateur de rechercher des lignes à partir du curseur alors que ce dernier continue d'être rempli.</span><span class="sxs-lookup"><span data-stu-id="ef95e-106">If the query optimizer estimates that the number of returned rows is greater than this threshold, the cursor is generated asynchronously, allowing the user to fetch rows from the cursor while the cursor continues to be populated.</span></span> <span data-ttu-id="ef95e-107">Dans le cas contraire, le curseur est généré de façon synchrone et la requête attend que toutes les lignes soient renvoyées.</span><span class="sxs-lookup"><span data-stu-id="ef95e-107">Otherwise, the cursor is generated synchronously, and the query waits until all rows are returned.</span></span>  
  
 <span data-ttu-id="ef95e-108">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="ef95e-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ef95e-109">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="ef95e-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ef95e-110">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="ef95e-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ef95e-111">Recommandations</span><span class="sxs-lookup"><span data-stu-id="ef95e-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="ef95e-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ef95e-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ef95e-113">**Pour configurer l'option cursor threshold, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="ef95e-113">**To configure the cursor threshold option, using:**</span></span>  
  
     [<span data-ttu-id="ef95e-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ef95e-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ef95e-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ef95e-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="ef95e-116">**Suivi :**  [Après avoir configuré l’option cursor threshold](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="ef95e-116">**Follow Up:**  [After you configure the cursor threshold option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ef95e-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ef95e-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ef95e-118">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="ef95e-118">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ef95e-119">ne prend pas en charge la génération asynchrone de curseurs [!INCLUDE[tsql](../../includes/tsql-md.md)] pilotés par jeux de clés ou statiques.</span><span class="sxs-lookup"><span data-stu-id="ef95e-119">does not support generating keyset-driven or static [!INCLUDE[tsql](../../includes/tsql-md.md)] cursors asynchronously.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="ef95e-120">sur les curseurs telles que OPEN ou FETCH sont exécutées par lot : la génération asynchrone de curseurs [!INCLUDE[tsql](../../includes/tsql-md.md)] n'est donc pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="ef95e-120">cursor operations such as OPEN or FETCH are batched, so there is no need for the asynchronous generation of [!INCLUDE[tsql](../../includes/tsql-md.md)] cursors.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ef95e-121">continue de prendre en charge les curseurs côté serveur d’API pilotés par jeux de clés ou statiques asynchrones si l’opération de curseur OPEN présente une latence trop faible, en raison des boucles clientes de chaque opération de curseur.</span><span class="sxs-lookup"><span data-stu-id="ef95e-121">continues to support asynchronous keyset-driven or static application programming interface (API) server cursors where low latency OPEN is a concern, due to client round trips for each cursor operation.</span></span>  
  
-   <span data-ttu-id="ef95e-122">La précision avec laquelle l'optimiseur de requête va évaluer le nombre de lignes d'un jeu de clés dépend du degré d'actualité des statistiques pour chacune des tables dans le curseur.</span><span class="sxs-lookup"><span data-stu-id="ef95e-122">The accuracy of the query optimizer to determine an estimate for the number of rows in a keyset depends on the currency of the statistics for each of the tables in the cursor.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="ef95e-123">Recommandations</span><span class="sxs-lookup"><span data-stu-id="ef95e-123">Recommendations</span></span>  
  
-   <span data-ttu-id="ef95e-124">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ef95e-124">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="ef95e-125">Si vous attribuez la valeur -1 à l’option **Seuil du curseur** , tous les jeux de clés sont générés de façon synchrone (ce qui avantage les jeux de curseurs de petite taille).</span><span class="sxs-lookup"><span data-stu-id="ef95e-125">If you set **cursor threshold** to -1, all keysets are generated synchronously, which benefits small cursor sets.</span></span> <span data-ttu-id="ef95e-126">Si vous attribuez la valeur 0 à l'option **cursor threshold** , tous les jeux de clés de curseurs sont générés de manière asynchrone.</span><span class="sxs-lookup"><span data-stu-id="ef95e-126">If you set **cursor threshold** to 0, all cursor keysets are generated asynchronously.</span></span> <span data-ttu-id="ef95e-127">Si d'autres valeurs sont définies, l'optimiseur de requêtes compare le nombre estimé de lignes du jeu de curseurs et crée le jeu de clés de façon asynchrone si ce nombre dépasse celui de l'option **cursor threshold**.</span><span class="sxs-lookup"><span data-stu-id="ef95e-127">With other values, the query optimizer compares the number of expected rows in the cursor set and builds the keyset asynchronously if it exceeds the number set in **cursor threshold**.</span></span> <span data-ttu-id="ef95e-128">N'attribuez pas une valeur trop faible à l'option **Seuil du curseur** , sachant que les petits jeux de résultats sont mieux générés de manière synchrone.</span><span class="sxs-lookup"><span data-stu-id="ef95e-128">Do not set **cursor threshold** too low, because small result sets are better built synchronously.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ef95e-129">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ef95e-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ef95e-130">Autorisations</span><span class="sxs-lookup"><span data-stu-id="ef95e-130">Permissions</span></span>  
 <span data-ttu-id="ef95e-131">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ef95e-131">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="ef95e-132">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="ef95e-132">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="ef95e-133">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="ef95e-133">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ef95e-134">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ef95e-134">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-cursor-threshold-option"></a><span data-ttu-id="ef95e-135">Pour configurer l'option cursor threshold</span><span class="sxs-lookup"><span data-stu-id="ef95e-135">To configure the cursor threshold option</span></span>  
  
1.  <span data-ttu-id="ef95e-136">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ef95e-136">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="ef95e-137">Cliquez sur le nœud **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="ef95e-137">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="ef95e-138">Sous **Divers**, modifiez l'option **Seuil du curseur** selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="ef95e-138">Under **Miscellaneous**, change the **Cursor Threshold** option to the value you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ef95e-139">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ef95e-139">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-cursor-threshold-option"></a><span data-ttu-id="ef95e-140">Pour configurer l'option cursor threshold</span><span class="sxs-lookup"><span data-stu-id="ef95e-140">To configure the cursor threshold option</span></span>  
  
1.  <span data-ttu-id="ef95e-141">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef95e-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ef95e-142">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="ef95e-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ef95e-143">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ef95e-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ef95e-144">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `cursor threshold` la valeur `0` pour que les jeux de clés du curseur soient générés de façon asynchrone.</span><span class="sxs-lookup"><span data-stu-id="ef95e-144">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the `cursor threshold` option to `0` so that cursor keysets are generated asynchronously.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'cursor threshold', 0 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="ef95e-145">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ef95e-145">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-cursor-threshold-option"></a><a name="FollowUp"></a> <span data-ttu-id="ef95e-146">Suivi : Après avoir configuré l’option cursor threshold</span><span class="sxs-lookup"><span data-stu-id="ef95e-146">Follow Up: After you configure the cursor threshold option</span></span>  
 <span data-ttu-id="ef95e-147">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="ef95e-147">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef95e-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef95e-148">See Also</span></span>  
 <span data-ttu-id="ef95e-149">[@@CURSOR_ROWS &#40;Transact-SQL&#41;](/sql/t-sql/functions/cursor-rows-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ef95e-149">[@@CURSOR_ROWS &#40;Transact-SQL&#41;](/sql/t-sql/functions/cursor-rows-transact-sql) </span></span>  
 <span data-ttu-id="ef95e-150">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ef95e-150">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="ef95e-151">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ef95e-151">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="ef95e-152">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ef95e-152">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="ef95e-153">UPDATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ef95e-153">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  
