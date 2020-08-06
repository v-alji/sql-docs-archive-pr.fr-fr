---
title: Déplacer des fichiers de bases de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- disaster recovery [SQL Server], moving database files
- files [SQL Server], moving
- data files [SQL Server], moving
- file moving [SQL Server]
- moving full-text catalogs
- moving databases
- full-text catalogs [SQL Server], moving
- moving database files
- scheduled disk maintenance [SQL Server]
- moving files
- relocating database files
- planned database relocations [SQL Server]
- databases [SQL Server], moving
ms.assetid: 89f01b10-5fae-4ed8-b0fb-a4b9f540fd28
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5491f3c4dfd47cac4047d0409c78001be80d6f13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705155"
---
# <a name="move-database-files"></a><span data-ttu-id="6d507-102">Déplacer des fichiers de bases de données</span><span class="sxs-lookup"><span data-stu-id="6d507-102">Move Database Files</span></span>
  <span data-ttu-id="6d507-103">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous pouvez déplacer les bases de données système et utilisateur en spécifiant le nouvel emplacement des fichiers dans la clause FILENAME de l’instruction [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="6d507-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can move system and user databases by specifying the new file location in the FILENAME clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="6d507-104">Cette méthode peut être appliquée aux fichiers de données, aux fichiers journaux et aux fichiers de catalogues de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="6d507-104">Data, log, and full-text catalog files can be moved in this way.</span></span> <span data-ttu-id="6d507-105">Elle peut être utile dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="6d507-105">This may be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="6d507-106">Récupération après défaillance.</span><span class="sxs-lookup"><span data-stu-id="6d507-106">Failure recovery.</span></span> <span data-ttu-id="6d507-107">Par exemple, la base de données est en mode suspect ou a été fermée en raison d'une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="6d507-107">For example, the database is in suspect mode or has shut down, because of a hardware failure.</span></span>  
  
-   <span data-ttu-id="6d507-108">Déplacement prévu.</span><span class="sxs-lookup"><span data-stu-id="6d507-108">Planned relocation.</span></span>  
  
-   <span data-ttu-id="6d507-109">Déplacement en vue d'une maintenance de disque planifiée.</span><span class="sxs-lookup"><span data-stu-id="6d507-109">Relocation for scheduled disk maintenance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6d507-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6d507-110">In This Section</span></span>  
  
|<span data-ttu-id="6d507-111">Rubrique</span><span class="sxs-lookup"><span data-stu-id="6d507-111">Topic</span></span>|<span data-ttu-id="6d507-112">Description</span><span class="sxs-lookup"><span data-stu-id="6d507-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="6d507-113">Déplacer des bases de données utilisateur</span><span class="sxs-lookup"><span data-stu-id="6d507-113">Move User Databases</span></span>](move-user-databases.md)|<span data-ttu-id="6d507-114">Décrit les procédures permettant de déplacer les fichiers de base de données utilisateur et les fichiers de catalogue de texte intégral vers un nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="6d507-114">Describes the procedures for moving user database files and full-text catalog files to a new location.</span></span>|  
|[<span data-ttu-id="6d507-115">Déplacer des bases de données système</span><span class="sxs-lookup"><span data-stu-id="6d507-115">Move System Databases</span></span>](system-databases.md)|<span data-ttu-id="6d507-116">Décrit les procédures permettant de déplacer les fichiers de base de données système vers un nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="6d507-116">Describes the procedures for moving system database files to a new location.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6d507-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d507-117">See Also</span></span>  
 <span data-ttu-id="6d507-118">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6d507-118">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="6d507-119">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6d507-119">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="6d507-120">Attacher et détacher une base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d507-120">Database Detach and Attach &#40;SQL Server&#41;</span></span>](database-detach-and-attach-sql-server.md)  
  
  
