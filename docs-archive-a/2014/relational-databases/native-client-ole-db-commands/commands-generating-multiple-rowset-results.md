---
title: Commandes générant des résultats dans plusieurs ensembles de lignes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- multiple rowsets
- rowsets [OLE DB], multiple
- SQL Server Native Client OLE DB provider, commands
- SQL Server Native Client OLE DB provider, multiple rowsets
- commands [OLE DB]
- multiple-rowset results
ms.assetid: 4567668d-35fd-4162-b61f-f7536862cdcb
author: rothja
ms.author: jroth
ms.openlocfilehash: 8b42a89c0b043e4c72e8b5634cf70e16b435167a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695592"
---
# <a name="commands-generating-multiple-rowset-results"></a><span data-ttu-id="e0135-102">Commandes générant des résultats dans plusieurs ensembles de lignes</span><span class="sxs-lookup"><span data-stu-id="e0135-102">Commands Generating Multiple-Rowset Results</span></span>
  <span data-ttu-id="e0135-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client peut retourner plusieurs ensembles de lignes à partir d' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instructions.</span><span class="sxs-lookup"><span data-stu-id="e0135-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can return multiple rowsets from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements.</span></span> <span data-ttu-id="e0135-104">Les instructions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retournent des résultats dans plusieurs ensembles de lignes dans les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="e0135-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements return multiple-rowset results under the following conditions:</span></span>  
  
-   <span data-ttu-id="e0135-105">des instructions SQL groupées sont soumises en tant que commande unique ;</span><span class="sxs-lookup"><span data-stu-id="e0135-105">Batched SQL statements are submitted as a single command.</span></span>  
  
-   <span data-ttu-id="e0135-106">des procédures stockées implémentent un lot d'instructions SQL ;</span><span class="sxs-lookup"><span data-stu-id="e0135-106">Stored procedures implement a batch of SQL statements.</span></span>  
  
## <a name="batches"></a><span data-ttu-id="e0135-107">Lots</span><span class="sxs-lookup"><span data-stu-id="e0135-107">Batches</span></span>  
 <span data-ttu-id="e0135-108">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client reconnaît le point-virgule comme délimiteur de lot pour les instructions SQL :</span><span class="sxs-lookup"><span data-stu-id="e0135-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes the semicolon character as a batch delimiter for SQL statements:</span></span>  
  
```  
WCHAR*       wSQLString = L"SELECT * FROM Categories; "  
                          L"SELECT * FROM Products";  
```  
  
 <span data-ttu-id="e0135-109">Il est plus efficace d'envoyer plusieurs instructions SQL dans un lot que d'exécuter chaque instruction SQL séparément.</span><span class="sxs-lookup"><span data-stu-id="e0135-109">Sending multiple SQL statements in one batch is more efficient than executing each SQL statement separately.</span></span> <span data-ttu-id="e0135-110">L'envoi d'un lot réduit les allers-retours sur le réseau entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="e0135-110">Sending one batch reduces the network round trips from the client to the server.</span></span>  
  
## <a name="stored-procedures"></a><span data-ttu-id="e0135-111">Procédures stockées</span><span class="sxs-lookup"><span data-stu-id="e0135-111">Stored Procedures</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e0135-112">retourne un jeu de résultats pour chaque instruction dans une procédure stockée ; ainsi, la plupart des procédures stockées [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retournent plusieurs jeux de résultats.</span><span class="sxs-lookup"><span data-stu-id="e0135-112">returns a result set for each statement in a stored procedure, so most [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures return multiple result sets.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e0135-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="e0135-113">In This Section</span></span>  
  
-   [<span data-ttu-id="e0135-114">Utilisation d'IMultipleResults pour traiter plusieurs jeux de résultats</span><span class="sxs-lookup"><span data-stu-id="e0135-114">Using IMultipleResults to Process Multiple Result Sets</span></span>](using-imultipleresults-to-process-multiple-result-sets.md)  
  
## <a name="see-also"></a><span data-ttu-id="e0135-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e0135-115">See Also</span></span>  
 [<span data-ttu-id="e0135-116">Commandes</span><span class="sxs-lookup"><span data-stu-id="e0135-116">Commands</span></span>](commands.md)  
  
  
