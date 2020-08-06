---
title: Utiliser la liaison d’ensemble de lignes (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowset binding [ODBC]
ms.assetid: a7be05f0-6b11-4b53-9fbc-501e591eef09
author: rothja
ms.author: jroth
ms.openlocfilehash: e2e0671fd1140e72005cd1a7532ea581f077382f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599974"
---
# <a name="use-rowset-binding-odbc"></a><span data-ttu-id="4b93d-102">Utiliser une liaison d'ensembles de lignes (ODBC)</span><span class="sxs-lookup"><span data-stu-id="4b93d-102">Use Rowset Binding (ODBC)</span></span>
    
### <a name="to-use-column-wise-binding"></a><span data-ttu-id="4b93d-103">Pour utiliser la liaison selon les colonnes</span><span class="sxs-lookup"><span data-stu-id="4b93d-103">To use column-wise binding</span></span>  
  
1.  <span data-ttu-id="4b93d-104">Pour chaque colonne dépendante, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4b93d-104">For each bound column, do the following:</span></span>  
  
    -   <span data-ttu-id="4b93d-105">Allouez un tableau de R (ou plus) tampons de colonnes pour stocker les valeurs des données. R désigne le nombre de lignes dans l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="4b93d-105">Allocate an array of R (or more) column buffers to store data values, where R is number of rows in the rowset.</span></span>  
  
    -   <span data-ttu-id="4b93d-106">Allouez éventuellement un tableau de R (ou plus) tampons de colonnes pour le stockage des longueurs des données.</span><span class="sxs-lookup"><span data-stu-id="4b93d-106">Optionally, allocate an array of R (or more) column buffers to store data lengths.</span></span>  
  
    -   <span data-ttu-id="4b93d-107">Appelez [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) pour lier la valeur de données de la colonne et les tableaux de longueur des données à la colonne de l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="4b93d-107">Call [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) to bind the column's data value and data length arrays to the column of the rowset.</span></span>  
  
2.  <span data-ttu-id="4b93d-108">Appelez [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) pour définir les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="4b93d-108">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="4b93d-109">Définissez SQL_ATTR_ROW_ARRAY_SIZE sur le nombre de lignes dans l'ensemble de lignes (R).</span><span class="sxs-lookup"><span data-stu-id="4b93d-109">Set SQL_ATTR_ROW_ARRAY_SIZE to the number of rows in the rowset (R).</span></span>  
  
    -   <span data-ttu-id="4b93d-110">Définissez SQL_ATTR_ROW_BIND_TYPE sur SQL_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="4b93d-110">Set SQL_ATTR_ROW_BIND_TYPE to SQL_BIND_BY_COLUMN.</span></span>  
  
    -   <span data-ttu-id="4b93d-111">Définissez l'attribut SQL_ATTR_ROWS_FETCHED_PTR de sorte qu'il pointe vers une variable SQLUINTEGER contenant le nombre de lignes extraites.</span><span class="sxs-lookup"><span data-stu-id="4b93d-111">Set the SQL_ATTR_ROWS FETCHED_PTR attribute to point to a SQLUINTEGER variable to hold the number of rows fetched.</span></span>  
  
    -   <span data-ttu-id="4b93d-112">Définissez SQL_ATTR_ROWS_STATUS_PTR de sorte qu'il pointe vers un tableau [R] de variables SQLUSSMALLINT contenant les indicateurs d'état de ligne.</span><span class="sxs-lookup"><span data-stu-id="4b93d-112">Set SQL_ATTR_ROW_STATUS_PTR to point to an array[R] of SQLUSSMALLINT variables to hold the row-status indicators.</span></span>  
  
3.  <span data-ttu-id="4b93d-113">Exécution de l'instruction.</span><span class="sxs-lookup"><span data-stu-id="4b93d-113">Execute the statement.</span></span>  
  
4.  <span data-ttu-id="4b93d-114">Chaque appel à [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) ou [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) extrait des lignes R et transfère les données dans les colonnes dépendantes.</span><span class="sxs-lookup"><span data-stu-id="4b93d-114">Each call to [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) retrieves R rows and transfers the data into the bound columns.</span></span>  
  
### <a name="to-use-row-wise-binding"></a><span data-ttu-id="4b93d-115">Pour utiliser la liaison selon les lignes</span><span class="sxs-lookup"><span data-stu-id="4b93d-115">To use row-wise binding</span></span>  
  
1.  <span data-ttu-id="4b93d-116">Allouez un tableau [R] de structures, où R correspond au nombre de lignes dans l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="4b93d-116">Allocate an array[R] of structures, where R is the number of rows in the rowset.</span></span> <span data-ttu-id="4b93d-117">La structure dispose d'un élément pour chaque colonne, et chaque élément a deux parties :</span><span class="sxs-lookup"><span data-stu-id="4b93d-117">The structure has one element for each column, and each element has two parts:</span></span>  
  
    -   <span data-ttu-id="4b93d-118">La première partie est une variable de type de données approprié destinée à contenir les données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="4b93d-118">The first part is a variable of the appropriate data type to hold the column data.</span></span>  
  
    -   <span data-ttu-id="4b93d-119">La deuxième est une variable SQLINTEGER qui affiche l'indicateur d'état de la colonne.</span><span class="sxs-lookup"><span data-stu-id="4b93d-119">The second part is a SQLINTEGER variable to hold the column status indicator.</span></span>  
  
2.  <span data-ttu-id="4b93d-120">Appelez [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) pour définir les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="4b93d-120">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="4b93d-121">Définissez SQL_ATTR_ROW_ARRAY_SIZE sur le nombre de lignes dans l'ensemble de lignes (R).</span><span class="sxs-lookup"><span data-stu-id="4b93d-121">Set SQL_ATTR_ROW_ARRAY_SIZE to the number of rows in the rowset (R).</span></span>  
  
    -   <span data-ttu-id="4b93d-122">Définissez SQL_ATTR_ROW_BIND_TYPE conformément à la taille de la structure allouée à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="4b93d-122">Set SQL_ATTR_ROW_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
    -   <span data-ttu-id="4b93d-123">Définissez l'attribut SQL_ATTR_ROWS_FETCHED_PTR de sorte qu'il pointe vers une variable SQLUINTEGER contenant le nombre de lignes extraites.</span><span class="sxs-lookup"><span data-stu-id="4b93d-123">Set the SQL_ATTR_ROWS_FETCHED_PTR attribute to point to a SQLUINTEGER variable to hold the number of rows fetched.</span></span>  
  
    -   <span data-ttu-id="4b93d-124">Définissez SQL_ATTR_PARAMS_STATUS_PTR de sorte qu'il pointe vers un tableau [R] de variables SQLUSSMALLINT contenant les indicateurs d'état de ligne.</span><span class="sxs-lookup"><span data-stu-id="4b93d-124">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[R] of SQLUSSMALLINT variables to hold the row-status indicators.</span></span>  
  
3.  <span data-ttu-id="4b93d-125">Pour chaque colonne dans le jeu de résultats, appelez [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) pour diriger les pointeurs de valeur de données et de longueur de données de colonne vers leurs variables dans le premier élément du tableau de structures alloué à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="4b93d-125">For each column in the result set, call [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) to point the data value and data length pointer of the column to their variables in the first element of the array of structures allocated in Step 1.</span></span>  
  
4.  <span data-ttu-id="4b93d-126">Exécution de l'instruction.</span><span class="sxs-lookup"><span data-stu-id="4b93d-126">Execute the statement.</span></span>  
  
5.  <span data-ttu-id="4b93d-127">Chaque appel à [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) ou [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) extrait des lignes R et transfère les données dans les colonnes dépendantes.</span><span class="sxs-lookup"><span data-stu-id="4b93d-127">Each call to [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) retrieves R rows and transfers the data into the bound columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b93d-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4b93d-128">See Also</span></span>  
 <span data-ttu-id="4b93d-129">[Rubriques de procédures relatives à l’utilisation des curseurs &#40;ODBC&#41;](using-cursors-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="4b93d-129">[Using Cursors How-to Topics &#40;ODBC&#41;](using-cursors-how-to-topics-odbc.md) </span></span>  
 <span data-ttu-id="4b93d-130">[Comment les curseurs sont implémentés](../../native-client-odbc-cursors/implementation/how-cursors-are-implemented.md) </span><span class="sxs-lookup"><span data-stu-id="4b93d-130">[How Cursors Are Implemented](../../native-client-odbc-cursors/implementation/how-cursors-are-implemented.md) </span></span>  
 [<span data-ttu-id="4b93d-131">Utiliser des curseurs &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="4b93d-131">Use Cursors &#40;ODBC&#41;</span></span>](use-cursors-odbc.md)  
  
  
