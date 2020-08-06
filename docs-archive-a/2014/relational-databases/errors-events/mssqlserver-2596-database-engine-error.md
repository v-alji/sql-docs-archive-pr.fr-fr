---
title: MSSQLSERVER_2596 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2596 (Database Engine error)
ms.assetid: 49ab892f-8ba3-4ba1-b562-ddf205019802
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27b2ceed40274df4ba57c4d61a83fbc60b6a7f80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605493"
---
# <a name="mssqlserver_2596"></a><span data-ttu-id="379a7-102">MSSQLSERVER_2596</span><span class="sxs-lookup"><span data-stu-id="379a7-102">MSSQLSERVER_2596</span></span>
    
## <a name="details"></a><span data-ttu-id="379a7-103">Détails</span><span class="sxs-lookup"><span data-stu-id="379a7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="379a7-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="379a7-104">Product Name</span></span>|<span data-ttu-id="379a7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="379a7-105">SQL Server</span></span>|  
|<span data-ttu-id="379a7-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="379a7-106">Event ID</span></span>|<span data-ttu-id="379a7-107">2596</span><span class="sxs-lookup"><span data-stu-id="379a7-107">2596</span></span>|  
|<span data-ttu-id="379a7-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="379a7-108">Event Source</span></span>|<span data-ttu-id="379a7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="379a7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="379a7-110">Composant</span><span class="sxs-lookup"><span data-stu-id="379a7-110">Component</span></span>|<span data-ttu-id="379a7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="379a7-111">SQLEngine</span></span>|  
|<span data-ttu-id="379a7-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="379a7-112">Symbolic Name</span></span>|<span data-ttu-id="379a7-113">DBCC_DATABASE_IN_READ_ONLY_MODE</span><span class="sxs-lookup"><span data-stu-id="379a7-113">DBCC_DATABASE_IN_READ_ONLY_MODE</span></span>|  
|<span data-ttu-id="379a7-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="379a7-114">Message Text</span></span>|<span data-ttu-id="379a7-115">L’instruction de réparation n’a pas été traitée.</span><span class="sxs-lookup"><span data-stu-id="379a7-115">The repair statement was not processed.</span></span> <span data-ttu-id="379a7-116">La base de données ne peut pas être en mode lecture seule.</span><span class="sxs-lookup"><span data-stu-id="379a7-116">The database cannot be in read-only mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="379a7-117">Explication</span><span class="sxs-lookup"><span data-stu-id="379a7-117">Explanation</span></span>  
 <span data-ttu-id="379a7-118">Ce message indique que la base de données est en mode lecture seule.</span><span class="sxs-lookup"><span data-stu-id="379a7-118">This message indicates that the database is in read-only mode.</span></span> <span data-ttu-id="379a7-119">Il est impossible de réparer une base de données qui est en mode lecture seule.</span><span class="sxs-lookup"><span data-stu-id="379a7-119">Repairs are not possible when a database is in read-only mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="379a7-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="379a7-120">User Action</span></span>  
 <span data-ttu-id="379a7-121">Passez la base de données en mode lecture/écriture à l'aide de ALTER DATABASE, puis exécutez de nouveau la commande DBCC.</span><span class="sxs-lookup"><span data-stu-id="379a7-121">Set the database to read-write by using ALTER DATABASE, and then re-run the DBCC command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="379a7-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="379a7-122">See Also</span></span>  
 [<span data-ttu-id="379a7-123">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="379a7-123">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
