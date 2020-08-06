---
title: Utilisation des curseurs (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC cursors, about ODBC cursors
- ODBC applications, cursors
- cursors [ODBC]
- ODBC cursors
ms.assetid: 51322f92-0d76-44c9-9c33-9223676cf1d3
author: rothja
ms.author: jroth
ms.openlocfilehash: 61afedab4f4a1e309a08d9c2421ca7889811da8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707500"
---
# <a name="using-cursors-odbc"></a><span data-ttu-id="53866-102">Utilisation de curseurs (ODBC)</span><span class="sxs-lookup"><span data-stu-id="53866-102">Using Cursors (ODBC)</span></span>
  <span data-ttu-id="53866-103">ODBC prend en charge un modèle de curseur qui autorise :</span><span class="sxs-lookup"><span data-stu-id="53866-103">ODBC supports a cursor model that allows:</span></span>  
  
-   <span data-ttu-id="53866-104">plusieurs types de curseurs ;</span><span class="sxs-lookup"><span data-stu-id="53866-104">Several types of cursors.</span></span>  
  
-   <span data-ttu-id="53866-105">le défilement et le positionnement dans un curseur ;</span><span class="sxs-lookup"><span data-stu-id="53866-105">Scrolling and positioning within a cursor.</span></span>  
  
-   <span data-ttu-id="53866-106">plusieurs options de concurrence ;</span><span class="sxs-lookup"><span data-stu-id="53866-106">Several concurrency options.</span></span>  
  
-   <span data-ttu-id="53866-107">des mises à jour positionnées.</span><span class="sxs-lookup"><span data-stu-id="53866-107">Positioned updates.</span></span>  
  
 <span data-ttu-id="53866-108">Les applications ODBC ont rarement besoin de déclarer ou d'ouvrir des curseurs. De même, elles utilisent peu souvent les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] relatives aux curseurs.</span><span class="sxs-lookup"><span data-stu-id="53866-108">ODBC applications rarely declare and open cursors or use any cursor-related [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="53866-109">ODBC ouvre automatiquement un curseur pour chaque jeu de résultats retourné par une instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="53866-109">ODBC automatically opens a cursor for every result set returned from an SQL statement.</span></span> <span data-ttu-id="53866-110">Les caractéristiques des curseurs sont contrôlées par des attributs d’instruction définis avec [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) avant l’exécution de l’instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="53866-110">The characteristics of the cursors are controlled by statement attributes set with [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) before the SQL statement is executed.</span></span> <span data-ttu-id="53866-111">Les fonctions de l'API ODBC relatives au traitement des jeux de résultats prennent en charge l'ensemble des fonctionnalités des curseurs, y compris l'extraction, le défilement et les mises à jour positionnées.</span><span class="sxs-lookup"><span data-stu-id="53866-111">The ODBC API functions for processing result sets support the full range of cursor functionality, including fetching, scrolling, and positioned updates.</span></span>  
  
 <span data-ttu-id="53866-112">Le tableau suivant compare la façon dont les scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] et les applications ODBC utilisent les curseurs.</span><span class="sxs-lookup"><span data-stu-id="53866-112">This is a comparison of how [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts and ODBC applications work with cursors.</span></span>  
  
|<span data-ttu-id="53866-113">Action</span><span class="sxs-lookup"><span data-stu-id="53866-113">Action</span></span>|[!INCLUDE[tsql](../../includes/tsql-md.md)]|<span data-ttu-id="53866-114">ODBC</span><span class="sxs-lookup"><span data-stu-id="53866-114">ODBC</span></span>|  
|------------|------------------------|----------|  
|<span data-ttu-id="53866-115">Définir le comportement du curseur</span><span class="sxs-lookup"><span data-stu-id="53866-115">Define cursor behavior</span></span>|<span data-ttu-id="53866-116">Spécifier par le biais de paramètres DECLARE CURSOR</span><span class="sxs-lookup"><span data-stu-id="53866-116">Specify through DECLARE CURSOR parameters</span></span>|<span data-ttu-id="53866-117">Définir des attributs de curseur à l’aide de [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md)</span><span class="sxs-lookup"><span data-stu-id="53866-117">Set cursor attributes by using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md)</span></span>|  
|<span data-ttu-id="53866-118">Ouvrir un curseur</span><span class="sxs-lookup"><span data-stu-id="53866-118">Open a cursor</span></span>|<span data-ttu-id="53866-119">DÉCLARER le curseur ouvert *cursor_name*</span><span class="sxs-lookup"><span data-stu-id="53866-119">DECLARE CURSOR OPEN *cursor_name*</span></span>|<span data-ttu-id="53866-120">**SQLExecDirect** ou **SQLExecute**</span><span class="sxs-lookup"><span data-stu-id="53866-120">**SQLExecDirect** or **SQLExecute**</span></span>|  
|<span data-ttu-id="53866-121">Extraire des lignes</span><span class="sxs-lookup"><span data-stu-id="53866-121">Fetch rows</span></span>|<span data-ttu-id="53866-122">FETCH</span><span class="sxs-lookup"><span data-stu-id="53866-122">FETCH</span></span>|<span data-ttu-id="53866-123">**SQLFetch** ou [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md)</span><span class="sxs-lookup"><span data-stu-id="53866-123">**SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md)</span></span>|  
|<span data-ttu-id="53866-124">Mise à jour positionnée</span><span class="sxs-lookup"><span data-stu-id="53866-124">Positioned update</span></span>|<span data-ttu-id="53866-125">Clause WHERE CURRENT OF sur UPDATE ou DELETE</span><span class="sxs-lookup"><span data-stu-id="53866-125">WHERE CURRENT OF clause on UPDATE or DELETE</span></span>|<span data-ttu-id="53866-126">**SQLSetPos**</span><span class="sxs-lookup"><span data-stu-id="53866-126">**SQLSetPos**</span></span>|  
|<span data-ttu-id="53866-127">Fermer un curseur</span><span class="sxs-lookup"><span data-stu-id="53866-127">Close a cursor</span></span>|<span data-ttu-id="53866-128">FERMER *CURSOR_NAME* libérer</span><span class="sxs-lookup"><span data-stu-id="53866-128">CLOSE *cursor_name* DEALLOCATE</span></span>|[<span data-ttu-id="53866-129">SQLCloseCursor</span><span class="sxs-lookup"><span data-stu-id="53866-129">SQLCloseCursor</span></span>](../native-client-odbc-api/sqlclosecursor.md)|  
  
 <span data-ttu-id="53866-130">Les curseurs côté serveur implémentés dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prennent en charge les fonctionnalités du modèle de curseur ODBC.</span><span class="sxs-lookup"><span data-stu-id="53866-130">The server cursors implemented in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support the functionality of the ODBC cursor model.</span></span> <span data-ttu-id="53866-131">Le pilote [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client utilise des curseurs côté serveur pour prendre en charge les fonctionnalités de curseur de l'API ODBC.</span><span class="sxs-lookup"><span data-stu-id="53866-131">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client driver uses server cursors to support the cursor functionality of the ODBC API.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="53866-132">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="53866-132">In This Section</span></span>  
  
-   [<span data-ttu-id="53866-133">Comment les curseurs sont implémentés</span><span class="sxs-lookup"><span data-stu-id="53866-133">How Cursors Are Implemented</span></span>](implementation/how-cursors-are-implemented.md)  
  
-   [<span data-ttu-id="53866-134">Types de curseurs</span><span class="sxs-lookup"><span data-stu-id="53866-134">Cursor Types</span></span>](cursor-types.md)  
  
-   [<span data-ttu-id="53866-135">Comportements des curseurs</span><span class="sxs-lookup"><span data-stu-id="53866-135">Cursor Behaviors</span></span>](cursor-behaviors.md)  
  
-   [<span data-ttu-id="53866-136">Propriétés de curseur</span><span class="sxs-lookup"><span data-stu-id="53866-136">Cursor Properties</span></span>](properties/cursor-properties.md)  
  
-   [<span data-ttu-id="53866-137">Détails de programmation de curseur &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="53866-137">Cursor Programming Details &#40;ODBC&#41;</span></span>](programming/cursor-programming-details-odbc.md)  
  
-   [<span data-ttu-id="53866-138">Défilement et récupération (fetch) de lignes</span><span class="sxs-lookup"><span data-stu-id="53866-138">Scrolling and Fetching Rows</span></span>](../native-client-ole-db-rowsets/fetching-rows.md)  
  
-   [<span data-ttu-id="53866-139">Mises à jour positionnées &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="53866-139">Positioned Updates &#40;ODBC&#41;</span></span>](positioned-updates-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="53866-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="53866-140">See Also</span></span>  
 <span data-ttu-id="53866-141">[SQL Server Native Client &#40;&#41;ODBC](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="53866-141">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 <span data-ttu-id="53866-142">[FERMER &#40;&#41;Transact-SQL](/sql/t-sql/language-elements/close-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="53866-142">[CLOSE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/close-transact-sql) </span></span>  
 <span data-ttu-id="53866-143">[Curseurs](../../relational-databases/cursors.md) </span><span class="sxs-lookup"><span data-stu-id="53866-143">[Cursors](../../relational-databases/cursors.md) </span></span>  
 <span data-ttu-id="53866-144">[LIBÉRER &#40;&#41;Transact-SQL](/sql/t-sql/language-elements/deallocate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="53866-144">[DEALLOCATE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/deallocate-transact-sql) </span></span>  
 <span data-ttu-id="53866-145">[DÉCLARER un curseur &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-cursor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="53866-145">[DECLARE CURSOR &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-cursor-transact-sql) </span></span>  
 <span data-ttu-id="53866-146">[FETCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/fetch-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="53866-146">[FETCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/fetch-transact-sql) </span></span>  
 [<span data-ttu-id="53866-147">OPEN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="53866-147">OPEN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/open-transact-sql)  
  
  
