---
title: MSSQLSERVER_3431 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3431 (Database Engine error)
ms.assetid: 9541217f-e5c6-4a12-a19a-006058f1d3f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9b62047a25d71ca05dc3ab03651e5672353bc0a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612851"
---
# <a name="mssqlserver_3431"></a><span data-ttu-id="18b79-102">MSSQLSERVER_3431</span><span class="sxs-lookup"><span data-stu-id="18b79-102">MSSQLSERVER_3431</span></span>
    
## <a name="details"></a><span data-ttu-id="18b79-103">Détails</span><span class="sxs-lookup"><span data-stu-id="18b79-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="18b79-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="18b79-104">Product Name</span></span>|<span data-ttu-id="18b79-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="18b79-105">SQL Server</span></span>|  
|<span data-ttu-id="18b79-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="18b79-106">Event ID</span></span>|<span data-ttu-id="18b79-107">3431</span><span class="sxs-lookup"><span data-stu-id="18b79-107">3431</span></span>|  
|<span data-ttu-id="18b79-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="18b79-108">Event Source</span></span>|<span data-ttu-id="18b79-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="18b79-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="18b79-110">Composant</span><span class="sxs-lookup"><span data-stu-id="18b79-110">Component</span></span>|<span data-ttu-id="18b79-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="18b79-111">SQLEngine</span></span>|  
|<span data-ttu-id="18b79-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="18b79-112">Symbolic Name</span></span>|<span data-ttu-id="18b79-113">UNRESOLVED_XACT</span><span class="sxs-lookup"><span data-stu-id="18b79-113">UNRESOLVED_XACT</span></span>|  
|<span data-ttu-id="18b79-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="18b79-114">Message Text</span></span>|<span data-ttu-id="18b79-115">Impossible de récupérer la base de données '%.\*ls' (ID de base de données %d) en raison de transactions externes non résolues.</span><span class="sxs-lookup"><span data-stu-id="18b79-115">Could not recover database '%.\*ls' (database ID %d) because of unresolved transaction outcomes.</span></span> <span data-ttu-id="18b79-116">Les transactions MS DTC (Microsoft Distributed Transaction Coordinator) ont été préparées, mais MS DTC n'a pas réussi à déterminer la résolution.</span><span class="sxs-lookup"><span data-stu-id="18b79-116">Microsoft Distributed Transaction Coordinator (MS DTC) transactions were prepared, but MS DTC was unable to determine the resolution.</span></span> <span data-ttu-id="18b79-117">Pour corriger ce problème, réparez MS DTC, effectuez une restauration à partir d'une sauvegarde complète ou réparez la base de données.</span><span class="sxs-lookup"><span data-stu-id="18b79-117">To resolve, either fix MS DTC, restore from a full backup, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="18b79-118">Explication</span><span class="sxs-lookup"><span data-stu-id="18b79-118">Explanation</span></span>  
 <span data-ttu-id="18b79-119">Une ou plusieurs transactions distribuées utilisant MS DTC ([!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator) étaient incomplètes lorsque la base de données a été fermée.</span><span class="sxs-lookup"><span data-stu-id="18b79-119">One or more distributed transactions that were using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) were incomplete when the database was shut down.</span></span> <span data-ttu-id="18b79-120">La récupération de cette base de données a échoué car [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas terminer ou restaurer les transactions sans avoir plus d’informations de la part de MS DTC.</span><span class="sxs-lookup"><span data-stu-id="18b79-120">Recovery of this database failed because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot complete the transactions or roll back the transactions without more information from MS DTC.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="18b79-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="18b79-121">User Action</span></span>  
 <span data-ttu-id="18b79-122">Pour récupérer cette base de données, vous devez d'abord résoudre le problème avec MS DTC.</span><span class="sxs-lookup"><span data-stu-id="18b79-122">To recover this database, you must first resolve the problem with MS DTC.</span></span> <span data-ttu-id="18b79-123">Pour analyser ce problème, examinez les journaux des événements Windows.</span><span class="sxs-lookup"><span data-stu-id="18b79-123">To investigate the problem with MS DTC, examine the Windows event logs.</span></span> <span data-ttu-id="18b79-124">Si vous ne parvenez pas à résoudre le problème avec MS DTC et à récupérer la base de données, restaurez une sauvegarde de la base de données.</span><span class="sxs-lookup"><span data-stu-id="18b79-124">If you cannot resolve the problem with MS DTC and recover the database, restore a backup of database.</span></span>  
  
  
