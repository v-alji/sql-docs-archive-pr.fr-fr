---
title: MSSQLSERVER_3619 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3619 (Database Engine error)
ms.assetid: 7d94f8d9-65ca-4fde-9c17-7b83e94a3779
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2328ee6366d47130a02c444bce65b7b655af7965
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612845"
---
# <a name="mssqlserver_3619"></a><span data-ttu-id="d494d-102">MSSQLSERVER_3619</span><span class="sxs-lookup"><span data-stu-id="d494d-102">MSSQLSERVER_3619</span></span>
    
## <a name="details"></a><span data-ttu-id="d494d-103">Détails</span><span class="sxs-lookup"><span data-stu-id="d494d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d494d-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="d494d-104">Product Name</span></span>|<span data-ttu-id="d494d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d494d-105">SQL Server</span></span>|  
|<span data-ttu-id="d494d-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="d494d-106">Event ID</span></span>|<span data-ttu-id="d494d-107">3619</span><span class="sxs-lookup"><span data-stu-id="d494d-107">3619</span></span>|  
|<span data-ttu-id="d494d-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="d494d-108">Event Source</span></span>|<span data-ttu-id="d494d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d494d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d494d-110">Composant</span><span class="sxs-lookup"><span data-stu-id="d494d-110">Component</span></span>|<span data-ttu-id="d494d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d494d-111">SQLEngine</span></span>|  
|<span data-ttu-id="d494d-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="d494d-112">Symbolic Name</span></span>|<span data-ttu-id="d494d-113">SYS_NOLOG</span><span class="sxs-lookup"><span data-stu-id="d494d-113">SYS_NOLOG</span></span>|  
|<span data-ttu-id="d494d-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="d494d-114">Message Text</span></span>|<span data-ttu-id="d494d-115">Impossible d'écrire un enregistrement de point de contrôle dans la base de données ID %d car le journal est saturé.</span><span class="sxs-lookup"><span data-stu-id="d494d-115">Could not write a checkpoint record in database ID %d because the log is out of space.</span></span> <span data-ttu-id="d494d-116">Demandez à l'administrateur de la base de données de tronquer ce journal ou d'allouer davantage d'espace aux fichiers journaux de la base de données.</span><span class="sxs-lookup"><span data-stu-id="d494d-116">Contact the database administrator to truncate the log or allocate more space to the database log files.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d494d-117">Explication</span><span class="sxs-lookup"><span data-stu-id="d494d-117">Explanation</span></span>  
 <span data-ttu-id="d494d-118">Le journal des transactions est saturé.</span><span class="sxs-lookup"><span data-stu-id="d494d-118">The transaction log is out of disk space.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d494d-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d494d-119">User Action</span></span>  
 <span data-ttu-id="d494d-120">Tronquez le journal pour libérer de l'espace ou allouez plus d'espace au journal.</span><span class="sxs-lookup"><span data-stu-id="d494d-120">Truncate the log to release some space, or allocate more space to the log.</span></span> <span data-ttu-id="d494d-121">Pour plus d'informations, consultez « Résolution des problèmes en cas de journal des transactions saturé (erreur 9002) » dans la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d494d-121">For more information see, "Troubleshooting a Full Transaction Log (Error 9002)" in SQL Server Books Online.</span></span>  
  
  
