---
title: Classements et pages de codes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c626dcac-0474-432d-acc0-cfa643345372
author: stevestein
ms.author: sstein
ms.openlocfilehash: ab904771fa8ac4acf25a624cbf3e1139f7e96434
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611317"
---
# <a name="collations-and-code-pages"></a><span data-ttu-id="7f8aa-102">Classements et pages de codes</span><span class="sxs-lookup"><span data-stu-id="7f8aa-102">Collations and Code Pages</span></span>
  [!INCLUDE[hek_2](../includes/hek-2-md.md)] <span data-ttu-id="7f8aa-103">est limité au niveau des pages de codes prises en charge pour les colonnes (var)char dans les tables mémoire optimisées et les classements pris en charge utilisés dans des index et des procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-103">has restrictions on supported code pages for (var)char columns in memory-optimized tables and supported collations used in indexes and natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="7f8aa-104">La page de codes d'une valeur (var)char détermine le mappage entre les caractères et la représentation en octets stockée dans la table.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-104">The code page for a (var)char value determines the mapping between characters and the byte representation that is stored in the table.</span></span> <span data-ttu-id="7f8aa-105">Par exemple, dans la page de codes Windows Latin 1 (1252 ; valeur par défaut de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ), le caractère « a » correspond à l'octet 0x61.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-105">For example, with the Windows Latin 1 code page (1252; the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] default), the character 'a' corresponds to the byte 0x61.</span></span>  
  
 <span data-ttu-id="7f8aa-106">La page de codes d'une valeur (var)char est déterminée par le classement associé à la valeur.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-106">The code page of a (var)char value is determined by the collation associated with the value.</span></span> <span data-ttu-id="7f8aa-107">Par exemple, le classement SQL_Latin1_General_CP1_CI_AS est associé à la page de codes 1252.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-107">For example, the collation SQL_Latin1_General_CP1_CI_AS has the associated code page 1252.</span></span>  
  
 <span data-ttu-id="7f8aa-108">Le classement d'une valeur est soit hérité du classement de la base de données, soit spécifié explicitement à l'aide du mot clé COLLATE.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-108">The collation of a value is either inherited from the database collation, or can be specified explicitly using the COLLATE keyword.</span></span> <span data-ttu-id="7f8aa-109">Le classement de la base de données ne peut pas être modifié si la base de données contient des tables mémoire optimisées ou des procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-109">Database collation cannot be changed if the database contains memory-optimized tables or natively compiled stored procedures.</span></span> <span data-ttu-id="7f8aa-110">L'exemple suivant définit le classement de la base de données et crée une table, qui comporte une colonne avec un classement différent.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-110">The following example sets the database collation and creates a table, which has a column with a different collation.</span></span> <span data-ttu-id="7f8aa-111">La base de données utilise un classement non sensible à la casse latine.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-111">The database uses Latin case-insensitive collation.</span></span>  
  
 <span data-ttu-id="7f8aa-112">Les index peuvent être créés sur des colonnes de chaîne s'ils utilisent un classement BIN2.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-112">Indexes can only be created on string columns if they use a BIN2 collation.</span></span> <span data-ttu-id="7f8aa-113">La variable LastName utilise le classement BIN2.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-113">The LastName variable uses BIN2 collation.</span></span> <span data-ttu-id="7f8aa-114">FirstName utilise la valeur par défaut de la base de données, qui est CI_AS (non sensible à la casse, respect des accents).</span><span class="sxs-lookup"><span data-stu-id="7f8aa-114">FirstName uses the database default, which is CI_AS (case-insensitive, accent-sensitive).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7f8aa-115">Vous ne pouvez pas utiliser « order by » ou « group by » sur les colonnes de chaîne d'index qui n'utilisent pas le classement BIN2.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-115">You cannot use order by or group by on index string columns that do not use BIN2 collation.</span></span>  
  
```sql  
CREATE DATABASE IMOLTP  
  
ALTER DATABASE IMOLTP ADD FILEGROUP IMOLTP_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE IMOLTP ADD FILE( NAME = 'IMOLTP_mod' , FILENAME = 'c:\data\IMOLTP_mod') TO FILEGROUP IMOLTP_mod;  
--GO  
  
--  set the database collations  
ALTER DATABASE IMOLTP COLLATE Latin1_General_100_CI_AS  
GO  
  
--  
USE IMOLTP   
GO  
  
-- create a table with collation  
CREATE TABLE Employees (  
  EmployeeID int NOT NULL ,   
  LastName nvarchar(20) COLLATE Latin1_General_100_BIN2 NOT NULL INDEX IX_LastName NONCLUSTERED,   
  FirstName nvarchar(10) NOT NULL ,  
  CONSTRAINT PK_Employees PRIMARY KEY NONCLUSTERED HASH(EmployeeID)  WITH (BUCKET_COUNT=1024)  
) WITH (MEMORY_OPTIMIZED=ON, DURABILITY=SCHEMA_AND_DATA)  
GO  
```  
  
 <span data-ttu-id="7f8aa-116">Les limitations suivantes s'appliquent aux tables mémoire optimisées et aux procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-116">The following restrictions apply to memory-optimized tables and natively compiled stored procedures:</span></span>  
  
-   <span data-ttu-id="7f8aa-117">Les colonnes (var)char dans les tables mémoire optimisées doivent utiliser le classement de la page de codes 1252.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-117">(var)char columns in memory-optimized tables must use code page 1252 collation.</span></span> <span data-ttu-id="7f8aa-118">Cette restriction ne concerne pas les colonnes n(var)char.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-118">This restriction does not apply to n(var)char columns.</span></span> <span data-ttu-id="7f8aa-119">Le code suivant récupère tous les classements 1252 :</span><span class="sxs-lookup"><span data-stu-id="7f8aa-119">The following code retrieves all 1252 collations:</span></span>  
  
    ```sql  
    -- all supported collations for (var)char columns in memory-optimized tables  
    select * from sys.fn_helpcollations()  
    where collationproperty(name, 'codepage') = 1252;  
    ```  
  
     <span data-ttu-id="7f8aa-120">Si vous devez stocker des caractères non-latins, utilisez les colonnes n(var)char.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-120">If you need to store non-Latin characters, use n(var)char columns.</span></span>  
  
-   <span data-ttu-id="7f8aa-121">Les index sur des colonnes (n)(var)char peuvent être spécifiés avec les classements BIN2 (voir le premier exemple).</span><span class="sxs-lookup"><span data-stu-id="7f8aa-121">Indexes on (n)(var)char columns can only be specified with BIN2 collations (see the first example).</span></span> <span data-ttu-id="7f8aa-122">La requête suivante récupère tous les classements BIN2 pris en charge :</span><span class="sxs-lookup"><span data-stu-id="7f8aa-122">The following query retrieves all supported BIN2 collations:</span></span>  
  
    ```sql  
    -- all supported collations for indexes on memory-optimized tables and   
    -- comparison/sorting in natively compiled stored procedures  
    select * from sys.fn_helpcollations() where name like '%BIN2'  
    ```  
  
     <span data-ttu-id="7f8aa-123">Si vous accédez à la table par le [!INCLUDE[tsql](../includes/tsql-md.md)] interprété, vous pouvez utiliser le mot clé `COLLATE` pour modifier le classement avec des expressions ou des opérations de tri.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-123">If you access the table through interpreted [!INCLUDE[tsql](../includes/tsql-md.md)], you can use the `COLLATE` keyword to change the collation with expressions or sort operations.</span></span> <span data-ttu-id="7f8aa-124">Consultez le dernier exemple pour obtenir un modèle.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-124">See the last example for a sample of this.</span></span>  
  
-   <span data-ttu-id="7f8aa-125">Les procédures stockées compilées en mode natif ne peuvent pas utiliser des paramètres, des variables locales ou des constantes de chaîne de type (var)char si le classement de la base de données n'est pas un classement de page de codes 1252.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-125">Natively compiled stored procedures cannot use parameters, local variables, or string constants of (var)char type if the database collation is not a code page 1252 collation.</span></span>  
  
-   <span data-ttu-id="7f8aa-126">Toutes les expressions et les opérations de tri à l'intérieur des procédures stockées compilées en mode natif doivent utiliser les classements BIN2.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-126">All expressions and sort operations inside natively compiled stored procedures must use BIN2 collations.</span></span> <span data-ttu-id="7f8aa-127">La conséquence est que toutes les comparaisons et les opérations de tri sont basées sur les points de code Unicode des caractères (représentations binaires).</span><span class="sxs-lookup"><span data-stu-id="7f8aa-127">The implication is that all comparisons and sort operations are based on the Unicode code points of the characters (binary representations).</span></span> <span data-ttu-id="7f8aa-128">Par exemple, tous les tris respectent la casse (« Z » vient avant « a »).</span><span class="sxs-lookup"><span data-stu-id="7f8aa-128">For example all sorting is case sensitive ('Z' comes before 'a').</span></span> <span data-ttu-id="7f8aa-129">Si nécessaire, utilisez le [!INCLUDE[tsql](../includes/tsql-md.md)] interprété pour le tri et la comparaison insensibles à la casse.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-129">If necessary, use interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] for case-insensitive sorting and comparison.</span></span>  
  
-   <span data-ttu-id="7f8aa-130">La troncation des données UTF-16 n'est pas prise en charge dans les procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-130">Truncation of UTF-16 data is not supported inside natively compiled stored procedures.</span></span> <span data-ttu-id="7f8aa-131">Cela signifie que les valeurs n (var) char (*n*) ne peuvent pas être converties en type n (var) char (*i*), si *i*  <  *n*, si le classement a _SC propriété.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-131">This means that n(var)char(*n*) values cannot be converted to type n(var)char(*i*), if *i* < *n*, if the collation has _SC property.</span></span> <span data-ttu-id="7f8aa-132">Par exemple, ce qui suit n'est pas pris en charge :</span><span class="sxs-lookup"><span data-stu-id="7f8aa-132">For example, the following is not supported:</span></span>  
  
    ```sql  
    -- column definition using an _SC collation  
     c2 nvarchar(200) collate Latin1_General_100_CS_AS_SC not null   
    -- assignment to a smaller variable, requiring truncation  
     declare @c2 nvarchar(100) = '';  
     select @c2 = c2  
    ```  
  
     <span data-ttu-id="7f8aa-133">Les fonctions de manipulation de chaîne comme LEN, SUBSTRING, LTRIM, et RTRIM avec des données UTF-16 ne sont pas prises en charge à l'intérieur des procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-133">String manipulation functions, such as LEN, SUBSTRING, LTRIM, and RTRIM with UTF-16 data are not supported inside natively compiled stored procedures.</span></span> <span data-ttu-id="7f8aa-134">Vous ne pouvez pas utiliser les fonctions de manipulation de chaîne pour les valeurs n(var)char qui ont un classement an _SC.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-134">You cannot use these string manipulation functions for n(var)char values that have an _SC collation.</span></span>  
  
     <span data-ttu-id="7f8aa-135">Déclarez les variables avec des types suffisamment grands pour éviter la troncation.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-135">Declare variables using types that are large enough to avoid truncation.</span></span>  
  
 <span data-ttu-id="7f8aa-136">L'exemple suivant indique quelques-unes des conséquences et les solutions de contournement concernant les limitations de classement dans OLTP en mémoire.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-136">The following example shows some of the implications and workarounds for the collation limitations in In-Memory OLTP.</span></span> <span data-ttu-id="7f8aa-137">L'exemple utilise la table Employees spécifiée ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-137">The example uses the Employees table specified above.</span></span> <span data-ttu-id="7f8aa-138">Cet exemple répertorie tous les employés.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-138">This sample list all employees .</span></span> <span data-ttu-id="7f8aa-139">Notez que pour LastName, en raison du classement binaire, les noms en majuscules sont triés en minuscules.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-139">Notice that for LastName, due to the binary collation, the upper case names are sorted before lower case.</span></span> <span data-ttu-id="7f8aa-140">Par conséquent, « Thomas » précède « nolan » car les caractères en majuscules ont des points de code inférieurs.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-140">Therefore, 'Thomas' comes before 'nolan' because upper case characters have lower code points.</span></span> <span data-ttu-id="7f8aa-141">FirstName a un classement non sensible à la casse.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-141">FirstName has a case-insensitive collation.</span></span> <span data-ttu-id="7f8aa-142">Par conséquent, il est préférable de trier par lettre de l'alphabet, et non par point de code des caractères.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-142">So, sorting is by letter of the alphabet, not code point of the characters.</span></span>  
  
```sql  
-- insert a number of values  
INSERT Employees VALUES (1,'thomas', 'john')  
INSERT Employees VALUES (2,'Thomas', 'rupert')  
INSERT Employees VALUES (3,'Thomas', 'Jack')  
INSERT Employees VALUES (4,'Thomas', 'annie')  
INSERT Employees VALUES (5,'nolan', 'John')  
GO  
  
-- ===========  
SELECT EmployeeID, LastName, FirstName FROM Employees  
ORDER BY LastName, FirstName  
GO  
  
-- ===========  
-- specify collation: sorting uses case-insensitive collation, thus 'nolan' comes before 'Thomas'  
SELECT * FROM Employees  
ORDER BY LastName COLLATE Latin1_General_100_CI_AS, FirstName  
GO  
  
-- ===========  
-- retrieve employee by Name  
-- must use BIN2 collation for comparison in natively compiled stored procedures  
CREATE PROCEDURE usp_EmployeeByName @LastName nvarchar(20), @FirstName nvarchar(10)  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH   
(  TRANSACTION ISOLATION LEVEL = SNAPSHOT,  
  LANGUAGE = N'us_english'  
)  
  SELECT EmployeeID, LastName, FirstName FROM dbo.Employees  
  WHERE   
    LastName = @LastName AND  
    FirstName COLLATE Latin1_General_100_BIN2 = @FirstName  
  
END  
GO  
  
-- this does not return any rows, as EmployeeID 1 has first name 'john', which is not equal to 'John' in a binary collation  
EXEC usp_EmployeeByName 'thomas', 'John'  
  
-- this retrieves EmployeeID 1  
EXEC usp_EmployeeByName 'thomas', 'john'  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f8aa-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7f8aa-143">See Also</span></span>  
 [<span data-ttu-id="7f8aa-144">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="7f8aa-144">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
