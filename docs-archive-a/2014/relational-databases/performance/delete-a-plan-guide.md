---
title: Supprimer un repère de plan | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], deleting
ms.assetid: aa4d3188-6927-43de-a3e3-90fc16eeaca7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 303ad6f59cbe24265aec66f3cb780a5b4ad4f157
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698003"
---
# <a name="delete-a-plan-guide"></a><span data-ttu-id="cb302-102">Supprimer un repère de plan</span><span class="sxs-lookup"><span data-stu-id="cb302-102">Delete a Plan Guide</span></span>
  <span data-ttu-id="cb302-103">Vous pouvez supprimer (éliminer) un repère de plan dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb302-103">You can delete (drop) a plan guide in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="cb302-104">Avec [!INCLUDE[tsql](../../includes/tsql-md.md)], vous pouvez également supprimer tous les repères de plan dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="cb302-104">Using [!INCLUDE[tsql](../../includes/tsql-md.md)], you can also delete all of the plan guides in a database.</span></span>  
  
 <span data-ttu-id="cb302-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="cb302-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cb302-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="cb302-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cb302-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="cb302-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cb302-108">**Pour supprimer un repère de plan, à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="cb302-108">**To delete a plan guide, using:**</span></span>  
  
     [<span data-ttu-id="cb302-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cb302-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cb302-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cb302-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cb302-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="cb302-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cb302-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="cb302-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cb302-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="cb302-113">Permissions</span></span>  
 <span data-ttu-id="cb302-114">La suppression d'un repère de plan OBJECT nécessite l'autorisation ALTER sur l'objet (par exemple : fonction, procédure stockée) qui est référencé par le repère de plan.</span><span class="sxs-lookup"><span data-stu-id="cb302-114">Deleting an OBJECT plan guide requires ALTER permission on the object (for example: function, stored procedure) that is referenced by the plan guide.</span></span> <span data-ttu-id="cb302-115">Tous les autres repères de plan nécessitent l'autorisation ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="cb302-115">All other plan guides require ALTER DATABASE permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cb302-116">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cb302-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-plan-guide"></a><span data-ttu-id="cb302-117">Pour supprimer un repère de plan</span><span class="sxs-lookup"><span data-stu-id="cb302-117">To delete a plan guide</span></span>  
  
1.  <span data-ttu-id="cb302-118">Cliquez sur le signe plus pour développer la base de données dans laquelle vous souhaitez supprimer un repère de plan, puis cliquez sur le signe plus pour développer le dossier **Programmabilité** .</span><span class="sxs-lookup"><span data-stu-id="cb302-118">Click the plus sign to expand the database in which you want to delete a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="cb302-119">Cliquez sur le signe plus (+) pour développer le dossier **Repères de plan** .</span><span class="sxs-lookup"><span data-stu-id="cb302-119">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="cb302-120">Cliquez avec le bouton droit sur le repère de plan à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="cb302-120">Right-click the plan guide you want to delete and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="cb302-121">Dans la boîte de dialogue **Supprimer un objet** , assurez-vous que le repère de plan correct est sélectionné, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb302-121">In the **Delete Object** dialog box, ensure that the correct plan guide is selected and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cb302-122">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cb302-122">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-single-plan-guide"></a><span data-ttu-id="cb302-123">Pour supprimer un repère de plan unique</span><span class="sxs-lookup"><span data-stu-id="cb302-123">To delete a single plan guide</span></span>  
  
1.  <span data-ttu-id="cb302-124">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb302-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cb302-125">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="cb302-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cb302-126">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="cb302-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Create a procedure on which to define the plan guide.  
    IF OBJECT_ID(N'Sales.GetSalesOrderByCountry', N'P') IS NOT NULL  
        DROP PROCEDURE Sales.GetSalesOrderByCountry;  
    GO  
    CREATE PROCEDURE Sales.GetSalesOrderByCountry   
        (@Country nvarchar(60))  
    AS  
    BEGIN  
        SELECT *  
        FROM Sales.SalesOrderHeader AS h   
        INNER JOIN Sales.Customer AS c ON h.CustomerID = c.CustomerID  
        INNER JOIN Sales.SalesTerritory AS t ON c.TerritoryID = t.TerritoryID  
        WHERE t.CountryRegionCode = @Country;  
    END  
    GO  
    --Create the plan guide.  
    EXEC sp_create_plan_guide N'Guide3',  
        N'SELECT *  
        FROM Sales.SalesOrderHeader AS h   
        INNER JOIN Sales.Customer AS c ON h.CustomerID = c.CustomerID  
        INNER JOIN Sales.SalesTerritory AS t ON c.TerritoryID = t.TerritoryID  
        WHERE t.CountryRegionCode = @Country',  
        N'OBJECT',  
        N'Sales.GetSalesOrderByCountry',  
        NULL,  
        N'OPTION (OPTIMIZE FOR (@Country = N''US''))';  
    GO  
    --Drop the plan guide.  
    EXEC sp_control_plan_guide N'DROP', N'Guide3';  
    GO  
    ```  
  
#### <a name="to-delete-all-plan-guides-in-a-database"></a><span data-ttu-id="cb302-127">Pour supprimer tous les repères de plan dans une base de données</span><span class="sxs-lookup"><span data-stu-id="cb302-127">To delete all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="cb302-128">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb302-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cb302-129">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="cb302-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cb302-130">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="cb302-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_control_plan_guide N'DROP ALL';  
    GO  
    ```  
  
 <span data-ttu-id="cb302-131">Pour plus d’informations, consultez [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cb302-131">For more information, see [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span></span>  
  
  
