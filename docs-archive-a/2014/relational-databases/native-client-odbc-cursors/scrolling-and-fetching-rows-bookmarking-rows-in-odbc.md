---
title: Marquer des lignes dans ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], fetching rows
- ODBC cursors, fetching rows
- cursors [ODBC], scrolling rows
- ODBC cursors, scrolling rows
- bookmarks [ODBC]
ms.assetid: 9cfcd243-c9d4-4c2a-abc4-399dbabe5f6b
author: rothja
ms.author: jroth
ms.openlocfilehash: def05f478c16dcbcdc91771925a11b0b91da2e9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707524"
---
# <a name="bookmarking-rows-in-odbc"></a><span data-ttu-id="f4174-102">Création de signets pour des lignes dans ODBC</span><span class="sxs-lookup"><span data-stu-id="f4174-102">Bookmarking Rows in ODBC</span></span>
  <span data-ttu-id="f4174-103">Un signet est une valeur utilisée pour identifier une ligne de données.</span><span class="sxs-lookup"><span data-stu-id="f4174-103">A bookmark is a value used to identify a row of data.</span></span> <span data-ttu-id="f4174-104">La signification de la valeur du signet est connue uniquement du pilote ou de la source de données.</span><span class="sxs-lookup"><span data-stu-id="f4174-104">The meaning of the bookmark value is known only to the driver or data source.</span></span> <span data-ttu-id="f4174-105">Par exemple, il peut être aussi simple qu'un numéro de ligne ou aussi complexe qu'une adresse disque.</span><span class="sxs-lookup"><span data-stu-id="f4174-105">For example, it might be as simple as a row number or as complex as a disk address.</span></span> <span data-ttu-id="f4174-106">Dans ODBC, l'application demande un signet pour une ligne particulière, le stocke, puis le passe au curseur à retourner à la ligne.</span><span class="sxs-lookup"><span data-stu-id="f4174-106">In ODBC, the application requests a bookmark for a particular row, stores it, and passes it back to the cursor to return to the row.</span></span>  
  
 <span data-ttu-id="f4174-107">Lors de l’extraction de lignes avec [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md), une application peut utiliser un signet comme base pour la sélection de la ligne de départ.</span><span class="sxs-lookup"><span data-stu-id="f4174-107">When fetching rows with [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md), an application can use a bookmark as a basis for selecting the starting row.</span></span> <span data-ttu-id="f4174-108">Il s'agit d'une forme d'adressage absolu qui ne dépend pas de la position actuelle du curseur.</span><span class="sxs-lookup"><span data-stu-id="f4174-108">This is a form of absolute addressing because it does not depend on the current cursor position.</span></span> <span data-ttu-id="f4174-109">Pour faire défiler jusqu’à une ligne avec signet, l’application appelle **SQLFetchScroll** avec un *FetchOrientation* de SQL_FETCH_BOOKMARK.</span><span class="sxs-lookup"><span data-stu-id="f4174-109">To scroll to a bookmarked row, the application calls **SQLFetchScroll** with a *FetchOrientation* of SQL_FETCH_BOOKMARK.</span></span> <span data-ttu-id="f4174-110">Cette opération utilise le signet vers lequel pointe l'attribut d'option SQL_ATTR_FETCH_BOOKMARK_PTR.</span><span class="sxs-lookup"><span data-stu-id="f4174-110">This operation uses the bookmark pointed to by the SQL_ATTR_FETCH_BOOKMARK_PTR option attribute.</span></span> <span data-ttu-id="f4174-111">Elle retourne l'ensemble de lignes démarrant à la ligne identifiée par ce signet.</span><span class="sxs-lookup"><span data-stu-id="f4174-111">It returns the rowset starting with the row identified by that bookmark.</span></span> <span data-ttu-id="f4174-112">Une application peut spécifier un décalage pour cette opération dans l’argument *FetchOffset* de l’appel à **SQLFetchScroll**.</span><span class="sxs-lookup"><span data-stu-id="f4174-112">An application can specify an offset for this operation in the *FetchOffset* argument of the call to **SQLFetchScroll**.</span></span> <span data-ttu-id="f4174-113">Lorsqu'un décalage est spécifié, la première ligne de l'ensemble de lignes retourné est déterminée par l'ajout du nombre présent dans l'argument FetchOffset au numéro de la ligne identifiée par le signet.</span><span class="sxs-lookup"><span data-stu-id="f4174-113">When an offset is specified, the first row of the returned rowset is determined by adding the number in the FetchOffset argument to the number of the row identified by the bookmark.</span></span> <span data-ttu-id="f4174-114">Le pilote ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client prend en charge uniquement les signets sur les curseurs statiques et les curseurs de jeu de clés.</span><span class="sxs-lookup"><span data-stu-id="f4174-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver only supports bookmarks on static and keyset cursors.</span></span> <span data-ttu-id="f4174-115">Si un curseur dynamique est demandé lorsque les signets sont définis, un curseur de jeu de clés est ouvert à la place.</span><span class="sxs-lookup"><span data-stu-id="f4174-115">If a dynamic cursor is requested when bookmarks are set on, a keyset cursor is opened instead.</span></span>  
  
 <span data-ttu-id="f4174-116">Les signets peuvent également être utilisés avec la fonction **SQLBulkOperations** pour effectuer des opérations sur un ensemble de lignes en commençant par le signet.</span><span class="sxs-lookup"><span data-stu-id="f4174-116">Bookmarks can also be used with the **SQLBulkOperations** function to perform operations on a set of rows starting at the bookmark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4174-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f4174-117">See Also</span></span>  
 [<span data-ttu-id="f4174-118">Défilement et récupération (fetch) de lignes</span><span class="sxs-lookup"><span data-stu-id="f4174-118">Scrolling and Fetching Rows</span></span>](../native-client-ole-db-rowsets/fetching-rows.md)  
  
  
