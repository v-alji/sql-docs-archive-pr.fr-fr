---
title: Spécifier des conditions pour des groupes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- HAVING clause, query groups
- group query conditions [SQL Server]
ms.assetid: 269ad9c5-3261-4526-badf-7be3c869f229
author: stevestein
ms.author: sstein
ms.openlocfilehash: da9bc1b70fbfae8bf2a68a3a3ba332020020f310
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599724"
---
# <a name="specify-conditions-for-groups-visual-database-tools"></a><span data-ttu-id="b0f4c-102">Spécifier des conditions pour des groupes (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b0f4c-102">Specify Conditions for Groups (Visual Database Tools)</span></span>
  <span data-ttu-id="b0f4c-103">Vous pouvez limiter les groupes qui apparaissent dans une requête en spécifiant une condition qui s’applique à l’ensemble des groupes (une clause HAVING).</span><span class="sxs-lookup"><span data-stu-id="b0f4c-103">You can limit the groups that appear in a query by specifying a condition that applies to groups as a whole - a HAVING clause.</span></span> <span data-ttu-id="b0f4c-104">Après regroupement et agrégation des données, les conditions de la clause HAVING sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="b0f4c-104">After the data has been grouped and aggregated, the conditions in the HAVING clause are applied.</span></span> <span data-ttu-id="b0f4c-105">Seuls les groupes qui répondent aux conditions apparaissent dans la requête.</span><span class="sxs-lookup"><span data-stu-id="b0f4c-105">Only the groups that meet the conditions appear in the query.</span></span>  
  
 <span data-ttu-id="b0f4c-106">Supposons que vous vouliez voir le prix moyen de tous les livres pour chaque éditeur dans une table `titles` , mais uniquement dans le cas où ce prix serait supérieur à 10 $.</span><span class="sxs-lookup"><span data-stu-id="b0f4c-106">For example, you might want to see the average price of all books for each publisher in a `titles` table, but only if the average price exceeds $10.00.</span></span> <span data-ttu-id="b0f4c-107">Dans ce cas, vous pouvez spécifier une clause HAVING avec une condition telle que `AVG(price) > 10`.</span><span class="sxs-lookup"><span data-stu-id="b0f4c-107">In that case, you could specify a HAVING clause with a condition such as `AVG(price) > 10`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0f4c-108">Il peut arriver parfois que vous souhaitiez exclure des lignes individuelles de groupes avant d'appliquer une condition aux groupes dans leur ensemble.</span><span class="sxs-lookup"><span data-stu-id="b0f4c-108">In some instances, you might want to exclude individual rows from groups before applying a condition to groups as a whole.</span></span> <span data-ttu-id="b0f4c-109">Pour plus d’informations, consultez [Utiliser les clauses HAVING et WHERE dans la même requête &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b0f4c-109">For details, see [Use HAVING and WHERE Clauses in the Same Query &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="b0f4c-110">Vous pouvez créer des conditions complexes pour une clause HAVING en utilisant AND et OR pour lier les conditions.</span><span class="sxs-lookup"><span data-stu-id="b0f4c-110">You can create complex conditions for a HAVING clause by using AND and OR to link conditions.</span></span> <span data-ttu-id="b0f4c-111">Pour plus d’informations sur l’utilisation de AND et OU dans les conditions de recherche, consultez [Spécifier plusieurs conditions de recherche pour une colonne &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b0f4c-111">For details about using AND and OR in search conditions, see [Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md).</span></span>  
  
### <a name="to-specify-a-condition-for-a-group"></a><span data-ttu-id="b0f4c-112">Pour spécifier une condition destinée à un groupe</span><span class="sxs-lookup"><span data-stu-id="b0f4c-112">To specify a condition for a group</span></span>  
  
1.  <span data-ttu-id="b0f4c-113">Spécifiez les groupes de votre requête.</span><span class="sxs-lookup"><span data-stu-id="b0f4c-113">Specify the groups for your query.</span></span> <span data-ttu-id="b0f4c-114">Pour plus d’informations, consultez [Regrouper des lignes dans les résultats de requête &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b0f4c-114">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="b0f4c-115">Si elle ne figure pas encore dans le [volet Critères](criteria-pane-visual-database-tools.md), ajoutez la colonne sur laquelle vous souhaitez baser la condition.</span><span class="sxs-lookup"><span data-stu-id="b0f4c-115">If it is not already in the [Criteria pane](criteria-pane-visual-database-tools.md), add the column on which you want to base the condition.</span></span> <span data-ttu-id="b0f4c-116">(Souvent, la condition concerne une colonne qui est déjà une colonne de groupe ou de synthèse.) Vous ne pouvez pas utiliser une colonne qui ne fait pas partie d'une fonction d'agrégation ou de la clause GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="b0f4c-116">(Most often the condition involves a column that is already a group or summary column.) You cannot use a column that is not part of an aggregate function or of the GROUP BY clause.</span></span>  
  
3.  <span data-ttu-id="b0f4c-117">Dans la colonne **Filtre**, spécifiez la condition à appliquer au groupe.</span><span class="sxs-lookup"><span data-stu-id="b0f4c-117">In the **Filter** column, specify the condition to apply to the group.</span></span>  
  
     <span data-ttu-id="b0f4c-118">Le [Concepteur de requêtes et de vues](query-and-view-designer-tools-visual-database-tools.md) crée automatiquement une clause HAVING dans l’instruction du [volet SQL](sql-pane-visual-database-tools.md), comme illustré dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="b0f4c-118">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) automatically creates a HAVING clause in the statement in the [SQL pane](sql-pane-visual-database-tools.md), such as in the following example:</span></span>  
  
    ```  
    SELECT pub_id, AVG(price)  
    FROM titles  
    GROUP BY pub_id  
    HAVING (AVG(price) > 10)  
  
    ```  
  
4.  <span data-ttu-id="b0f4c-119">Répétez les étapes 2 et 3 pour chaque condition supplémentaire que vous souhaitez spécifier.</span><span class="sxs-lookup"><span data-stu-id="b0f4c-119">Repeat steps 2 and 3 for each additional condition you want to specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0f4c-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b0f4c-120">See Also</span></span>  
 [<span data-ttu-id="b0f4c-121">Trier et regrouper des résultats de requête &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="b0f4c-121">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
