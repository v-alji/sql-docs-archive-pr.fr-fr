---
title: SQLProcedures | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLProcedures function
ms.assetid: ec41f017-f5e0-40ef-913a-65d206068631
author: rothja
ms.author: jroth
ms.openlocfilehash: e37f15841a36eb95c1e9263d137ba2734d622367
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614014"
---
# <a name="sqlprocedures"></a><span data-ttu-id="ef7bd-102">SQLProcedures</span><span class="sxs-lookup"><span data-stu-id="ef7bd-102">SQLProcedures</span></span>
  <span data-ttu-id="ef7bd-103">Toutes les procédures stockées [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retournent une valeur.</span><span class="sxs-lookup"><span data-stu-id="ef7bd-103">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures return a value.</span></span> <span data-ttu-id="ef7bd-104">Les rapports **SQLProcedures** SQL_PT_FUNCTION pour la colonne de l’ensemble de résultats PROCEDURE_TYPE.</span><span class="sxs-lookup"><span data-stu-id="ef7bd-104">**SQLProcedures** reports SQL_PT_FUNCTION for the result set column PROCEDURE_TYPE.</span></span>  
  
 <span data-ttu-id="ef7bd-105">**SQLProcedures** retourne SQL_SUCCESS si des valeurs existent pour les paramètres *nomcatalogue, SchemaName* ou *procname* .</span><span class="sxs-lookup"><span data-stu-id="ef7bd-105">**SQLProcedures** returns SQL_SUCCESS whether or not values exist for *CatalogName, SchemaName,* or *ProcName* parameters.</span></span> <span data-ttu-id="ef7bd-106">**SQLFetch** retourne SQL_NO_DATA lorsque des valeurs non valides sont utilisées dans ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="ef7bd-106">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="ef7bd-107">Les **SQLProcedures** peuvent être exécutés sur un curseur côté serveur statique.</span><span class="sxs-lookup"><span data-stu-id="ef7bd-107">**SQLProcedures** can be executed on a static server cursor.</span></span> <span data-ttu-id="ef7bd-108">Une tentative d’exécution de **SQLProcedures** sur un curseur pouvant être mis à jour (dynamique ou de jeu de clés) retourne SQL_SUCCESS_WITH_INFO, ce qui indique que le type de curseur a été modifié.</span><span class="sxs-lookup"><span data-stu-id="ef7bd-108">An attempt to execute **SQLProcedures** on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO, indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="ef7bd-109">**SQLProcedures** retourne des informations sur les procédures dont les noms correspondent à *procname* et peuvent être exécutés par l’utilisateur actuel, ou pour lesquels l’utilisateur actuel a reçu l’autorisation View definition.</span><span class="sxs-lookup"><span data-stu-id="ef7bd-109">**SQLProcedures** returns information about any procedures whose names match *ProcName* and can be executed by the current user, or for which the current user has been granted VIEW DEFINITION permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef7bd-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef7bd-110">See Also</span></span>  
 <span data-ttu-id="ef7bd-111">[SQLProcedures (fonction)](https://go.microsoft.com/fwlink/?LinkId=59364) </span><span class="sxs-lookup"><span data-stu-id="ef7bd-111">[SQLProcedures Function](https://go.microsoft.com/fwlink/?LinkId=59364) </span></span>  
 [<span data-ttu-id="ef7bd-112">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="ef7bd-112">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
