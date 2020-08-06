---
title: SQLParamData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLParamData function
ms.assetid: 92349482-ea22-4a6a-8484-e9c6566794fa
author: rothja
ms.author: jroth
ms.openlocfilehash: a4e0e8b31a65f28ce83e0d114231bdedd7a35a4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614017"
---
# <a name="sqlparamdata"></a><span data-ttu-id="4ca33-102">SQLParamData</span><span class="sxs-lookup"><span data-stu-id="4ca33-102">SQLParamData</span></span>
  <span data-ttu-id="4ca33-103">Lorsque SQLParamData retourne le *ValuePtrPtr* associé à un paramètre table, l’application doit appeler SQLPutData avec *StrLen_Or_Ind*.</span><span class="sxs-lookup"><span data-stu-id="4ca33-103">When SQLParamData returns the *ValuePtrPtr* associated with a table-valued parameter, the application should call SQLPutData with *StrLen_Or_Ind*.</span></span> <span data-ttu-id="4ca33-104">Si *StrLen_Or_Ind* a une valeur supérieure à 0, cela signifie que l'application est prête et que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client peut collecter les données de paramètre pour la prochaine ligne de paramètre table.</span><span class="sxs-lookup"><span data-stu-id="4ca33-104">If *StrLen_Or_Ind* has a value greater than 0, it means that the application is ready for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client to gather parameter data for the next table-valued parameter row.</span></span> <span data-ttu-id="4ca33-105">Si *StrLen_Or_Ind* a une valeur égale à 0, cela signifie qu'il n'y a plus de lignes de données pour le paramètre table.</span><span class="sxs-lookup"><span data-stu-id="4ca33-105">If *StrLen_Or_Ind* has a value of 0, it means there are no more rows of data for the table-valued parameter.</span></span> <span data-ttu-id="4ca33-106">Pour plus d’informations, consultez [liaison et transfert de données des paramètres table et des valeurs de colonne](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span><span class="sxs-lookup"><span data-stu-id="4ca33-106">For more information, see [Binding and Data Transfer of Table-Valued Parameters and Column Values](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span></span>  
  
 <span data-ttu-id="4ca33-107">Pour plus d’informations sur les paramètres table, consultez [paramètres table &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="4ca33-107">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca33-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4ca33-108">See Also</span></span>  
 <span data-ttu-id="4ca33-109">[SQLParamData](/sql/odbc/reference/syntax/sqlparamdata-function) </span><span class="sxs-lookup"><span data-stu-id="4ca33-109">[SQLParamData](/sql/odbc/reference/syntax/sqlparamdata-function) </span></span>  
 [<span data-ttu-id="4ca33-110">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="4ca33-110">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
