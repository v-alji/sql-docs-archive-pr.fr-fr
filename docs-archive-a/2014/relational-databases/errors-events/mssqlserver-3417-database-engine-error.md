---
title: MSSQLSERVER_3417 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3417 (Database Engine error)
ms.assetid: 005829c8-cf57-4828-818a-bbe8ee2e00f0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 680e5a4266c7d0d9aaacb7b3deb9525a002077e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612853"
---
# <a name="mssqlserver_3417"></a><span data-ttu-id="4a2de-102">MSSQLSERVER_3417</span><span class="sxs-lookup"><span data-stu-id="4a2de-102">MSSQLSERVER_3417</span></span>
    
## <a name="details"></a><span data-ttu-id="4a2de-103">Détails</span><span class="sxs-lookup"><span data-stu-id="4a2de-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4a2de-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="4a2de-104">Product Name</span></span>|<span data-ttu-id="4a2de-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4a2de-105">SQL Server</span></span>|  
|<span data-ttu-id="4a2de-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="4a2de-106">Event ID</span></span>|<span data-ttu-id="4a2de-107">3417</span><span class="sxs-lookup"><span data-stu-id="4a2de-107">3417</span></span>|  
|<span data-ttu-id="4a2de-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="4a2de-108">Event Source</span></span>|<span data-ttu-id="4a2de-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4a2de-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4a2de-110">Composant</span><span class="sxs-lookup"><span data-stu-id="4a2de-110">Component</span></span>|<span data-ttu-id="4a2de-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4a2de-111">SQLEngine</span></span>|  
|<span data-ttu-id="4a2de-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="4a2de-112">Symbolic Name</span></span>|<span data-ttu-id="4a2de-113">REC_BADMASTER</span><span class="sxs-lookup"><span data-stu-id="4a2de-113">REC_BADMASTER</span></span>|  
|<span data-ttu-id="4a2de-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="4a2de-114">Message Text</span></span>|<span data-ttu-id="4a2de-115">Impossible de récupérer la base de données master.</span><span class="sxs-lookup"><span data-stu-id="4a2de-115">Cannot recover the master database.</span></span> <span data-ttu-id="4a2de-116">Impossible d'exécuter SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4a2de-116">SQL Server is unable to run.</span></span> <span data-ttu-id="4a2de-117">Restaurez la base master à partir d'une sauvegarde complète, réparez-la ou reconstruisez-la.</span><span class="sxs-lookup"><span data-stu-id="4a2de-117">Restore master from a full backup, repair it, or rebuild it.</span></span> <span data-ttu-id="4a2de-118">Pour plus d'informations sur la façon de reconstruire la base de données master, consultez la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4a2de-118">For more information about how to rebuild the master database, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4a2de-119">Explication</span><span class="sxs-lookup"><span data-stu-id="4a2de-119">Explanation</span></span>  
 <span data-ttu-id="4a2de-120">SQL Server ne peut pas démarrer la base de données **MASTER**.</span><span class="sxs-lookup"><span data-stu-id="4a2de-120">SQL Server cannot start the **master** database.</span></span> <span data-ttu-id="4a2de-121">Si les bases de données **MASTER** ou **tempdb** ne peuvent pas être mises en ligne, SQL Server ne peut pas s’exécuter.</span><span class="sxs-lookup"><span data-stu-id="4a2de-121">If the **master** or **tempdb** cannot be brought online, SQL Server cannot run.</span></span> <span data-ttu-id="4a2de-122">Cette erreur est généralement précédée d'autres erreurs.</span><span class="sxs-lookup"><span data-stu-id="4a2de-122">This error is usually preceded by other errors.</span></span> <span data-ttu-id="4a2de-123">Étudiez les journaux d'erreurs pour trouver la racine du problème.</span><span class="sxs-lookup"><span data-stu-id="4a2de-123">Review error logs to find the root cause.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4a2de-124">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="4a2de-124">User Action</span></span>  
 <span data-ttu-id="4a2de-125">Restaurez la sauvegarde de la base de données ou réparez la base de données.</span><span class="sxs-lookup"><span data-stu-id="4a2de-125">Restore backup of the database or repair the database.</span></span>  
  
  
