---
title: Utilisation de l’auto-extraction avec les curseurs ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC cursors, autofetch
- autofetch option
- cursors [ODBC], autofetch
ms.assetid: 57bd55f4-8945-4d8d-9f58-d30c81d2a514
author: rothja
ms.author: jroth
ms.openlocfilehash: e3d9374cf9ceab4a7e73cc0059783486f2bf9c41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612296"
---
# <a name="using-autofetch-with-odbc-cursors"></a><span data-ttu-id="058a6-102">Utilisation de l'auto-extraction avec les curseurs ODBC</span><span class="sxs-lookup"><span data-stu-id="058a6-102">Using Autofetch with ODBC Cursors</span></span>
  <span data-ttu-id="058a6-103">En cas de connexion à une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client prend en charge une option d’auto-extraction lors de l’utilisation d’un type de curseur de serveur.</span><span class="sxs-lookup"><span data-stu-id="058a6-103">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports an autofetch option when using any server cursor type.</span></span> <span data-ttu-id="058a6-104">Avec l’auto-extraction, la fonction **SQLExecute** ou **SQLExecDirect** qui ouvre le curseur a également une fonction [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md)(SQL_FIRST) implicite.</span><span class="sxs-lookup"><span data-stu-id="058a6-104">With autofetch, the **SQLExecute** or **SQLExecDirect** function that opens the cursor also has an implicit [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md)(SQL_FIRST) function.</span></span> <span data-ttu-id="058a6-105">Les lignes qui comprennent le premier ensemble de lignes sont retournées aux variables d'application liée dans le cadre de l'exécution d'instruction, économisant un autre aller-retour sur le réseau jusqu'au serveur.</span><span class="sxs-lookup"><span data-stu-id="058a6-105">The rows comprising the first rowset are returned to the bound application variables as part of the statement execution, saving another roundtrip across the network to the server.</span></span> <span data-ttu-id="058a6-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) n’est pas pris en charge lorsque l’option d’auto-extraction est activée ; les colonnes du jeu de résultats doivent être liées à des variables de programme.</span><span class="sxs-lookup"><span data-stu-id="058a6-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) is not supported when the autofetch option is enabled; the result set columns must be bound to program variables.</span></span>  
  
 <span data-ttu-id="058a6-107">Les applications demandent l'auto-extraction en attribuant à l'attribut d'instruction SQL_SOPT_SS_CURSOR_OPTIONS spécifique au pilote la valeur SQL_CO_AF.</span><span class="sxs-lookup"><span data-stu-id="058a6-107">Applications request autofetch by setting the driver-specific SQL_SOPT_SS_CURSOR_OPTIONS statement attribute to SQL_CO_AF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="058a6-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="058a6-108">See Also</span></span>  
 [<span data-ttu-id="058a6-109">Détails de programmation de curseur &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="058a6-109">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
