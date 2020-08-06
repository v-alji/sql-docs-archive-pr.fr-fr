---
title: Renommer une base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], renaming
- renaming databases
ms.assetid: 44c69d35-abcb-4da3-9370-5e0bc9a28496
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd25a78e3d3b9be2e7191ce6ed3d6bdcbb0f9606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604545"
---
# <a name="rename-a-database"></a><span data-ttu-id="8c6a9-102">Modifier le nom d'une base de données</span><span class="sxs-lookup"><span data-stu-id="8c6a9-102">Rename a Database</span></span>
  <span data-ttu-id="8c6a9-103">Cette rubrique explique comment renommer une base de données définie par l'utilisateur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c6a9-103">This topic describes how to rename a user-defined database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8c6a9-104">Le nom de la base de données peut contenir n'importe quel caractère conforme aux règles applicables aux identificateurs.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-104">The name of the database can include any characters that follow the rules for identifiers.</span></span>  
  
 <span data-ttu-id="8c6a9-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="8c6a9-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8c6a9-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="8c6a9-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8c6a9-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="8c6a9-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8c6a9-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8c6a9-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8c6a9-109">**Pour renommer une base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="8c6a9-109">**To rename a database, using:**</span></span>  
  
     [<span data-ttu-id="8c6a9-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8c6a9-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8c6a9-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8c6a9-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="8c6a9-112">**Suivi :**  [Après le renommage d’une base de données](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="8c6a9-112">**Follow Up:**  [After renaming a database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8c6a9-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="8c6a9-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8c6a9-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="8c6a9-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8c6a9-115">Les bases de données système ne peuvent pas être renommées.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-115">System databases cannot be renamed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8c6a9-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8c6a9-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8c6a9-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="8c6a9-117">Permissions</span></span>  
 <span data-ttu-id="8c6a9-118">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8c6a9-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8c6a9-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-database"></a><span data-ttu-id="8c6a9-120">Pour renommer une base de données</span><span class="sxs-lookup"><span data-stu-id="8c6a9-120">To rename a database</span></span>  
  
1.  <span data-ttu-id="8c6a9-121">Dans **l’Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], puis développez-la.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-121">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="8c6a9-122">Vérifiez que personne n’utilise la base de données, puis [configurez la base de données en mode mono-utilisateur](set-a-database-to-single-user-mode.md).</span><span class="sxs-lookup"><span data-stu-id="8c6a9-122">Make sure that no one is using the database, and then [set the database to single-user mode](set-a-database-to-single-user-mode.md).</span></span>  
  
3.  <span data-ttu-id="8c6a9-123">Développez **Bases de données**, cliquez avec le bouton droit sur la base de données à renommer, puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-123">Expand **Databases**, right-click the database to rename, and then click **Rename**.</span></span>  
  
4.  <span data-ttu-id="8c6a9-124">Entrez le nouveau nom de la base de données, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-124">Enter the new database name, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8c6a9-125">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8c6a9-125">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-database"></a><span data-ttu-id="8c6a9-126">Pour renommer une base de données</span><span class="sxs-lookup"><span data-stu-id="8c6a9-126">To rename a database</span></span>  
  
1.  <span data-ttu-id="8c6a9-127">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c6a9-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8c6a9-128">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8c6a9-129">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8c6a9-130">Cet exemple modifie le nom de la base de données `AdventureWorks2012` en `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="8c6a9-130">This example changes the name of the `AdventureWorks2012` database to `Northwind`.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
Modify Name = Northwind ;  
GO  
```  
  
###  <a name="TsqlExample"></a>   
##  <a name="follow-up-after-renaming-a-database"></a><a name="FollowUp"></a> <span data-ttu-id="8c6a9-131">Suivi : Après avoir renommé une base de données</span><span class="sxs-lookup"><span data-stu-id="8c6a9-131">Follow Up: After renaming a database</span></span>  
 <span data-ttu-id="8c6a9-132">Après avoir renommé une base de données, sauvegardez la base de données **master** .</span><span class="sxs-lookup"><span data-stu-id="8c6a9-132">Back up the **master** database after you rename any database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c6a9-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8c6a9-133">See Also</span></span>  
 <span data-ttu-id="8c6a9-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8c6a9-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="8c6a9-135">Identificateurs de base de données</span><span class="sxs-lookup"><span data-stu-id="8c6a9-135">Database Identifiers</span></span>](database-identifiers.md)  
  
  
