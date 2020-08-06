---
title: MSSQLSERVER_3181 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3181 (Database Engine error)
ms.assetid: e6d2e716-5263-477c-ad0e-7bcbfef4c1f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f18509d9a18ba8be1f4e40c93bff5abfcae3d69c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605469"
---
# <a name="mssqlserver_3181"></a><span data-ttu-id="9e470-102">MSSQLSERVER_3181</span><span class="sxs-lookup"><span data-stu-id="9e470-102">MSSQLSERVER_3181</span></span>
    
## <a name="details"></a><span data-ttu-id="9e470-103">Détails</span><span class="sxs-lookup"><span data-stu-id="9e470-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9e470-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="9e470-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="9e470-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="9e470-105">Event ID</span></span>|<span data-ttu-id="9e470-106">3181</span><span class="sxs-lookup"><span data-stu-id="9e470-106">3181</span></span>|  
|<span data-ttu-id="9e470-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="9e470-107">Event Source</span></span>|<span data-ttu-id="9e470-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9e470-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9e470-109">Composant</span><span class="sxs-lookup"><span data-stu-id="9e470-109">Component</span></span>|<span data-ttu-id="9e470-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9e470-110">SQLEngine</span></span>|  
|<span data-ttu-id="9e470-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="9e470-111">Symbolic Name</span></span>|<span data-ttu-id="9e470-112">LDDB_STORAGE_VERIFY</span><span class="sxs-lookup"><span data-stu-id="9e470-112">LDDB_STORAGE_VERIFY</span></span>|  
|<span data-ttu-id="9e470-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="9e470-113">Message Text</span></span>|<span data-ttu-id="9e470-114">La restauration de cette sauvegarde risque de rencontrer des problèmes d'espace de stockage.</span><span class="sxs-lookup"><span data-stu-id="9e470-114">Attempting to restore this backup may encounter storage space problems.</span></span> <span data-ttu-id="9e470-115">D'autres messages fourniront des détails.</span><span class="sxs-lookup"><span data-stu-id="9e470-115">Subsequent messages will provide details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9e470-116">Explication</span><span class="sxs-lookup"><span data-stu-id="9e470-116">Explanation</span></span>  
 <span data-ttu-id="9e470-117">L'instruction RESTORE VERIFYONLY vérifie l'espace de stockage disponible sur le disque sur lequel la base de données doit être restaurée.</span><span class="sxs-lookup"><span data-stu-id="9e470-117">The RESTORE VERIFYONLY statement checks the available storage space on the disk to which the database is to be restored.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="9e470-118">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="9e470-118">Possible Causes</span></span>  
 <span data-ttu-id="9e470-119">L'espace disque disponible est peut-être insuffisant pour restaurer la sauvegarde en cours de vérification.</span><span class="sxs-lookup"><span data-stu-id="9e470-119">The available disk space may be insufficient to restore the backup being verified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9e470-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9e470-120">User Action</span></span>  
 <span data-ttu-id="9e470-121">Restaurez la sauvegarde à un emplacement doté de suffisamment d'espace disque ou prévoyez plus d'espace sur le disque.</span><span class="sxs-lookup"><span data-stu-id="9e470-121">Restore the backup to a location with sufficient disk space, or provide more space on the disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e470-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9e470-122">See Also</span></span>  
 <span data-ttu-id="9e470-123">[Restaurer une base de données à un nouvel emplacement &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9e470-123">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="9e470-124">[Restaurer les fichiers à un nouvel emplacement &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9e470-124">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="9e470-125">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9e470-125">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="9e470-126">RESTORE VERIFYONLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9e470-126">RESTORE VERIFYONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql)  
  
  
