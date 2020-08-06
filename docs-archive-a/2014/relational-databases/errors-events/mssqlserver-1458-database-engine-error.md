---
title: MSSQLSERVER_1458 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1458 (Database Engine error)
ms.assetid: adc78c59-a6f2-432b-9a07-fdd1dc2b9026
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: efa45177a92402b25099be5bb3e3dcc91a5fa6d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612906"
---
# <a name="mssqlserver_1458"></a><span data-ttu-id="cbf42-102">MSSQLSERVER_1458</span><span class="sxs-lookup"><span data-stu-id="cbf42-102">MSSQLSERVER_1458</span></span>
    
## <a name="details"></a><span data-ttu-id="cbf42-103">Détails</span><span class="sxs-lookup"><span data-stu-id="cbf42-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cbf42-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="cbf42-104">Product Name</span></span>|<span data-ttu-id="cbf42-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cbf42-105">SQL Server</span></span>|  
|<span data-ttu-id="cbf42-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="cbf42-106">Event ID</span></span>|<span data-ttu-id="cbf42-107">1458</span><span class="sxs-lookup"><span data-stu-id="cbf42-107">1458</span></span>|  
|<span data-ttu-id="cbf42-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="cbf42-108">Event Source</span></span>|<span data-ttu-id="cbf42-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cbf42-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cbf42-110">Composant</span><span class="sxs-lookup"><span data-stu-id="cbf42-110">Component</span></span>|<span data-ttu-id="cbf42-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cbf42-111">SQLEngine</span></span>|  
|<span data-ttu-id="cbf42-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="cbf42-112">Symbolic Name</span></span>|<span data-ttu-id="cbf42-113">DBM_FAILREDO_ON_PRIMARY</span><span class="sxs-lookup"><span data-stu-id="cbf42-113">DBM_FAILREDO_ON_PRIMARY</span></span>|  
|<span data-ttu-id="cbf42-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="cbf42-114">Message Text</span></span>|<span data-ttu-id="cbf42-115">La copie principale de la base de données '%.\*ls' a rencontré l'erreur %d, état %d, gravité %d.</span><span class="sxs-lookup"><span data-stu-id="cbf42-115">The principal copy of the '%.\*ls' database encountered error %d, status %d, severity %d.</span></span> <span data-ttu-id="cbf42-116">La mise en miroir de bases de données a été interrompue.</span><span class="sxs-lookup"><span data-stu-id="cbf42-116">Database mirroring has been suspended.</span></span> <span data-ttu-id="cbf42-117">Essayez de résoudre l'erreur et reprenez la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="cbf42-117">Try to resolve the error condition, and resume mirroring.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cbf42-118">Explication</span><span class="sxs-lookup"><span data-stu-id="cbf42-118">Explanation</span></span>  
 <span data-ttu-id="cbf42-119">Ce message indique que la base de données principale a rencontré une erreur qui a provoqué la suspension de la mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="cbf42-119">This messages indicates that the principal database encountered an error that caused database mirroring to be suspended.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cbf42-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="cbf42-120">User Action</span></span>  
 <span data-ttu-id="cbf42-121">Dans la plupart des cas, cette erreur se corrige toute seule.</span><span class="sxs-lookup"><span data-stu-id="cbf42-121">Most cases of this error are self correcting.</span></span> <span data-ttu-id="cbf42-122">Si le problème persiste, le redémarrage de la base de données ou de l'instance du serveur corrige généralement le problème.</span><span class="sxs-lookup"><span data-stu-id="cbf42-122">If the problem persists, restarting the database or server instance typically corrects the problem.</span></span> <span data-ttu-id="cbf42-123">Pour plus d'informations, consultez le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur chaque serveur partenaire pour rechercher l'erreur associée qui a précédé ce message.</span><span class="sxs-lookup"><span data-stu-id="cbf42-123">For more information, look in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log on each partner for the associated error that preceded this message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbf42-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cbf42-124">See Also</span></span>  
 [<span data-ttu-id="cbf42-125">Surveillance de la mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cbf42-125">Monitoring Database Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  
