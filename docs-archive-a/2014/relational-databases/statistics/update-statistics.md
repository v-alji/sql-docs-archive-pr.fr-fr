---
title: Mettre à jour les statistiques | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- updating statistics
- statistics [SQL Server], updating
ms.assetid: 4b97c0b4-03ff-4cfb-9c3f-3b33290b7a2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 28491dda23c2ba9402e91dc051249f5bdcdf28d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613361"
---
# <a name="update-statistics"></a><span data-ttu-id="58237-102">Mettre à jour les statistiques</span><span class="sxs-lookup"><span data-stu-id="58237-102">Update Statistics</span></span>
  <span data-ttu-id="58237-103">Vous pouvez mettre à jour les statistiques d'optimisation de requête sur une table ou une vue indexée dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58237-103">You can update query optimization statistics on a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="58237-104">Par défaut, l'optimiseur de requête met à jour les statistiques en fonction des besoins afin d'améliorer le plan de requête ; dans certains cas, vous pouvez optimiser les performances des requêtes en utilisant UPDATE STATISTICS ou la procédure stockée `sp_updatestats` pour mettre à jour les statistiques de manière plus fréquente qu'avec les mises à jour par défaut.</span><span class="sxs-lookup"><span data-stu-id="58237-104">By default, the query optimizer already updates statistics as necessary to improve the query plan; in some cases you can improve query performance by using UPDATE STATISTICS or the stored procedure `sp_updatestats` to update statistics more frequently than the default updates.</span></span>  
  
 <span data-ttu-id="58237-105">La mise à jour des statistiques est l'assurance que les requêtes sont compilées avec des statistiques à jour.</span><span class="sxs-lookup"><span data-stu-id="58237-105">Updating statistics ensures that queries compile with up-to-date statistics.</span></span> <span data-ttu-id="58237-106">Toutefois, la mise à jour des statistiques entraîne une recompilation des requêtes.</span><span class="sxs-lookup"><span data-stu-id="58237-106">However, updating statistics causes queries to recompile.</span></span> <span data-ttu-id="58237-107">À ce titre, il est déconseillé de mettre à jour les statistiques de façon trop régulière eu égard aux performances. Un compromis doit être trouvé entre le souhait d'améliorer les plans de requête et le temps nécessaire à la recompilation des requêtes.</span><span class="sxs-lookup"><span data-stu-id="58237-107">We recommend not updating statistics too frequently because there is a performance tradeoff between improving query plans and the time it takes to recompile queries.</span></span> <span data-ttu-id="58237-108">Ce compromis peut varier en fonction de votre application.</span><span class="sxs-lookup"><span data-stu-id="58237-108">The specific tradeoffs depend on your application.</span></span> <span data-ttu-id="58237-109">UPDATE STATISTICS peut utiliser tempdb pour trier l’échantillon de lignes à des fins statistiques.</span><span class="sxs-lookup"><span data-stu-id="58237-109">UPDATE STATISTICS can use tempdb to sort the sample of rows for building statistics.</span></span>  
  
 <span data-ttu-id="58237-110">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="58237-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="58237-111">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="58237-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="58237-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="58237-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="58237-113">**Pour mettre à jour un objet de statistiques, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="58237-113">**To update a statistics object, using:**</span></span>  
  
     [<span data-ttu-id="58237-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="58237-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="58237-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="58237-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="58237-116">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="58237-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="58237-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="58237-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="58237-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="58237-118">Permissions</span></span>  
 <span data-ttu-id="58237-119">L'utilisation d'UPDATE STATISTICS ou l'apport de modifications par le biais de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]exige l'autorisation ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="58237-119">If using UPDATE STATISTICS or making changes through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], requires ALTER permission on the table or view.</span></span> <span data-ttu-id="58237-120">En cas d’utilisation de `sp_updatestats`, nécessite l’appartenance au rôle serveur fixe **sysadmin** ou la propriété de la base de données (**dbo**).</span><span class="sxs-lookup"><span data-stu-id="58237-120">If using `sp_updatestats`, requires membership in the **sysadmin** fixed server role, or ownership of the database (**dbo**).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="58237-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="58237-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-update-a-statistics-object"></a><span data-ttu-id="58237-122">Pour mettre à jour un objet de statistiques</span><span class="sxs-lookup"><span data-stu-id="58237-122">To update a statistics object</span></span>  
  
1.  <span data-ttu-id="58237-123">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer la base de données dans laquelle vous souhaitez mettre à jour la statistique.</span><span class="sxs-lookup"><span data-stu-id="58237-123">In **Object Explorer**, click the plus sign to expand the database in which you want to update the statistic.</span></span>  
  
2.  <span data-ttu-id="58237-124">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="58237-124">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="58237-125">Cliquez sur le signe plus (+) pour développer la table dans laquelle vous souhaitez mettre à jour la statistique.</span><span class="sxs-lookup"><span data-stu-id="58237-125">Click the plus sign to expand the table in which you want to update the statistic.</span></span>  
  
4.  <span data-ttu-id="58237-126">Cliquez sur le signe plus (+) pour développer le dossier **Statistiques** .</span><span class="sxs-lookup"><span data-stu-id="58237-126">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="58237-127">Cliquez avec le bouton droit sur l’objet de statistiques à mettre à jour et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="58237-127">Right-click the statistics object you wish to update and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="58237-128">Dans la boîte de dialogue **Propriétés des statistiques-**_statistics_name_ , activez la case à cocher **mettre à jour les statistiques pour ces colonnes** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="58237-128">In the **Statistics Properties -**_statistics_name_ dialog box, select the **Update statistics for these columns** check box and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="58237-129">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="58237-129">Using Transact-SQL</span></span>  
  
#### <a name="to-update-a-specific-statistics-object"></a><span data-ttu-id="58237-130">Pour mettre à jour un objet de statistiques spécifique</span><span class="sxs-lookup"><span data-stu-id="58237-130">To update a specific statistics object</span></span>  
  
1.  <span data-ttu-id="58237-131">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58237-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="58237-132">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="58237-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="58237-133">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="58237-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- The following example updates the statistics for the AK_SalesOrderDetail_rowguid index of the SalesOrderDetail table.   
    UPDATE STATISTICS Sales.SalesOrderDetail AK_SalesOrderDetail_rowguid;   
    GO  
    ```  
  
#### <a name="to-update-all-statistics-in-a-table"></a><span data-ttu-id="58237-134">Pour mettre à jour toutes les statistiques d'une table</span><span class="sxs-lookup"><span data-stu-id="58237-134">To update all statistics in a table</span></span>  
  
1.  <span data-ttu-id="58237-135">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58237-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="58237-136">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="58237-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="58237-137">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="58237-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- The following example updates the statistics for all indexes on the SalesOrderDetail table.   
    UPDATE STATISTICS Sales.SalesOrderDetail;   
    GO  
    ```  
  
 <span data-ttu-id="58237-138">Pour plus d’informations, consultez [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="58237-138">For more information, see [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
#### <a name="to-update-all-statistics-in-a-database"></a><span data-ttu-id="58237-139">Pour mettre à jour toutes les statistiques d'une base de données</span><span class="sxs-lookup"><span data-stu-id="58237-139">To update all statistics in a database</span></span>  
  
1.  <span data-ttu-id="58237-140">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58237-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="58237-141">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="58237-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="58237-142">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="58237-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- The following example updates the statistics for all tables in the database.   
    EXEC sp_updatestats;  
    ```  
  
 <span data-ttu-id="58237-143">Pour plus d’informations, consultez [sp_updatestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-updatestats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="58237-143">For more information, see [sp_updatestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-updatestats-transact-sql).</span></span>  
  
  
