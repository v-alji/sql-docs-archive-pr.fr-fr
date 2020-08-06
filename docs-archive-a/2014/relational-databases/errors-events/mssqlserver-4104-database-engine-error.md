---
title: MSSQLSERVER_4104 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4104 (Database Engine error)
ms.assetid: 52dc32d8-97ad-4ef0-834d-2e68f215d007
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbbc28a3e15af6fdc8fd44633ccbdfc46e49149d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612386"
---
# <a name="mssqlserver_4104"></a><span data-ttu-id="4862f-102">MSSQLSERVER_4104</span><span class="sxs-lookup"><span data-stu-id="4862f-102">MSSQLSERVER_4104</span></span>
    
## <a name="details"></a><span data-ttu-id="4862f-103">Détails</span><span class="sxs-lookup"><span data-stu-id="4862f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4862f-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="4862f-104">Product Name</span></span>|<span data-ttu-id="4862f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4862f-105">SQL Server</span></span>|  
|<span data-ttu-id="4862f-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="4862f-106">Event ID</span></span>|<span data-ttu-id="4862f-107">4104</span><span class="sxs-lookup"><span data-stu-id="4862f-107">4104</span></span>|  
|<span data-ttu-id="4862f-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="4862f-108">Event Source</span></span>|<span data-ttu-id="4862f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4862f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4862f-110">Composant</span><span class="sxs-lookup"><span data-stu-id="4862f-110">Component</span></span>|<span data-ttu-id="4862f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4862f-111">SQLEngine</span></span>|  
|<span data-ttu-id="4862f-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="4862f-112">Symbolic Name</span></span>|<span data-ttu-id="4862f-113">ALG_MULTI_ID_BAD</span><span class="sxs-lookup"><span data-stu-id="4862f-113">ALG_MULTI_ID_BAD</span></span>|  
|<span data-ttu-id="4862f-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="4862f-114">Message Text</span></span>|<span data-ttu-id="4862f-115">L'identificateur en plusieurs parties "%.\*ls" ne peut pas être lié.</span><span class="sxs-lookup"><span data-stu-id="4862f-115">The multi-part identifier "%.\*ls" could not be bound.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4862f-116">Explication</span><span class="sxs-lookup"><span data-stu-id="4862f-116">Explanation</span></span>  
 <span data-ttu-id="4862f-117">Le nom d’une entité dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est appelé son *identificateur*.</span><span class="sxs-lookup"><span data-stu-id="4862f-117">The name of an entity in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is referred to as its *identifier*.</span></span> <span data-ttu-id="4862f-118">Vous utilisez des identificateurs chaque fois que vous référencez des entités, par exemple en spécifiant les noms des colonnes et des tables dans une requête.</span><span class="sxs-lookup"><span data-stu-id="4862f-118">You use identifiers whenever you reference entities, for example, by specifying column and table names in a query.</span></span> <span data-ttu-id="4862f-119">Un identificateur en plusieurs parties contient un ou plusieurs qualificateurs en tant que préfixe pour l'identificateur.</span><span class="sxs-lookup"><span data-stu-id="4862f-119">A multi-part identifier contains one or more qualifiers as a prefix for the identifier.</span></span> <span data-ttu-id="4862f-120">Par exemple, un identificateur de table peut avoir pour préfixe des qualificateurs tels que le nom de la base de données et le nom du schéma dans lesquels la table est contenue, ou un identificateur de colonne peut avoir pour préfixe des qualificateurs tels qu'un nom de table ou un alias de table.</span><span class="sxs-lookup"><span data-stu-id="4862f-120">For example, a table identifier may be prefixed with qualifiers such as the database name and schema name in which the table is contained, or a column identifier may be prefixed with qualifiers such as a table name or table alias.</span></span>  
  
 <span data-ttu-id="4862f-121">L'erreur 4104 indique que l'identificateur en plusieurs parties spécifié n'a pas pu être mappé à une entité existante.</span><span class="sxs-lookup"><span data-stu-id="4862f-121">Error 4104 indicates that the specified multi-part identifier could not be mapped to an existing entity.</span></span> <span data-ttu-id="4862f-122">Cette erreur peut être retournée dans les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="4862f-122">This error can be returned under the following conditions:</span></span>  
  
-   <span data-ttu-id="4862f-123">Le qualificateur fourni en tant que préfixe pour un nom de colonne ne correspond à aucun nom de table ou d'alias utilisé dans la requête.</span><span class="sxs-lookup"><span data-stu-id="4862f-123">The qualifier supplied as a prefix for a column name does not correspond to any table or alias name used in the query.</span></span>  
  
     <span data-ttu-id="4862f-124">Par exemple, l'instruction suivante utilise un alias de table (`Dept`) en tant que préfixe de colonne, mais l'alias de table n'est pas référencé dans la clause FROM.</span><span class="sxs-lookup"><span data-stu-id="4862f-124">For example, the following statement uses a table alias (`Dept`) as a column prefix, but the table alias is not referenced in the FROM clause.</span></span>  
  
    ```  
    SELECT Dept.Name FROM HumanResources.Department;  
    ```  
  
     <span data-ttu-id="4862f-125">Dans les instructions suivantes, un identificateur de colonne en plusieurs parties `TableB.KeyCol` est spécifié dans la clause WHERE dans le cadre d'une condition JOIN entre deux tables ; toutefois, `TableB` n'est pas référencé explicitement dans la requête.</span><span class="sxs-lookup"><span data-stu-id="4862f-125">In the following statements, a multi-part column identifier `TableB.KeyCol` is specified in the WHERE clause as part of a JOIN condition between two tables, however, `TableB` is not explicitly referenced in the query.</span></span>  
  
    ```  
    DELETE FROM TableA WHERE TableA.KeyCol = TableB.KeyCol;  
    ```  
  
    ```  
    SELECT 'X' FROM TableA WHERE TableB.KeyCol = TableA.KeyCol;  
    ```  
  
-   <span data-ttu-id="4862f-126">Un nom d'alias est spécifié pour la table dans la clause FROM, mais le qualificateur fourni pour une colonne correspond au nom de la table.</span><span class="sxs-lookup"><span data-stu-id="4862f-126">An alias name for the table is supplied in the FROM clause, but the qualifier supplied for a column is the table name.</span></span> <span data-ttu-id="4862f-127">Par exemple, l'instruction suivante utilise le nom de table `Department` en tant que préfixe de colonne ; toutefois, la table a un alias (`Dept`) référencé dans la clause FROM.</span><span class="sxs-lookup"><span data-stu-id="4862f-127">For example, the following statement uses the table name `Department` as the column prefix; however, the table has an alias (`Dept`) referenced in the FROM clause.</span></span>  
  
    ```  
    SELECT Department.Name FROM HumanResources.Department AS Dept;  
    ```  
  
     <span data-ttu-id="4862f-128">Lorsqu'un alias est utilisé, le nom de table ne peut pas être utilisé ailleurs dans l'instruction.</span><span class="sxs-lookup"><span data-stu-id="4862f-128">When an alias is used, the table name cannot be used elsewhere in the statement.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4862f-129">ne peut pas déterminer si l'identificateur en plusieurs parties fait référence à une colonne préfixée par une table ou à un type de données défini par l'utilisateur (UDT) CLR préfixé par une colonne.</span><span class="sxs-lookup"><span data-stu-id="4862f-129">is unable to determine if the multi-part identifier refers to a column prefixed by a table or to a property of a CLR user-defined data type (UDT) prefixed by a column.</span></span> <span data-ttu-id="4862f-130">Cette situation se présente, car les propriétés des colonnes UDT sont référencées à l'aide du point de séparation (.), placé entre le nom de la colonne et le nom de la propriété, de la même manière qu'un nom de colonne est préfixé à l'aide d'un nom de table.</span><span class="sxs-lookup"><span data-stu-id="4862f-130">This happens because properties of UDT columns are referenced by using the period separator (.) between the column name and the property name in the same way that a column name is prefixed with a table name.</span></span> <span data-ttu-id="4862f-131">L’exemple suivant crée deux tables, `a` et `b`.</span><span class="sxs-lookup"><span data-stu-id="4862f-131">The following example creates two tables, `a` and `b`.</span></span> <span data-ttu-id="4862f-132">La table `b` contient la colonne `a`, qui utilise un UDT CLR `dbo.myudt2` en tant que type de données.</span><span class="sxs-lookup"><span data-stu-id="4862f-132">Table `b` contains column `a`, which uses a CLR UDT `dbo.myudt2` as its data type.</span></span> <span data-ttu-id="4862f-133">L'instruction SELECT contient un identificateur en plusieurs parties `a.c2`.</span><span class="sxs-lookup"><span data-stu-id="4862f-133">The SELECT statement contains a multi-part identifier `a.c2`.</span></span>  
  
    ```  
    CREATE TABLE a (c2 int);   
    GO  
    ```  
  
    ```  
    CREATE TABLE b (a dbo.myudt2);   
    GO  
    ```  
  
    ```  
    SELECT a.c2 FROM a, b;   
    ```  
  
     <span data-ttu-id="4862f-134">En supposant que l’UDT `myudt2`ne dispose pas d’une propriété nommée `c2`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas déterminer si l’identificateur `a.c2` fait référence à la colonne `c2` dans la table `a` ou à la colonne `b`, propriété `a` dans la table `c2`.</span><span class="sxs-lookup"><span data-stu-id="4862f-134">Assuming that the UDT `myudt2` does not have a property named `c2`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot determine whether identifier `a.c2`refers to column `c2` in table `a` or to the column `a`, property `c2` in table `b`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4862f-135">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="4862f-135">User Action</span></span>  
  
-   <span data-ttu-id="4862f-136">Faites correspondre les préfixes de colonnes aux noms de tables ou d'alias spécifiés dans la clause FROM de la requête.</span><span class="sxs-lookup"><span data-stu-id="4862f-136">Match the column prefixes against the table names or alias names specified in the FROM clause of the query.</span></span> <span data-ttu-id="4862f-137">Si un alias est défini pour un nom de table dans la clause FROM, seul cet alias peut être utilisé en tant que qualificateur pour les colonnes associées à cette table.</span><span class="sxs-lookup"><span data-stu-id="4862f-137">If an alias is defined for a table name in the FROM clause, you can only use the alias as a qualifier for columns associated with that table.</span></span>  
  
     <span data-ttu-id="4862f-138">Les instructions ci-dessus qui référencent la table `HumanResources.Department` peuvent être corrigées comme suit :</span><span class="sxs-lookup"><span data-stu-id="4862f-138">The statements above that reference the `HumanResources.Department` table can be corrected as follows:</span></span>  
  
    ```  
    SELECT Dept.Name FROM HumanResources.Department AS Dept;  
    GO  
    ```  
  
    ```  
    SELECT Department.Name FROM HumanResources.Department;  
    GO  
    ```  
  
-   <span data-ttu-id="4862f-139">Vérifiez que toutes les tables sont spécifiées dans la requête et que les conditions JOIN entre les tables sont spécifiées correctement.</span><span class="sxs-lookup"><span data-stu-id="4862f-139">Ensure that all tables are specified in the query and that the JOIN conditions between tables are specified correctly.</span></span> <span data-ttu-id="4862f-140">L'instruction DELETE ci-dessus peut être corrigée comme suit :</span><span class="sxs-lookup"><span data-stu-id="4862f-140">The DELETE statement above can be corrected as follows:</span></span>  
  
    ```  
    DELETE FROM dbo.TableA  
    WHERE TableA.KeyCol = (SELECT TableB.KeyCol   
                            FROM TableB   
                            WHERE TableA.KeyCol = TableB.KeyCol);  
    GO  
    ```  
  
     <span data-ttu-id="4862f-141">L'instruction SELECT ci-dessus pour `TableA` peut être corrigée comme suit :</span><span class="sxs-lookup"><span data-stu-id="4862f-141">The SELECT statement above for `TableA` can be corrected as follows:</span></span>  
  
    ```  
    SELECT 'X' FROM TableA, TableB WHERE TableB.KeyCol = TableA.KeyCol;  
    ```  
  
     <span data-ttu-id="4862f-142">or</span><span class="sxs-lookup"><span data-stu-id="4862f-142">or</span></span>  
  
    ```  
    SELECT 'X' FROM TableA INNER JOIN TableB ON TableB.KeyCol = TableA.KeyCol;  
    ```  
  
-   <span data-ttu-id="4862f-143">Utilisez des noms uniques et clairement définis pour les identificateurs.</span><span class="sxs-lookup"><span data-stu-id="4862f-143">Use unique, clearly defined names for identifiers.</span></span> <span data-ttu-id="4862f-144">Vous facilitez ainsi la lecture et la gestion de votre code et vous réduisez également le risque de références ambiguës à plusieurs entités.</span><span class="sxs-lookup"><span data-stu-id="4862f-144">Doing so makes your code easier to read and maintain, and it also minimizes the risk of ambiguous references to multiple entities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4862f-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4862f-145">See Also</span></span>  
 <span data-ttu-id="4862f-146">[MSSQLSERVER_107](mssqlserver-107-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="4862f-146">[MSSQLSERVER_107](mssqlserver-107-database-engine-error.md) </span></span>  
 [<span data-ttu-id="4862f-147">Identificateurs de base de données</span><span class="sxs-lookup"><span data-stu-id="4862f-147">Database Identifiers</span></span>](../databases/database-identifiers.md)  
  
  
