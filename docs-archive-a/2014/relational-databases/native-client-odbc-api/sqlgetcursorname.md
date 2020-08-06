---
title: SQLGetCursorName | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetCursorName function
ms.assetid: 3a427a23-28ef-49aa-b9ec-6cab0914bdf3
author: rothja
ms.author: jroth
ms.openlocfilehash: 01ce6e42b4e8753d07309ec7ce298d4f743d4a6d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599998"
---
# <a name="sqlgetcursorname"></a><span data-ttu-id="b9d7a-102">SQLGetCursorName</span><span class="sxs-lookup"><span data-stu-id="b9d7a-102">SQLGetCursorName</span></span>
  <span data-ttu-id="b9d7a-103">Si l'application ne spécifie pas de nom de curseur, le pilote ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client en génère un pour l'application lors de la génération du curseur.</span><span class="sxs-lookup"><span data-stu-id="b9d7a-103">If the application does not specify a cursor name, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver generates one for the application upon cursor generation.</span></span> <span data-ttu-id="b9d7a-104">L'application peut utiliser **SQLGetCursorName** pour récupérer le nom du curseur défini par le pilote pour les instructions UPDATE et DELETE positionnées.</span><span class="sxs-lookup"><span data-stu-id="b9d7a-104">The application can use **SQLGetCursorName** to retrieve the driver-defined cursor name for positioned UPDATE and DELETE statements.</span></span> <span data-ttu-id="b9d7a-105">L'application n'a pas besoin d'appeler **SQLSetCursorName** pour tirer parti des instructions de manipulation de données positionnées.</span><span class="sxs-lookup"><span data-stu-id="b9d7a-105">The application does not need to call **SQLSetCursorName** to take advantage of positioned data manipulation statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9d7a-106">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9d7a-106">See Also</span></span>  
 <span data-ttu-id="b9d7a-107">[SQLGetCursorName, fonction](https://go.microsoft.com/fwlink/?LinkId=59349) </span><span class="sxs-lookup"><span data-stu-id="b9d7a-107">[SQLGetCursorName Function](https://go.microsoft.com/fwlink/?LinkId=59349) </span></span>  
 [<span data-ttu-id="b9d7a-108">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="b9d7a-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
