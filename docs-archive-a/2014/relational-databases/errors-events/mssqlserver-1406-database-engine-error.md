---
title: MSSQLSERVER_1406 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1406 (Database Engine error)
ms.assetid: 915f97de-9b74-41f8-8bd5-b2d061416718
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: adaa0084b875f720c477189e0e8e085af124f4cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702947"
---
# <a name="mssqlserver_1406"></a><span data-ttu-id="ed437-102">MSSQLSERVER_1406</span><span class="sxs-lookup"><span data-stu-id="ed437-102">MSSQLSERVER_1406</span></span>
    
## <a name="details"></a><span data-ttu-id="ed437-103">Détails</span><span class="sxs-lookup"><span data-stu-id="ed437-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ed437-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="ed437-104">Product Name</span></span>|<span data-ttu-id="ed437-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ed437-105">SQL Server</span></span>|  
|<span data-ttu-id="ed437-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="ed437-106">Event ID</span></span>|<span data-ttu-id="ed437-107">1406</span><span class="sxs-lookup"><span data-stu-id="ed437-107">1406</span></span>|  
|<span data-ttu-id="ed437-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="ed437-108">Event Source</span></span>|<span data-ttu-id="ed437-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ed437-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ed437-110">Composant</span><span class="sxs-lookup"><span data-stu-id="ed437-110">Component</span></span>|<span data-ttu-id="ed437-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ed437-111">SQLEngine</span></span>|  
|<span data-ttu-id="ed437-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="ed437-112">Symbolic Name</span></span>|<span data-ttu-id="ed437-113">DBM_BADSTATEFORFORCESERVICE</span><span class="sxs-lookup"><span data-stu-id="ed437-113">DBM_BADSTATEFORFORCESERVICE</span></span>|  
|<span data-ttu-id="ed437-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="ed437-114">Message Text</span></span>|<span data-ttu-id="ed437-115">Impossible de forcer le service en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="ed437-115">Unable to force service safely.</span></span> <span data-ttu-id="ed437-116">Supprimez la mise en miroir de bases de données et récupérez la base de données "%.\*ls" pour y accéder.</span><span class="sxs-lookup"><span data-stu-id="ed437-116">Remove database mirroring and recover database "%.\*ls" to gain access.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ed437-117">Explication</span><span class="sxs-lookup"><span data-stu-id="ed437-117">Explanation</span></span>  
 <span data-ttu-id="ed437-118">Le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] ne peut pas forcer le service car l'état de la mise en miroir ne peut pas garantir le bon fonctionnement du processus impliqué pour forcer le service.</span><span class="sxs-lookup"><span data-stu-id="ed437-118">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] cannot force service because the mirroring state cannot guarantee that the force service process would work correctly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ed437-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="ed437-119">User Action</span></span>  
 <span data-ttu-id="ed437-120">Supprimez la mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="ed437-120">Remove database mirroring.</span></span> <span data-ttu-id="ed437-121">Vous pouvez ensuite récupérer la base de données miroir pour y accéder.</span><span class="sxs-lookup"><span data-stu-id="ed437-121">You can then recover the mirror database to gain access to it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed437-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed437-122">See Also</span></span>  
 <span data-ttu-id="ed437-123">[Forcer le service dans une session de mise en miroir de bases de données &#40;Transact-SQL&#41;](../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="ed437-123">[Force Service in a Database Mirroring Session &#40;Transact-SQL&#41;](../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md) </span></span>  
 [<span data-ttu-id="ed437-124">Suppression d’une mise en miroir des bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ed437-124">Removing Database Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  
