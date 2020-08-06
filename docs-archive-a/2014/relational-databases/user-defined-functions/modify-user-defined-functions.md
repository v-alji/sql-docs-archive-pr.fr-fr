---
title: Modifier les fonctions définies par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 891c37b3-cb72-411f-9937-ee87e6d95f34
author: rothja
ms.author: jroth
ms.openlocfilehash: 1cf25fef91834e237f5cbaac26350220840830bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613853"
---
# <a name="modify-user-defined-functions"></a><span data-ttu-id="72991-102">Modifier les fonctions définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="72991-102">Modify User-defined Functions</span></span>
  <span data-ttu-id="72991-103">Vous pouvez modifier les fonctions définies par l'utilisateur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72991-103">You can modify user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="72991-104">Le fait de modifier des fonctions définies par l’utilisateur comme décrit ci-dessous n’affecte pas les autorisations des fonctions et n’a aucune incidence sur les fonctions, les procédures stockées et les déclencheurs qui en dépendent.</span><span class="sxs-lookup"><span data-stu-id="72991-104">Modifying user-defined functions as described below will not change the functions' permissions, nor will it affect any dependent functions, stored procedures, or triggers.</span></span>  
  
 <span data-ttu-id="72991-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="72991-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="72991-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="72991-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="72991-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="72991-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="72991-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="72991-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="72991-109">**Pour modifier une fonction définie par l'utilisateur à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="72991-109">**To modify a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="72991-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="72991-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="72991-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="72991-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="72991-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="72991-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="72991-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="72991-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="72991-114">ALTER FUNCTION ne peut pas être utilisé pour effectuer les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="72991-114">ALTER FUNCTION cannot be used to perform any of the following actions:</span></span>  
  
-   <span data-ttu-id="72991-115">Convertir une fonction scalaire en fonction table, et inversement.</span><span class="sxs-lookup"><span data-stu-id="72991-115">Change a scalar-valued function to a table-valued function, or vice versa.</span></span>  
  
-   <span data-ttu-id="72991-116">Convertir une fonction inline en fonction à instructions multiples, et inversement.</span><span class="sxs-lookup"><span data-stu-id="72991-116">Change an inline function to a multistatement function, or vice versa.</span></span>  
  
-   <span data-ttu-id="72991-117">Convertir une fonction Transact-SQL en fonction CLR, et inversement.</span><span class="sxs-lookup"><span data-stu-id="72991-117">Change a Transact-SQL function to a CLR function, or vice-versa.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="72991-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="72991-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="72991-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="72991-119">Permissions</span></span>  
 <span data-ttu-id="72991-120">Nécessite l'autorisation ALTER sur la fonction ou sur le schéma.</span><span class="sxs-lookup"><span data-stu-id="72991-120">Requires ALTER permission on the function or on the schema.</span></span> <span data-ttu-id="72991-121">Si la fonction spécifie un type défini par l'utilisateur, elle requiert l'autorisation EXECUTE sur le type.</span><span class="sxs-lookup"><span data-stu-id="72991-121">If the function specifies a user-defined type, requires EXECUTE permission on the type.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="72991-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="72991-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-user-defined-function"></a><span data-ttu-id="72991-123">Pour modifier une fonction définie par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="72991-123">To modify a user-defined function</span></span>  
  
1.  <span data-ttu-id="72991-124">Cliquez sur le signe plus (+° en regard de la base de données qui contient la fonction à modifier.</span><span class="sxs-lookup"><span data-stu-id="72991-124">Click on the plus sign next to the database that contains the function you wish to modify.</span></span>  
  
2.  <span data-ttu-id="72991-125">Cliquez sur le signe plus en regard du dossier **Programmabilité** .</span><span class="sxs-lookup"><span data-stu-id="72991-125">Click on the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="72991-126">Cliquez sur le signe plus en regard du dossier qui contient la fonction à modifier :</span><span class="sxs-lookup"><span data-stu-id="72991-126">Click the plus sign next to the folder that contains the function you wish to modify:</span></span>  
  
    -   <span data-ttu-id="72991-127">Fonction table</span><span class="sxs-lookup"><span data-stu-id="72991-127">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="72991-128">Fonction scalaire</span><span class="sxs-lookup"><span data-stu-id="72991-128">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="72991-129">Fonction d'agrégation</span><span class="sxs-lookup"><span data-stu-id="72991-129">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="72991-130">Cliquez avec le bouton droit sur la fonction à modifier, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="72991-130">Right-click the function you want to modify and select **Modify**.</span></span>  
  
5.  <span data-ttu-id="72991-131">Dans la fenêtre de requête, apportez les modifications nécessaires à l'instruction ALTER FUNCTION.</span><span class="sxs-lookup"><span data-stu-id="72991-131">In the Query Window, make the necessary changes to the ALTER FUNCTION statement.</span></span>  
  
6.  <span data-ttu-id="72991-132">Dans le menu **Fichier** , cliquez sur **Enregistrer**_nom_fonction_.</span><span class="sxs-lookup"><span data-stu-id="72991-132">On the **File** menu, click **Save**_function_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="72991-133">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="72991-133">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-user-defined-function"></a><span data-ttu-id="72991-134">Pour modifier une fonction définie par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="72991-134">To modify a user-defined function</span></span>  
  
1.  <span data-ttu-id="72991-135">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72991-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="72991-136">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="72991-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="72991-137">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="72991-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Scalar-Valued Function  
    USE [AdventureWorks2012]  
    GO  
    ALTER FUNCTION [dbo].[ufnGetAccountingEndDate]()  
    RETURNS [datetime]   
    AS   
    BEGIN  
        RETURN DATEADD(millisecond, -2, CONVERT(datetime, '20040701', 112));  
    END;  
    ```  
  
    ```  
    -- Table-Valued Function   
    USE [AdventureWorks2012]  
    GO  
    ALTER FUNCTION [dbo].[ufnGetContactInformation](@PersonID int)  
    RETURNS @retContactInformation TABLE   
    (  
        -- Columns returned by the function  
        [PersonID] int NOT NULL,   
        [FirstName] [nvarchar](50) NULL,   
        [LastName] [nvarchar](50) NULL,   
        [JobTitle] [nvarchar](50) NULL,  
        [BusinessEntityType] [nvarchar](50) NULL  
    )  
    AS   
    -- Returns the first name, last name, job title and business entity type for the specified contact.  
    -- Since a contact can serve multiple roles, more than one row may be returned.  
    BEGIN  
    IF @PersonID IS NOT NULL   
    BEGIN  
         IF EXISTS(SELECT * FROM [HumanResources].[Employee] e   
         WHERE e.[BusinessEntityID] = @PersonID)   
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, e.[JobTitle], 'Employee'  
              FROM [HumanResources].[Employee] AS e  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = e.[BusinessEntityID]  
              WHERE e.[BusinessEntityID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Purchasing].[Vendor] AS v  
         INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = v.[BusinessEntityID]  
         WHERE bec.[PersonID] = @PersonID)  
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, ct.[Name], 'Vendor Contact'   
              FROM [Purchasing].[Vendor] AS v  
              INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = v.[BusinessEntityID]  
              INNER JOIN [Person].ContactType ct ON ct.[ContactTypeID] = bec.[ContactTypeID]  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = bec.[PersonID]  
              WHERE bec.[PersonID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Sales].[Store] AS s  
         INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = s.[BusinessEntityID]  
         WHERE bec.[PersonID] = @PersonID)  
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, ct.[Name], 'Store Contact'   
              FROM [Sales].[Store] AS s  
              INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = s.[BusinessEntityID]  
              INNER JOIN [Person].ContactType ct ON ct.[ContactTypeID] = bec.[ContactTypeID]  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = bec.[PersonID]  
              WHERE bec.[PersonID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Person].[Person] AS p  
         INNER JOIN [Sales].[Customer] AS c ON c.[PersonID] = p.[BusinessEntityID]  
         WHERE p.[BusinessEntityID] = @PersonID AND c.[StoreID] IS NULL)   
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, NULL, 'Consumer'   
              FROM [Person].[Person] AS p  
              INNER JOIN [Sales].[Customer] AS c ON c.[PersonID] = p.[BusinessEntityID]  
              WHERE p.[BusinessEntityID] = @PersonID AND c.[StoreID] IS NULL;   
         END  
    RETURN;  
    END;  
    ```  
  
 <span data-ttu-id="72991-138">Pour plus d’informations, consultez [ALTER FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="72991-138">For more information, see [ALTER FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-function-transact-sql).</span></span>  
  
  
