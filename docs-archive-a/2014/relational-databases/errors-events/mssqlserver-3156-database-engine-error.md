---
title: MSSQLSERVER_3156 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3156 (Database Engine error)
ms.assetid: 345d8ed4-177e-4ec3-bab3-25d30000e323
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 25b5a037012a6d6b47b91e763a49cfb67b89f43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605474"
---
# <a name="mssqlserver_3156"></a><span data-ttu-id="35a89-102">MSSQLSERVER_3156</span><span class="sxs-lookup"><span data-stu-id="35a89-102">MSSQLSERVER_3156</span></span>
    
## <a name="details"></a><span data-ttu-id="35a89-103">Détails</span><span class="sxs-lookup"><span data-stu-id="35a89-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="35a89-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="35a89-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="35a89-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="35a89-105">Event ID</span></span>|<span data-ttu-id="35a89-106">3156</span><span class="sxs-lookup"><span data-stu-id="35a89-106">3156</span></span>|  
|<span data-ttu-id="35a89-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="35a89-107">Event Source</span></span>|<span data-ttu-id="35a89-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="35a89-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="35a89-109">Composant</span><span class="sxs-lookup"><span data-stu-id="35a89-109">Component</span></span>|<span data-ttu-id="35a89-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="35a89-110">SQLEngine</span></span>|  
|<span data-ttu-id="35a89-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="35a89-111">Symbolic Name</span></span>|<span data-ttu-id="35a89-112">LDDB_CANT_WRITE</span><span class="sxs-lookup"><span data-stu-id="35a89-112">LDDB_CANT_WRITE</span></span>|  
|<span data-ttu-id="35a89-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="35a89-113">Message Text</span></span>|<span data-ttu-id="35a89-114">Impossible de restaurer le fichier '%ls' en '%ls'.</span><span class="sxs-lookup"><span data-stu-id="35a89-114">File '%ls' cannot be restored to '%ls'.</span></span> <span data-ttu-id="35a89-115">Pour identifier un emplacement valide pour le fichier, faites appel à WITH MOVE.</span><span class="sxs-lookup"><span data-stu-id="35a89-115">Use WITH MOVE to identify a valid location for the file.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="35a89-116">Explication</span><span class="sxs-lookup"><span data-stu-id="35a89-116">Explanation</span></span>  
 <span data-ttu-id="35a89-117">Ce message général identifie les noms logiques ou physiques des fichiers qui n'ont pas pu être restaurés en raison d'un problème à l'emplacement spécifié.</span><span class="sxs-lookup"><span data-stu-id="35a89-117">This general message identifies the logical or physical file names of files that could not be restored because of a problem with the specified location.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="35a89-118">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="35a89-118">Possible Causes</span></span>  
 <span data-ttu-id="35a89-119">Les raisons peuvent être les suivantes :</span><span class="sxs-lookup"><span data-stu-id="35a89-119">The possible causes include the following:</span></span>  
  
-   <span data-ttu-id="35a89-120">Vous devez peut-être disposer d'un accès au répertoire Windows spécifié.</span><span class="sxs-lookup"><span data-stu-id="35a89-120">You might need access to the specified Windows directory.</span></span>  
  
-   <span data-ttu-id="35a89-121">Vous avez peut-être mal tapé le chemin d'accès ou spécifié un chemin d'accès qui n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="35a89-121">You might have mistyped the path or specified a path that does not exist.</span></span>  
  
-   <span data-ttu-id="35a89-122">Le nom du fichier est peut-être utilisé par un fichier qu'il est impossible de remplacer.</span><span class="sxs-lookup"><span data-stu-id="35a89-122">The file name might be being used by a file that cannot be overwritten.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="35a89-123">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="35a89-123">User Action</span></span>  
 <span data-ttu-id="35a89-124">Recherchez dans les journaux des erreurs d'autres messages susceptibles de vous fournir plus de détails.</span><span class="sxs-lookup"><span data-stu-id="35a89-124">Look at the error logs for other messages that provide more details.</span></span>  
  
 <span data-ttu-id="35a89-125">Corrigez le problème à l'emplacement spécifié, notamment en octroyant un accès, ou bien utilisez l'option WITH MOVE de votre instruction RESTORE pour déplacer le fichier.</span><span class="sxs-lookup"><span data-stu-id="35a89-125">Correct the problem with the specified location, for example, by granting access, or use the WITH MOVE option in your RESTORE statement to relocate the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a89-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="35a89-126">See Also</span></span>  
 <span data-ttu-id="35a89-127">[Restaurer une base de données à un nouvel emplacement &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="35a89-127">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="35a89-128">[Restaurer les fichiers à un nouvel emplacement &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="35a89-128">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 [<span data-ttu-id="35a89-129">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="35a89-129">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
