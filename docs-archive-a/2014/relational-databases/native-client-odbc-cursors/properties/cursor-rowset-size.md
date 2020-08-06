---
title: Taille de l’ensemble de lignes du curseur | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], rowset size
- ODBC cursors, rowset size
- rowsets [ODBC]
ms.assetid: 2febe2ae-fdc1-490e-a79f-c516bc8e7c3f
author: rothja
ms.author: jroth
ms.openlocfilehash: 83c4e55025e6e3724f354f022760b7ba1e2f10e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612289"
---
# <a name="cursor-rowset-size"></a><span data-ttu-id="1dd07-102">Taille de l'ensemble de lignes d'un curseur</span><span class="sxs-lookup"><span data-stu-id="1dd07-102">Cursor Rowset Size</span></span>
  <span data-ttu-id="1dd07-103">Les curseurs ODBC peuvent extraire plusieurs lignes à la fois.</span><span class="sxs-lookup"><span data-stu-id="1dd07-103">ODBC cursors are not limited to fetching one row at a time.</span></span> <span data-ttu-id="1dd07-104">Ils peuvent récupérer plusieurs lignes dans chaque appel à **SQLFetch** ou [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="1dd07-104">They can retrieve multiple rows in each call to **SQLFetch** or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md).</span></span> <span data-ttu-id="1dd07-105">Lorsque vous utilisez une base de données client/serveur, telle que Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], il est plus efficace d'extraire plusieurs lignes à la fois.</span><span class="sxs-lookup"><span data-stu-id="1dd07-105">When you are working with a client/server database such as Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it is more efficient to fetch several rows at a time.</span></span> <span data-ttu-id="1dd07-106">Le nombre de lignes retournées sur une extraction est appelé la taille de l’ensemble de lignes et est spécifié à l’aide de la SQL_ATTR_ROW_ARRAY_SIZE de [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="1dd07-106">The number of rows returned on a fetch is called the rowset size and is specified by using the SQL_ATTR_ROW_ARRAY_SIZE of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
```  
SQLUINTEGER uwRowsize;  
SQLSetStmtAttr(m_hstmt, SQL_ATTR_ROW_ARRAY_SIZE, (SQLPOINTER)uwRowsetSize, SQL_IS_UINTEGER);  
```  
  
 <span data-ttu-id="1dd07-107">Les curseurs dont la taille de l'ensemble de lignes est supérieure à 1 sont appelés « curseurs de bloc ».</span><span class="sxs-lookup"><span data-stu-id="1dd07-107">Cursors with a rowset size greater than 1 are called block cursors.</span></span>  
  
 <span data-ttu-id="1dd07-108">Deux options s'offrent à vous pour lier des colonnes de jeu de résultats pour des curseurs de bloc :</span><span class="sxs-lookup"><span data-stu-id="1dd07-108">There are two options for binding result set columns for block cursors:</span></span>  
  
-   <span data-ttu-id="1dd07-109">Liaison selon les colonnes</span><span class="sxs-lookup"><span data-stu-id="1dd07-109">Column-wise binding</span></span>  
  
     <span data-ttu-id="1dd07-110">Chaque colonne est liée à un tableau de variables.</span><span class="sxs-lookup"><span data-stu-id="1dd07-110">Each column is bound to an array of variables.</span></span> <span data-ttu-id="1dd07-111">Chaque tableau possède un nombre d'éléments égal à la taille de l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="1dd07-111">Each array has the same number of elements as the rowset size.</span></span>  
  
-   <span data-ttu-id="1dd07-112">Liaison selon les lignes</span><span class="sxs-lookup"><span data-stu-id="1dd07-112">Row-wise binding</span></span>  
  
     <span data-ttu-id="1dd07-113">Un tableau est construit à l'aide de structures qui contiennent les données et d'indicateurs pour toutes les colonnes d'une ligne.</span><span class="sxs-lookup"><span data-stu-id="1dd07-113">An array is built using structures that hold the data and indicators for all the columns in a row.</span></span> <span data-ttu-id="1dd07-114">Le tableau possède un nombre de structures égal à la taille de l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="1dd07-114">The array has the same number of structures as the rowset size.</span></span>  
  
 <span data-ttu-id="1dd07-115">Lorsque l’une des liaisons selon les colonnes ou les lignes est utilisée, chaque appel à **SQLFetch** ou **SQLFetchScroll** remplit les tableaux liés avec les données de l’ensemble de lignes récupéré.</span><span class="sxs-lookup"><span data-stu-id="1dd07-115">When either column-wise or row-wise binding is used, each call to **SQLFetch** or **SQLFetchScroll** fills the bound arrays with data from the rowset retrieved.</span></span>  
  
 <span data-ttu-id="1dd07-116">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) peut également être utilisé pour récupérer des données de colonne à partir d’un curseur de bloc.</span><span class="sxs-lookup"><span data-stu-id="1dd07-116">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) can also be used to retrieve column data from a block cursor.</span></span> <span data-ttu-id="1dd07-117">Comme **SQLGetData** travaille une ligne à la fois, **SQLSetPos** doit être appelé pour définir une ligne spécifique dans l’ensemble de lignes comme ligne actuelle avant d’appeler **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="1dd07-117">Because **SQLGetData** works one row at a time, **SQLSetPos** must be called to set a specific row in the rowset as the current row before calling **SQLGetData**.</span></span>  
  
 <span data-ttu-id="1dd07-118">Le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client offre une optimisation à l’aide d’ensembles de lignes pour récupérer rapidement un jeu de résultats entier.</span><span class="sxs-lookup"><span data-stu-id="1dd07-118">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver offers an optimization using rowsets to retrieve a whole result set quickly.</span></span> <span data-ttu-id="1dd07-119">Pour utiliser cette optimisation, définissez les attributs de curseur à leurs valeurs par défaut (avant uniquement, lecture seule, taille de l’ensemble de lignes = 1) au moment de l’appel de **SQLExecDirect** ou **SQLExecute** .</span><span class="sxs-lookup"><span data-stu-id="1dd07-119">To use this optimization, set the cursor attributes to their defaults (forward-only, read-only, rowset size = 1) at the time **SQLExecDirect** or **SQLExecute** is called.</span></span> <span data-ttu-id="1dd07-120">Le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC native client configure un jeu de résultats par défaut.</span><span class="sxs-lookup"><span data-stu-id="1dd07-120">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver sets up a default result set.</span></span> <span data-ttu-id="1dd07-121">Cette approche est plus efficace que les curseurs côté serveur lors du transfert de résultats au client sans défilement.</span><span class="sxs-lookup"><span data-stu-id="1dd07-121">This is more efficient than server cursors when transferring results to the client without scrolling.</span></span> <span data-ttu-id="1dd07-122">Après avoir exécuté l'instruction, augmentez la taille de l'ensemble de lignes et utilisez la liaison selon les colonnes ou la liaison selon les lignes.</span><span class="sxs-lookup"><span data-stu-id="1dd07-122">After the statement has been executed, increase the rowset size and use either column-wise or row-wise binding.</span></span> <span data-ttu-id="1dd07-123">Cela permet d' [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utiliser un jeu de résultats par défaut pour envoyer efficacement des lignes de résultat au client, tandis que le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client extrait en continu des lignes des tampons réseau sur le client.</span><span class="sxs-lookup"><span data-stu-id="1dd07-123">This lets [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] use a default result set to send result rows efficiently to the client, while the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver continuously pulls rows from the network buffers on the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dd07-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1dd07-124">See Also</span></span>  
 [<span data-ttu-id="1dd07-125">Propriétés de curseur</span><span class="sxs-lookup"><span data-stu-id="1dd07-125">Cursor Properties</span></span>](cursor-properties.md)  
  
  
