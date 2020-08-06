---
title: MSSQLSERVER_1105 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1105 (Database Engine error)
ms.assetid: e7f4ad02-8c7f-4bb9-9781-2c86253f2138
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dea326fab7edd6a5c155c8f0182bffc044505eb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600991"
---
# <a name="mssqlserver_1105"></a><span data-ttu-id="7813f-102">MSSQLSERVER_1105</span><span class="sxs-lookup"><span data-stu-id="7813f-102">MSSQLSERVER_1105</span></span>
    
## <a name="details"></a><span data-ttu-id="7813f-103">Détails</span><span class="sxs-lookup"><span data-stu-id="7813f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7813f-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="7813f-104">Product Name</span></span>|<span data-ttu-id="7813f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7813f-105">SQL Server</span></span>|  
|<span data-ttu-id="7813f-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="7813f-106">Event ID</span></span>|<span data-ttu-id="7813f-107">1105</span><span class="sxs-lookup"><span data-stu-id="7813f-107">1105</span></span>|  
|<span data-ttu-id="7813f-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="7813f-108">Event Source</span></span>|<span data-ttu-id="7813f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7813f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7813f-110">Composant</span><span class="sxs-lookup"><span data-stu-id="7813f-110">Component</span></span>|<span data-ttu-id="7813f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7813f-111">SQLEngine</span></span>|  
|<span data-ttu-id="7813f-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="7813f-112">Symbolic Name</span></span>|<span data-ttu-id="7813f-113">NO_MORE_SPACE_IN_FG</span><span class="sxs-lookup"><span data-stu-id="7813f-113">NO_MORE_SPACE_IN_FG</span></span>|  
|<span data-ttu-id="7813f-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="7813f-114">Message Text</span></span>|<span data-ttu-id="7813f-115">Impossible d’allouer de l’espace pour l’objet ’%.\*ls’%.\*ls dans la base de données ’%.\*ls’, car le groupe de fichiers ’%.\*ls’ est plein.</span><span class="sxs-lookup"><span data-stu-id="7813f-115">Could not allocate space for object '%.\*ls'%.\*ls in database '%.\*ls' because the '%.\*ls' filegroup is full.</span></span> <span data-ttu-id="7813f-116">Créez de l'espace disque en supprimant des fichiers qui ne sont pas indispensables, en supprimant des objets dans le groupe de fichiers, en ajoutant des fichiers supplémentaires au groupe de fichiers ou en définissant Autogrowth à ON pour les fichiers existants dans le groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="7813f-116">Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7813f-117">Explication</span><span class="sxs-lookup"><span data-stu-id="7813f-117">Explanation</span></span>  
 <span data-ttu-id="7813f-118">Il n'y a pas d'espace disque disponible dans un groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="7813f-118">No disk space is available in a filegroup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7813f-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="7813f-119">User Action</span></span>  
 <span data-ttu-id="7813f-120">Les actions ci-dessous peuvent éventuellement créer de l'espace disponible dans le groupe de fichiers :</span><span class="sxs-lookup"><span data-stu-id="7813f-120">The following actions may make space available in the filegroup:</span></span>  
  
-   <span data-ttu-id="7813f-121">Activez la croissance automatique.</span><span class="sxs-lookup"><span data-stu-id="7813f-121">Turn on autogrow.</span></span>  
  
-   <span data-ttu-id="7813f-122">Ajoutez d'autres fichiers au groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="7813f-122">Add more files to the file group.</span></span>  
  
-   <span data-ttu-id="7813f-123">Libérez de l'espace disque en supprimant des index ou des tables qui ne sont plus nécessaires.</span><span class="sxs-lookup"><span data-stu-id="7813f-123">Free disk space by dropping index or tables that are no longer needed.</span></span>  
  
-   <span data-ttu-id="7813f-124">Pour plus d'informations, consultez la section « Résolution des problèmes d'espace disque insuffisant » dans la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7813f-124">For more information, see "Troubleshooting Insufficient Data Disk Space" in SQL Server Books Online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7813f-125">Si un index se trouve sur plusieurs fichiers, `ALTER INDEX REORGANIZE` peut retourner une erreur 1105 quand un des fichiers est plein.</span><span class="sxs-lookup"><span data-stu-id="7813f-125">When an index is located on several files, `ALTER INDEX REORGANIZE` can return error 1105 when one of the files is full.</span></span> <span data-ttu-id="7813f-126">Le processus de réorganisation est bloqué quand il tente de déplacer des lignes vers le fichier plein.</span><span class="sxs-lookup"><span data-stu-id="7813f-126">The reorganization process is blocked when the process tries to move rows to the full file.</span></span> <span data-ttu-id="7813f-127">Pour contourner cette limitation, effectuez une opération `ALTER INDEX REBUILD` au lieu de `ALTER INDEX REORGANIZE` ou augmentez la limite de croissance des fichiers qui sont pleins.</span><span class="sxs-lookup"><span data-stu-id="7813f-127">To work around this limitation perform an `ALTER INDEX REBUILD` instead of `ALTER INDEX REORGANIZE` or increase the file growth limit of any files that are full.</span></span>  
  
  
