---
title: Sélectionner les lignes ne correspondant pas à une valeur (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search conditions [SQL Server], rows not matching value
- row not matching value [SQL Server]
- NOT operator [Visual Database Tools]
- search criteria [SQL Server], rows not matching value
ms.assetid: 19898578-7b2f-401c-bb8f-9f2a017efdf7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 412ec93cbfedc87e92da9e86c7e4c7455919722a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703687"
---
# <a name="select-rows-that-do-not-match-a-value-visual-database-tools"></a><span data-ttu-id="3d59f-102">Sélectionner les lignes ne correspondant pas à une valeur (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="3d59f-102">Select Rows That Do Not Match a Value (Visual Database Tools)</span></span>
  <span data-ttu-id="3d59f-103">Pour rechercher des lignes ne correspondant pas à une valeur, utilisez l'opérateur NOT.</span><span class="sxs-lookup"><span data-stu-id="3d59f-103">To find rows that do not match a value, use the NOT operator.</span></span>  
  
### <a name="to-find-rows-that-do-not-match-a-value"></a><span data-ttu-id="3d59f-104">Pour rechercher des lignes ne correspondant pas à une valeur</span><span class="sxs-lookup"><span data-stu-id="3d59f-104">To find rows that do not match a value</span></span>  
  
1.  <span data-ttu-id="3d59f-105">Si ce n’est déjà fait, ajoutez les colonnes ou les expressions que vous souhaitez utiliser dans votre condition de recherche au [volet Critères](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3d59f-105">If you have not done so already, add the columns or expressions that you want to use within your search condition to the [Criteria pane](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="3d59f-106">Localisez la ligne comportant l’expression ou la colonne de données à rechercher, puis entrez l’opérateur NOT suivi d’une valeur de recherche dans la colonne de la grille **Filtre** .</span><span class="sxs-lookup"><span data-stu-id="3d59f-106">Locate the row containing the data column or expression to search, and then in the **Filter** grid column, enter the NOT operator followed by a search value.</span></span>  
  
 <span data-ttu-id="3d59f-107">Si vous souhaitez, par exemple, rechercher toutes les lignes figurant dans une table `products` dans laquelle les valeurs de la colonne des codes produits commencent par un autre caractère que « A », vous pouvez alors entrer la condition de recherche suivante :</span><span class="sxs-lookup"><span data-stu-id="3d59f-107">For example, to find all the rows in a `products` table where the values in the product code column begin with a character other than "A," you can enter a search condition such as the following:</span></span>  
  
```  
NOT LIKE 'A%'  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d59f-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3d59f-108">See Also</span></span>  
 <span data-ttu-id="3d59f-109">[Règles pour l’entrée de valeurs de recherche &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3d59f-109">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="3d59f-110">Spécifier des critères de recherche &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="3d59f-110">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
