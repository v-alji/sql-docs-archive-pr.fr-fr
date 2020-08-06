---
title: 'Didacticiel : chaînes de propriétés et changement de contexte | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- context switching [SQL Server], tutorials
- ownership chains [SQL Server]
ms.assetid: db5d4cc3-5fc5-4cf5-afc1-8d4edc1d512b
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e9072a68dd3179e5900fda06d4fea58b484a37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603358"
---
# <a name="tutorial-ownership-chains-and-context-switching"></a><span data-ttu-id="aadb3-102">Tutorial: Ownership Chains and Context Switching</span><span class="sxs-lookup"><span data-stu-id="aadb3-102">Tutorial: Ownership Chains and Context Switching</span></span>
  <span data-ttu-id="aadb3-103">Ce didacticiel explore en se fondant sur un scénario les concepts de sécurité de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] impliquant les chaînes de propriétés et le changement de contexte utilisateur.</span><span class="sxs-lookup"><span data-stu-id="aadb3-103">This tutorial uses a scenario to illustrate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] security concepts involving ownership chains and user context switching.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aadb3-104">Pour exécuter le code de ce didacticiel, vous devez à la fois configurer la sécurité en mode mixte et installer la base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aadb3-104">To run the code in this tutorial you must have both Mixed Mode security configured and the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database installed.</span></span> <span data-ttu-id="aadb3-105">Pour plus d’informations sur la sécurité en mode mixte, consultez [Choisir un mode d’authentification](security/choose-an-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="aadb3-105">For more information about Mixed Mode security, see [Choose an Authentication Mode](security/choose-an-authentication-mode.md).</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="aadb3-106">Scénario</span><span class="sxs-lookup"><span data-stu-id="aadb3-106">Scenario</span></span>  
 <span data-ttu-id="aadb3-107">Dans ce scénario, deux utilisateurs ont besoin de comptes leur permettant d'accéder aux données des bons de commande stockées dans la base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aadb3-107">In this scenario, two users need accounts to access purchase order data stored in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="aadb3-108">Les exigences requises sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="aadb3-108">The requirements are as follows:</span></span>  
  
-   <span data-ttu-id="aadb3-109">Le premier compte (TestManagerUser) doit être en mesure de dévoiler toutes les données détaillées dans chaque bon de commande.</span><span class="sxs-lookup"><span data-stu-id="aadb3-109">The first account (TestManagerUser) must be able to see all details in every purchase order.</span></span>  
  
-   <span data-ttu-id="aadb3-110">Le deuxième compte (TestEmployeeUser) doit afficher le numéro de bon de commande, la date de commande, la date d'expédition, les ID des produits et les articles commandés et reçus par bon de commande (par numéro de bon de commande) pour les articles pour lesquels des livraisons partielles ont été reçues.</span><span class="sxs-lookup"><span data-stu-id="aadb3-110">The second account (TestEmployeeUser) must be able to see the purchase order number, order date, shipping date, product ID numbers, and the ordered and received items per purchase order, by purchase order number, for items where partial shipments have been received.</span></span>  
  
-   <span data-ttu-id="aadb3-111">Tous les autres comptes doivent conserver leurs autorisations actuelles.</span><span class="sxs-lookup"><span data-stu-id="aadb3-111">All other accounts must retain their current permissions.</span></span>  
  
 <span data-ttu-id="aadb3-112">Pour répondre aux exigences de ce scénario, l'exemple est divisé en quatre parties décrivant les concepts relatifs aux chaînes de propriétés et au changement de contexte :</span><span class="sxs-lookup"><span data-stu-id="aadb3-112">To fulfill the requirements of this scenario, the example is broken into four parts that demonstrate the concepts of ownership chains and context switching:</span></span>  
  
1.  <span data-ttu-id="aadb3-113">Configuration de l'environnement</span><span class="sxs-lookup"><span data-stu-id="aadb3-113">Configuring the environment.</span></span>  
  
2.  <span data-ttu-id="aadb3-114">Création d'une procédure stockée pour l'accès aux données par bon de commande</span><span class="sxs-lookup"><span data-stu-id="aadb3-114">Creating a stored procedure to access data by purchase order.</span></span>  
  
3.  <span data-ttu-id="aadb3-115">Accès aux données par le biais de la procédure stockée</span><span class="sxs-lookup"><span data-stu-id="aadb3-115">Accessing the data through the stored procedure.</span></span>  
  
4.  <span data-ttu-id="aadb3-116">Réinitialisation de l'environnement</span><span class="sxs-lookup"><span data-stu-id="aadb3-116">Resetting the environment.</span></span>  
  
 <span data-ttu-id="aadb3-117">Chaque bloc de code dans cet exemple est présenté sous forme de lignes.</span><span class="sxs-lookup"><span data-stu-id="aadb3-117">Each code block in this example is explained in line.</span></span> <span data-ttu-id="aadb3-118">Pour copier l'exemple tout entier, consultez la section [Exemple complet](#CompleteExample) à la fin de ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="aadb3-118">To copy the complete example, see [Complete Example](#CompleteExample) at the end of this tutorial.</span></span>  
  
## <a name="1-configure-the-environment"></a><span data-ttu-id="aadb3-119">1. Configurez l'environnement</span><span class="sxs-lookup"><span data-stu-id="aadb3-119">1. Configure the Environment</span></span>  
 <span data-ttu-id="aadb3-120">Utilisez [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] et le code suivant pour ouvrir la `AdventureWorks2012` base de données et utilisez l' `CURRENT_USER` [!INCLUDE[tsql](../includes/tsql-md.md)] instruction pour vérifier que l’utilisateur dbo est affiché comme contexte.</span><span class="sxs-lookup"><span data-stu-id="aadb3-120">Use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and the following code to open the `AdventureWorks2012` database, and use the `CURRENT_USER` [!INCLUDE[tsql](../includes/tsql-md.md)] statement to check that the dbo user is displayed as the context.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
```  
  
 <span data-ttu-id="aadb3-121">Pour plus d’informations sur l’instruction CURRENT_USER, consultez [CURRENT_USER &#40;Transact-SQL&#41;](/sql/t-sql/functions/current-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="aadb3-121">For more information about the CURRENT_USER statement, see [CURRENT_USER &#40;Transact-SQL&#41;](/sql/t-sql/functions/current-user-transact-sql).</span></span>  
  
 <span data-ttu-id="aadb3-122">Utilisez ce code en tant qu'utilisateur dbo pour créer deux utilisateurs sur le serveur et dans la base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aadb3-122">Use this code as the dbo user to create two users on the server and in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
CREATE LOGIN TestManagerUser   
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khx';  
GO  
CREATE USER TestManagerUser   
   FOR LOGIN TestManagerUser  
   WITH DEFAULT_SCHEMA = Purchasing;  
GO   
  
CREATE LOGIN TestEmployeeUser  
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
GO  
CREATE USER TestEmployeeUser   
   FOR LOGIN TestEmployeeUser;  
GO   
```  
  
 <span data-ttu-id="aadb3-123">Pour plus d’informations sur l’instruction CREATE USER, consultez [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="aadb3-123">For more information about the CREATE USER statement, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span> <span data-ttu-id="aadb3-124">Pour plus d’informations sur l’instruction CREATE LOGIN, consultez [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="aadb3-124">For more information about the CREATE LOGIN statement, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
 <span data-ttu-id="aadb3-125">Utilisez le code suivant pour modifier la propriété du schéma `Purchasing` du compte `TestManagerUser` .</span><span class="sxs-lookup"><span data-stu-id="aadb3-125">Use the following code to change the ownership of the `Purchasing` schema to the `TestManagerUser` account.</span></span> <span data-ttu-id="aadb3-126">Le compte peut alors exploiter l'accès à toutes les instructions DML (Data Manipulation Language, langage de manipulation de données), notamment les autorisations `SELECT` et `INSERT` , sur les objets qu'il contient.</span><span class="sxs-lookup"><span data-stu-id="aadb3-126">This allows that account to use all Data Manipulation Language (DML) statement access (such as `SELECT` and `INSERT` permissions) on the objects it contains.</span></span> <span data-ttu-id="aadb3-127">`TestManagerUser` se voit également octroyer la possibilité de créer des procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="aadb3-127">`TestManagerUser` is also granted the ability to create stored procedures.</span></span>  
  
```  
/* Change owner of the Purchasing Schema to TestManagerUser */  
ALTER AUTHORIZATION   
   ON SCHEMA::Purchasing   
   TO TestManagerUser;  
GO  
  
GRANT CREATE PROCEDURE   
   TO TestManagerUser   
   WITH GRANT OPTION;  
GO  
```  
  
 <span data-ttu-id="aadb3-128">Pour plus d’informations sur l’instruction GRANT, consultez [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="aadb3-128">For more information about the GRANT statement, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span> <span data-ttu-id="aadb3-129">Pour plus d’informations sur les procédures stockées, consultez [Procédures stockées &#40;moteur de base de données&#41;](stored-procedures/stored-procedures-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="aadb3-129">For more information about stored procedures, see [Stored Procedures &#40;Database Engine&#41;](stored-procedures/stored-procedures-database-engine.md).</span></span> <span data-ttu-id="aadb3-130">Pour obtenir une affiche de toutes les [!INCLUDE[ssDE](../includes/ssde-md.md)] autorisations, consultez [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf) .</span><span class="sxs-lookup"><span data-stu-id="aadb3-130">For a poster of all [!INCLUDE[ssDE](../includes/ssde-md.md)] permissions, see [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span></span>  
  
## <a name="2-create-a-stored-procedure-to-access-data"></a><span data-ttu-id="aadb3-131">2. Créer une procédure stockée pour accéder aux données</span><span class="sxs-lookup"><span data-stu-id="aadb3-131">2. Create a Stored Procedure to Access Data</span></span>  
 <span data-ttu-id="aadb3-132">Pour basculer le contexte dans une base de données, utilisez l’instruction EXECUTE AS.</span><span class="sxs-lookup"><span data-stu-id="aadb3-132">To switch context within a database, use the EXECUTE AS statement.</span></span> <span data-ttu-id="aadb3-133">EXECUTE AS nécessite des autorisations IMPERSONATE.</span><span class="sxs-lookup"><span data-stu-id="aadb3-133">EXECUTE AS requires IMPERSONATE permissions.</span></span>  
  
 <span data-ttu-id="aadb3-134">Utilisez l'instruction `EXECUTE AS` dans le code ci-après pour modifier le contexte et le redéfinir à `TestManagerUser` et pour créer une procédure stockée affichant uniquement les données requises par `TestEmployeeUser`.</span><span class="sxs-lookup"><span data-stu-id="aadb3-134">Use the `EXECUTE AS` statement in the following code to change the context to `TestManagerUser` and create a stored procedure showing only the data required by `TestEmployeeUser`.</span></span> <span data-ttu-id="aadb3-135">Pour répondre aux exigences, la procédure stockée accepte une variable pour le numéro de bon de commande et n'affiche pas de données financières. De même, la clause WHERE limite les résultats aux expéditions partielles.</span><span class="sxs-lookup"><span data-stu-id="aadb3-135">To satisfy the requirements, the stored procedure accepts one variable for the purchase order number and does not display financial information, and the WHERE clause limits the results to partial shipments.</span></span>  
  
```  
EXECUTE AS LOGIN = 'TestManagerUser'  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
  
/* Note: The user that calls the EXECUTE AS statement must have IMPERSONATE permissions on the target principal */  
CREATE PROCEDURE usp_ShowWaitingItems @ProductID int  
AS  
BEGIN   
   SELECT a.PurchaseOrderID, a.OrderDate, a.ShipDate  
      , b.ProductID, b.OrderQty, b.ReceivedQty  
   FROM Purchasing.PurchaseOrderHeader a  
      INNER JOIN Purchasing.PurchaseOrderDetail b  
         ON a.PurchaseOrderID = b.PurchaseOrderID  
   WHERE b.OrderQty > b.ReceivedQty  
      AND @ProductID = b.ProductID  
   ORDER BY b.ProductID ASC  
END  
GO  
```  
  
 <span data-ttu-id="aadb3-136">Actuellement, `TestEmployeeUser` n'a accès à aucun objet de base de données.</span><span class="sxs-lookup"><span data-stu-id="aadb3-136">Currently `TestEmployeeUser` does not have access to any database objects.</span></span> <span data-ttu-id="aadb3-137">Le code suivant (toujours dans le contexte `TestManagerUser` ) accorde au compte de l'utilisateur la possibilité d'interroger les informations des tables de base par l'intermédiaire de la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="aadb3-137">The following code (still in the `TestManagerUser` context) grants the user account the ability to query base-table information through the stored procedure.</span></span>  
  
```  
GRANT EXECUTE  
   ON OBJECT::Purchasing.usp_ShowWaitingItems  
   TO TestEmployeeUser;  
GO  
```  
  
 <span data-ttu-id="aadb3-138">La procédure stockée est un élément inhérent au schéma `Purchasing` , même si aucun schéma n'a été spécifié, puisque `TestManagerUser` est attribué par défaut au schéma `Purchasing` .</span><span class="sxs-lookup"><span data-stu-id="aadb3-138">The stored procedure is part of the `Purchasing` schema, even though no schema was explicitly specified, because `TestManagerUser` is assigned by default to the `Purchasing` schema.</span></span> <span data-ttu-id="aadb3-139">Vous pouvez utiliser les informations du catalogue système pour rechercher des objets, comme le montre le code suivant.</span><span class="sxs-lookup"><span data-stu-id="aadb3-139">You can use system catalog information to locate objects, as shown in the following code.</span></span>  
  
```  
SELECT a.name AS 'Schema'  
   , b.name AS 'Object Name'  
   , b.type AS 'Object Type'  
FROM sys.schemas a  
   INNER JOIN sys.objects b  
      ON a.schema_id = b.schema_id   
WHERE b.name = 'usp_ShowWaitingItems';  
GO  
```  
  
 <span data-ttu-id="aadb3-140">Une fois cette section de l'exemple terminée, le code change de nouveau de contexte pour repasser à dbo à l'aide de l'instruction `REVERT`.</span><span class="sxs-lookup"><span data-stu-id="aadb3-140">With this section of the example completed, the code switches context back to dbo using the `REVERT` statement.</span></span>  
  
```  
REVERT;  
GO  
```  
  
 <span data-ttu-id="aadb3-141">Pour plus d’informations sur l’instruction REVERT, consultez [REVERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/revert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="aadb3-141">For more information about the REVERT statement, see [REVERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/revert-transact-sql).</span></span>  
  
## <a name="3-access-data-through-the-stored-procedure"></a><span data-ttu-id="aadb3-142">3. Accéder aux données par le biais de la procédure stockée</span><span class="sxs-lookup"><span data-stu-id="aadb3-142">3. Access Data Through the Stored Procedure</span></span>  
 <span data-ttu-id="aadb3-143">`TestEmployeeUser` ne dispose d’aucune autorisation pour les objets de la base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] en dehors d’une connexion et des droits attribués au rôle de base de données public.</span><span class="sxs-lookup"><span data-stu-id="aadb3-143">`TestEmployeeUser` has no permissions on the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database objects other than a login and the rights assigned to the public database role.</span></span> <span data-ttu-id="aadb3-144">Le code suivant retourne une erreur lorsque `TestEmployeeUser` tente d'accéder aux tables de base.</span><span class="sxs-lookup"><span data-stu-id="aadb3-144">The following code returns an error when `TestEmployeeUser` attempts to access base tables.</span></span>  
  
```  
EXECUTE AS LOGIN = 'TestEmployeeUser'  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
/* This won't work */  
SELECT *  
FROM Purchasing.PurchaseOrderHeader;  
GO  
SELECT *  
FROM Purchasing.PurchaseOrderDetail;  
GO  
```  
  
 <span data-ttu-id="aadb3-145">Du fait que les objets référencés par la procédure stockée créée au cours de la dernière section appartiennent à `TestManagerUser` en raison de la propriété du schéma `Purchasing` , `TestEmployeeUser` peut accéder aux tables de base par le biais de la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="aadb3-145">Because the objects referenced by the stored procedure created in the last section are owned by `TestManagerUser` by virtue of the `Purchasing` schema ownership, `TestEmployeeUser` can access the base tables through the stored procedure.</span></span> <span data-ttu-id="aadb3-146">Le code suivant qui utilise toujours le contexte `TestEmployeeUser` transmet le bon de commande 952 en guise de paramètre.</span><span class="sxs-lookup"><span data-stu-id="aadb3-146">The following code, still using the `TestEmployeeUser` context, passes purchase order 952 as a parameter.</span></span>  
  
```  
EXEC Purchasing.usp_ShowWaitingItems 952  
GO  
```  
  
## <a name="4-reset-the-environment"></a><span data-ttu-id="aadb3-147">4. Réinitialisez l'environnement</span><span class="sxs-lookup"><span data-stu-id="aadb3-147">4. Reset the Environment</span></span>  
 <span data-ttu-id="aadb3-148">Le code ci-dessous exploite la commande `REVERT` pour retourner le contexte du compte actuel à `dbo`, puis réinitialise l'environnement.</span><span class="sxs-lookup"><span data-stu-id="aadb3-148">The following code uses the `REVERT` command to return the context of the current account to `dbo`, and then resets the environment.</span></span>  
  
```  
REVERT;  
GO  
ALTER AUTHORIZATION   
ON SCHEMA::Purchasing TO dbo;  
GO  
DROP PROCEDURE Purchasing.usp_ShowWaitingItems;  
GO  
DROP USER TestEmployeeUser;  
GO  
DROP USER TestManagerUser;  
GO  
DROP LOGIN TestEmployeeUser;  
GO  
DROP LOGIN TestManagerUser;  
GO  
```  
  
##  <a name="complete-example"></a><a name="CompleteExample"></a><span data-ttu-id="aadb3-149">Exemple complet</span><span class="sxs-lookup"><span data-stu-id="aadb3-149">Complete Example</span></span>  
 <span data-ttu-id="aadb3-150">Cette section affiche l'exemple de code dans son intégralité.</span><span class="sxs-lookup"><span data-stu-id="aadb3-150">This section displays the complete example code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aadb3-151">Ce code n'inclut pas les deux erreurs attendues et expliquant l'inaptitude de `TestEmployeeUser` à effectuer une sélection à partir des tables de base.</span><span class="sxs-lookup"><span data-stu-id="aadb3-151">This code does not include the two expected errors that demonstrate the inability of `TestEmployeeUser` to select from base tables.</span></span>  
  
```  
/*   
Script:       UserContextTutorial.sql  
Author:       Microsoft  
Last Updated: Books Online  
Conditions:   Execute as DBO or sysadmin in the AdventureWorks database  
Section 1:    Configure the Environment   
*/  
USE AdventureWorks2012;  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
/* Create server and database users */  
CREATE LOGIN TestManagerUser   
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khx';  
  
GO  
  
CREATE USER TestManagerUser   
   FOR LOGIN TestManagerUser  
   WITH DEFAULT_SCHEMA = Purchasing;  
GO   
  
CREATE LOGIN TestEmployeeUser  
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
GO  
CREATE USER TestEmployeeUser   
   FOR LOGIN TestEmployeeUser;  
GO   
  
/* Change owner of the Purchasing Schema to TestManagerUser */  
ALTER AUTHORIZATION   
   ON SCHEMA::Purchasing   
   TO TestManagerUser;  
GO  
  
GRANT CREATE PROCEDURE   
   TO TestManagerUser   
   WITH GRANT OPTION;  
GO  
  
/*   
Section 2: Switch Context and Create Objects  
*/  
EXECUTE AS LOGIN = 'TestManagerUser';  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
  
/* Note: The user that calls the EXECUTE AS statement must have IMPERSONATE permissions on the target principal */  
CREATE PROCEDURE usp_ShowWaitingItems @ProductID int  
AS  
BEGIN   
   SELECT a.PurchaseOrderID, a.OrderDate, a.ShipDate  
      , b.ProductID, b.OrderQty, b.ReceivedQty  
   FROM Purchasing.PurchaseOrderHeader AS a  
      INNER JOIN Purchasing.PurchaseOrderDetail AS b  
         ON a.PurchaseOrderID = b.PurchaseOrderID  
   WHERE b.OrderQty > b.ReceivedQty  
      AND @ProductID = b.ProductID  
   ORDER BY b.ProductID ASC  
END;  
GO  
  
/* Give the employee the ability to run the procedure */  
GRANT EXECUTE   
   ON OBJECT::Purchasing.usp_ShowWaitingItems  
   TO TestEmployeeUser;  
GO   
  
/* Notice that the stored procedure is located in the Purchasing   
schema. This also demonstrates system catalogs */  
SELECT a.name AS 'Schema'  
   , b.name AS 'Object Name'  
   , b.type AS 'Object Type'  
FROM sys.schemas AS a  
   INNER JOIN sys.objects AS b  
      ON a.schema_id = b.schema_id   
WHERE b.name = 'usp_ShowWaitingItems';  
GO  
  
/* Go back to being the dbo user */  
REVERT;  
GO  
  
/*  
Section 3: Switch Context and Observe Security   
*/  
EXECUTE AS LOGIN = 'TestEmployeeUser';  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
EXEC Purchasing.usp_ShowWaitingItems 952;  
GO  
  
/*   
Section 4: Clean Up Example  
*/  
REVERT;  
GO  
ALTER AUTHORIZATION   
ON SCHEMA::Purchasing TO dbo;  
GO  
DROP PROCEDURE Purchasing.usp_ShowWaitingItems;  
GO  
DROP USER TestEmployeeUser;  
GO  
DROP USER TestManagerUser;  
GO  
DROP LOGIN TestEmployeeUser;  
GO  
DROP LOGIN TestManagerUser;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="aadb3-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aadb3-152">See Also</span></span>  
 [<span data-ttu-id="aadb3-153">Centre de sécurité pour le moteur de base de données SQL Server et Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="aadb3-153">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
