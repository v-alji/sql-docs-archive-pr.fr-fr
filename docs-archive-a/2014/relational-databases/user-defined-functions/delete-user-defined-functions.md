---
title: Supprimer des fonctions définies par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: db1d668a-23b7-4757-a9c5-1bd848ba7f6d
author: rothja
ms.author: jroth
ms.openlocfilehash: e5f6b2b306c4fe8db08b088d9607cfb19ab0f25e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613856"
---
# <a name="delete-user-defined-functions"></a><span data-ttu-id="d47dc-102">Supprimer des fonctions définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d47dc-102">Delete User-defined Functions</span></span>
  <span data-ttu-id="d47dc-103">Vous pouvez supprimer des fonctions définies par l’utilisateur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d47dc-103">You can delete (drop) user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="d47dc-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="d47dc-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d47dc-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="d47dc-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d47dc-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="d47dc-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d47dc-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d47dc-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d47dc-108">**Pour supprimer une fonction définie par l'utilisateur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="d47dc-108">**To delete a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="d47dc-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d47dc-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d47dc-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d47dc-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d47dc-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d47dc-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d47dc-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="d47dc-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d47dc-113">Vous ne pourrez pas supprimer la fonction si la base de données contient des fonctions ou des vues Transact-SQL qui font référence à cette fonction et qui ont été créées au moyen de SCHEMABINDING. Elle échoue également s'il existe des colonnes calculées, des contraintes CHECK ou des contraintes DEFAULT qui font référence à cette fonction.</span><span class="sxs-lookup"><span data-stu-id="d47dc-113">You will not be able to delete the function if there are Transact-SQL functions or views in the database that reference this function and were created by using SCHEMABINDING, or if there are computed columns, CHECK constraints, or DEFAULT constraints that reference the function.</span></span>  
  
-   <span data-ttu-id="d47dc-114">Vous ne pourrez pas supprimer la fonction si des colonnes calculées qui ont été indexées font référence à cette fonction.</span><span class="sxs-lookup"><span data-stu-id="d47dc-114">You will not be able to delete the function if there are computed columns that reference this function and have been indexed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d47dc-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d47dc-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d47dc-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="d47dc-116">Permissions</span></span>  
 <span data-ttu-id="d47dc-117">Exige l'autorisation ALTER sur le schéma auquel la fonction appartient, ou l'autorisation CONTROL sur la fonction.</span><span class="sxs-lookup"><span data-stu-id="d47dc-117">Requires ALTER permission on the schema to which the function belongs, or CONTROL permission on the function.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d47dc-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d47dc-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-user-defined-function"></a><span data-ttu-id="d47dc-119">Pour supprimer une fonction définie par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d47dc-119">To delete a user-defined function</span></span>  
  
1.  <span data-ttu-id="d47dc-120">Cliquez sur le signe plus (+° en regard de la base de données qui contient la fonction à modifier.</span><span class="sxs-lookup"><span data-stu-id="d47dc-120">Click on the plus sign next to the database that contains the function you wish to modify.</span></span>  
  
2.  <span data-ttu-id="d47dc-121">Cliquez sur le signe plus en regard du dossier **Programmabilité** .</span><span class="sxs-lookup"><span data-stu-id="d47dc-121">Click on the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="d47dc-122">Cliquez sur le signe plus en regard du dossier qui contient la fonction à modifier :</span><span class="sxs-lookup"><span data-stu-id="d47dc-122">Click the plus sign next to the folder that contains the function you wish to modify:</span></span>  
  
    -   <span data-ttu-id="d47dc-123">Fonction table</span><span class="sxs-lookup"><span data-stu-id="d47dc-123">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="d47dc-124">Fonction scalaire</span><span class="sxs-lookup"><span data-stu-id="d47dc-124">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="d47dc-125">Fonction d'agrégation</span><span class="sxs-lookup"><span data-stu-id="d47dc-125">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="d47dc-126">Cliquez avec le bouton droit sur la fonction à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="d47dc-126">Right-click the function you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="d47dc-127">Dans la boîte de dialogue **Supprimer l'objet** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d47dc-127">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="d47dc-128">Cliquez sur **afficher les dépendances** dans la boîte de dialogue **supprimer un objet** pour ouvrir la boîte de dialogue _function_name_les**dépendances** .</span><span class="sxs-lookup"><span data-stu-id="d47dc-128">Click **Show Dependencies** in the **Delete Object** dialog box to open the _function_name_**Dependencies** dialog box.</span></span> <span data-ttu-id="d47dc-129">Cette opération affiche tous les objets qui dépendent de la fonction et tous les objets dont la fonction dépend.</span><span class="sxs-lookup"><span data-stu-id="d47dc-129">This will show all of the objects that depend on the function and all of the objects on which the function depends.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d47dc-130">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d47dc-130">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-user-defined-function"></a><span data-ttu-id="d47dc-131">Pour supprimer une fonction définie par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d47dc-131">To delete a user-defined function</span></span>  
  
1.  <span data-ttu-id="d47dc-132">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d47dc-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d47dc-133">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="d47dc-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d47dc-134">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d47dc-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates function called "Sales.ufn_SalesByStore"  
    USE AdventureWorks2012;  
    GO  
    CREATE FUNCTION Sales.ufn_SalesByStore (@storeid int)  
    RETURNS TABLE  
    AS  
    RETURN   
    (  
        SELECT P.ProductID, P.Name, SUM(SD.LineTotal) AS 'Total'  
        FROM Production.Product AS P   
        JOIN Sales.SalesOrderDetail AS SD ON SD.ProductID = P.ProductID  
        JOIN Sales.SalesOrderHeader AS SH ON SH.SalesOrderID = SD.SalesOrderID  
        JOIN Sales.Customer AS C ON SH.CustomerID = C.CustomerID  
        WHERE C.StoreID = @storeid  
        GROUP BY P.ProductID, P.Name  
    );  
    GO  
    ```  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- determines if function exists in database  
    IF OBJECT_ID (N'Sales.fn_SalesByStore', N'IF') IS NOT NULL  
    -- deletes function  
        DROP FUNCTION Sales.fn_SalesByStore;  
    GO  
    ```  
  
 <span data-ttu-id="d47dc-135">Pour plus d’informations, consultez [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d47dc-135">For more information, see [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span></span>  
  
  
