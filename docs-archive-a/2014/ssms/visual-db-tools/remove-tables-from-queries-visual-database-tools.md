---
title: Supprimer des tables des requêtes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting tables
- removing tables
- dropping tables
- queries [SQL Server], tables
ms.assetid: 8fea0b4f-99b7-4050-8d6f-a97ffb839619
author: stevestein
ms.author: sstein
ms.openlocfilehash: fab5380e13742f3cd289ce17f26ad2e5fb9089ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604805"
---
# <a name="remove-tables-from-queries-visual-database-tools"></a><span data-ttu-id="2ef0b-102">Supprimer des tables des requêtes (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="2ef0b-102">Remove Tables from Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="2ef0b-103">Vous pouvez supprimer une table, ou un objet table, dans une requête.</span><span class="sxs-lookup"><span data-stu-id="2ef0b-103">You can remove a table - or any table-valued object - from the query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ef0b-104">Lorsque vous procédez à la suppression d'une table ou d'un objet table, cette suppression ne s'effectue que dans la requête en cours et non dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2ef0b-104">Removing a table or table-valued object does not delete anything from the database; it only removes it from the current query.</span></span> <span data-ttu-id="2ef0b-105">Pour plus d’informations sur la suppression d’une table d’une base de données, consultez [Delete Tables &#40;Moteur de base de données&#41;](../../relational-databases/tables/delete-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="2ef0b-105">For details about removing a table from a database, see [Delete Tables &#40;Database Engine&#41;](../../relational-databases/tables/delete-tables-database-engine.md).</span></span>  
  
### <a name="to-remove-a-table-or-table-structured-object"></a><span data-ttu-id="2ef0b-106">Pour supprimer une table ou un objet structuré comme une table</span><span class="sxs-lookup"><span data-stu-id="2ef0b-106">To remove a table or table-structured object</span></span>  
  
-   <span data-ttu-id="2ef0b-107">Dans le **volet Schéma**, sélectionnez la table, la vue, la fonction définie par l’utilisateur, le synonyme ou la requête, puis appuyez sur la touche Suppr ou cliquez avec le bouton droit sur l’objet et sélectionnez **Supprimer** dans la boîte de dialogue qui s’affiche.</span><span class="sxs-lookup"><span data-stu-id="2ef0b-107">In the **Diagram Pane**, select the table, view, user-defined function, synonym, or query, and then press DELETE, or right-click the object and then choose **Remove** in the resulting dialog box.</span></span> <span data-ttu-id="2ef0b-108">Vous pouvez sélectionner et supprimer plusieurs objets à la fois.</span><span class="sxs-lookup"><span data-stu-id="2ef0b-108">You can select and remove multiple objects at one time.</span></span>  
  
     <span data-ttu-id="2ef0b-109">-ou-</span><span class="sxs-lookup"><span data-stu-id="2ef0b-109">-or-</span></span>  
  
-   <span data-ttu-id="2ef0b-110">Supprimez toutes les références à l’objet dans le **volet SQL**.</span><span class="sxs-lookup"><span data-stu-id="2ef0b-110">Remove all references to the object in the **SQL Pane.**</span></span>  
  
 <span data-ttu-id="2ef0b-111">Quand vous supprimez une table ou un objet table, le Concepteur de requêtes et de vues supprime automatiquement les jointures relatives à cette table ou à cet objet table, ainsi que les références aux colonnes de l’objet dans le **volet SQL** et le **volet Critères**.</span><span class="sxs-lookup"><span data-stu-id="2ef0b-111">When you remove a table or table-valued object, the Query and View Designer automatically removes joins that involve that table or table-valued object and removes references to the object's columns in the **SQL Pane** and **Criteria Pane**.</span></span> <span data-ttu-id="2ef0b-112">Si la requête comporte toutefois des expressions complexes relatives à l'objet, la suppression automatique de cet objet ne s'effectue pas tant que toutes les références le concernant n'ont pas été supprimées.</span><span class="sxs-lookup"><span data-stu-id="2ef0b-112">However, if the query contains complex expressions involving the object, the object is not automatically removed until all references to it are removed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ef0b-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ef0b-113">See Also</span></span>  
 <span data-ttu-id="2ef0b-114">[Ajouter des tables à des requêtes &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2ef0b-114">[Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="2ef0b-115">[Créer des alias de table &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2ef0b-115">[Create Table Aliases &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) </span></span>  
 <span data-ttu-id="2ef0b-116">[Spécifier les critères de recherche &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2ef0b-116">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="2ef0b-117">[Résumer les résultats de la requête &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2ef0b-117">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="2ef0b-118">Effectuer des opérations de base concernant les requêtes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="2ef0b-118">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
