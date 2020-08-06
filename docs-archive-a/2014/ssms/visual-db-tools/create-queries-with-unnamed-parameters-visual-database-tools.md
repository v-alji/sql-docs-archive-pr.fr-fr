---
title: Créer des requêtes avec des paramètres sans nom (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- unnamed parameters
- parameters [SQL Server], unnamed
ms.assetid: 5f4b664b-3d3d-4d07-a0e7-791d78743504
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0ea53afd1fa4d44390f5805d6b28494428608b90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600448"
---
# <a name="create-queries-with-unnamed-parameters-visual-database-tools"></a><span data-ttu-id="75c7c-102">Créer des requêtes avec des paramètres sans nom (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="75c7c-102">Create Queries with Unnamed Parameters (Visual Database Tools)</span></span>
  <span data-ttu-id="75c7c-103">Vous pouvez créer une requête avec un paramètre sans nom en spécifiant un point d'interrogation (?) comme espace réservé pour une valeur littérale.</span><span class="sxs-lookup"><span data-stu-id="75c7c-103">You can create a query with an unnamed parameter by specifying a question mark (?) as a placeholder for a literal value.</span></span> <span data-ttu-id="75c7c-104">Le Concepteur de requêtes et de vues lui donnera un nom temporaire.</span><span class="sxs-lookup"><span data-stu-id="75c7c-104">Query and View Designer will give it a temporary name.</span></span> <span data-ttu-id="75c7c-105">Vous pouvez définir autant de paramètres sans nom que vous le souhaitez dans la requête.</span><span class="sxs-lookup"><span data-stu-id="75c7c-105">You can specify as many unnamed parameters in the query as you need.</span></span>  
  
 <span data-ttu-id="75c7c-106">Lorsque vous exécutez la requête dans le Concepteur de requêtes et de vues, la boîte de dialogue Paramètres de la requête s'affiche avec le nom temporaire.</span><span class="sxs-lookup"><span data-stu-id="75c7c-106">When you run the query in the Query and View Designer, the Query Parameters Dialog Box is displayed with the temporary name.</span></span>  
  
### <a name="to-specify-an-unnamed-parameter"></a><span data-ttu-id="75c7c-107">Pour spécifier un paramètre sans nom</span><span class="sxs-lookup"><span data-stu-id="75c7c-107">To specify an unnamed parameter</span></span>  
  
1.  <span data-ttu-id="75c7c-108">Ajoutez les colonnes ou expressions à rechercher dans le [volet Critères](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="75c7c-108">Add the columns or expressions that you want to search to the [Criteria pane](visual-database-tools.md).</span></span> <span data-ttu-id="75c7c-109">Si vous ne souhaitez pas que les colonnes ou expressions de recherche apparaissent dans le résultat de la requête, supprimez-les comme colonnes de sortie.</span><span class="sxs-lookup"><span data-stu-id="75c7c-109">If you do not want the search columns or expressions to appear in the query output, remove them as output columns.</span></span>  
  
2.  <span data-ttu-id="75c7c-110">Recherchez la ligne contenant la colonne de données ou l’expression à rechercher puis, dans la colonne **Filtre** de la grille, entrez un point d’interrogation (?).</span><span class="sxs-lookup"><span data-stu-id="75c7c-110">Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter a question mark (?).</span></span>  
  
     <span data-ttu-id="75c7c-111">Par défaut, le Concepteur de requêtes et de vues ajoute l'opérateur « = ».</span><span class="sxs-lookup"><span data-stu-id="75c7c-111">By default, the Query and View Designer adds the "=" operator.</span></span> <span data-ttu-id="75c7c-112">Toutefois, vous pouvez modifier la cellule pour le remplacer par « > », « < », ou un autre opérateur de comparaison SQL.</span><span class="sxs-lookup"><span data-stu-id="75c7c-112">However, you can edit the cell to substitute ">", "<", or any other SQL comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75c7c-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="75c7c-113">See Also</span></span>  
 [<span data-ttu-id="75c7c-114">Requête avec des paramètres &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="75c7c-114">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](query-with-parameters-visual-database-tools.md)  
  
  
