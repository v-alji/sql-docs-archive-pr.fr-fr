---
title: Afficher ou modifier le niveau de compatibilité d’une base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- compatibility levels [SQL Server], viewing
- compatibility [SQL Server], databases
- compatibility levels [SQL Server], changing
ms.assetid: 579867ec-57cb-4cb8-af35-9688c1e9e15d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35cf7af50eba333440c42a1bac428df1fff156b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708440"
---
# <a name="view-or-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="7e386-102">Afficher ou modifier le niveau de compatibilité d'une base de données</span><span class="sxs-lookup"><span data-stu-id="7e386-102">View or Change the Compatibility Level of a Database</span></span>
  <span data-ttu-id="7e386-103">Cette rubrique explique comment afficher ou modifier le niveau de compatibilité d'une base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e386-103">This topic describes how to view or change the compatibility level of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7e386-104">Avant de modifier le niveau de compatibilité d'une base de données, vous devez comprendre l'impact de cette modification sur vos applications.</span><span class="sxs-lookup"><span data-stu-id="7e386-104">Before you change the compatibility level of a database, you should understand the impact of the change on your applications.</span></span> <span data-ttu-id="7e386-105">Pour plus d’informations, consultez [Niveau de compatibilité ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="7e386-105">For more information, see [ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
 <span data-ttu-id="7e386-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="7e386-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7e386-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="7e386-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7e386-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7e386-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7e386-109">**Pour afficher ou modifier le niveau de compatibilité d'une base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="7e386-109">**To view or change the compatibility level of a database, using:**</span></span>  
  
     [<span data-ttu-id="7e386-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7e386-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7e386-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7e386-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7e386-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="7e386-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7e386-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7e386-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7e386-114">Autorisations</span><span class="sxs-lookup"><span data-stu-id="7e386-114">Permissions</span></span>  
 <span data-ttu-id="7e386-115">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="7e386-115">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7e386-116">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7e386-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="7e386-117">Pour afficher ou modifier le niveau de compatibilité d'une base de données</span><span class="sxs-lookup"><span data-stu-id="7e386-117">To view or change the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="7e386-118">Après la connexion à l'instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], cliquez sur le nom du serveur dans l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="7e386-118">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name.</span></span>  
  
2.  <span data-ttu-id="7e386-119">Développez **Bases de données**puis, selon la base de données, sélectionnez une base de données utilisateur ou développez **Bases de données système** et sélectionnez une base de données système.</span><span class="sxs-lookup"><span data-stu-id="7e386-119">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="7e386-120">Cliquez avec le bouton droit sur la base de données, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7e386-120">Right-click the database, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="7e386-121">La boîte de dialogue **Propriétés de la base de données** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="7e386-121">The **Database Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="7e386-122">Dans le volet **Sélectionner une page** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="7e386-122">In the **Select a page** pane, click **Options**.</span></span>  
  
     <span data-ttu-id="7e386-123">Le niveau de compatibilité actuel apparaît dans la zone de liste **Niveau de compatibilité** .</span><span class="sxs-lookup"><span data-stu-id="7e386-123">The current compatibility level is displayed in the **Compatibility level** list box.</span></span>  
  
5.  <span data-ttu-id="7e386-124">Pour modifier le niveau de compatibilité, sélectionnez une option différente dans la liste.</span><span class="sxs-lookup"><span data-stu-id="7e386-124">To change the compatibility level, select a different option from the list.</span></span> <span data-ttu-id="7e386-125">Les choix sont **SQL Server 2008 (100)**, **SQL Server 2012 (110)** ou **SQL Server 2014 (120)**.</span><span class="sxs-lookup"><span data-stu-id="7e386-125">The choices are **SQL Server 2008 (100)**, **SQL Server 2012 (110)**, or **SQL Server 2014 (120)**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7e386-126">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7e386-126">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-compatibility-level-of-a-database"></a><span data-ttu-id="7e386-127">Pour afficher le niveau de compatibilité d'une base de données</span><span class="sxs-lookup"><span data-stu-id="7e386-127">To view the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="7e386-128">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e386-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7e386-129">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="7e386-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7e386-130">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="7e386-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7e386-131">Cet exemple retourne le niveau de compatibilité de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7e386-131">This example returns the compatibility level of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT compatibility_level  
FROM sys.databases WHERE name = 'AdventureWorks2012';  
GO  
  
```  
  
#### <a name="to-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="7e386-132">Pour modifier le niveau de compatibilité d'une base de données</span><span class="sxs-lookup"><span data-stu-id="7e386-132">To change the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="7e386-133">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e386-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7e386-134">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="7e386-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7e386-135">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="7e386-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7e386-136">Cet exemple modifie le niveau de compatibilité de [!INCLUDE[ssSampleDBobject](../../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7e386-136">This example changes the compatibility level of the [!INCLUDE[ssSampleDBobject](../../includes/sssql14-md.md)].</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET COMPATIBILITY_LEVEL = 120;  
GO  
```  
  
  
