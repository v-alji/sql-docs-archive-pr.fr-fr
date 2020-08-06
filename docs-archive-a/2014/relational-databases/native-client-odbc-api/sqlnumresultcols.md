---
title: SQLNumResultCols | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLNumResultCols function
ms.assetid: f79d8b3c-521e-4e50-a564-21d73ae5767b
author: rothja
ms.author: jroth
ms.openlocfilehash: 45e72165eef621dc377b02ed3d2e7e1e3cf7ab8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614018"
---
# <a name="sqlnumresultcols"></a><span data-ttu-id="7b49b-102">SQLNumResultCols</span><span class="sxs-lookup"><span data-stu-id="7b49b-102">SQLNumResultCols</span></span>
  <span data-ttu-id="7b49b-103">Pour les instructions exécutées, le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client n'accède pas au serveur pour indiquer le nombre de colonnes d'un jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="7b49b-103">For executed statements, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not visit the server to report the number of columns in a result set.</span></span> <span data-ttu-id="7b49b-104">Dans ce cas, `SQLNumResultCols` n’entraîne pas l’aller-retour du serveur.</span><span class="sxs-lookup"><span data-stu-id="7b49b-104">In this case, `SQLNumResultCols` does not cause a server roundtrip.</span></span> <span data-ttu-id="7b49b-105">À l’instar de [SQLDescribeCol](sqldescribecol.md) et [SQLColAttribute](sqlcolattribute.md), l’appel `SQLNumResultCols` de sur des instructions préparées mais non exécutées génère un aller-retour sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="7b49b-105">Like [SQLDescribeCol](sqldescribecol.md) and [SQLColAttribute](sqlcolattribute.md), calling `SQLNumResultCols` on prepared but not executed statements generates a server roundtrip.</span></span>  
  
 <span data-ttu-id="7b49b-106">Lorsqu'une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] ou un lot d'instructions retourne plusieurs ensembles de lignes de résultat, il est possible que le nombre de colonnes de jeu de résultats soit différent d'un ensemble de lignes à un autre.</span><span class="sxs-lookup"><span data-stu-id="7b49b-106">When a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statement batch returns multiple result row sets, it is possible for the number of result set columns to change from one set to another.</span></span> <span data-ttu-id="7b49b-107">`SQLNumResultCols`doit être appelé pour chaque ensemble.</span><span class="sxs-lookup"><span data-stu-id="7b49b-107">`SQLNumResultCols` should be called for each set.</span></span> <span data-ttu-id="7b49b-108">Lorsque le nombre de colonnes change, l'application doit réassocier les valeurs de données avant d'extraire les résultats de ligne.</span><span class="sxs-lookup"><span data-stu-id="7b49b-108">When the number of columns changes, the application should rebind data values prior to fetching row results.</span></span> <span data-ttu-id="7b49b-109">Pour plus d'informations sur la gestion de plusieurs retours de jeux de résultats, consultez [SQLMoreResults](sqlmoreresults.md).</span><span class="sxs-lookup"><span data-stu-id="7b49b-109">For more information about handling multiple result set returns, see [SQLMoreResults](sqlmoreresults.md).</span></span>  
  
 <span data-ttu-id="7b49b-110">Les améliorations apportées au moteur de base de données à partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] permettent à SQLNumResultCols d’obtenir des descriptions plus précises des résultats attendus.</span><span class="sxs-lookup"><span data-stu-id="7b49b-110">Improvements in the database engine starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow SQLNumResultCols to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="7b49b-111">Ces résultats plus précis peuvent différer des valeurs retournées par SQLNumResultCols dans les versions précédentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b49b-111">These more accurate results may differ from the values returned by SQLNumResultCols in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7b49b-112">Pour plus d’informations, consultez [Découverte des métadonnées](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="7b49b-112">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b49b-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7b49b-113">See Also</span></span>  
 <span data-ttu-id="7b49b-114">[SQLNumResultCols fonction)](https://go.microsoft.com/fwlink/?LinkId=59359) </span><span class="sxs-lookup"><span data-stu-id="7b49b-114">[SQLNumResultCols Function](https://go.microsoft.com/fwlink/?LinkId=59359) </span></span>  
 [<span data-ttu-id="7b49b-115">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="7b49b-115">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
