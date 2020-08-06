---
title: Supprimer une base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- database removal [SQL Server], SQL Server Management Studio
- removing databases
- deleting databases
- dropping databases
- databases [SQL Server], dropping
- database removal [SQL Server]
ms.assetid: 1fd8c0f5-03e1-449a-af45-b8cacb479d9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 633d97815cf69da12f1aa67fd8ef626a2d46e0b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709559"
---
# <a name="delete-a-database"></a><span data-ttu-id="30b6f-102">Supprimer une base de données</span><span class="sxs-lookup"><span data-stu-id="30b6f-102">Delete a Database</span></span>
  <span data-ttu-id="30b6f-103">Cette rubrique explique comment supprimer une base de données définie par l'utilisateur dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30b6f-103">This topic describes how to delete a user-defined database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="30b6f-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="30b6f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="30b6f-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="30b6f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="30b6f-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="30b6f-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="30b6f-107">Composants requis</span><span class="sxs-lookup"><span data-stu-id="30b6f-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="30b6f-108">Recommandations</span><span class="sxs-lookup"><span data-stu-id="30b6f-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="30b6f-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="30b6f-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="30b6f-110">**Pour supprimer une base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="30b6f-110">**To delete a database, using:**</span></span>  
  
     [<span data-ttu-id="30b6f-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="30b6f-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="30b6f-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="30b6f-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="30b6f-113">**Suivi :**  [Après la suppression d’une base de données](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="30b6f-113">**Follow Up:**  [After deleting a database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="30b6f-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="30b6f-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="30b6f-115">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="30b6f-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="30b6f-116">Les bases de données système ne peuvent pas être supprimées.</span><span class="sxs-lookup"><span data-stu-id="30b6f-116">System databases cannot be deleted.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="30b6f-117">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="30b6f-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="30b6f-118">Supprimez les instantanés de la base de données qui existent.</span><span class="sxs-lookup"><span data-stu-id="30b6f-118">Delete any database snapshots that exist on the database.</span></span> <span data-ttu-id="30b6f-119">Pour plus d’informations, consultez [Supprimer un instantané de base de données &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="30b6f-119">For more information, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span>  
  
-   <span data-ttu-id="30b6f-120">Si la base de données intervient dans l'envoi de journaux, supprimez l'envoi de journaux.</span><span class="sxs-lookup"><span data-stu-id="30b6f-120">If the database is involved in log shipping, remove log shipping.</span></span>  
  
-   <span data-ttu-id="30b6f-121">Si la base de données est publiée pour une réplication transactionnelle, ou encore publiée ou souscrite pour une réplication de fusion, supprimez la réplication.</span><span class="sxs-lookup"><span data-stu-id="30b6f-121">If the database is published for transactional replication, or published or subscribed to merge replication, remove replication from the database.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="30b6f-122">Recommandations</span><span class="sxs-lookup"><span data-stu-id="30b6f-122">Recommendations</span></span>  
  
-   <span data-ttu-id="30b6f-123">Effectuez une sauvegarde complète de la base de données.</span><span class="sxs-lookup"><span data-stu-id="30b6f-123">Consider taking a full backup of the database.</span></span> <span data-ttu-id="30b6f-124">Vous ne pouvez recréer une base de données supprimée qu'en restaurant une copie de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="30b6f-124">A deleted database can be re-created only by restoring a backup.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="30b6f-125">Sécurité</span><span class="sxs-lookup"><span data-stu-id="30b6f-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="30b6f-126">Autorisations</span><span class="sxs-lookup"><span data-stu-id="30b6f-126">Permissions</span></span>  
 <span data-ttu-id="30b6f-127">Pour exécuter DROP DATABASE, un utilisateur doit au moins disposer de l'autorisation CONTROL sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="30b6f-127">To execute DROP DATABASE, at a minimum, a user must have CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="30b6f-128">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="30b6f-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-database"></a><span data-ttu-id="30b6f-129">Pour supprimer une base de données</span><span class="sxs-lookup"><span data-stu-id="30b6f-129">To delete a database</span></span>  
  
1.  <span data-ttu-id="30b6f-130">Dans **l’Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], puis développez-la.</span><span class="sxs-lookup"><span data-stu-id="30b6f-130">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="30b6f-131">Développez le dossier **Bases de données**, cliquez avec le bouton droit sur la base de données à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="30b6f-131">Expand **Databases**, right-click the database to delete, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="30b6f-132">Vérifiez que la base de données correcte est sélectionnée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="30b6f-132">Confirm the correct database is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="30b6f-133">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="30b6f-133">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-database"></a><span data-ttu-id="30b6f-134">Pour supprimer une base de données</span><span class="sxs-lookup"><span data-stu-id="30b6f-134">To delete a database</span></span>  
  
1.  <span data-ttu-id="30b6f-135">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30b6f-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="30b6f-136">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="30b6f-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="30b6f-137">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="30b6f-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="30b6f-138">L'exemple suivant supprime les bases de données `Sales` et `NewSales` .</span><span class="sxs-lookup"><span data-stu-id="30b6f-138">The example removes the `Sales` and `NewSales` databases.</span></span>  
  
```sql  
USE master ;  
GO  
DROP DATABASE Sales, NewSales ;  
GO  
```  
  
##  <a name="follow-up-after-deleting-a-database"></a><a name="FollowUp"></a> <span data-ttu-id="30b6f-139">Suivi : Après la suppression d’une base de données</span><span class="sxs-lookup"><span data-stu-id="30b6f-139">Follow Up: After deleting a database</span></span>  
 <span data-ttu-id="30b6f-140">Sauvegardez la base de données **master** .</span><span class="sxs-lookup"><span data-stu-id="30b6f-140">Back up the **master** database.</span></span> <span data-ttu-id="30b6f-141">Si vous devez restaurer la base de données **master** , toutes les bases de données supprimées depuis la dernière sauvegarde de **master** seront encore référencées dans les vues du catalogue système, ce qui risque de générer des messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="30b6f-141">If **master** must be restored, any database that has been deleted since the last backup of **master** will still have references in the system catalog views and may cause error messages to be raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30b6f-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="30b6f-142">See Also</span></span>  
 <span data-ttu-id="30b6f-143">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="30b6f-143">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="30b6f-144">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="30b6f-144">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
