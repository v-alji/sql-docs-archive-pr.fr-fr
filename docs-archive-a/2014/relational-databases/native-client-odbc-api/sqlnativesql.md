---
title: SQLNativeSql | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLNativeSql function
ms.assetid: 2d999fec-9e22-4514-ad5f-22a64b82f95b
author: rothja
ms.author: jroth
ms.openlocfilehash: 433b086dc36a79cb82868edebac9f0a4814c21fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614019"
---
# <a name="sqlnativesql"></a><span data-ttu-id="2046a-102">SQLNativeSql</span><span class="sxs-lookup"><span data-stu-id="2046a-102">SQLNativeSql</span></span>
  <span data-ttu-id="2046a-103">Le pilote ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client répond aux demandes **SQLNativeSql** sans visiter le serveur.</span><span class="sxs-lookup"><span data-stu-id="2046a-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver satisfies **SQLNativeSql** requests without visiting the server.</span></span> <span data-ttu-id="2046a-104">La fonction teste efficacement la syntaxe d'instructions SQL.</span><span class="sxs-lookup"><span data-stu-id="2046a-104">The function efficiently tests the syntax of SQL statements.</span></span> <span data-ttu-id="2046a-105">La vérification de la syntaxe ne détermine pas si des identificateurs ou les résultats d'expressions dans les instructions SQL sont valides, et l'exécution du code SQL natif [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retourné par **SQLNativeSql** peut échouer.</span><span class="sxs-lookup"><span data-stu-id="2046a-105">Syntax checking does not determine if identifiers or the results of expressions in the SQL statements are valid, and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native SQL returned by **SQLNativeSql** can fail to run.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2046a-106">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2046a-106">See Also</span></span>  
 <span data-ttu-id="2046a-107">[SQLNativeSql fonction)](https://go.microsoft.com/fwlink/?LinkID=59358) </span><span class="sxs-lookup"><span data-stu-id="2046a-107">[SQLNativeSql Function](https://go.microsoft.com/fwlink/?LinkID=59358) </span></span>  
 [<span data-ttu-id="2046a-108">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="2046a-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
