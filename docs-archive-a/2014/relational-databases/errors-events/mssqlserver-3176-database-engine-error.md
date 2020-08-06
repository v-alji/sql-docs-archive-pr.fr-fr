---
title: MSSQLSERVER_3176 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3176 (Database Engine error)
ms.assetid: 4be24c64-2d52-4cb4-b4d7-36efbe4555b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 64e1a836995fe8738bb5c2ff0cb4de10d84d1f29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605470"
---
# <a name="mssqlserver_3176"></a><span data-ttu-id="60212-102">MSSQLSERVER_3176</span><span class="sxs-lookup"><span data-stu-id="60212-102">MSSQLSERVER_3176</span></span>
    
## <a name="details"></a><span data-ttu-id="60212-103">Détails</span><span class="sxs-lookup"><span data-stu-id="60212-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60212-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="60212-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="60212-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="60212-105">Event ID</span></span>|<span data-ttu-id="60212-106">3176</span><span class="sxs-lookup"><span data-stu-id="60212-106">3176</span></span>|  
|<span data-ttu-id="60212-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="60212-107">Event Source</span></span>|<span data-ttu-id="60212-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="60212-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="60212-109">Composant</span><span class="sxs-lookup"><span data-stu-id="60212-109">Component</span></span>|<span data-ttu-id="60212-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="60212-110">SQLEngine</span></span>|  
|<span data-ttu-id="60212-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="60212-111">Symbolic Name</span></span>|<span data-ttu-id="60212-112">LDDB_FILE_CLAIM</span><span class="sxs-lookup"><span data-stu-id="60212-112">LDDB_FILE_CLAIM</span></span>|  
|<span data-ttu-id="60212-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="60212-113">Message Text</span></span>|<span data-ttu-id="60212-114">Le fichier '%ls' est revendiqué par '%ls'(%d) et '%ls'(%d).</span><span class="sxs-lookup"><span data-stu-id="60212-114">File '%ls' is claimed by '%ls'(%d) and '%ls'(%d).</span></span> <span data-ttu-id="60212-115">La clause WITH MOVE peut être utilisée pour déplacer un ou plusieurs fichiers.</span><span class="sxs-lookup"><span data-stu-id="60212-115">The WITH MOVE clause can be used to relocate one or more files.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="60212-116">Explication</span><span class="sxs-lookup"><span data-stu-id="60212-116">Explanation</span></span>  
 <span data-ttu-id="60212-117">Tentative d'utilisation d'un fichier dans plusieurs buts.</span><span class="sxs-lookup"><span data-stu-id="60212-117">Attempting to use a file for more than one purpose.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="60212-118">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="60212-118">Possible Causes</span></span>  
 <span data-ttu-id="60212-119">Une autre base de données utilise déjà le nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="60212-119">Another database is already using the file name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="60212-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="60212-120">User Action</span></span>  
 <span data-ttu-id="60212-121">Restaurez les fichiers de la base de données à un emplacement différent.</span><span class="sxs-lookup"><span data-stu-id="60212-121">Restore the database files to a different location.</span></span> <span data-ttu-id="60212-122">Dans une instruction RESTORE, utilisez une clause WITH MOVE pour déplacer chaque fichier.</span><span class="sxs-lookup"><span data-stu-id="60212-122">In a RESTORE statement, use a WITH MOVE clause to move each file.</span></span> <span data-ttu-id="60212-123">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], modifiez les emplacements des fichiers dans la grille **Restaurer les fichiers de la base de données en tant que** de la boîte de dialogue **Options de restauration de la base de données**.</span><span class="sxs-lookup"><span data-stu-id="60212-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], change the file locations in the **Restore the database files as** grid of the **Restore Database Options** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60212-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="60212-124">See Also</span></span>  
 <span data-ttu-id="60212-125">[Restaurer une base de données à un nouvel emplacement &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="60212-125">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="60212-126">[Restaurer les fichiers à un nouvel emplacement &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="60212-126">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 [<span data-ttu-id="60212-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60212-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
