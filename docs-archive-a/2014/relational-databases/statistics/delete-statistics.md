---
title: Supprimer des statistiques | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- statistics [SQL Server], deleting
- deleting statistics
ms.assetid: eccce0aa-591e-4a1d-bd10-373b022f8749
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 36b74d7e1465c0742cda4fef9f34fb4b3930719c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613372"
---
# <a name="delete-statistics"></a><span data-ttu-id="80cd3-102">Supprimer des statistiques</span><span class="sxs-lookup"><span data-stu-id="80cd3-102">Delete Statistics</span></span>
  <span data-ttu-id="80cd3-103">Vous pouvez supprimer des statistiques des tables et des vues dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80cd3-103">You can delete (drop) statistics from tables and views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="80cd3-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="80cd3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="80cd3-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="80cd3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="80cd3-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="80cd3-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="80cd3-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="80cd3-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="80cd3-108">**Pour supprimer des statistiques d'une table ou d'une vue, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="80cd3-108">**To drop statistics from a table or view, using:**</span></span>  
  
     [<span data-ttu-id="80cd3-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="80cd3-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="80cd3-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="80cd3-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="80cd3-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="80cd3-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="80cd3-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="80cd3-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="80cd3-113">Soyez prudent lorsque vous supprimez des statistiques.</span><span class="sxs-lookup"><span data-stu-id="80cd3-113">Be careful when you drop statistics.</span></span> <span data-ttu-id="80cd3-114">En effet, vous risquez d'affecter le plan d'exécution choisi par l'optimiseur de requête.</span><span class="sxs-lookup"><span data-stu-id="80cd3-114">Doing so may affect the execution plan chosen by the query optimizer.</span></span>  
  
-   <span data-ttu-id="80cd3-115">Les statistiques sur les index ne peuvent pas être supprimées à l'aide de DROP STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="80cd3-115">Statistics on indexes cannot be dropped by using DROP STATISTICS.</span></span> <span data-ttu-id="80cd3-116">Les statistiques sont conservées aussi longtemps que l'index existe.</span><span class="sxs-lookup"><span data-stu-id="80cd3-116">Statistics remain as long as the index exists.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="80cd3-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="80cd3-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="80cd3-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="80cd3-118">Permissions</span></span>  
 <span data-ttu-id="80cd3-119">Nécessite une autorisation ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="80cd3-119">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="80cd3-120">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="80cd3-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-drop-statistics-from-a-table-or-view"></a><span data-ttu-id="80cd3-121">Pour supprimer des statistiques d'une table ou d'une vue</span><span class="sxs-lookup"><span data-stu-id="80cd3-121">To drop statistics from a table or view</span></span>  
  
1.  <span data-ttu-id="80cd3-122">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer la base de données dans laquelle vous souhaitez supprimer une statistique.</span><span class="sxs-lookup"><span data-stu-id="80cd3-122">In **Object Explorer**, click the plus sign to expand the database in which you want to delete a statistic.</span></span>  
  
2.  <span data-ttu-id="80cd3-123">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="80cd3-123">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="80cd3-124">Cliquez sur le signe plus (+) pour développer la table dans laquelle vous souhaitez supprimer une statistique.</span><span class="sxs-lookup"><span data-stu-id="80cd3-124">Click the plus sign to expand the table in which you want to delete a statistic.</span></span>  
  
4.  <span data-ttu-id="80cd3-125">Cliquez sur le signe plus (+) pour développer le dossier **Statistiques** .</span><span class="sxs-lookup"><span data-stu-id="80cd3-125">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="80cd3-126">Cliquez avec le bouton droit sur l’objet de statistiques à supprimer et sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="80cd3-126">Right-click the statistics object that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="80cd3-127">Dans la boîte de dialogue **Supprimer un objet** , assurez-vous d'avoir sélectionné la statistique correcte, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="80cd3-127">In the **Delete Object** dialog box, ensure that the correct statistic has been selected and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="80cd3-128">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="80cd3-128">Using Transact-SQL</span></span>  
  
#### <a name="to-drop-statistics-from-a-table-or-view"></a><span data-ttu-id="80cd3-129">Pour supprimer des statistiques d'une table ou d'une vue</span><span class="sxs-lookup"><span data-stu-id="80cd3-129">To drop statistics from a table or view</span></span>  
  
1.  <span data-ttu-id="80cd3-130">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80cd3-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="80cd3-131">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="80cd3-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="80cd3-132">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="80cd3-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- First, create two statistics named VendorCredit and CustomerTotal  
    -- The first statistic uses a random 50% sample of information provided from the Name and CreditRating columns in the Purchasing.Vendor table.  
    CREATE STATISTICS VendorCredit  
        ON Purchasing.Vendor (Name, CreditRating)  
        WITH SAMPLE 50 PERCENT  
    -- The second statistic uses all of the information from the CustomerID and TotalDue columns in the Sales.SalesOrderHeader table  
    CREATE STATISTICS CustomerTotal  
        ON Sales.SalesOrderHeader (CustomerID, TotalDue)  
        WITH FULLSCAN;  
    GO  
    -- This next statement drops both of the statistics created above. Note that the naming convention is [table_name].[statistics_name].  
    DROP STATISTICS Purchasing.Vendor.VendorCredit, Sales.SalesOrderHeader.CustomerTotal;  
    GO  
    ```  
  
 <span data-ttu-id="80cd3-133">Pour plus d’informations, consultez [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="80cd3-133">For more information, see [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql).</span></span>  
  
  
