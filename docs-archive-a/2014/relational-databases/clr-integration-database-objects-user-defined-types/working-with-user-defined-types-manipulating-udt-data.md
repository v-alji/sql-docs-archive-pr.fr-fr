---
title: Manipulation de données UDT | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- CAST function
- data deletions [CLR integration]
- data insertions [CLR integration]
- CONVERT function
- data updates [CLR integration]
- comparing data
- updating data [CLR integration]
- removing data
- IsByteOrdered property
- variables [CLR integration]
- data manipulation [CLR integration]
- user-defined types [CLR integration], data manipulation
- deleting data
- UDTs [CLR integration], data manipulation
- invoking UDT methods
- inserting data
ms.assetid: 51b1a5f2-7591-4e11-bfe2-d88e0836403f
author: rothja
ms.author: jroth
ms.openlocfilehash: 75810a2ffd92130e45025f742d43ba7917d73992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698309"
---
# <a name="manipulating-udt-data"></a><span data-ttu-id="48eb3-102">Manipulation de données UDT</span><span class="sxs-lookup"><span data-stu-id="48eb3-102">Manipulating UDT Data</span></span>
  [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="48eb3-103">ne fournit aucune syntaxe spécialisée pour les instructions INSERT, UPDATE ou DELETE lors de la modification de données dans des colonnes de type défini par l'utilisateur (UDT).</span><span class="sxs-lookup"><span data-stu-id="48eb3-103">provides no specialized syntax for INSERT, UPDATE, or DELETE statements when modifying data in user-defined type (UDT) columns.</span></span> <span data-ttu-id="48eb3-104">Les fonctions [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST ou CONVERT sont utilisées pour convertir des types de données natives en type UDT.</span><span class="sxs-lookup"><span data-stu-id="48eb3-104">The [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST or CONVERT functions are used to cast native data types to the UDT type.</span></span>  
  
## <a name="inserting-data-in-a-udt-column"></a><span data-ttu-id="48eb3-105">Insertion de données dans une colonne UDT</span><span class="sxs-lookup"><span data-stu-id="48eb3-105">Inserting Data in a UDT Column</span></span>  
 <span data-ttu-id="48eb3-106">Les [!INCLUDE[tsql](../../includes/tsql-md.md)] instructions suivantes insèrent trois lignes d’exemples de données dans la table **points** .</span><span class="sxs-lookup"><span data-stu-id="48eb3-106">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements insert three rows of sample data into the **Points** table.</span></span> <span data-ttu-id="48eb3-107">Le type de données **point** est constitué de valeurs entières X et Y qui sont exposées en tant que propriétés de l’UDT.</span><span class="sxs-lookup"><span data-stu-id="48eb3-107">The **Point** data type consists of X and Y integer values that are exposed as properties of the UDT.</span></span> <span data-ttu-id="48eb3-108">Vous devez utiliser la fonction CAST ou CONVERT pour effectuer un cast des valeurs X et Y délimitées par des virgules en type **point** .</span><span class="sxs-lookup"><span data-stu-id="48eb3-108">You must use either the CAST or CONVERT function to cast the comma-delimited X and Y values to the **Point** type.</span></span> <span data-ttu-id="48eb3-109">Les deux premières instructions utilisent la fonction CONVERT pour convertir une valeur de chaîne en type **point** , et la troisième instruction utilise la fonction CAST :</span><span class="sxs-lookup"><span data-stu-id="48eb3-109">The first two statements use the CONVERT function to convert a string value to the **Point** type, and the third statement uses the CAST function:</span></span>  
  
```  
INSERT INTO dbo.Points (PointValue) VALUES (CONVERT(Point, '3,4'));  
INSERT INTO dbo.Points (PointValue) VALUES (CONVERT(Point, '1,5'));  
INSERT INTO dbo.Points (PointValue) VALUES (CAST ('1,99' AS Point));  
```  
  
## <a name="selecting-data"></a><span data-ttu-id="48eb3-110">Sélection de données</span><span class="sxs-lookup"><span data-stu-id="48eb3-110">Selecting Data</span></span>  
 <span data-ttu-id="48eb3-111">L'instruction SELECT suivante sélectionne la valeur binaire du type UDT.</span><span class="sxs-lookup"><span data-stu-id="48eb3-111">The following SELECT statement selects the binary value of the UDT.</span></span>  
  
```  
SELECT ID, PointValue FROM dbo.Points  
```  
  
 <span data-ttu-id="48eb3-112">Pour afficher la sortie affichée dans un format lisible, appelez la `ToString` méthode de l’UDT **point** , qui convertit la valeur en sa représentation sous forme de chaîne.</span><span class="sxs-lookup"><span data-stu-id="48eb3-112">To see the output displayed in a readable format, call the `ToString` method of the **Point** UDT, which converts the value to its string representation.</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS PointValue   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="48eb3-113">Ce code produit les résultats suivants.</span><span class="sxs-lookup"><span data-stu-id="48eb3-113">This produces the following results.</span></span>  
  
```  
IDPointValue  
----------  
13,4  
21,5  
31,99  
```  
  
 <span data-ttu-id="48eb3-114">Vous pouvez également utiliser les fonctions [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST et CONVERT pour obtenir les mêmes résultats.</span><span class="sxs-lookup"><span data-stu-id="48eb3-114">You can also use the [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST and CONVERT functions to achieve the same results.</span></span>  
  
```  
SELECT ID, CAST(PointValue AS varchar)   
FROM dbo.Points;  
  
SELECT ID, CONVERT(varchar, PointValue)   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="48eb3-115">L’UDT **point** expose ses coordonnées X et Y en tant que propriétés, que vous pouvez ensuite sélectionner individuellement.</span><span class="sxs-lookup"><span data-stu-id="48eb3-115">The **Point** UDT exposes its X and Y coordinates as properties, which you can then select individually.</span></span> <span data-ttu-id="48eb3-116">L'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante sélectionne les coordonnées X et Y séparément :</span><span class="sxs-lookup"><span data-stu-id="48eb3-116">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement selects the X and Y coordinates separately:</span></span>  
  
```  
SELECT ID, PointValue.X AS xVal, PointValue.Y AS yVal   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="48eb3-117">Les propriétés X et Y retournent une valeur entière qui est affichée dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="48eb3-117">The X and Y properties return an integer value, which is displayed in the result set.</span></span>  
  
```  
IDxValyVal  
----------  
134  
215  
3199  
```  
  
## <a name="working-with-variables"></a><span data-ttu-id="48eb3-118">Utilisation de variables</span><span class="sxs-lookup"><span data-stu-id="48eb3-118">Working with Variables</span></span>  
 <span data-ttu-id="48eb3-119">Vous pouvez utiliser des variables à l'aide de l'instruction DECLARE pour attribuer une variable à un type UDT.</span><span class="sxs-lookup"><span data-stu-id="48eb3-119">You can work with variables using the DECLARE statement to assign a variable to a UDT type.</span></span> <span data-ttu-id="48eb3-120">Les instructions suivantes attribuent une valeur à l'aide de l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] SET et affichent les résultats en appelant la méthode `ToString` du type UDT sur la variable :</span><span class="sxs-lookup"><span data-stu-id="48eb3-120">The following statements assign a value using the [!INCLUDE[tsql](../../includes/tsql-md.md)] SET statement and display the results by calling the UDT's `ToString` method on the variable:</span></span>  
  
```  
DECLARE @PointValue Point;  
SET @PointValue = (SELECT PointValue FROM dbo.Points  
    WHERE ID = 2);  
SELECT @PointValue.ToString() AS PointValue;  
```  
  
 <span data-ttu-id="48eb3-121">Le jeu de résultats affiche la valeur de la variable :</span><span class="sxs-lookup"><span data-stu-id="48eb3-121">The result set displays the variable value:</span></span>  
  
```  
PointValue  
----------  
-1,5  
```  
  
 <span data-ttu-id="48eb3-122">Les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes génèrent le même résultat en remplaçant SET par SELECT pour l'attribution de la variable :</span><span class="sxs-lookup"><span data-stu-id="48eb3-122">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements achieve the same result using SELECT rather than SET for the variable assignment:</span></span>  
  
```  
DECLARE @PointValue Point;  
SELECT @PointValue = PointValue FROM dbo.Points  
    WHERE ID = 2;  
SELECT @PointValue.ToString() AS PointValue;  
```  
  
 <span data-ttu-id="48eb3-123">La différence entre SELECT et SET pour l'attribution de la variable réside dans le fait que SELECT vous permet d'attribuer plusieurs variables dans une instruction SELECT, tandis que la syntaxe SET nécessite que chaque attribution de variable possède sa propre instruction SET.</span><span class="sxs-lookup"><span data-stu-id="48eb3-123">The difference between using SELECT and SET for variable assignment is that SELECT allows you to assign multiple variables in one SELECT statement, whereas the SET syntax requires each variable assignment to have its own SET statement.</span></span>  
  
## <a name="comparing-data"></a><span data-ttu-id="48eb3-124">Comparaison de données</span><span class="sxs-lookup"><span data-stu-id="48eb3-124">Comparing Data</span></span>  
 <span data-ttu-id="48eb3-125">Vous pouvez utiliser des opérateurs de comparaison pour comparer des valeurs dans votre type UDT si vous avez attribuez à la propriété `IsByteOrdered` la valeur `true` lors de la définition de la classe.</span><span class="sxs-lookup"><span data-stu-id="48eb3-125">You can use comparison operators to compare values in your UDT if you have set the `IsByteOrdered` property to `true` when defining the class.</span></span> <span data-ttu-id="48eb3-126">Pour plus d’informations, consultez [création d’un type défini par l’utilisateur](creating-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="48eb3-126">For more information, see [Creating a User-Defined Type](creating-user-defined-types.md).</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS Points   
FROM dbo.Points  
WHERE PointValue > CONVERT(Point, '2,2');  
```  
  
 <span data-ttu-id="48eb3-127">Vous pouvez comparer les valeurs internes du type UDT indépendamment du paramètre `IsByteOrdered` si les valeurs elles-mêmes sont comparables.</span><span class="sxs-lookup"><span data-stu-id="48eb3-127">You can compare internal values of the UDT regardless of the `IsByteOrdered` setting if the values themselves are comparable.</span></span> <span data-ttu-id="48eb3-128">L'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante sélectionne des lignes où X est supérieur à Y :</span><span class="sxs-lookup"><span data-stu-id="48eb3-128">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement selects rows where X is greater than Y:</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS PointValue   
FROM dbo.Points  
WHERE PointValue.X < PointValue.Y;  
```  
  
 <span data-ttu-id="48eb3-129">Vous pouvez également utiliser des opérateurs de comparaison avec des variables, comme indiqué dans cette requête que recherche un PointValue correspondant.</span><span class="sxs-lookup"><span data-stu-id="48eb3-129">You can also use comparison operators with variables, as shown in this query that searches for a matching PointValue.</span></span>  
  
```  
DECLARE @ComparePoint Point;  
SET @ComparePoint = CONVERT(Point, '3,4');  
SELECT ID, PointValue.ToString() AS MatchingPoint   
FROM dbo.Points  
WHERE PointValue = @ComparePoint;  
```  
  
## <a name="invoking-udt-methods"></a><span data-ttu-id="48eb3-130">Appel de méthodes UDT</span><span class="sxs-lookup"><span data-stu-id="48eb3-130">Invoking UDT Methods</span></span>  
 <span data-ttu-id="48eb3-131">Vous pouvez également appeler des méthodes qui sont définies dans votre type UDT dans [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48eb3-131">You can also invoke methods that are defined in your UDT in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="48eb3-132">La classe **point** contient trois méthodes, `Distance` , `DistanceFrom` et `DistanceFromXY` .</span><span class="sxs-lookup"><span data-stu-id="48eb3-132">The **Point** class contains three methods, `Distance`, `DistanceFrom`, and `DistanceFromXY`.</span></span> <span data-ttu-id="48eb3-133">Pour obtenir les listes de code qui définissent ces trois méthodes, consultez [codage de types définis par l’utilisateur](creating-user-defined-types-coding.md).</span><span class="sxs-lookup"><span data-stu-id="48eb3-133">For the code listings defining these three methods, see [Coding User-Defined Types](creating-user-defined-types-coding.md).</span></span>  
  
 <span data-ttu-id="48eb3-134">L'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante appelle la méthode `PointValue.Distance` :</span><span class="sxs-lookup"><span data-stu-id="48eb3-134">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement calls the `PointValue.Distance` method:</span></span>  
  
```  
SELECT ID, PointValue.X AS [Point.X],   
    PointValue.Y AS [Point.Y],  
    PointValue.Distance() AS DistanceFromZero   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="48eb3-135">Les résultats sont affichés dans la `Distance` colonne :</span><span class="sxs-lookup"><span data-stu-id="48eb3-135">The results are displayed in the `Distance` column:</span></span>  
  
```  
IDXYDistance  
------------------------  
1345  
2155.09901951359278  
319999.0050503762308  
```  
  
 <span data-ttu-id="48eb3-136">La `DistanceFrom` méthode prend un argument de type de données **point** et affiche la distance entre le point spécifié et PointValue :</span><span class="sxs-lookup"><span data-stu-id="48eb3-136">The `DistanceFrom` method takes an argument of **Point** data type, and displays the distance from the specified point to the PointValue:</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS Pnt,  
   PointValue.DistanceFrom(CONVERT(Point, '1,99')) AS DistanceFromPoint  
FROM dbo.Points;  
```  
  
 <span data-ttu-id="48eb3-137">Les résultats affichent les résultats de la méthode `DistanceFrom` pour chaque ligne dans la table :</span><span class="sxs-lookup"><span data-stu-id="48eb3-137">The results display the results of the `DistanceFrom` method for each row in the table:</span></span>  
  
```  
ID PntDistanceFromPoint  
---------------------  
13,495.0210502993942  
21,594  
31,990  
```  
  
 <span data-ttu-id="48eb3-138">La méthode `DistanceFromXY` accepte individuellement les points en tant qu'arguments :</span><span class="sxs-lookup"><span data-stu-id="48eb3-138">The `DistanceFromXY` method takes the points individually as arguments:</span></span>  
  
```  
SELECT ID, PointValue.X as X, PointValue.Y as Y,   
PointValue.DistanceFromXY(1, 99) AS DistanceFromXY   
FROM dbo.Points  
```  
  
 <span data-ttu-id="48eb3-139">Le jeu de résultats est le même que la méthode `DistanceFrom`.</span><span class="sxs-lookup"><span data-stu-id="48eb3-139">The result set is the same as the `DistanceFrom` method.</span></span>  
  
## <a name="updating-data-in-a-udt-column"></a><span data-ttu-id="48eb3-140">Mise à jour de données dans une colonne UDT</span><span class="sxs-lookup"><span data-stu-id="48eb3-140">Updating Data in a UDT Column</span></span>  
 <span data-ttu-id="48eb3-141">Pour mettre à jour des données dans une colonne UDT, utilisez l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE.</span><span class="sxs-lookup"><span data-stu-id="48eb3-141">To update data in a UDT column, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE statement.</span></span> <span data-ttu-id="48eb3-142">Vous pouvez également utiliser une méthode du type UDT pour mettre à jour l'état de l'objet.</span><span class="sxs-lookup"><span data-stu-id="48eb3-142">You can also use a method of the UDT to update the state of the object.</span></span> <span data-ttu-id="48eb3-143">L'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante met à jour une ligne unique dans la table :</span><span class="sxs-lookup"><span data-stu-id="48eb3-143">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement updates a single row in the table:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = CAST('1,88' AS Point)  
WHERE ID = 3  
```  
  
 <span data-ttu-id="48eb3-144">Vous pouvez également mettre à jour des éléments UDT séparément.</span><span class="sxs-lookup"><span data-stu-id="48eb3-144">You can also update UDT elements separately.</span></span> <span data-ttu-id="48eb3-145">L'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante met à jour uniquement la coordonnée Y :</span><span class="sxs-lookup"><span data-stu-id="48eb3-145">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement updates only the Y coordinate:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.Y = 99  
WHERE ID = 3  
```  
  
 <span data-ttu-id="48eb3-146">Si l'ordre d'octet du type UDT a la valeur `true`, [!INCLUDE[tsql](../../includes/tsql-md.md)] peut évaluer la colonne UDT dans une clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="48eb3-146">If the UDT has been defined with byte ordering set to `true`, [!INCLUDE[tsql](../../includes/tsql-md.md)] can evaluate the UDT column in a WHERE clause.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = '4,5'  
WHERE PointValue = '3,4';  
```  
  
### <a name="updating-limitations"></a><span data-ttu-id="48eb3-147">Mise à jour de limitations</span><span class="sxs-lookup"><span data-stu-id="48eb3-147">Updating Limitations</span></span>  
 <span data-ttu-id="48eb3-148">Vous ne pouvez pas mettre à jour plusieurs propriétés à la fois à l'aide de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48eb3-148">You cannot update multiple properties at once using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="48eb3-149">Par exemple, l'instruction UPDATE suivante échoue avec une erreur parce que vous ne pouvez pas utiliser le même nom de colonne à deux reprises dans une instruction UDATE.</span><span class="sxs-lookup"><span data-stu-id="48eb3-149">For example, the following UPDATE statement fails with an error because you cannot use the same column name twice in one UDATE statement.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.X = 5, PointValue.Y = 99  
WHERE ID = 3  
```  
  
 <span data-ttu-id="48eb3-150">Pour mettre à jour chaque point individuellement, vous devez créer une méthode mutateur dans l'assembly UDT Point.</span><span class="sxs-lookup"><span data-stu-id="48eb3-150">To update each point individually, you would need to create a mutator method in the Point UDT assembly.</span></span> <span data-ttu-id="48eb3-151">Vous pouvez ensuite appeler la méthode mutateur pour mettre à jour l'objet dans une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE, comme suit :</span><span class="sxs-lookup"><span data-stu-id="48eb3-151">You can then invoke the mutator method to update the object in a [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE statement, as in the following:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.SetXY(5, 99)  
WHERE ID = 3  
```  
  
## <a name="deleting-data-in-a-udt-column"></a><span data-ttu-id="48eb3-152">Suppression de données dans une colonne UDT</span><span class="sxs-lookup"><span data-stu-id="48eb3-152">Deleting Data in a UDT Column</span></span>  
 <span data-ttu-id="48eb3-153">Pour supprimer des données dans un type UDT, utilisez l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE.</span><span class="sxs-lookup"><span data-stu-id="48eb3-153">To delete data in a UDT, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE statement.</span></span> <span data-ttu-id="48eb3-154">L'instruction suivante supprime toutes les lignes dans la table qui correspondent aux critères spécifiés dans la clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="48eb3-154">The following statement deletes all rows in the table that match the criteria specified in the WHERE clause.</span></span> <span data-ttu-id="48eb3-155">Si vous omettez la clause WHERE dans une instruction DELETE, toutes les lignes dans la table seront supprimées.</span><span class="sxs-lookup"><span data-stu-id="48eb3-155">If you omit the WHERE clause in a DELETE statement, all rows in the table will be deleted.</span></span>  
  
```  
DELETE FROM dbo.Points  
WHERE PointValue = CAST('1,99' AS Point)  
```  
  
 <span data-ttu-id="48eb3-156">Utilisez l'instruction UPDATE si vous souhaitez supprimer les valeurs dans une colonne UDT tout en laissant d'autres valeurs de lignes intactes.</span><span class="sxs-lookup"><span data-stu-id="48eb3-156">Use the UPDATE statement if you want to remove the values in a UDT column while leaving other row values intact.</span></span> <span data-ttu-id="48eb3-157">Cet exemple attribut la valeur null à PointValue.</span><span class="sxs-lookup"><span data-stu-id="48eb3-157">This example sets the PointValue to null.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = null  
WHERE ID = 2  
```  
  
## <a name="see-also"></a><span data-ttu-id="48eb3-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="48eb3-158">See Also</span></span>  
 [<span data-ttu-id="48eb3-159">Utilisation de types définis par l’utilisateur dans SQL Server</span><span class="sxs-lookup"><span data-stu-id="48eb3-159">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
  
  
