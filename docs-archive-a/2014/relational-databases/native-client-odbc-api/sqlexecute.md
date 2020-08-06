---
title: SQLExecute | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLExecute function
ms.assetid: 4d7db8b6-611f-4fe4-be85-2a407059de45
author: rothja
ms.author: jroth
ms.openlocfilehash: 514436c65ef103cafae2189a03b560255b447eda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604433"
---
# <a name="sqlexecute"></a><span data-ttu-id="f5f20-102">SQLExecute</span><span class="sxs-lookup"><span data-stu-id="f5f20-102">SQLExecute</span></span>
  <span data-ttu-id="f5f20-103">Si l’attribut d’instruction SQL_SOPT_SS_PARAM_FOCUS n’a pas la valeur 0, SQLExecute retourne SQL_ERROR et génère un enregistrement de diagnostic avec SQLSTATE = HY024 et le message « valeur d’attribut non valide, SQL_SOPT_SS_PARAM_FOCUS (doit être égal à zéro au moment de l’exécution) ».</span><span class="sxs-lookup"><span data-stu-id="f5f20-103">If the statement attribute SQL_SOPT_SS_PARAM_FOCUS is not set to 0, SQLExecute will return SQL_ERROR and generate a diagnostic record with SQLSTATE=HY024 and the message "Invalid attribute value, SQL_SOPT_SS_PARAM_FOCUS (must be zero at execution time)".</span></span> <span data-ttu-id="f5f20-104">Pour plus d'informations sur SQL_SOPT_SS_PARAM_FOCUS, consultez [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="f5f20-104">For more information about SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5f20-105">Notes</span><span class="sxs-lookup"><span data-stu-id="f5f20-105">Remarks</span></span>  
 <span data-ttu-id="f5f20-106">Pour plus d’informations sur les paramètres table, consultez [paramètres table &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="f5f20-106">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5f20-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5f20-107">See Also</span></span>  
 <span data-ttu-id="f5f20-108">[SQLExecute](https://go.microsoft.com/fwlink/?LinkId=80708) </span><span class="sxs-lookup"><span data-stu-id="f5f20-108">[SQLExecute](https://go.microsoft.com/fwlink/?LinkId=80708) </span></span>  
 [<span data-ttu-id="f5f20-109">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="f5f20-109">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
