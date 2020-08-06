---
title: SQLFetchScroll | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLFetchScroll function
ms.assetid: 524a3985-a08d-4445-99e0-bb551a666615
author: rothja
ms.author: jroth
ms.openlocfilehash: eecf9714a97577ff490b642cee5b9c380333e40b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603527"
---
# <a name="sqlfetchscroll"></a><span data-ttu-id="479d6-102">SQLFetchScroll</span><span class="sxs-lookup"><span data-stu-id="479d6-102">SQLFetchScroll</span></span>
  <span data-ttu-id="479d6-103">**SQLFetchScroll** retourne un ensemble de lignes de données à l'application.</span><span class="sxs-lookup"><span data-stu-id="479d6-103">**SQLFetchScroll** returns one row set of data to the application.</span></span> <span data-ttu-id="479d6-104">La taille de l'ensemble de lignes est définie à l'aide de [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="479d6-104">The size of the row set is set using [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span> <span data-ttu-id="479d6-105">Le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client prend en charge toutes les instructions d'extraction définies (par exemple, SQL_FETCH_RELATIVE) avec les limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="479d6-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports all defined fetch instructions (for example, SQL_FETCH_RELATIVE) with the following limitations:</span></span>  
  
-   <span data-ttu-id="479d6-106">Si un curseur avant uniquement est défini pour l'instruction, SQL_FETCH_NEXT est requis et toute tentative d'extraction effectuée d'une autre manière retournera une erreur.</span><span class="sxs-lookup"><span data-stu-id="479d6-106">If a forward-only cursor is defined for the statement, SQL_FETCH_NEXT is required and attempts to fetch in any other fashion will result in an error return.</span></span>  
  
-   <span data-ttu-id="479d6-107">SQL_FETCH_BOOKMARK est uniquement pris en charge pour les curseurs statiques et les curseurs de jeu de clés.</span><span class="sxs-lookup"><span data-stu-id="479d6-107">SQL_FETCH_BOOKMARK is supported for static and keyset-driven cursors only.</span></span>  
  
## <a name="sqlfetchscroll-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="479d6-108">Prise en charge par SQLFetchScroll des fonctionnalités de date et heure améliorées</span><span class="sxs-lookup"><span data-stu-id="479d6-108">SQLFetchScroll Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="479d6-109">Les valeurs de colonne de résultats de types date/heure sont converties comme décrit dans [conversions de SQL en C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span><span class="sxs-lookup"><span data-stu-id="479d6-109">Result column values of date/time types are converted as described in [Conversions from SQL to C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span></span>  
  
 <span data-ttu-id="479d6-110">Pour plus d’informations, consultez améliorations de la [date et de l’heure &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="479d6-110">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlfetchscroll-support-for-large-clr-udts"></a><span data-ttu-id="479d6-111">Prise en charge par SQLFetchScroll des grands types CLR définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="479d6-111">SQLFetchScroll Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="479d6-112">**SQLFetchScroll** prend en charge les types CLR volumineux définis par l'utilisateur (UDT).</span><span class="sxs-lookup"><span data-stu-id="479d6-112">**SQLFetchScroll** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="479d6-113">Pour plus d’informations, consultez [types CLR volumineux définis par l’utilisateur &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="479d6-113">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="479d6-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="479d6-114">See Also</span></span>  
 <span data-ttu-id="479d6-115">[SQLFetchScroll, fonction](https://go.microsoft.com/fwlink/?LinkId=59343) </span><span class="sxs-lookup"><span data-stu-id="479d6-115">[SQLFetchScroll Function](https://go.microsoft.com/fwlink/?LinkId=59343) </span></span>  
 [<span data-ttu-id="479d6-116">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="479d6-116">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
