---
title: Afficher ou modifier les propriétés d’une base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- displaying databases
- database viewing [SQL Server]
- databases [SQL Server], viewing
- viewing databases
ms.assetid: 9e8ac097-84b7-46c7-85e3-c1e79f94d747
author: stevestein
ms.author: sstein
ms.openlocfilehash: d6aee7503ca02d47575be4e8103641f61d9696d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708423"
---
# <a name="view-or-change-the-properties-of-a-database"></a><span data-ttu-id="43d0c-102">Afficher ou modifier les propriétés d'une base de données</span><span class="sxs-lookup"><span data-stu-id="43d0c-102">View or Change the Properties of a Database</span></span>
  <span data-ttu-id="43d0c-103">Cette rubrique explique comment afficher ou modifier les propriétés d'une base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43d0c-103">This topic describes how to view or change the properties of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="43d0c-104">Lorsque vous modifiez une propriété de base de données, la modification prend effet immédiatement.</span><span class="sxs-lookup"><span data-stu-id="43d0c-104">After you change a database property, the modification takes effect immediately.</span></span>  
  
 <span data-ttu-id="43d0c-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="43d0c-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="43d0c-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="43d0c-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="43d0c-107">Recommandations</span><span class="sxs-lookup"><span data-stu-id="43d0c-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="43d0c-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="43d0c-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="43d0c-109">**Pour afficher ou modifier les propriétés d'une base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="43d0c-109">**To view or change the properties of a database, using:**</span></span>  
  
     [<span data-ttu-id="43d0c-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43d0c-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="43d0c-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43d0c-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="43d0c-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="43d0c-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="43d0c-113">Recommandations</span><span class="sxs-lookup"><span data-stu-id="43d0c-113">Recommendations</span></span>  
  
-   <span data-ttu-id="43d0c-114">Quand AUTO_CLOSE a la valeur ON, certaines colonnes de l’affichage catalogue [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) et la fonction DATABASEPROPERTYEX retournent la valeur NULL, car la base de données est inaccessible et qu’aucune donnée ne peut être extraite.</span><span class="sxs-lookup"><span data-stu-id="43d0c-114">When AUTO_CLOSE is ON, some columns in the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view and DATABASEPROPERTYEX function will return NULL because the database is unavailable to retrieve the data.</span></span> <span data-ttu-id="43d0c-115">Pour résoudre ce problème, exécutez une instruction USE pour ouvrir la base de données.</span><span class="sxs-lookup"><span data-stu-id="43d0c-115">To resolve this, execute a USE statement to open the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="43d0c-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="43d0c-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="43d0c-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="43d0c-117">Permissions</span></span>  
 <span data-ttu-id="43d0c-118">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="43d0c-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="43d0c-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43d0c-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-properties-of-a-database"></a><span data-ttu-id="43d0c-120">Pour afficher ou modifier les propriétés d'une base de données</span><span class="sxs-lookup"><span data-stu-id="43d0c-120">To view or change the properties of a database</span></span>  
  
1.  <span data-ttu-id="43d0c-121">Dans **l’Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], puis développez-la.</span><span class="sxs-lookup"><span data-stu-id="43d0c-121">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="43d0c-122">Développez **Bases de données**, cliquez avec le bouton droit sur la base de données à afficher, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="43d0c-122">Expand **Databases**, right-click the database to view, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="43d0c-123">Dans la boîte de dialogue **Propriétés de la base de données** , sélectionnez une page pour afficher les informations correspondantes.</span><span class="sxs-lookup"><span data-stu-id="43d0c-123">In the **Database Properties** dialog box, select a page to view the corresponding information.</span></span> <span data-ttu-id="43d0c-124">Par exemple, sélectionnez la page **Fichiers** pour afficher les informations sur les fichiers journaux et les fichiers de données.</span><span class="sxs-lookup"><span data-stu-id="43d0c-124">For example, select the **Files** page to view data and log file information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="43d0c-125">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43d0c-125">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-property-of-a-database-by-using-databasepropertyex"></a><span data-ttu-id="43d0c-126">Pour afficher une propriété d'une base de données à l'aide de DATABASEPROPERTYEX</span><span class="sxs-lookup"><span data-stu-id="43d0c-126">To view a property of a database by using DATABASEPROPERTYEX</span></span>  
  
1.  <span data-ttu-id="43d0c-127">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43d0c-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="43d0c-128">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="43d0c-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="43d0c-129">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="43d0c-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="43d0c-130">Cet exemple utilise la fonction système [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) pour retourner l’état de l’option de base de données AUTO_SHRINK dans la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="43d0c-130">This example uses the [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) system function to return the status of the AUTO_SHRINK database option in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="43d0c-131">Une valeur de retour de 1 signifie que l'option est activée (ON), et une valeur de retour de 0 signifie que l'option est désactivée (OFF).</span><span class="sxs-lookup"><span data-stu-id="43d0c-131">A return value of 1 means that the option is set to ON, and a return value of 0 means that the option is set to OFF.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT DATABASEPROPERTYEX('AdventureWorks2012', 'IsAutoShrink');  
GO  
  
```  
  
#### <a name="to-view-the-properties-of-a-database-by-querying-sysdatabases"></a><span data-ttu-id="43d0c-132">Pour afficher les propriétés d'une base de données en interrogeant sys.databases</span><span class="sxs-lookup"><span data-stu-id="43d0c-132">To view the properties of a database by querying sys.databases</span></span>  
  
1.  <span data-ttu-id="43d0c-133">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43d0c-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="43d0c-134">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="43d0c-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="43d0c-135">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="43d0c-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="43d0c-136">L'exemple suivant interroge l'affichage catalogue [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) pour afficher plusieurs propriétés de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="43d0c-136">This example queries the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view to view several properties of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="43d0c-137">Cet exemple renvoie le numéro d'ID de base de données (`database_id`), indique si la base de données est en lecture seule ou en lecture-écriture (`is_read_only`), et renvoie le classement de la base de données (`collation_name`) et le niveau de compatibilité de la base de données (`compatibility_level`).</span><span class="sxs-lookup"><span data-stu-id="43d0c-137">This example returns the database ID number (`database_id`), whether the database is read-only or read-write (`is_read_only`), the collation for the database (`collation_name`), and the database compatibility level (`compatibility_level`).</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT database_id, is_read_only, collation_name, compatibility_level  
FROM sys.databases WHERE name = 'AdventureWorks2012';  
GO  
  
```  
  
#### <a name="to-change-the-properties-of-a-database"></a><span data-ttu-id="43d0c-138">Pour modifier les propriétés d'une base de données</span><span class="sxs-lookup"><span data-stu-id="43d0c-138">To change the properties of a database</span></span>  
  
1.  <span data-ttu-id="43d0c-139">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43d0c-139">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="43d0c-140">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="43d0c-140">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="43d0c-141">Copiez et collez l'exemple suivant dans la fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="43d0c-141">Copy and paste the following example into the query window.</span></span> <span data-ttu-id="43d0c-142">L'exemple détermine l'état de l'isolement d'instantané sur la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , modifie l'état de la propriété, puis vérifie la modification.</span><span class="sxs-lookup"><span data-stu-id="43d0c-142">The example determines the state of snapshot isolation on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, changes the state of the property, and then verifies the change.</span></span>  
  
     <span data-ttu-id="43d0c-143">Pour déterminer l'état de l'isolement d'instantané, sélectionnez la première instruction `SELECT` et cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="43d0c-143">To determine the state of snapshot isolation, select the first `SELECT` statement and click **Execute**.</span></span>  
  
     <span data-ttu-id="43d0c-144">Pour modifier l'état de l'isolement d'instantané, sélectionnez l'instruction `ALTER DATABASE` , puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="43d0c-144">To change the state of snapshot isolation, select the `ALTER DATABASE` statement and click **Execute**.</span></span>  
  
     <span data-ttu-id="43d0c-145">Pour vérifier la modification, sélectionnez la deuxième instruction `SELECT` , puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="43d0c-145">To verify the change, select the second `SELECT` statement, and click **Execute**.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase9](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase9)]  
  
## <a name="see-also"></a><span data-ttu-id="43d0c-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43d0c-146">See Also</span></span>  
 <span data-ttu-id="43d0c-147">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="43d0c-147">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="43d0c-148">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span><span class="sxs-lookup"><span data-stu-id="43d0c-148">[ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) </span></span>  
 <span data-ttu-id="43d0c-149">[Options ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span><span class="sxs-lookup"><span data-stu-id="43d0c-149">[ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span></span>  
 <span data-ttu-id="43d0c-150">[Mise en miroir de bases de données ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="43d0c-150">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="43d0c-151">[Niveau de compatibilité ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span><span class="sxs-lookup"><span data-stu-id="43d0c-151">[ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) </span></span>  
 [<span data-ttu-id="43d0c-152">Options de fichiers et de groupes de fichiers ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="43d0c-152">ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options)  
  
  
