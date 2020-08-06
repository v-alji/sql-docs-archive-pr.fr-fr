---
title: Obtention d’informations sur les assemblys | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration], metadata
- status information [SQL Server], assemblies
- metadata [SQL Server], assemblies
ms.assetid: 6aa7f18e-baad-4481-9777-8c3b230b392f
author: rothja
ms.author: jroth
ms.openlocfilehash: ec559ba5ccbb53dd92f3a5e1175a10a59fbaf43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704188"
---
# <a name="getting-information-about-assemblies"></a><span data-ttu-id="9d59f-102">Obtention d'informations sur les assemblys</span><span class="sxs-lookup"><span data-stu-id="9d59f-102">Getting Information About Assemblies</span></span>
  <span data-ttu-id="9d59f-103">Vous pouvez interroger les fonctions et affichages catalogue suivants pour obtenir des métadonnées sur les assemblys.</span><span class="sxs-lookup"><span data-stu-id="9d59f-103">The following catalog views and functions can be queried for metadata about assemblies.</span></span>  
  
 <span data-ttu-id="9d59f-104">**Pour obtenir des informations sur des assemblys particuliers**</span><span class="sxs-lookup"><span data-stu-id="9d59f-104">**To get information about individual assemblies**</span></span>  
  
-   [<span data-ttu-id="9d59f-105">ASSEMBLYPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9d59f-105">ASSEMBLYPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/assemblyproperty-transact-sql)  
  
 <span data-ttu-id="9d59f-106">**Pour obtenir des informations sur tous les assemblys de la base de données**</span><span class="sxs-lookup"><span data-stu-id="9d59f-106">**To get information about all assemblies in the database**</span></span>  
  
-   [<span data-ttu-id="9d59f-107">sys. Assemblies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9d59f-107">sys.assemblies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assemblies-transact-sql)  
  
 <span data-ttu-id="9d59f-108">**Pour obtenir des informations sur les fichiers d'assembly, notamment sur les fichiers de débogage, les fichiers sources et les binaires d'assembly**</span><span class="sxs-lookup"><span data-stu-id="9d59f-108">**To get information about assembly files, including assembly binaries, source files, and debug files**</span></span>  
  
-   [<span data-ttu-id="9d59f-109">sys.assembly_files &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9d59f-109">sys.assembly_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-files-transact-sql)  
  
 <span data-ttu-id="9d59f-110">**Pour obtenir des informations sur les références croisées d'assembly**</span><span class="sxs-lookup"><span data-stu-id="9d59f-110">**To get information about cross-assembly references**</span></span>  
  
-   [<span data-ttu-id="9d59f-111">sys. assembly_references &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9d59f-111">sys.assembly_references &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-references-transact-sql)  
  
 <span data-ttu-id="9d59f-112">**Pour obtenir des informations d'assembly sur les types définis par l'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="9d59f-112">**To get assembly information about user-defined types**</span></span>  
  
-   [<span data-ttu-id="9d59f-113">sys.assembly_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9d59f-113">sys.assembly_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-types-transact-sql)  
  
-   [<span data-ttu-id="9d59f-114">sys.types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9d59f-114">sys.types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-types-transact-sql)  
  
 <span data-ttu-id="9d59f-115">**Pour obtenir des informations d'assembly sur les fonctions, les déclencheurs et les procédures stockées CLR (Common Language Runtime)**</span><span class="sxs-lookup"><span data-stu-id="9d59f-115">**To get assembly information about common language runtime (CLR) stored procedures, triggers, and functions**</span></span>  
  
-   [<span data-ttu-id="9d59f-116">sys.assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9d59f-116">sys.assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql)  
  
 <span data-ttu-id="9d59f-117">**Pour obtenir des informations sur les objets non-CLR**</span><span class="sxs-lookup"><span data-stu-id="9d59f-117">**To get information about non-CLR objects**</span></span>  
  
-   [<span data-ttu-id="9d59f-118">sys.sql_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9d59f-118">sys.sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="9d59f-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9d59f-119">See Also</span></span>  
 <span data-ttu-id="9d59f-120">[Assemblys &#40;Moteur de base de données&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="9d59f-120">[Assemblies &#40;Database Engine&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span></span>  
 <span data-ttu-id="9d59f-121">[Conception d’assemblys](../../relational-databases/clr-integration/assemblies-designing.md) </span><span class="sxs-lookup"><span data-stu-id="9d59f-121">[Designing Assemblies](../../relational-databases/clr-integration/assemblies-designing.md) </span></span>  
 [<span data-ttu-id="9d59f-122">Implémentation d'assemblys</span><span class="sxs-lookup"><span data-stu-id="9d59f-122">Implementing Assemblies</span></span>](assemblies-implementing.md)  
  
  
