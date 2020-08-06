---
title: Créer de déclencheurs DML pour gérer plusieurs lignes de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- multiple row DML triggers
- UPDATE statement [SQL Server], DML triggers
- DELETE statement [SQL Server], DML triggers
- multirow DML triggers [SQL Server]
- INSERT statement [SQL Server], DML triggers
- DML triggers, multirow
ms.assetid: d476c124-596b-4b27-a883-812b6b50a735
author: rothja
ms.author: jroth
ms.openlocfilehash: 11ea7aa457a5cdfcafd4a8c4e0ac170ae0e3b9c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613896"
---
# <a name="create-dml-triggers-to-handle-multiple-rows-of-data"></a><span data-ttu-id="3bdbe-102">Créer de déclencheurs DML pour gérer plusieurs lignes de données</span><span class="sxs-lookup"><span data-stu-id="3bdbe-102">Create DML Triggers to Handle Multiple Rows of Data</span></span>
  <span data-ttu-id="3bdbe-103">Lors de l'écriture du code d'un déclencheur DML, tenez compte du fait que l'instruction qui active le déclencheur peut être une instruction unique concernant plusieurs lignes de données au lieu d'une seule.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-103">When you write the code for a DML trigger, consider that the statement that causes the trigger to fire can be a single statement that affects multiple rows of data, instead of a single row.</span></span> <span data-ttu-id="3bdbe-104">Ce comportement est courant pour les déclencheurs UPDATE et DELETE qui concernent souvent plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-104">This behavior is common for UPDATE and DELETE triggers because these statements frequently affect multiple rows.</span></span> <span data-ttu-id="3bdbe-105">Il est moins fréquent dans le cas des déclencheurs INSERT car l'instruction INSERT de base n'ajoute qu'une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-105">The behavior is less common for INSERT triggers because the basic INSERT statement adds only a single row.</span></span> <span data-ttu-id="3bdbe-106">Toutefois, comme un déclencheur INSERT peut être activé par une instruction SELECT INSERT INTO (*nom_table*), l’insertion de nombreuses lignes peut aboutir à un appel de déclencheur unique.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-106">However, because an INSERT trigger can be fired by an INSERT INTO (*table_name*) SELECT statement, the insertion of many rows may cause a single trigger invocation.</span></span>  
  
 <span data-ttu-id="3bdbe-107">Les facteurs à prendre en compte au sujet des lignes multiples sont particulièrement importants lorsque la fonction d'un déclencheur DML consiste à recalculer automatiquement les totaux d'une table et à enregistrer les résultats dans une autre table en vue de subir d'autres calculs.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-107">Multirow considerations are especially important when the function of a DML trigger is to automatically recalculate summary values from one table and store the results in another for ongoing tallies.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3bdbe-108">Il n'est pas conseillé d'utiliser les curseurs dans le déclencheur, car ils pourraient réduire les performances.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-108">We do not recommend using cursors in triggers because they could potentially reduce performance.</span></span> <span data-ttu-id="3bdbe-109">Pour concevoir un déclencheur portant sur plusieurs lignes, utilisez au lieu des curseurs une logique basée sur un ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-109">To design a trigger that affects multiple rows, use rowset-based logic instead of cursors.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3bdbe-110">Exemples</span><span class="sxs-lookup"><span data-stu-id="3bdbe-110">Examples</span></span>  
 <span data-ttu-id="3bdbe-111">Les déclencheurs DML des exemples suivants sont conçus pour stocker le total cumulé d'une colonne dans une autre table de l'exemple de bases de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bdbe-111">The DML triggers in the following examples are designed to store a running total of a column in another table of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
### <a name="a-storing-a-running-total-for-a-single-row-insert"></a><span data-ttu-id="3bdbe-112">R.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-112">A.</span></span> <span data-ttu-id="3bdbe-113">Stockage d'un total cumulé pour l'insertion d'une seule ligne</span><span class="sxs-lookup"><span data-stu-id="3bdbe-113">Storing a running total for a single-row insert</span></span>  
 <span data-ttu-id="3bdbe-114">La première version du déclencheur DML fonctionne correctement pour l'insertion d'une seule ligne, lorsqu'une ligne de données est chargée dans la table `PurchaseOrderDetail` .</span><span class="sxs-lookup"><span data-stu-id="3bdbe-114">The first version of the DML trigger works well for a single-row insert when a row of data is loaded into the `PurchaseOrderDetail` table.</span></span> <span data-ttu-id="3bdbe-115">Le déclencheur DML est activé par une instruction INSERT et la nouvelle ligne est chargée dans la table **inserted** pendant la durée d’exécution du déclencheur.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-115">An INSERT statement fires the DML trigger, and the new row is loaded into the **inserted** table for the duration of the trigger execution.</span></span> <span data-ttu-id="3bdbe-116">L'instruction `UPDATE` lit la valeur de la colonne `LineTotal` correspondant à la ligne et l'ajoute à la valeur existante dans la colonne `SubTotal` de la table `PurchaseOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="3bdbe-116">The `UPDATE` statement reads the `LineTotal` column value for the row and adds that value to the existing value in the `SubTotal` column in the `PurchaseOrderHeader` table.</span></span> <span data-ttu-id="3bdbe-117">La clause `WHERE` garantit que la ligne mise à jour dans la table `PurchaseOrderDetail` correspond à la valeur `PurchaseOrderID` de la ligne dans la table **inserted** .</span><span class="sxs-lookup"><span data-stu-id="3bdbe-117">The `WHERE` clause makes sure that the updated row in the `PurchaseOrderDetail` table matches the `PurchaseOrderID` of the row in the **inserted** table.</span></span>  
  
```  
-- Trigger is valid for single-row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail  
ON Purchasing.PurchaseOrderDetail  
AFTER INSERT AS  
   UPDATE PurchaseOrderHeader  
   SET SubTotal = SubTotal + LineTotal  
   FROM inserted  
   WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID ;  
```  
  
### <a name="b-storing-a-running-total-for-a-multirow-or-single-row-insert"></a><span data-ttu-id="3bdbe-118">B.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-118">B.</span></span> <span data-ttu-id="3bdbe-119">Stockage d'un total cumulé pour l'insertion d'une ou de plusieurs lignes</span><span class="sxs-lookup"><span data-stu-id="3bdbe-119">Storing a running total for a multirow or single-row insert</span></span>  
 <span data-ttu-id="3bdbe-120">Dans le cas d’une insertion de plusieurs lignes, le déclencheur DML de l’exemple A peut ne pas fonctionner correctement ; l’expression à droite d’une expression d’affectation dans une instruction UPDATE (`SubTotal` + `LineTotal`) ne peut être qu’une unique valeur, et non une liste de valeurs.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-120">For a multirow insert, the DML trigger in example A might not operate correctly; the expression to the right of an assignment expression in an UPDATE statement (`SubTotal` + `LineTotal`) can be only a single value, not a list of values.</span></span> <span data-ttu-id="3bdbe-121">Ainsi, le déclencheur extrait une valeur à partir d’une seule ligne de la table **inserted** et l’ajoute à la valeur `SubTotal` existante de la table `PurchaseOrderHeader` correspondant à une valeur `PurchaseOrderID` spécifique.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-121">Therefore, the effect of the trigger is to retrieve a value from any single row in the **inserted** table and add that value to the existing `SubTotal` value in the `PurchaseOrderHeader` table for a specific `PurchaseOrderID` value.</span></span> <span data-ttu-id="3bdbe-122">Cette opération risque de ne pas produire l’effet escompté si une valeur unique `PurchaseOrderID` se trouve plus d’une fois dans la table **inserted** .</span><span class="sxs-lookup"><span data-stu-id="3bdbe-122">This operation might not have the expected effect if a single `PurchaseOrderID` value occurred more than one time in the **inserted** table.</span></span>  
  
 <span data-ttu-id="3bdbe-123">Pour mettre à jour correctement la table `PurchaseOrderHeader` , le déclencheur doit tenir compte de l’existence possible de plusieurs lignes dans la table **inserted** .</span><span class="sxs-lookup"><span data-stu-id="3bdbe-123">To correctly update the `PurchaseOrderHeader` table, the trigger must allow for the chance of multiple rows in the **inserted** table.</span></span> <span data-ttu-id="3bdbe-124">Pour ce faire, vous pouvez utiliser la fonction `SUM` , qui calcule le total `LineTotal` d’un groupe de lignes de la table **inserted** pour chaque `PurchaseOrderID`.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-124">You can do this by using the `SUM` function that calculates the total `LineTotal` for a group of rows in the **inserted** table for each `PurchaseOrderID`.</span></span> <span data-ttu-id="3bdbe-125">La fonction `SUM` est incluse dans une sous-requête corrélée (l'instruction `SELECT` entre parenthèses).</span><span class="sxs-lookup"><span data-stu-id="3bdbe-125">The `SUM` function is included in a correlated subquery (the `SELECT` statement in parentheses).</span></span> <span data-ttu-id="3bdbe-126">Cette sous-requête retourne une valeur unique pour chaque `PurchaseOrderID` de la table **inserted** qui correspond ou est corrélée à `PurchaseOrderID` dans la table `PurchaseOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="3bdbe-126">This subquery returns a single value for each `PurchaseOrderID` in the **inserted** table that matches or is correlated with a `PurchaseOrderID` in the `PurchaseOrderHeader` table.</span></span>  
  
```  
-- Trigger is valid for multirow and single-row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail2  
ON Purchasing.PurchaseOrderDetail  
AFTER INSERT AS  
   UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal +   
      (SELECT SUM(LineTotal)  
      FROM inserted  
      WHERE PurchaseOrderHeader.PurchaseOrderID  
       = inserted.PurchaseOrderID)  
   WHERE PurchaseOrderHeader.PurchaseOrderID IN  
      (SELECT PurchaseOrderID FROM inserted);  
```  
  
 <span data-ttu-id="3bdbe-127">Le fonctionnement de ce déclencheur est également correct dans le cas de l'insertion d'une seule ligne ; le total de la colonne `LineTotal` est alors la somme d'une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-127">This trigger also works correctly in a single-row insert; the sum of the `LineTotal` value column is the sum of a single row.</span></span> <span data-ttu-id="3bdbe-128">La sous-requête corrélée et l'opérateur `IN` utilisé dans la clause `WHERE` demandent toutefois un traitement complémentaire de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)],</span><span class="sxs-lookup"><span data-stu-id="3bdbe-128">However, with this trigger the correlated subquery and the `IN` operator that is used in the `WHERE` clause require additional processing from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3bdbe-129">ce qui n'est pas nécessaire pour l'insertion d'une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-129">This is unnecessary for a single-row insert.</span></span>  
  
### <a name="c-storing-a-running-total-based-on-the-type-of-insert"></a><span data-ttu-id="3bdbe-130">C.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-130">C.</span></span> <span data-ttu-id="3bdbe-131">Stockage d'un total cumulé basé sur le type d'insertion</span><span class="sxs-lookup"><span data-stu-id="3bdbe-131">Storing a running total based on the type of insert</span></span>  
 <span data-ttu-id="3bdbe-132">Pour rectifier ce problème, vous pouvez modifier le déclencheur afin d'utiliser la méthode optimale en fonction du nombre de lignes.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-132">You can change the trigger to use the method optimal for the number of rows.</span></span> <span data-ttu-id="3bdbe-133">Par exemple, la fonction `@@ROWCOUNT` peut être utilisée dans la logique du déclencheur pour différencier une insertion d'une seule ligne d'une insertion de plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="3bdbe-133">For example, the `@@ROWCOUNT` function can be used in the logic of the trigger to distinguish between a single and a multirow insert.</span></span>  
  
```  
-- Trigger valid for multirow and single row inserts  
-- and optimal for single row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail3  
ON Purchasing.PurchaseOrderDetail  
FOR INSERT AS  
IF @@ROWCOUNT = 1  
BEGIN  
   UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal + LineTotal  
   FROM inserted  
   WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID  
END  
ELSE  
BEGIN  
      UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal +   
      (SELECT SUM(LineTotal)  
      FROM inserted  
      WHERE PurchaseOrderHeader.PurchaseOrderID  
       = inserted.PurchaseOrderID)  
   WHERE PurchaseOrderHeader.PurchaseOrderID IN  
      (SELECT PurchaseOrderID FROM inserted)  
END;  
```  
  
## <a name="see-also"></a><span data-ttu-id="3bdbe-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3bdbe-134">See Also</span></span>  
 [<span data-ttu-id="3bdbe-135">Déclencheurs DML</span><span class="sxs-lookup"><span data-stu-id="3bdbe-135">DML Triggers</span></span>](dml-triggers.md)  
  
  
