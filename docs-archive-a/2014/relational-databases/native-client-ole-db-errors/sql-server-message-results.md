---
title: Résultats des messages SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- errors [OLE DB], SQL Server message results
- OLE DB error handling, SQL Server message results
ms.assetid: 6663c6f9-def1-4d9e-845b-2085e5efc401
author: rothja
ms.author: jroth
ms.openlocfilehash: aa63445b81ec89b87523fa29c50817e128d48515
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612792"
---
# <a name="sql-server-message-results"></a><span data-ttu-id="6ba4b-102">Résultats des messages SQL Server</span><span class="sxs-lookup"><span data-stu-id="6ba4b-102">SQL Server Message Results</span></span>
  <span data-ttu-id="6ba4b-103">Les [!INCLUDE[tsql](../../includes/tsql-md.md)] instructions suivantes ne génèrent pas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB les ensembles de lignes de fournisseur ou un nombre de lignes affectées lors de l’exécution :</span><span class="sxs-lookup"><span data-stu-id="6ba4b-103">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements do not generate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets or a count of affected rows when executed:</span></span>  
  
-   <span data-ttu-id="6ba4b-104">PRINT</span><span class="sxs-lookup"><span data-stu-id="6ba4b-104">PRINT</span></span>  
  
-   <span data-ttu-id="6ba4b-105">RAISERROR avec une gravité égale ou inférieure à 10</span><span class="sxs-lookup"><span data-stu-id="6ba4b-105">RAISERROR with a severity of 10 or lower</span></span>  
  
-   <span data-ttu-id="6ba4b-106">DBCC</span><span class="sxs-lookup"><span data-stu-id="6ba4b-106">DBCC</span></span>  
  
-   <span data-ttu-id="6ba4b-107">SET SHOWPLAN</span><span class="sxs-lookup"><span data-stu-id="6ba4b-107">SET SHOWPLAN</span></span>  
  
-   <span data-ttu-id="6ba4b-108">SET STATISTICS</span><span class="sxs-lookup"><span data-stu-id="6ba4b-108">SET STATISTICS</span></span>  
  
 <span data-ttu-id="6ba4b-109">Ces instructions retournent un ou plusieurs messages d'information ou entraînent le renvoi par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de messages d'information au lieu de résultats sous forme d'ensemble de lignes ou de nombre.</span><span class="sxs-lookup"><span data-stu-id="6ba4b-109">These statements either return one or more informational messages or cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to return informational messages in place of rowset or count results.</span></span> <span data-ttu-id="6ba4b-110">En cas de réussite de l’exécution, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client retourne S_OK et les messages sont disponibles pour le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consommateur du fournisseur OLE DB Native Client.</span><span class="sxs-lookup"><span data-stu-id="6ba4b-110">On successful execution, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns S_OK, and the messages are available to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer.</span></span>  
  
 <span data-ttu-id="6ba4b-111">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client retourne S_OK et un ou plusieurs messages d’information sont disponibles à la suite de l’exécution de nombreuses [!INCLUDE[tsql](../../includes/tsql-md.md)] instructions ou de l’exécution du consommateur d’une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fonction membre du fournisseur OLE DB Native Client.</span><span class="sxs-lookup"><span data-stu-id="6ba4b-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns S_OK and has one or more informational messages available following the execution of many [!INCLUDE[tsql](../../includes/tsql-md.md)] statements or the consumer execution of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function.</span></span>  
  
 <span data-ttu-id="6ba4b-112">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consommateur du fournisseur OLE DB Native Client qui autorise la spécification dynamique du texte de la requête doit vérifier les interfaces d’erreur après chaque exécution de fonction membre, quelle que soit la valeur du code de retour, la présence ou l’absence d’une référence d’interface **IRowset** ou **IMultipleResults** retournée, ou un nombre de lignes affectées.</span><span class="sxs-lookup"><span data-stu-id="6ba4b-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer allowing dynamic specification of query text should check error interfaces after every member function execution regardless of the value of the return code, the presence or absence of a returned **IRowset** or **IMultipleResults** interface reference, or a count of affected rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ba4b-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6ba4b-113">See Also</span></span>  
 [<span data-ttu-id="6ba4b-114">Erreurs</span><span class="sxs-lookup"><span data-stu-id="6ba4b-114">Errors</span></span>](errors.md)  
  
  
