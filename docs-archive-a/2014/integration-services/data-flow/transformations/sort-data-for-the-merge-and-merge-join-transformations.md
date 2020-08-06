---
title: Trier des données pour les transformations de fusion et de jointure de fusion | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- sort attributes [Integration Services]
- output columns [Integration Services]
ms.assetid: 22ce3f5d-8a88-4423-92c2-60a8f82cd4fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7bb4e91ad84c6baa52e1d7fb4b0104d835b7e4cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695859"
---
# <a name="sort-data-for-the-merge-and-merge-join-transformations"></a><span data-ttu-id="8bf57-102">Trier des données pour les transformations de fusion et de jointure de fusion</span><span class="sxs-lookup"><span data-stu-id="8bf57-102">Sort Data for the Merge and Merge Join Transformations</span></span>
  <span data-ttu-id="8bf57-103">Dans [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], les transformations de fusion et de jointure de fusion nécessitent des données triées pour leurs entrées.</span><span class="sxs-lookup"><span data-stu-id="8bf57-103">In [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], the Merge and Merge Join transformations require sorted data for their inputs.</span></span> <span data-ttu-id="8bf57-104">Les données d'entrée doivent être triés physiquement et les options de tri doivent être définies sur les sorties et les colonnes de sortie dans la source ou dans la transformation amont.</span><span class="sxs-lookup"><span data-stu-id="8bf57-104">The input data must be sorted physically, and sort options must be set on the outputs and the output columns in the source or in the upstream transformation.</span></span> <span data-ttu-id="8bf57-105">Si les options de tri indiquent que les données sont triées alors qu'elles ne le sont pas en réalité, les résultats de l'opération de fusion ou de jointure de fusion sont imprévisibles.</span><span class="sxs-lookup"><span data-stu-id="8bf57-105">If the sort options indicate that the data is sorted, but the data is not actually sorted, the results of the merge or merge join operation are unpredictable.</span></span>  
  
## <a name="sorting-the-data"></a><span data-ttu-id="8bf57-106">Tri des données</span><span class="sxs-lookup"><span data-stu-id="8bf57-106">Sorting the Data</span></span>  
 <span data-ttu-id="8bf57-107">Pour trier ces données, procédez selon l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="8bf57-107">You can sort this data by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="8bf57-108">Dans la source, utilisez une clause ORDER BY dans l'instruction utilisée pour charger les données.</span><span class="sxs-lookup"><span data-stu-id="8bf57-108">In the source, use an ORDER BY clause in the statement that is used to load the data.</span></span>  
  
-   <span data-ttu-id="8bf57-109">Dans le flux de données, insérez une transformation de tri avant la transformation de fusion ou de jointure de fusion.</span><span class="sxs-lookup"><span data-stu-id="8bf57-109">In the data flow, insert a Sort transformation before the Merge or Merge Join transformation.</span></span>  
  
 <span data-ttu-id="8bf57-110">Si les données sont des données de chaînes, les transformations de fusion ou de jointure de fusion requièrent que ces valeurs de chaîne soient triées en utilisant le classement Windows.</span><span class="sxs-lookup"><span data-stu-id="8bf57-110">If the data is string data, both the Merge and Merge Join transformations expect the string values to have been sorted by using Windows collation.</span></span> <span data-ttu-id="8bf57-111">Pour fournir des valeurs de chaîne aux transformations de fusion et de jointure de fusion triées à l'aide du classement Windows, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8bf57-111">To provide string values to the Merge and Merge Join transformations that are sorted by using Windows collation, use the following procedure.</span></span>  
  
#### <a name="to-provide-string-values-that-are-sorted-by-using-windows-collation"></a><span data-ttu-id="8bf57-112">Pour fournir des valeurs de chaîne triées à l'aide du classement Windows</span><span class="sxs-lookup"><span data-stu-id="8bf57-112">To provide string values that are sorted by using Windows collation</span></span>  
  
-   <span data-ttu-id="8bf57-113">Utilisez une transformation de tri pour trier les données.</span><span class="sxs-lookup"><span data-stu-id="8bf57-113">Use a Sort transformation to sort the data.</span></span>  
  
     <span data-ttu-id="8bf57-114">La transformation de tri utilise le classement Windows pour trier les valeurs de chaîne.</span><span class="sxs-lookup"><span data-stu-id="8bf57-114">The Sort transformation uses Windows collation to sort string values.</span></span>  
  
     <span data-ttu-id="8bf57-115">-ou-</span><span class="sxs-lookup"><span data-stu-id="8bf57-115">-or-</span></span>  
  
-   <span data-ttu-id="8bf57-116">Utilisez l'opérateur Transact-SQL CAST pour commencer par effectuer un cast des valeurs `varchar` en valeurs `nvarchar`, puis utilisez la clause Transact-SQL ORDER BY pour trier les données.</span><span class="sxs-lookup"><span data-stu-id="8bf57-116">Use the Transact-SQL CAST operator to first cast `varchar` values to `nvarchar` values, and then use the Transact-SQL ORDER BY clause to sort the data.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8bf57-117">Vous ne pouvez pas utiliser la clause ORDER BY seule parce qu'elle utilise un classement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour trier les valeurs de chaîne.</span><span class="sxs-lookup"><span data-stu-id="8bf57-117">You cannot use the ORDER BY clause alone because the ORDER BY clause uses a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] collation to sort string values.</span></span> <span data-ttu-id="8bf57-118">L’utilisation du classement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] peut générer un ordre de tri différent du classement Windows, la transformation de fusion ou de jointure de fusion pouvant alors générer des résultats inattendus.</span><span class="sxs-lookup"><span data-stu-id="8bf57-118">The use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] collation might result in a different sort order than Windows collation, which can cause the Merge or Merge Join transformation to produce unexpected results.</span></span>  
  
## <a name="setting-sort-options-on-the-data"></a><span data-ttu-id="8bf57-119">Définition d'options de tri sur les données</span><span class="sxs-lookup"><span data-stu-id="8bf57-119">Setting Sort Options on the Data</span></span>  
 <span data-ttu-id="8bf57-120">Deux propriétés de tri importantes doivent être définies pour la source ou la transformation amont qui fournit des données aux transformations de fusion et de jointure de fusion :</span><span class="sxs-lookup"><span data-stu-id="8bf57-120">There are two important sort properties that must be set for the source or upstream transformation that supplies data to the Merge and Merge Join transformations:</span></span>  
  
-   <span data-ttu-id="8bf57-121">La propriété `IsSorted` de la sortie qui indique si les données ont été triées.</span><span class="sxs-lookup"><span data-stu-id="8bf57-121">The `IsSorted` property of the output that indicates whether the data has been sorted.</span></span> <span data-ttu-id="8bf57-122">Cette propriété doit avoir la valeur `True`.</span><span class="sxs-lookup"><span data-stu-id="8bf57-122">This property must be set to `True`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8bf57-123">La définition de la propriété `IsSorted` à la valeur `True` ne permet pas de trier les données.</span><span class="sxs-lookup"><span data-stu-id="8bf57-123">Setting the value of the `IsSorted` property to `True` does not sort the data.</span></span> <span data-ttu-id="8bf57-124">Cette propriété indique uniquement aux composants en aval que les données ont été précédemment triées.</span><span class="sxs-lookup"><span data-stu-id="8bf57-124">This property only provides a hint to downstream components that the data has been previously sorted.</span></span>  
  
-   <span data-ttu-id="8bf57-125">La Propriété `SortKeyPosition` des colonnes de sortie qui indique si une colonne est triée, son ordre de tri et la séquence dans laquelle plusieurs colonnes sont triées.</span><span class="sxs-lookup"><span data-stu-id="8bf57-125">The `SortKeyPosition` property of output columns that indicates whether a column is sorted, the column's sort order, and the sequence in which multiple columns are sorted.</span></span> <span data-ttu-id="8bf57-126">Cette propriété doit être définie pour chaque colonne de données triées.</span><span class="sxs-lookup"><span data-stu-id="8bf57-126">This property must be set for each column of sorted data.</span></span>  
  
 <span data-ttu-id="8bf57-127">Si vous utilisez une transformation de tri pour trier les données, elle définit ces deux propriétés tel que requis par la transformation de fusion ou de jointure de fusion.</span><span class="sxs-lookup"><span data-stu-id="8bf57-127">If you use a Sort transformation to sort the data, the Sort transformation sets both of these properties as required by the Merge or Merge Join transformation.</span></span> <span data-ttu-id="8bf57-128">Autrement dit, la transformation de tri définit la propriété `IsSorted` de sa sortie à `True`, puis définit les propriétés `SortKeyPosition` de ses colonnes de sortie.</span><span class="sxs-lookup"><span data-stu-id="8bf57-128">That is, the Sort transformation sets the `IsSorted` property of its output to `True`, and sets the `SortKeyPosition` properties of its output columns.</span></span>  
  
 <span data-ttu-id="8bf57-129">Toutefois, si vous n'utilisez pas de transformation de tri pour trier les données, vous devez définir ces propriétés de tri manuellement sur la source ou la transformation amont.</span><span class="sxs-lookup"><span data-stu-id="8bf57-129">However, if you do not use a Sort transformation to sort the data, you must set these sort properties manually on the source or the upstream transformation.</span></span> <span data-ttu-id="8bf57-130">Pour définir manuellement les propriétés de tri sur la source ou la transformation en amont, appliquez la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="8bf57-130">To manually set the sort properties on the source or upstream transformation, use the following procedure.</span></span>  
  
#### <a name="to-manually-set-sort-attributes-on-a-source-or-transformation-component"></a><span data-ttu-id="8bf57-131">Pour définir manuellement des attributs de tri sur un composant source ou de transformation</span><span class="sxs-lookup"><span data-stu-id="8bf57-131">To manually set sort attributes on a source or transformation component</span></span>  
  
1.  <span data-ttu-id="8bf57-132">Dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="8bf57-132">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="8bf57-133">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="8bf57-133">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="8bf57-134">Sous l’onglet **Flux de données** , recherchez la source ou la transformation en amont appropriée, ou faites-la glisser de la **Boîte à outils** vers l’aire de conception.</span><span class="sxs-lookup"><span data-stu-id="8bf57-134">On the **Data Flow** tab, locate the appropriate source or upstream transformation, or drag it from the **Toolbox** to the design surface.</span></span>  
  
4.  <span data-ttu-id="8bf57-135">Cliquez avec le bouton droit sur le composant, puis cliquez sur **Afficher l’éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="8bf57-135">Right-click the component and click **Show Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="8bf57-136">Cliquez sur l'onglet **Propriétés d'entrée et de sortie** .</span><span class="sxs-lookup"><span data-stu-id="8bf57-136">Click the **Input and Output Properties** tab.</span></span>  
  
6.  <span data-ttu-id="8bf57-137">Cliquez sur \*\* \<component name> sortie\*\*, puis affectez à la propriété la valeur `IsSorted` `True` .</span><span class="sxs-lookup"><span data-stu-id="8bf57-137">Click **\<component name> Output**, and set the `IsSorted` property to `True`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8bf57-138">Si vous définissez manuellement la propriété `IsSorted` de la sortie à `True` et que les données ne sont pas triées, il se peut que des données soient manquantes ou que des comparaisons de données incorrectes figurent dans la transformation de fusion ou de jointure de fusion en aval lors de l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="8bf57-138">If you manually set the `IsSorted` property of the output to `True` and the data is not sorted, there might be missing data or bad data comparisons in the downstream Merge or Merge Join transformation when you run the package.</span></span>  
  
7.  <span data-ttu-id="8bf57-139">Développez **Colonnes de sortie**.</span><span class="sxs-lookup"><span data-stu-id="8bf57-139">Expand **Output Columns**.</span></span>  
  
8.  <span data-ttu-id="8bf57-140">Cliquez sur la colonne que vous souhaitez identifier comme triée et définissez sa propriété `SortKeyPosition` sur une valeur entière non nulle conformément aux indications suivantes :</span><span class="sxs-lookup"><span data-stu-id="8bf57-140">Click the column that you want to indicate is sorted and set its `SortKeyPosition` property to a nonzero integer value by following these guidelines:</span></span>  
  
    -   <span data-ttu-id="8bf57-141">La valeur entière doit représenter une séquence numérique, partant de 1 et incrémentée de 1.</span><span class="sxs-lookup"><span data-stu-id="8bf57-141">The integer value must represent a numeric sequence, starting with 1 and incremented by 1.</span></span>  
  
    -   <span data-ttu-id="8bf57-142">Une valeur entière positive indique un ordre de tri croissant.</span><span class="sxs-lookup"><span data-stu-id="8bf57-142">A positive integer value indicates an ascending sort order.</span></span>  
  
    -   <span data-ttu-id="8bf57-143">Une valeur entière négative indique un ordre de tri décroissant.</span><span class="sxs-lookup"><span data-stu-id="8bf57-143">A negative integer value indicates a descending sort order.</span></span> <span data-ttu-id="8bf57-144">(Si un nombre négatif est défini, la valeur absolue du nombre détermine la position de la colonne dans la séquence de tri.)</span><span class="sxs-lookup"><span data-stu-id="8bf57-144">(If set to a negative number, the absolute value of the number determines the column's position in the sort sequence.)</span></span>  
  
    -   <span data-ttu-id="8bf57-145">Une valeur par défaut de 0 indique que la colonne n'est pas triée.</span><span class="sxs-lookup"><span data-stu-id="8bf57-145">The default value of 0 indicates that the column is not sorted.</span></span> <span data-ttu-id="8bf57-146">Laissez la valeur 0 pour les colonnes de sortie qui ne participent pas au tri.</span><span class="sxs-lookup"><span data-stu-id="8bf57-146">Leave the value of 0 for output columns that do not participate in the sort.</span></span>  
  
     <span data-ttu-id="8bf57-147">Comme exemple de définition de la propriété `SortKeyPosition`, prenons l'instruction Transact-SQL suivante qui charge des données dans une source.</span><span class="sxs-lookup"><span data-stu-id="8bf57-147">As an example of how to set the `SortKeyPosition` property, consider the following Transact-SQL statement that loads data in a source:</span></span>  
  
     `SELECT * FROM MyTable ORDER BY ColumnA, ColumnB DESC, ColumnC`  
  
     <span data-ttu-id="8bf57-148">Pour cette instruction, vous définissez la propriété `SortKeyPosition` de chaque colonne comme suit :</span><span class="sxs-lookup"><span data-stu-id="8bf57-148">For this statement, you would set the `SortKeyPosition` property for each column as follows:</span></span>  
  
    -   <span data-ttu-id="8bf57-149">Définissez la propriété `SortKeyPosition` de ColumnA à 1.</span><span class="sxs-lookup"><span data-stu-id="8bf57-149">Set the `SortKeyPosition` property of ColumnA to 1.</span></span> <span data-ttu-id="8bf57-150">Cela indique que ColumnA est la première colonne à trier et dans l'ordre croissant.</span><span class="sxs-lookup"><span data-stu-id="8bf57-150">This indicates that ColumnA is the first column to be sorted and is sorted in ascending order.</span></span>  
  
    -   <span data-ttu-id="8bf57-151">Définissez la propriété `SortKeyPosition` de ColumnB à -2.</span><span class="sxs-lookup"><span data-stu-id="8bf57-151">Set the `SortKeyPosition` property of ColumnB to -2.</span></span> <span data-ttu-id="8bf57-152">Cela indique que ColumnB est la deuxième colonne à trier et dans l'ordre décroissant.</span><span class="sxs-lookup"><span data-stu-id="8bf57-152">This indicates that ColumnB is the second column to be sorted and is sorted in descending order</span></span>  
  
    -   <span data-ttu-id="8bf57-153">Définissez la propriété `SortKeyPosition` de ColumnC à 3.</span><span class="sxs-lookup"><span data-stu-id="8bf57-153">Set the `SortKeyPosition` property of ColumnC to 3.</span></span> <span data-ttu-id="8bf57-154">Cela indique que ColumnC est la troisième colonne à trier et dans l'ordre croissant.</span><span class="sxs-lookup"><span data-stu-id="8bf57-154">This indicates that ColumnC is the third column to be sorted and is sorted in ascending order.</span></span>  
  
9. <span data-ttu-id="8bf57-155">Répétez l'étape 8 pour chaque colonne triée.</span><span class="sxs-lookup"><span data-stu-id="8bf57-155">Repeat step 8 for each sorted column.</span></span>  
  
10. <span data-ttu-id="8bf57-156">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8bf57-156">Click **OK**.</span></span>  
  
11. <span data-ttu-id="8bf57-157">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="8bf57-157">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bf57-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8bf57-158">See Also</span></span>  
 <span data-ttu-id="8bf57-159">[Transformation de fusion](merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="8bf57-159">[Merge Transformation](merge-transformation.md) </span></span>  
 <span data-ttu-id="8bf57-160">[Transformation de jointure de fusion](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="8bf57-160">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="8bf57-161">[Transformations Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="8bf57-161">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="8bf57-162">[Chemins Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="8bf57-162">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="8bf57-163">tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="8bf57-163">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
