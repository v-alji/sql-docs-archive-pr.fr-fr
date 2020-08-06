---
title: MSSQLSERVER_3437 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3437 (Database Engine error)
ms.assetid: b38216e2-b650-43bd-97af-061d54f60031
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ed8f2050f6f1b38bc5f3fcb7a9700b80e52f2763
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612846"
---
# <a name="mssqlserver_3437"></a><span data-ttu-id="3c478-102">MSSQLSERVER_3437</span><span class="sxs-lookup"><span data-stu-id="3c478-102">MSSQLSERVER_3437</span></span>
    
## <a name="details"></a><span data-ttu-id="3c478-103">Détails</span><span class="sxs-lookup"><span data-stu-id="3c478-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c478-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="3c478-104">Product Name</span></span>|<span data-ttu-id="3c478-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3c478-105">SQL Server</span></span>|  
|<span data-ttu-id="3c478-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="3c478-106">Event ID</span></span>|<span data-ttu-id="3c478-107">3437</span><span class="sxs-lookup"><span data-stu-id="3c478-107">3437</span></span>|  
|<span data-ttu-id="3c478-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="3c478-108">Event Source</span></span>|<span data-ttu-id="3c478-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3c478-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3c478-110">Composant</span><span class="sxs-lookup"><span data-stu-id="3c478-110">Component</span></span>|<span data-ttu-id="3c478-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3c478-111">SQLEngine</span></span>|  
|<span data-ttu-id="3c478-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="3c478-112">Symbolic Name</span></span>|<span data-ttu-id="3c478-113">NODTC</span><span class="sxs-lookup"><span data-stu-id="3c478-113">NODTC</span></span>|  
|<span data-ttu-id="3c478-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="3c478-114">Message Text</span></span>|<span data-ttu-id="3c478-115">Une erreur s'est produite lors de la récupération de la base de données '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="3c478-115">An error occurred while recovering database '%.\*ls'.</span></span> <span data-ttu-id="3c478-116">Impossible de se connecter à MS DTC pour vérifier l'état d'avancement de la transaction %S_XID.</span><span class="sxs-lookup"><span data-stu-id="3c478-116">Unable to connect to Microsoft Distributed Transaction Coordinator (MS DTC) to check the completion status of transaction %S_XID.</span></span> <span data-ttu-id="3c478-117">Corrigez MS DTC et réexécutez la récupération.</span><span class="sxs-lookup"><span data-stu-id="3c478-117">Fix MS DTC, and run recovery again.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3c478-118">Explication</span><span class="sxs-lookup"><span data-stu-id="3c478-118">Explanation</span></span>  
 <span data-ttu-id="3c478-119">Une ou plusieurs transactions distribuées utilisant MS DTC ([!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator) étaient incomplètes lorsque la base de données a été fermée.</span><span class="sxs-lookup"><span data-stu-id="3c478-119">One or more distributed transactions that were using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) were incomplete when the database was shut down.</span></span> <span data-ttu-id="3c478-120">La récupération de cette base de données a échoué car [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas se connecter à MS DTC pour terminer ou restaurer les transactions.</span><span class="sxs-lookup"><span data-stu-id="3c478-120">Recovery of this database failed because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot connect to MS DTC to complete or roll back the transactions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3c478-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="3c478-121">User Action</span></span>  
 <span data-ttu-id="3c478-122">Pour récupérer cette base de données, vous devez d'abord résoudre le problème avec MS DTC.</span><span class="sxs-lookup"><span data-stu-id="3c478-122">To recover this database, you must first resolve the problem with MS DTC.</span></span> <span data-ttu-id="3c478-123">Pour analyser ce problème, examinez les journaux des événements Windows.</span><span class="sxs-lookup"><span data-stu-id="3c478-123">To investigate the problem with MS DTC, examine the Windows event logs.</span></span> <span data-ttu-id="3c478-124">Si vous ne parvenez pas à résoudre le problème avec MS DTC et à récupérer la base de données, restaurez une sauvegarde de la base de données.</span><span class="sxs-lookup"><span data-stu-id="3c478-124">If you cannot resolve the problem with MS DTC and recover the database, restore a backup of database.</span></span>  
  
  
