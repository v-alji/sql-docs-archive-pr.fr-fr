---
title: Spécifier des conditions de recherche (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- choosing search criteria
- search conditions [SQL Server], specifying
- search criteria [SQL Server], specifying conditions
ms.assetid: 18e2c759-68ec-4efe-b208-2f73418cd9bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa5dab8326de079c385a3a508bc1b01b1ee1247d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604801"
---
# <a name="specify-search-conditions-visual-database-tools"></a><span data-ttu-id="c4f4a-102">Spécifier des conditions de recherche (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c4f4a-102">Specify Search Conditions (Visual Database Tools)</span></span>
  <span data-ttu-id="c4f4a-103">Vous pouvez spécifier les lignes de données figurant dans votre requête en spécifiant des conditions de recherche.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-103">You can specify the data rows that appear in your query by specifying search conditions.</span></span> <span data-ttu-id="c4f4a-104">Par exemple, si vous formulez une requête sur une table `employee` , vous pouvez spécifier que vous ne souhaitez rechercher que les employés travaillant dans une région donnée.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-104">For example, if you are querying an `employee` table, you can specify that you want to find only the employees who work in a particular region.</span></span>  
  
 <span data-ttu-id="c4f4a-105">Vous spécifiez des conditions de recherche à l'aide d'une expression.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-105">You specify search conditions using an expression.</span></span> <span data-ttu-id="c4f4a-106">La plupart du temps, cette expression comporte un opérateur et une valeur de recherche.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-106">Most commonly the expression consists of an operator and a search value.</span></span> <span data-ttu-id="c4f4a-107">Pour rechercher, par exemple, les employés d'une région commerciale donnée, vous pouvez spécifier le critère de recherche suivant pour la colonne `region` :</span><span class="sxs-lookup"><span data-stu-id="c4f4a-107">For example, to find employees in a particular sales region, you might specify the following search criterion for the `region` column:</span></span>  
  
```  
='UK'  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c4f4a-108">Si vous utilisez plusieurs tables, le Concepteur de requêtes et de vues étudie chaque condition de recherche, afin de déterminer si la comparaison que vous établissez donne lieu à une jointure.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-108">If you are working with multiple tables, the Query and View Designer examines each search condition to determine whether the comparison you are making results in a join.</span></span> <span data-ttu-id="c4f4a-109">Si tel est le cas, le Concepteur de requêtes et de vues convertit alors automatiquement la condition de recherche en jointure.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-109">If so, the Query and View Designer automatically converts the search condition into a join.</span></span> <span data-ttu-id="c4f4a-110">Pour plus d’informations, consultez [Joindre automatiquement des tables &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c4f4a-110">For more information, see [Join Tables Automatically &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
### <a name="to-specify-search-conditions"></a><span data-ttu-id="c4f4a-111">Pour spécifier des conditions de recherche</span><span class="sxs-lookup"><span data-stu-id="c4f4a-111">To specify search conditions</span></span>  
  
1.  <span data-ttu-id="c4f4a-112">Si vous ne l'avez pas encore effectué, ajoutez les colonnes ou les expressions que vous souhaitez utiliser dans votre condition de recherche au volet Critères.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-112">If you have not done so already, add the columns or expressions that you want to use within your search condition to the Criteria pane.</span></span>  
  
     <span data-ttu-id="c4f4a-113">Si vous créez une requête Select et si vous ne souhaitez pas que les expressions ou les colonnes de recherche figurent dans le résultat de la requête, effacez chaque expression ou colonne de recherche de la colonne **Sortie** pour les exclure des colonnes de sortie.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-113">If you are creating a Select query and do not want the search columns or expressions to appear in the query output, clear the **Output** column for each search column or expression to remove them as output columns.</span></span>  
  
2.  <span data-ttu-id="c4f4a-114">Localisez la ligne comportant l’expression ou la colonne de données à rechercher, puis entrez une condition de recherche dans la colonne **Filtres** .</span><span class="sxs-lookup"><span data-stu-id="c4f4a-114">Locate the row containing the data column or expression to search, and then in the **Filter** column, enter a search condition.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4f4a-115">Si vous n'entrez pas d'opérateur, le Concepteur de requêtes et de vues insère automatiquement l'opérateur d'égalité « = ».</span><span class="sxs-lookup"><span data-stu-id="c4f4a-115">If you do not enter an operator, the Query and View Designer automatically inserts the equality operator "=".</span></span>  
  
 <span data-ttu-id="c4f4a-116">Le Concepteur de requêtes et de vues met à jour l’instruction SQL dans le [volet SQL](sql-pane-visual-database-tools.md) en ajoutant ou en modifiant la clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-116">The Query and View Designer updates the SQL statement in the [SQL Pane](sql-pane-visual-database-tools.md) by adding or modifying the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f4a-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c4f4a-117">See Also</span></span>  
 <span data-ttu-id="c4f4a-118">[Règles pour l’entrée de valeurs de recherche &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c4f4a-118">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="c4f4a-119">Spécifier des critères de recherche &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c4f4a-119">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
