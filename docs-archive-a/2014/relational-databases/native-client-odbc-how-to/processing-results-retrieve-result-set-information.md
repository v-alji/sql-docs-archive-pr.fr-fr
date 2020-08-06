---
title: Récupérer les informations du jeu de résultats (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- result sets [ODBC]
- result sets [ODBC], fetching
ms.assetid: 34f235e4-f80b-4123-8764-9deb18506f14
author: rothja
ms.author: jroth
ms.openlocfilehash: 0f7ed275eb9b6558a77160c3c7fb2fc233c199cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603492"
---
# <a name="retrieve-result-set-information-odbc"></a><span data-ttu-id="b5222-102">Récupérer des informations du jeu de résultats (ODBC)</span><span class="sxs-lookup"><span data-stu-id="b5222-102">Retrieve Result Set Information (ODBC)</span></span>
    
### <a name="to-get-information-about-a-result-set"></a><span data-ttu-id="b5222-103">Pour obtenir des informations sur un jeu de résultats</span><span class="sxs-lookup"><span data-stu-id="b5222-103">To get information about a result set</span></span>  
  
1.  <span data-ttu-id="b5222-104">Appelez [SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) pour obtenir le nombre de colonnes dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="b5222-104">Call [SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) to get the number of columns in the result set.</span></span>  
  
2.  <span data-ttu-id="b5222-105">Pour chaque colonne de l'ensemble de résultats :</span><span class="sxs-lookup"><span data-stu-id="b5222-105">For each column in the result set:</span></span>  
  
    -   <span data-ttu-id="b5222-106">Appelez [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) pour obtenir des informations sur la colonne de résultats.</span><span class="sxs-lookup"><span data-stu-id="b5222-106">Call [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) to get information about the result column.</span></span>  
  
     <span data-ttu-id="b5222-107">ou</span><span class="sxs-lookup"><span data-stu-id="b5222-107">Or</span></span>  
  
    -   <span data-ttu-id="b5222-108">Appelez [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) pour obtenir des informations de descripteur spécifiques sur la colonne de résultats.</span><span class="sxs-lookup"><span data-stu-id="b5222-108">Call [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) to get specific descriptor information about the result column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5222-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5222-109">See Also</span></span>  
 <span data-ttu-id="b5222-110">[Rubriques de procédures relatives au traitement des résultats &#40;ODBC&#41;](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="b5222-110">[Processing Results How-to Topics &#40;ODBC&#41;](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="b5222-111">Détermination des caractéristiques d’un jeu de résultats &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="b5222-111">Determining the Characteristics of a Result Set &#40;ODBC&#41;</span></span>](../native-client-odbc-results/determining-the-characteristics-of-a-result-set-odbc.md)  
  
  
