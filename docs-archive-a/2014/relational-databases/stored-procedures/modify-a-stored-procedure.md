---
title: Modifier une procédure stockée | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- modifying stored procedures
- editing stored procedures
- stored procedures [SQL Server], modifying
ms.assetid: 13396239-6100-48ce-aa34-461358d99c92
author: stevestein
ms.author: sstein
ms.openlocfilehash: 906f0e06650da505094d18774ce86dab53d53f38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695487"
---
# <a name="modify-a-stored-procedure"></a><span data-ttu-id="7af7a-102">Modifier une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="7af7a-102">Modify a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-modify-a-stored-procedure-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="7af7a-103">Cette rubrique explique comment modifier une procédure stockée dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7af7a-103">This topic describes how to modify a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="7af7a-104">**Avant de commencer :**  [Limitations et restrictions](#Restrictions), [sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="7af7a-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="7af7a-105">**Pour modifier une procédure avec :**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="7af7a-105">**To alter a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7af7a-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="7af7a-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7af7a-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="7af7a-107">Limitations and Restrictions</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="7af7a-108">pour les transformer en procédures stockées CLR et inversement.</span><span class="sxs-lookup"><span data-stu-id="7af7a-108">stored procedures cannot be modified to be CLR stored procedures and vice versa.</span></span>  
  
 <span data-ttu-id="7af7a-109">Si la procédure précédente a été créée avec les options WITH ENCRYPTION ou WITH RECOMPILE, ces options sont activées seulement si elles figurent dans l'instruction ALTER PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="7af7a-109">If the previous procedure definition was created using WITH ENCRYPTION or WITH RECOMPILE, these options are enabled only if they are included in the ALTER PROCEDURE statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7af7a-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7af7a-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7af7a-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="7af7a-111">Permissions</span></span>  
 <span data-ttu-id="7af7a-112">Nécessite l'autorisation ALTER PROCEDURE sur la procédure.</span><span class="sxs-lookup"><span data-stu-id="7af7a-112">Requires ALTER PROCEDURE permission on the procedure.</span></span>  
  
##  <a name="how-to-modify-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="7af7a-113">Pour modifier une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="7af7a-113">How to Modify a Stored Procedure</span></span>  
 <span data-ttu-id="7af7a-114">Vous pouvez utiliser l'un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7af7a-114">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="7af7a-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7af7a-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="7af7a-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7af7a-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7af7a-117">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7af7a-117">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="7af7a-118">**Pour modifier une procédure dans Management Studio**</span><span class="sxs-lookup"><span data-stu-id="7af7a-118">**To modify a procedure in Management Studio**</span></span>  
  
1.  <span data-ttu-id="7af7a-119">Dans l'Explorateur d'objets, connectez-vous à une instance de [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="7af7a-119">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7af7a-120">Développez **Bases de données**, développez la base de données à laquelle appartient la procédure, puis développez **Programmabilité**.</span><span class="sxs-lookup"><span data-stu-id="7af7a-120">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="7af7a-121">Développez **Procédures stockées**, cliquez avec le bouton droit sur la procédure à modifier, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="7af7a-121">Expand **Stored Procedures**, right-click the procedure to modify, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="7af7a-122">Modifiez le texte de la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="7af7a-122">Modify the text of the stored procedure.</span></span>  
  
5.  <span data-ttu-id="7af7a-123">Pour tester la syntaxe, dans le menu **Requête** , cliquez sur **Analyser**.</span><span class="sxs-lookup"><span data-stu-id="7af7a-123">To test the syntax, on the **Query** menu, click **Parse**.</span></span>  
  
6.  <span data-ttu-id="7af7a-124">Pour enregistrer les modifications apportées à la procédure, dans le menu **Requête** , cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="7af7a-124">To save the modifications to the procedure definition, on the **Query** menu, click **Execute**.</span></span>  
  
7.  <span data-ttu-id="7af7a-125">Pour enregistrer la procédure mise à jour en tant que script [!INCLUDE[tsql](../../includes/tsql-md.md)] , dans le menu **Fichier** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="7af7a-125">To save the updated procedure definition as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, on the **File** menu, click **Save As**.</span></span> <span data-ttu-id="7af7a-126">Acceptez le nom de fichier ou remplacez-le par un autre nom, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7af7a-126">Accept the file name or replace it with a new name, and then click **Save**.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7af7a-127">Validez toutes les entrées utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7af7a-127">Validate all user input.</span></span> <span data-ttu-id="7af7a-128">Ne concaténez pas les entrées utilisateur avant de les avoir validées.</span><span class="sxs-lookup"><span data-stu-id="7af7a-128">Do not concatenate user input before you validate it.</span></span> <span data-ttu-id="7af7a-129">N'exécutez jamais une commande élaborée à partir d'une entrée utilisateur non validée.</span><span class="sxs-lookup"><span data-stu-id="7af7a-129">Never execute a command constructed from unvalidated user input.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7af7a-130">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7af7a-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="7af7a-131">**Pour modifier une procédure dans l'Éditeur de requête**</span><span class="sxs-lookup"><span data-stu-id="7af7a-131">**To modify a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="7af7a-132">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="7af7a-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7af7a-133">Développez **Bases de données**, développez la base de données à laquelle appartient la procédure.</span><span class="sxs-lookup"><span data-stu-id="7af7a-133">Expand **Databases**, expand the database in which the procedure belongs.</span></span> <span data-ttu-id="7af7a-134">Sinon, dans la barre d'outils, sélectionnez une base de données dans la liste des bases de données disponibles.</span><span class="sxs-lookup"><span data-stu-id="7af7a-134">Or, from the tool bar, select the database from the list of available databases.</span></span> <span data-ttu-id="7af7a-135">Pour cet exemple, sélectionnez la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7af7a-135">For this example, select the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
3.  <span data-ttu-id="7af7a-136">Dans le menu **Fichier** , cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="7af7a-136">On the **File** menu, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="7af7a-137">Copiez et collez l'exemple suivant dans l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="7af7a-137">Copy and paste the following example into the query editor.</span></span> <span data-ttu-id="7af7a-138">L'exemple crée la procédure `uspVendorAllInfo` qui retourne le nom de tous les fournisseurs dans la base de données [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , les produits qu'ils vendent, leurs conditions de crédit et leur disponibilité.</span><span class="sxs-lookup"><span data-stu-id="7af7a-138">The example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
    ```  
  
    IF OBJECT_ID ( 'Purchasing.uspVendorAllInfo', 'P' ) IS NOT NULL   
        DROP PROCEDURE Purchasing.uspVendorAllInfo;  
    GO  
    CREATE PROCEDURE Purchasing.uspVendorAllInfo  
    WITH EXECUTE AS CALLER  
    AS  
        SET NOCOUNT ON;  
        SELECT v.Name AS Vendor, p.Name AS 'Product name',   
          v.CreditRating AS 'Rating',   
          v.ActiveFlag AS Availability  
        FROM Purchasing.Vendor v   
        INNER JOIN Purchasing.ProductVendor pv  
          ON v.BusinessEntityID = pv.BusinessEntityID   
        INNER JOIN Production.Product p  
          ON pv.ProductID = p.ProductID   
        ORDER BY v.Name ASC;  
    GO  
  
    ```  
  
5.  <span data-ttu-id="7af7a-139">Dans le menu **Fichier** , cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="7af7a-139">On the **File** menu, click **New Query**.</span></span>  
  
6.  <span data-ttu-id="7af7a-140">Copiez et collez l'exemple suivant dans l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="7af7a-140">Copy and paste the following example into the query editor.</span></span> <span data-ttu-id="7af7a-141">L'exemple modifie la procédure `uspVendorAllInfo` .</span><span class="sxs-lookup"><span data-stu-id="7af7a-141">The example modifies the `uspVendorAllInfo` procedure.</span></span> <span data-ttu-id="7af7a-142">La clause EXECUTE AS CALLER est supprimée et le corps de la procédure est modifié pour qu'elle retourne uniquement les fournisseurs qui proposent le produit spécifié.</span><span class="sxs-lookup"><span data-stu-id="7af7a-142">The EXECUTE AS CALLER clause is removed and the body of the procedure is modified to return only those vendors that supply the specified product.</span></span> <span data-ttu-id="7af7a-143">Les fonctions `LEFT` et `CASE` personnalisent l'affichage du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="7af7a-143">The `LEFT` and `CASE` functions customize the appearance of the result set.</span></span>  
  
    ```  
    ALTER PROCEDURE Purchasing.uspVendorAllInfo  
        @Product varchar(25)   
    AS  
        SET NOCOUNT ON;  
        SELECT LEFT(v.Name, 25) AS Vendor, LEFT(p.Name, 25) AS 'Product name',   
        'Rating' = CASE v.CreditRating   
            WHEN 1 THEN 'Superior'  
            WHEN 2 THEN 'Excellent'  
            WHEN 3 THEN 'Above average'  
            WHEN 4 THEN 'Average'  
            WHEN 5 THEN 'Below average'  
            ELSE 'No rating'  
            END  
        , Availability = CASE v.ActiveFlag  
            WHEN 1 THEN 'Yes'  
            ELSE 'No'  
            END  
        FROM Purchasing.Vendor AS v   
        INNER JOIN Purchasing.ProductVendor AS pv  
          ON v.BusinessEntityID = pv.BusinessEntityID   
        INNER JOIN Production.Product AS p   
          ON pv.ProductID = p.ProductID   
        WHERE p.Name LIKE @Product  
        ORDER BY v.Name ASC;  
    GO  
  
    ```  
  
7.  <span data-ttu-id="7af7a-144">Pour enregistrer les modifications apportées à la procédure, dans le menu **Requête** , cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="7af7a-144">To save the modifications to the procedure definition, on the **Query** menu, click **Execute**.</span></span>  
  
8.  <span data-ttu-id="7af7a-145">Pour enregistrer la procédure mise à jour en tant que script [!INCLUDE[tsql](../../includes/tsql-md.md)] , dans le menu **Fichier** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="7af7a-145">To save the updated procedure definition as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, on the **File** menu, click **Save As**.</span></span> <span data-ttu-id="7af7a-146">Acceptez le nom de fichier ou remplacez-le par un autre nom, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7af7a-146">Accept the file name or replace it with a new name, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="7af7a-147">Pour exécuter la procédure stockée modifiée, exécutez l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="7af7a-147">To run the modified stored procedure, execute the following example.</span></span>  
  
    ```  
    EXEC Purchasing.uspVendorAllInfo N'LL Crankarm';  
    GO  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7af7a-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7af7a-148">See Also</span></span>  
 [<span data-ttu-id="7af7a-149">ALTER PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7af7a-149">ALTER PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-procedure-transact-sql)  
  
  
