---
title: Libération d’un descripteur d’instruction | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- reusing statement handles
- freeing statement handles
- statements [ODBC], statement handles
- SQLFreeStmt function
- ODBC applications, statements
- statement handles [ODBC]
ms.assetid: 96fdff84-0ca7-460a-a240-94ee826ea41c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8d7a1e93d222e2b87058bc878f7eca85313b4108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600850"
---
# <a name="freeing-a-statement-handle"></a><span data-ttu-id="ce25b-102">Libération d'un descripteur d'instruction</span><span class="sxs-lookup"><span data-stu-id="ce25b-102">Freeing a Statement Handle</span></span>
  <span data-ttu-id="ce25b-103">Il est plus efficace de réutiliser des descripteurs d'instruction que de les supprimer et d'en allouer de nouveaux.</span><span class="sxs-lookup"><span data-stu-id="ce25b-103">It is more efficient to reuse statement handles than to drop them and allocate new ones.</span></span> <span data-ttu-id="ce25b-104">Avant d'exécuter une nouvelle instruction SQL sur un descripteur d'instruction, les applications doivent s'assurer que les paramètres de l'instruction actuelle sont appropriés.</span><span class="sxs-lookup"><span data-stu-id="ce25b-104">Before executing a new SQL statement on a statement handle, applications should verify that the current statement settings are appropriate.</span></span> <span data-ttu-id="ce25b-105">Cela inclut les attributs d'instruction, les liaisons de paramètres et les liaisons de jeux de résultats.</span><span class="sxs-lookup"><span data-stu-id="ce25b-105">These include statement attributes, parameter bindings, and result set bindings.</span></span> <span data-ttu-id="ce25b-106">En règle générale, les paramètres et les jeux de résultats de l’ancienne instruction SQL doivent être détachés en appelant [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) avec les options SQL_RESET_PARAMS et SQL_UNBIND, puis reliés pour la nouvelle instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="ce25b-106">Generally, parameters and result sets for the old SQL statement must be unbound by calling [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with the SQL_RESET_PARAMS and SQL_UNBIND options and then re-bound for the new SQL statement.</span></span>  
  
 <span data-ttu-id="ce25b-107">Lorsque l’application a terminé d’utiliser l’instruction, elle appelle [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) pour libérer l’instruction.</span><span class="sxs-lookup"><span data-stu-id="ce25b-107">When the application has finished using the statement, it calls [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) to free the statement.</span></span> <span data-ttu-id="ce25b-108">Notez que **SQLDisconnect** libère automatiquement toutes les instructions sur une connexion.</span><span class="sxs-lookup"><span data-stu-id="ce25b-108">Note that **SQLDisconnect** automatically frees all statements on a connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce25b-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ce25b-109">See Also</span></span>  
 [<span data-ttu-id="ce25b-110">Exécution de requêtes &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="ce25b-110">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
