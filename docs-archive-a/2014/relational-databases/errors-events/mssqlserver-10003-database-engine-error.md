---
title: MSSQLSERVER_10003 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10003 (Database Engine error)
ms.assetid: 9e2cb199-f077-4d88-8117-1b7550afc696
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8ea44fc9591602bfc8279924e10a1803d0d5a87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600994"
---
# <a name="mssqlserver_10003"></a><span data-ttu-id="2b501-102">MSSQLSERVER_10003</span><span class="sxs-lookup"><span data-stu-id="2b501-102">MSSQLSERVER_10003</span></span>
    
## <a name="details"></a><span data-ttu-id="2b501-103">Détails</span><span class="sxs-lookup"><span data-stu-id="2b501-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b501-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="2b501-104">Product Name</span></span>|<span data-ttu-id="2b501-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2b501-105">SQL Server</span></span>|  
|<span data-ttu-id="2b501-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="2b501-106">Event ID</span></span>|<span data-ttu-id="2b501-107">10003</span><span class="sxs-lookup"><span data-stu-id="2b501-107">10003</span></span>|  
|<span data-ttu-id="2b501-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="2b501-108">Event Source</span></span>|<span data-ttu-id="2b501-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2b501-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2b501-110">Composant</span><span class="sxs-lookup"><span data-stu-id="2b501-110">Component</span></span>|<span data-ttu-id="2b501-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2b501-111">SQLEngine</span></span>|  
|<span data-ttu-id="2b501-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="2b501-112">Symbolic Name</span></span>|<span data-ttu-id="2b501-113">HR_E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2b501-113">HR_E_OUTOFMEMORY</span></span>|  
|<span data-ttu-id="2b501-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="2b501-114">Message Text</span></span>|<span data-ttu-id="2b501-115">Le fournisseur n'a plus de mémoire.</span><span class="sxs-lookup"><span data-stu-id="2b501-115">The provider ran out of memory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2b501-116">Explication</span><span class="sxs-lookup"><span data-stu-id="2b501-116">Explanation</span></span>  
 <span data-ttu-id="2b501-117">L'insuffisance de mémoire système a provoqué une pénurie de mémoire pour le fournisseur OLE DB.</span><span class="sxs-lookup"><span data-stu-id="2b501-117">Low system memory has caused the OLE DB provider to run out of memory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2b501-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="2b501-118">User Action</span></span>  
 <span data-ttu-id="2b501-119">Redémarrez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b501-119">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2b501-120">Si cela ne change rien, redémarrez l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2b501-120">If that does not help, restart the computer.</span></span> <span data-ttu-id="2b501-121">Si le problème persiste, collectez les événements de trace OLE DB à l’aide de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] et fournissez ces données au support technique du fournisseur OLE DB.</span><span class="sxs-lookup"><span data-stu-id="2b501-121">If the problem persists, collect OLE DB trace events using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and provide this data to product support for the OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b501-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2b501-122">See Also</span></span>  
 <span data-ttu-id="2b501-123">[Modèles et autorisations du générateur de SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="2b501-123">[SQL Server Profiler Templates and Permissions](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="2b501-124">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="2b501-124">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
