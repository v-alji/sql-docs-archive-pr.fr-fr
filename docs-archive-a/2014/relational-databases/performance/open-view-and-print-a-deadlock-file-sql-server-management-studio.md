---
title: Ouvrir, afficher et imprimer un fichier d’interblocage (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- deadlocks [SQL Server], printing files
- deadlocks [SQL Server], opening files
- opening deadlock files
- printing deadlock files
ms.assetid: 5061b13f-2cb7-457a-b8d0-fbd437b510ab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 08bacd7a99e45e10163216c69057b167088441ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611739"
---
# <a name="open-view-and-print-a-deadlock-file-sql-server-management-studio"></a><span data-ttu-id="c359f-102">Ouvrir, afficher et imprimer un fichier d'interblocage (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c359f-102">Open, View, and Print a Deadlock File (SQL Server Management Studio)</span></span>
  <span data-ttu-id="c359f-103">Lorsque le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] génère un interblocage, vous pouvez capturer et enregistrer les informations correspondantes dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="c359f-103">When [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] generates a deadlock, you can capture and save the deadlock information to a file.</span></span> <span data-ttu-id="c359f-104">Une fois le fichier de blocage enregistré, vous pouvez l'ouvrir dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour le consulter ou l'imprimer.</span><span class="sxs-lookup"><span data-stu-id="c359f-104">After you have saved the deadlock file, you can open it in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to view or print.</span></span>  
  
### <a name="to-open-and-view-a-deadlock-file"></a><span data-ttu-id="c359f-105">Pour ouvrir et consulter un fichier de blocage</span><span class="sxs-lookup"><span data-stu-id="c359f-105">To open and view a deadlock file</span></span>  
  
1.  <span data-ttu-id="c359f-106">Dans le menu **fichier** de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , pointez sur **ouvrir**, puis cliquez sur **fichier**.</span><span class="sxs-lookup"><span data-stu-id="c359f-106">On the **File** menu in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="c359f-107">Dans la boîte de dialogue **Ouvrir un fichier** , sélectionnez le type de fichier .xdl dans la zone **Fichiers de type** .</span><span class="sxs-lookup"><span data-stu-id="c359f-107">In the **Open File** dialog box, select the .xdl file type in the **Files of type** box.</span></span> <span data-ttu-id="c359f-108">Vous obtenez alors une liste filtrée comportant uniquement les fichiers de blocage.</span><span class="sxs-lookup"><span data-stu-id="c359f-108">You will now have a filtered list of only deadlock files.</span></span>  
  
### <a name="to-print-a-deadlock-file"></a><span data-ttu-id="c359f-109">Pour imprimer un fichier de blocage</span><span class="sxs-lookup"><span data-stu-id="c359f-109">To print a deadlock file</span></span>  
  
1.  <span data-ttu-id="c359f-110">Dans le menu **Fichier** de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], pointez sur **Ouvrir** , puis cliquez sur **Fichier**.</span><span class="sxs-lookup"><span data-stu-id="c359f-110">On the **File** menu in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], point to **Open,** and then click **File**.</span></span>  
  
2.  <span data-ttu-id="c359f-111">Dans la boîte de dialogue **Ouvrir un fichier** , sélectionnez le type de fichier .xdl dans la zone **Fichiers de type** .</span><span class="sxs-lookup"><span data-stu-id="c359f-111">In the **Open File** dialog box, select the .xdl file type in the **Files of type** box.</span></span> <span data-ttu-id="c359f-112">Vous obtenez alors une liste filtrée comportant uniquement les fichiers de blocage.</span><span class="sxs-lookup"><span data-stu-id="c359f-112">You will now have a filtered list of only deadlock files.</span></span>  
  
3.  <span data-ttu-id="c359f-113">Sélectionnez le fichier de blocage à imprimer, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="c359f-113">Select the deadlock file you want to print, and click **Open**.</span></span>  
  
4.  <span data-ttu-id="c359f-114">Dans le menu **Fichier** , cliquez sur **Imprimer**.</span><span class="sxs-lookup"><span data-stu-id="c359f-114">On the **File** menu, click **Print.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c359f-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c359f-115">See Also</span></span>  
 [<span data-ttu-id="c359f-116">Enregistrer les événements Deadlock Graph &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="c359f-116">Save Deadlock Graphs &#40;SQL Server Profiler&#41;</span></span>](save-deadlock-graphs-sql-server-profiler.md)  
  
  
