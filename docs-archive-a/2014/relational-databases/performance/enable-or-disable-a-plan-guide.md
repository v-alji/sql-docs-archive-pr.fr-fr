---
title: Activer ou désactiver un repère de plan | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], disabling
- enabling plan guides
- plan guides [SQL Server], enabling
- disabling plan guides
ms.assetid: b00ab550-5308-4cb8-8330-483cd1d25654
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2611697e479d318245d8306b28c826e744ae85ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705092"
---
# <a name="enable-or-disable-a-plan-guide"></a><span data-ttu-id="c34ae-102">Activer ou désactiver un repère de plan</span><span class="sxs-lookup"><span data-stu-id="c34ae-102">Enable or Disable a Plan Guide</span></span>
  <span data-ttu-id="c34ae-103">Vous pouvez désactiver et activer les repères de plan dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c34ae-103">You can disable and enable plan guides in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c34ae-104">Il est possible d'activer ou de désactiver un seul repère de plan ou tous les repères de plan d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="c34ae-104">Either a single plan guides or all plan guides in a database can be enabled or disabled.</span></span>  
  
 <span data-ttu-id="c34ae-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="c34ae-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c34ae-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="c34ae-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c34ae-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="c34ae-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c34ae-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c34ae-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c34ae-109">**Pour désactiver et activer des repères de plan, à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="c34ae-109">**To disable and enable plan guides, using:**</span></span>  
  
     [<span data-ttu-id="c34ae-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c34ae-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c34ae-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c34ae-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c34ae-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c34ae-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c34ae-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="c34ae-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c34ae-114">Si vous tentez de supprimer ou de modifier une fonction, une procédure stockée ou un déclencheur DML référencé par un repère de plan, qu'il soit activé ou désactivé, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="c34ae-114">Trying to drop or modify a function, stored procedure, or DML trigger that is referenced by a plan guide, either enabled or disabled, causes an error.</span></span> <span data-ttu-id="c34ae-115">Vérifiez toujours les dépendances avant de supprimer ou de modifier l'un des objets répertoriés ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="c34ae-115">Always check for dependencies before dropping or modifying any of the objects listed above.</span></span>  
  
-   <span data-ttu-id="c34ae-116">Désactiver un repère de plan désactivé, ou activer un repère de plan activé n'a pas d'effet et ne provoque pas d'erreur.</span><span class="sxs-lookup"><span data-stu-id="c34ae-116">Disabling a disabled plan guide or enabling an enabled plan guide has no effect and runs without error.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c34ae-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c34ae-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c34ae-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c34ae-118">Permissions</span></span>  
 <span data-ttu-id="c34ae-119">La désactivation ou l'activation d'un repère de plan OBJECT nécessite l'autorisation ALTER sur l'objet (par exemple : fonction, procédure stockée) qui est référencé par le repère de plan.</span><span class="sxs-lookup"><span data-stu-id="c34ae-119">Disabling or enabling an OBJECT plan guide requires ALTER permission on the object (for example: function, stored procedure) that is referenced by the plan guide.</span></span> <span data-ttu-id="c34ae-120">Tous les autres repères de plan nécessitent l'autorisation ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="c34ae-120">All other plan guides require ALTER DATABASE permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c34ae-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c34ae-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-enable-a-plan-guide"></a><span data-ttu-id="c34ae-122">Pour désactiver ou activer un repère de plan</span><span class="sxs-lookup"><span data-stu-id="c34ae-122">To disable or enable a plan guide</span></span>  
  
1.  <span data-ttu-id="c34ae-123">Cliquez sur le signe plus pour développer la base de données dans laquelle vous souhaitez désactiver ou activer un repère de plan, puis cliquez sur le signe plus pour développer le dossier **Programmabilité** .</span><span class="sxs-lookup"><span data-stu-id="c34ae-123">Click the plus sign to expand the database in which you want to disable or enable a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="c34ae-124">Cliquez sur le signe plus (+) pour développer le dossier **Repères de plan** .</span><span class="sxs-lookup"><span data-stu-id="c34ae-124">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="c34ae-125">Cliquez avec le bouton droit sur le repère de plan que vous souhaitez désactiver ou activer et sélectionnez **Désactiver** ou **Activer**.</span><span class="sxs-lookup"><span data-stu-id="c34ae-125">Right-click the plan guide you want to disable or enable and select either **Disable** or **Enable**.</span></span>  
  
4.  <span data-ttu-id="c34ae-126">Dans la boîte de dialogue **Désactiver le repère de plan** ou **Activer le repère de plan** , vérifiez que l'action choisie a abouti, puis cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="c34ae-126">In either the **Disable Plan Guide** or **Enable Plan Guide** dialog box, verify that the chosen action was successful and then click **Close**.</span></span>  
  
#### <a name="to-disable-or-enable-all-plan-guides-in-a-database"></a><span data-ttu-id="c34ae-127">Pour activer ou désactiver tous les repères de plan dans une base de données</span><span class="sxs-lookup"><span data-stu-id="c34ae-127">To disable or enable all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="c34ae-128">Cliquez sur le signe plus pour développer la base de données dans laquelle vous souhaitez désactiver ou activer un repère de plan, puis cliquez sur le signe plus pour développer le dossier **Programmabilité** .</span><span class="sxs-lookup"><span data-stu-id="c34ae-128">Click the plus sign to expand the database in which you want to disable or enable a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="c34ae-129">Cliquez avec le bouton droit sur le dossier **Repères de plan** , puis sélectionnez **Tout activer** ou **Tout désactiver**.</span><span class="sxs-lookup"><span data-stu-id="c34ae-129">Right-click the **Plan Guides** folder and then select either **Enable All** or **Disable All**.</span></span>  
  
3.  <span data-ttu-id="c34ae-130">Dans la boîte de dialogue **Désactiver tous les repères de plan** ou **Activer tous les repères de plan** , vérifiez que l'action choisie a abouti, puis cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="c34ae-130">In either the **Disable all Plan Guides** or **Enable all Plan Guides** dialog box, verify that the chosen action was successful and then click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c34ae-131">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c34ae-131">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-enable-a-plan-guide"></a><span data-ttu-id="c34ae-132">Pour désactiver ou activer un repère de plan</span><span class="sxs-lookup"><span data-stu-id="c34ae-132">To disable or enable a plan guide</span></span>  
  
1.  <span data-ttu-id="c34ae-133">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c34ae-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c34ae-134">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="c34ae-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c34ae-135">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c34ae-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
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
    --Disable the plan guide.  
    EXEC sp_control_plan_guide N'DISABLE', N'Guide3';  
    GO  
    --Enable the plan guide.  
    EXEC sp_control_plan_guide N'ENABLE', N'Guide3';  
    GO  
  
    ```  
  
#### <a name="to-disable-or-enable-all-plan-guides-in-a-database"></a><span data-ttu-id="c34ae-136">Pour activer ou désactiver tous les repères de plan dans une base de données</span><span class="sxs-lookup"><span data-stu-id="c34ae-136">To disable or enable all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="c34ae-137">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c34ae-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c34ae-138">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="c34ae-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c34ae-139">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c34ae-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Disable all plan guides in the database.  
    EXEC sp_control_plan_guide N'DISABLE ALL';  
    GO  
    --Enable all plan guides in the database.  
    EXEC sp_control_plan_guide N'ENABLE ALL';  
    GO  
  
    ```  
  
 <span data-ttu-id="c34ae-140">Pour plus d’informations, consultez [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c34ae-140">For more information, see [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span></span>  
  
  
