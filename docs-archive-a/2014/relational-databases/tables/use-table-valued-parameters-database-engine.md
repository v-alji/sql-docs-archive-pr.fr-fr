---
title: Utiliser les paramètres table (Moteur de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- DECLARE
- CREATE TYPE
helpviewer_keywords:
- table-valued parameters
- table-valued parameters, about table-valued parameters
- parameters [SQL Server], table-valued
- TVP See table-valued parameters
ms.assetid: 5e95a382-1e01-4c74-81f5-055612c2ad99
author: stevestein
ms.author: sstein
ms.openlocfilehash: fa7013fddc6b2ce12ad9ad0f9fcb511d93915e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605311"
---
# <a name="use-table-valued-parameters-database-engine"></a><span data-ttu-id="deb3f-102">Utiliser les paramètres table (Moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="deb3f-102">Use Table-Valued Parameters (Database Engine)</span></span>
  <span data-ttu-id="deb3f-103">Les paramètres table sont déclarés en utilisant des types de table définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="deb3f-103">Table-valued parameters are declared by using user-defined table types.</span></span> <span data-ttu-id="deb3f-104">Vous pouvez utiliser des paramètres table pour envoyer plusieurs lignes de données à une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] ou à une routine, telle qu'une procédure stockée ou une fonction, sans créer de table temporaire ou de nombreux paramètres.</span><span class="sxs-lookup"><span data-stu-id="deb3f-104">You can use table-valued parameters to send multiple rows of data to a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or a routine, such as a stored procedure or function, without creating a temporary table or many parameters.</span></span>  
  
 <span data-ttu-id="deb3f-105">Les paramètres table sont comme les tableaux de paramètres dans OLE DB et ODBC, mais ils offrent plus de souplesse et une intégration plus étroite avec [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="deb3f-105">Table-valued parameters are like parameter arrays in OLE DB and ODBC, but offer more flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="deb3f-106">Ils ont également l'avantage de pouvoir participer aux opérations basées sur des ensembles.</span><span class="sxs-lookup"><span data-stu-id="deb3f-106">Table-valued parameters also have the benefit of being able to participate in set-based operations.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="deb3f-107">passe des paramètres table aux routines par référence afin d’éviter d’effectuer une copie des données d’entrée.</span><span class="sxs-lookup"><span data-stu-id="deb3f-107">passes table-valued parameters to routines by reference to avoid making a copy of the input data.</span></span> <span data-ttu-id="deb3f-108">Vous pouvez créer et exécuter des routines [!INCLUDE[tsql](../../includes/tsql-md.md)] avec des paramètres table et les appeler depuis du code [!INCLUDE[tsql](../../includes/tsql-md.md)] , des clients gérés et natifs dans tout langage managé.</span><span class="sxs-lookup"><span data-stu-id="deb3f-108">You can create and execute [!INCLUDE[tsql](../../includes/tsql-md.md)] routines with table-valued parameters, and call them from [!INCLUDE[tsql](../../includes/tsql-md.md)] code, managed and native clients in any managed language.</span></span>  
  
 <span data-ttu-id="deb3f-109">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="deb3f-109">**In This Topic:**</span></span>  
  
 [<span data-ttu-id="deb3f-110">Avantages</span><span class="sxs-lookup"><span data-stu-id="deb3f-110">Benefits</span></span>](#Benefits)  
  
 [<span data-ttu-id="deb3f-111">Restrictions</span><span class="sxs-lookup"><span data-stu-id="deb3f-111">Restrictions</span></span>](#Restrictions)  
  
 [<span data-ttu-id="deb3f-112">Paramètres table et opérations BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="deb3f-112">Table-Valued Parameters vs. BULK INSERT Operations</span></span>](#BulkInsert)  
  
 [<span data-ttu-id="deb3f-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="deb3f-113">Example</span></span>](#Example)  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="deb3f-114">Avantages</span><span class="sxs-lookup"><span data-stu-id="deb3f-114">Benefits</span></span>  
 <span data-ttu-id="deb3f-115">Un paramètre table a comme portée la procédure stockée, la fonction ou le texte [!INCLUDE[tsql](../../includes/tsql-md.md)] dynamique, exactement comme d'autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="deb3f-115">A table-valued parameter is scoped to the stored procedure, function, or dynamic [!INCLUDE[tsql](../../includes/tsql-md.md)] text, exactly like other parameters.</span></span> <span data-ttu-id="deb3f-116">De même, une variable de type de table a une portée semblable à toute autre variable locale créée à l'aide d'une instruction DECLARE.</span><span class="sxs-lookup"><span data-stu-id="deb3f-116">Similarly, a variable of table type has scope like any other local variable that is created by using a DECLARE statement.</span></span> <span data-ttu-id="deb3f-117">Vous pouvez déclarer des variables table dans des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] dynamiques et passer ces variables comme paramètres table à des procédures stockées et des fonctions.</span><span class="sxs-lookup"><span data-stu-id="deb3f-117">You can declare table-valued variables within dynamic [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and pass these variables as table-valued parameters to stored procedures and functions.</span></span>  
  
 <span data-ttu-id="deb3f-118">Les paramètres table offrent davantage de souplesse et dans certains cas de meilleures performances que les tables temporaires ou autres méthodes de passage d'une liste de paramètres.</span><span class="sxs-lookup"><span data-stu-id="deb3f-118">Table-valued parameters offer more flexibility and in some cases better performance than temporary tables or other ways to pass a list of parameters.</span></span> <span data-ttu-id="deb3f-119">Les paramètres table offrent les avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="deb3f-119">Table-valued parameters offer the following benefits:</span></span>  
  
-   <span data-ttu-id="deb3f-120">Pas d'acquisition de verrous pour le remplissage initial de données à partir d'un client.</span><span class="sxs-lookup"><span data-stu-id="deb3f-120">Do not acquire locks for the initial population of data from a client.</span></span>  
  
-   <span data-ttu-id="deb3f-121">Fournissent un modèle de programmation simple.</span><span class="sxs-lookup"><span data-stu-id="deb3f-121">Provide a simple programming model.</span></span>  
  
-   <span data-ttu-id="deb3f-122">Vous permettent d'inclure une logique métier complexe dans une routine unique.</span><span class="sxs-lookup"><span data-stu-id="deb3f-122">Enable you to include complex business logic in a single routine.</span></span>  
  
-   <span data-ttu-id="deb3f-123">Réduisent les boucles au serveur.</span><span class="sxs-lookup"><span data-stu-id="deb3f-123">Reduce round trips to the server.</span></span>  
  
-   <span data-ttu-id="deb3f-124">Peuvent avoir une structure de table de cardinalité différente.</span><span class="sxs-lookup"><span data-stu-id="deb3f-124">Can have a table structure of different cardinality.</span></span>  
  
-   <span data-ttu-id="deb3f-125">Sont fortement typées.</span><span class="sxs-lookup"><span data-stu-id="deb3f-125">Are strongly typed.</span></span>  
  
-   <span data-ttu-id="deb3f-126">Permettent au client de spécifier un ordre de tri et des clés uniques.</span><span class="sxs-lookup"><span data-stu-id="deb3f-126">Enable the client to specify sort order and unique keys.</span></span>  
  
-   <span data-ttu-id="deb3f-127">Sont mis en cache comme une table temporaire en cas de utilisation dans une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="deb3f-127">Are cached like a temp table when used in a stored procedure.</span></span> <span data-ttu-id="deb3f-128">À compter de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], les paramètres table sont également mis en cache pour les requêtes paramétrables.</span><span class="sxs-lookup"><span data-stu-id="deb3f-128">Starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], table-valued parameters are also cached for parameterized queries.</span></span>  
  
##  <a name="restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="deb3f-129">Restrictions</span><span class="sxs-lookup"><span data-stu-id="deb3f-129">Restrictions</span></span>  
 <span data-ttu-id="deb3f-130">Les paramètres table ont les restrictions suivantes :</span><span class="sxs-lookup"><span data-stu-id="deb3f-130">Table-valued parameters have the following restrictions:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="deb3f-131">ne maintient pas de statistiques sur les colonnes de paramètres table.</span><span class="sxs-lookup"><span data-stu-id="deb3f-131">does not maintain statistics on columns of table-valued parameters.</span></span>  
  
-   <span data-ttu-id="deb3f-132">Les paramètres table doivent être passés comme paramètres READONLY d'entrée aux routines [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="deb3f-132">Table-valued parameters must be passed as input READONLY parameters to [!INCLUDE[tsql](../../includes/tsql-md.md)] routines.</span></span> <span data-ttu-id="deb3f-133">Vous ne pouvez pas effectuer d'opérations DML telles que UPDATE, DELETE ou INSERT sur un paramètre table dans le corps d'une routine.</span><span class="sxs-lookup"><span data-stu-id="deb3f-133">You cannot perform DML operations such as UPDATE, DELETE, or INSERT on a table-valued parameter in the body of a routine.</span></span>  
  
-   <span data-ttu-id="deb3f-134">Vous ne pouvez pas utiliser de paramètre table comme cible d'une instruction SELECT INTO ou INSERT EXEC.</span><span class="sxs-lookup"><span data-stu-id="deb3f-134">You cannot use a table-valued parameter as target of a SELECT INTO or INSERT EXEC statement.</span></span> <span data-ttu-id="deb3f-135">Un paramètre table peut être dans la clause FROM de SELECT INTO ou dans la chaîne ou procédure stockée INSERT EXEC.</span><span class="sxs-lookup"><span data-stu-id="deb3f-135">A table-valued parameter can be in the FROM clause of SELECT INTO or in the INSERT EXEC string or stored procedure.</span></span>  
  
##  <a name="table-valued-parameters-vs-bulk-insert-operations"></a><a name="BulkInsert"></a><span data-ttu-id="deb3f-136">Paramètres table et opérations BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="deb3f-136">Table-Valued Parameters vs. BULK INSERT Operations</span></span>  
 <span data-ttu-id="deb3f-137">L'utilisation de paramètres table est comparable à d'autres méthodes d'utilisation de variables basées sur des ensembles ; toutefois, l'utilisation de paramètres table peut souvent s'avérer plus rapide pour les grands ensembles de données.</span><span class="sxs-lookup"><span data-stu-id="deb3f-137">Using table-valued parameters is comparable to other ways of using set-based variables; however, using table-valued parameters frequently can be faster for large data sets.</span></span> <span data-ttu-id="deb3f-138">Comparé aux opérations en bloc, qui ont un coût de démarrage supérieur, les paramètres table sont particulièrement adaptés à l'insertion de moins de 1000 lignes.</span><span class="sxs-lookup"><span data-stu-id="deb3f-138">Compared to bulk operations that have a greater startup cost than table-valued parameters, table-valued parameters perform well for inserting less than 1000 rows.</span></span>  
  
 <span data-ttu-id="deb3f-139">Les paramètres table réutilisés tirent parti de la mise en cache de table temporaire.</span><span class="sxs-lookup"><span data-stu-id="deb3f-139">Table-valued parameters that are reused benefit from temporary table caching.</span></span> <span data-ttu-id="deb3f-140">Cette mise en cache de table autorise une meilleure extensibilité que les opérations BULK INSERT équivalentes.</span><span class="sxs-lookup"><span data-stu-id="deb3f-140">This table caching enables better scalability than equivalent BULK INSERT operations.</span></span> <span data-ttu-id="deb3f-141">En utilisant de petites opérations d'insertion de ligne, vous pouvez retirer un petit avantage en matière de performances en utilisant des listes de paramètres ou des instructions groupées au lieu d'opérations BULK INSERT ou de paramètres table.</span><span class="sxs-lookup"><span data-stu-id="deb3f-141">By using small row-insert operations a small performance benefit might be gained by using parameter lists or batched statements instead of BULK INSERT operations or table-valued parameters.</span></span> <span data-ttu-id="deb3f-142">Toutefois, ces méthodes sont moins commodes à programmer et les performances diminuent rapidement à mesure que le nombre de lignes augmente.</span><span class="sxs-lookup"><span data-stu-id="deb3f-142">However, these methods are less convenient to program, and performance decreases quickly as rows increase.</span></span>  
  
 <span data-ttu-id="deb3f-143">Les paramètres table procurent des performances supérieures ou égales à une implémentation de tableau de paramètres équivalente.</span><span class="sxs-lookup"><span data-stu-id="deb3f-143">Table-valued parameters perform equally well or better than an equivalent parameter array implementation.</span></span>  
  
##  <a name="example"></a><a name="Example"></a> <span data-ttu-id="deb3f-144">Exemple</span><span class="sxs-lookup"><span data-stu-id="deb3f-144">Example</span></span>  
 <span data-ttu-id="deb3f-145">L'exemple suivant utilise [!INCLUDE[tsql](../../includes/tsql-md.md)] et montre comment créer un type de paramètre table, déclarer une variable pour y faire référence, remplir la liste de paramètres, puis passer les valeurs à une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="deb3f-145">The following example uses [!INCLUDE[tsql](../../includes/tsql-md.md)] and shows you how to create a table-valued parameter type, declare a variable to reference it, fill the parameter list, and then pass the values to a stored procedure.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
/* Create a table type. */  
CREATE TYPE LocationTableType AS TABLE   
( LocationName VARCHAR(50)  
, CostRate INT );  
GO  
  
/* Create a procedure to receive data for the table-valued parameter. */  
CREATE PROCEDURE dbo. usp_InsertProductionLocation  
    @TVP LocationTableType READONLY  
    AS   
    SET NOCOUNT ON  
    INSERT INTO AdventureWorks2012.Production.Location  
           (Name  
           ,CostRate  
           ,Availability  
           ,ModifiedDate)  
        SELECT *, 0, GETDATE()  
        FROM  @TVP;  
        GO  
  
/* Declare a variable that references the type. */  
DECLARE @LocationTVP AS LocationTableType;  
  
/* Add data to the table variable. */  
INSERT INTO @LocationTVP (LocationName, CostRate)  
    SELECT Name, 0.00  
    FROM AdventureWorks2012.Person.StateProvince;  
  
/* Pass the table variable data to a stored procedure. */  
EXEC usp_InsertProductionLocation @LocationTVP;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="deb3f-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="deb3f-146">See Also</span></span>  
 <span data-ttu-id="deb3f-147">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="deb3f-147">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) </span></span>  
 <span data-ttu-id="deb3f-148">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="deb3f-148">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="deb3f-149">[sys. types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="deb3f-149">[sys.types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-types-transact-sql) </span></span>  
 <span data-ttu-id="deb3f-150">[sys. Parameters &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameters-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="deb3f-150">[sys.parameters &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameters-transact-sql) </span></span>  
 <span data-ttu-id="deb3f-151">[sys. parameter_type_usages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameter-type-usages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="deb3f-151">[sys.parameter_type_usages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameter-type-usages-transact-sql) </span></span>  
 <span data-ttu-id="deb3f-152">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="deb3f-152">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 [<span data-ttu-id="deb3f-153">CREATE FUNCTION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="deb3f-153">CREATE FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-function-transact-sql)  
  
  
