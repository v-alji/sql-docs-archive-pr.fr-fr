---
title: Créer une procédure stockée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- new stored procedures
- stored procedures [SQL Server], creating
- creating stored procedures
ms.assetid: 76e8a6ba-1381-4620-b356-4311e1331ca7
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6781840e6a6c84773f40a6cd0557ccb79b676eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613354"
---
# <a name="create-a-stored-procedure"></a><span data-ttu-id="fb842-102">Créer une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="fb842-102">Create a Stored Procedure</span></span>
  <span data-ttu-id="fb842-103">Cette rubrique explique comment créer une procédure stockée [!INCLUDE[tsql](../../includes/tsql-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] et de l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="fb842-103">This topic describes how to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE PROCEDURE statement.</span></span>  
  
##  <a name="Top"></a>   
-   <span data-ttu-id="fb842-104">**Avant de commencer :**  [Autorisations](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="fb842-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="fb842-105">**Pour créer une procédure avec :**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="fb842-105">**To create a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fb842-106">Autorisations</span><span class="sxs-lookup"><span data-stu-id="fb842-106">Permissions</span></span>  
 <span data-ttu-id="fb842-107">Nécessite l'autorisation CREATE PROCEDURE dans la base de données et l'autorisation ALTER sur le schéma dans lequel la procédure est créée.</span><span class="sxs-lookup"><span data-stu-id="fb842-107">Requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
##  <a name="how-to-create-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="fb842-108">Comment créer une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="fb842-108">How to Create a Stored Procedure</span></span>  
 <span data-ttu-id="fb842-109">Vous pouvez utiliser l'un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="fb842-109">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="fb842-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fb842-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="fb842-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fb842-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fb842-112">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fb842-112">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="fb842-113">**Pour créer une procédure dans l'Explorateur d'objets**</span><span class="sxs-lookup"><span data-stu-id="fb842-113">**To create a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="fb842-114">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="fb842-114">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="fb842-115">Développez **Bases de données**, la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , puis **Programmabilité**.</span><span class="sxs-lookup"><span data-stu-id="fb842-115">Expand **Databases**, expand the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="fb842-116">Cliquez avec le bouton droit sur **Procédures stockées**, puis cliquez sur **Nouvelle procédure stockée**.</span><span class="sxs-lookup"><span data-stu-id="fb842-116">Right-click **Stored Procedures**, and then click **New Stored Procedure**.</span></span>  
  
4.  <span data-ttu-id="fb842-117">Dans le menu **Requête** , cliquez sur **Spécifier les valeurs des paramètres du modèle**.</span><span class="sxs-lookup"><span data-stu-id="fb842-117">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
5.  <span data-ttu-id="fb842-118">Dans la boîte de dialogue **Spécifier les valeurs des paramètres du modèle** , entrez les valeurs suivantes pour les paramètres affichés.</span><span class="sxs-lookup"><span data-stu-id="fb842-118">In the **Specify Values for Template Parameters** dialog box, enter the following values for the parameters shown.</span></span>  
  
    |<span data-ttu-id="fb842-119">Paramètre</span><span class="sxs-lookup"><span data-stu-id="fb842-119">Parameter</span></span>|<span data-ttu-id="fb842-120">Valeur</span><span class="sxs-lookup"><span data-stu-id="fb842-120">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="fb842-121">Auteur</span><span class="sxs-lookup"><span data-stu-id="fb842-121">Author</span></span>|<span data-ttu-id="fb842-122">*Votre nom*</span><span class="sxs-lookup"><span data-stu-id="fb842-122">*Your name*</span></span>|  
    |<span data-ttu-id="fb842-123">Date de création</span><span class="sxs-lookup"><span data-stu-id="fb842-123">Create Date</span></span>|<span data-ttu-id="fb842-124">*Date du jour*</span><span class="sxs-lookup"><span data-stu-id="fb842-124">*Today's date*</span></span>|  
    |<span data-ttu-id="fb842-125">Description</span><span class="sxs-lookup"><span data-stu-id="fb842-125">Description</span></span>|<span data-ttu-id="fb842-126">Retourne des données sur les employés.</span><span class="sxs-lookup"><span data-stu-id="fb842-126">Returns employee data.</span></span>|  
    |<span data-ttu-id="fb842-127">Procedure_name</span><span class="sxs-lookup"><span data-stu-id="fb842-127">Procedure_name</span></span>|<span data-ttu-id="fb842-128">HumanResources.uspGetEmployeesTest</span><span class="sxs-lookup"><span data-stu-id="fb842-128">HumanResources.uspGetEmployeesTest</span></span>|  
    |@Param1|@LastName|  
    |@Datatype_For_Param1|<span data-ttu-id="fb842-129">`nvarchar`(50)</span><span class="sxs-lookup"><span data-stu-id="fb842-129">`nvarchar`(50)</span></span>|  
    |<span data-ttu-id="fb842-130">Default_Value_For_Param1</span><span class="sxs-lookup"><span data-stu-id="fb842-130">Default_Value_For_Param1</span></span>|<span data-ttu-id="fb842-131">NULL</span><span class="sxs-lookup"><span data-stu-id="fb842-131">NULL</span></span>|  
    |@Param2|@FirstName|  
    |@Datatype_For_Param2|<span data-ttu-id="fb842-132">`nvarchar`(50)</span><span class="sxs-lookup"><span data-stu-id="fb842-132">`nvarchar`(50)</span></span>|  
    |<span data-ttu-id="fb842-133">Default_Value_For_Param2</span><span class="sxs-lookup"><span data-stu-id="fb842-133">Default_Value_For_Param2</span></span>|<span data-ttu-id="fb842-134">NULL</span><span class="sxs-lookup"><span data-stu-id="fb842-134">NULL</span></span>|  
  
6.  <span data-ttu-id="fb842-135">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb842-135">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="fb842-136">Dans l' **Éditeur de requête**, remplacez l'instruction SELECT par l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="fb842-136">In the **Query Editor**, replace the SELECT statement with the following statement:</span></span>  
  
    ```sql  
    SELECT FirstName, LastName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory  
    WHERE FirstName = @FirstName AND LastName = @LastName  
        AND EndDate IS NULL;  
    ```  
  
8.  <span data-ttu-id="fb842-137">Pour tester la syntaxe, dans le menu **Requête** , cliquez sur **Analyser**.</span><span class="sxs-lookup"><span data-stu-id="fb842-137">To test the syntax, on the **Query** menu, click **Parse**.</span></span> <span data-ttu-id="fb842-138">Si un message d'erreur est retourné, comparez les instructions avec les informations ci-dessus et apportez les corrections nécessaires.</span><span class="sxs-lookup"><span data-stu-id="fb842-138">If an error message is returned, compare the statements with the information above and correct as needed.</span></span>  
  
9. <span data-ttu-id="fb842-139">Pour créer la procédure, dans le menu **Requête** , cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="fb842-139">To create the procedure, from  the **Query** menu, click **Execute**.</span></span> <span data-ttu-id="fb842-140">La procédure est créée en tant qu'objet dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="fb842-140">The procedure is created as an object in the database.</span></span>  
  
10. <span data-ttu-id="fb842-141">Pour afficher la procédure répertoriée dans l’Explorateur d’objets, cliquez avec le bouton droit sur **Procédures stockées** et sélectionnez **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="fb842-141">To see the procedure listed in Object Explorer, right-click **Stored Procedures** and select **Refresh**.</span></span>  
  
11. <span data-ttu-id="fb842-142">Pour exécuter la procédure, dans l’Explorateur d’objets, cliquez avec le bouton droit sur le nom de la procédure stockée **HumanResources.uspGetEmployeesTest** et sélectionnez **Exécuter la procédure stockée**.</span><span class="sxs-lookup"><span data-stu-id="fb842-142">To run the procedure, in Object Explorer, right-click the stored procedure name **HumanResources.uspGetEmployeesTest** and select **Execute Stored Procedure**.</span></span>  
  
12. <span data-ttu-id="fb842-143">Dans la fenêtre **Exécuter la procédure** , entrez Margheim comme valeur pour le paramètre @LastName et entrez la valeur Diane comme valeur pour le paramètre @FirstName.</span><span class="sxs-lookup"><span data-stu-id="fb842-143">In the **Execute Procedure** window, enter Margheim as the value for the parameter @LastName and enter the value Diane as the value for the parameter @FirstName.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="fb842-144">Validez toutes les entrées utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fb842-144">Validate all user input.</span></span> <span data-ttu-id="fb842-145">Ne concaténez pas les entrées utilisateur avant de les avoir validées.</span><span class="sxs-lookup"><span data-stu-id="fb842-145">Do not concatenate user input before you validate it.</span></span> <span data-ttu-id="fb842-146">N'exécutez jamais une commande élaborée à partir d'une entrée utilisateur non validée.</span><span class="sxs-lookup"><span data-stu-id="fb842-146">Never execute a command constructed from unvalidated user input.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fb842-147">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fb842-147">Using Transact-SQL</span></span>  
 <span data-ttu-id="fb842-148">**Pour créer une procédure dans l'Éditeur de requête**</span><span class="sxs-lookup"><span data-stu-id="fb842-148">**To create a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="fb842-149">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb842-149">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fb842-150">Dans le menu **Fichier** , cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="fb842-150">From the **File** menu, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fb842-151">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="fb842-151">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="fb842-152">Cet exemple crée la même procédure stockée que ci-dessus à l'aide d'un nom de procédure différent.</span><span class="sxs-lookup"><span data-stu-id="fb842-152">This example creates the same stored procedure as above using a different procedure name.</span></span>  
  
    ```sql
    USE AdventureWorks2012;  
    GO  
    CREATE PROCEDURE HumanResources.uspGetEmployeesTest2   
        @LastName nvarchar(50),   
        @FirstName nvarchar(50)   
    AS
  
        SET NOCOUNT ON;  
        SELECT FirstName, LastName, Department  
        FROM HumanResources.vEmployeeDepartmentHistory  
        WHERE FirstName = @FirstName AND LastName = @LastName  
        AND EndDate IS NULL;  
    GO
    ```  
  
4.  <span data-ttu-id="fb842-153">Pour exécuter la procédure, copiez et collez l'exemple suivant dans une nouvelle fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="fb842-153">To run the procedure, copy and paste the following example into a new query window and click **Execute**.</span></span> <span data-ttu-id="fb842-154">Notez que différentes méthodes de spécification des valeurs de paramètre sont affichées.</span><span class="sxs-lookup"><span data-stu-id="fb842-154">Notice that different methods of specifying the parameter values are shown.</span></span>  
  
    ```sql
    EXECUTE HumanResources.uspGetEmployeesTest2 N'Ackerman', N'Pilar';  
    -- Or  
    EXEC HumanResources.uspGetEmployeesTest2 @LastName = N'Ackerman', @FirstName = N'Pilar';  
    GO  
    -- Or  
    EXECUTE HumanResources.uspGetEmployeesTest2 @FirstName = N'Pilar', @LastName = N'Ackerman';  
    GO
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fb842-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fb842-155">See Also</span></span>  
 [<span data-ttu-id="fb842-156">CREATE PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fb842-156">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  