---
title: Les bases de données en lecture seule ne peuvent pas être mises à niveau | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- database cannot be upgraded
ms.assetid: 27964211-ea30-4390-b791-dcf225fb9ae7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ba48ed2bd80961a4949dc13f04fed0637ecc27ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612657"
---
# <a name="read-only-databases-cannot-be-upgraded"></a><span data-ttu-id="2b147-102">Les bases de données en lecture seule ne peuvent pas être mises à niveau</span><span class="sxs-lookup"><span data-stu-id="2b147-102">Read-only databases cannot be upgraded</span></span>
  <span data-ttu-id="2b147-103">Le Conseiller de mise à niveau a déterminé que certaines bases de données sur cette instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peuvent pas être mises à niveau.</span><span class="sxs-lookup"><span data-stu-id="2b147-103">Upgrade Advisor has determined that some databases on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be upgraded.</span></span>  
  
## <a name="component"></a><span data-ttu-id="2b147-104">Composant</span><span class="sxs-lookup"><span data-stu-id="2b147-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="2b147-105">Description</span><span class="sxs-lookup"><span data-stu-id="2b147-105">Description</span></span>  
 <span data-ttu-id="2b147-106">Une base de données en lecture seule a été détectée.</span><span class="sxs-lookup"><span data-stu-id="2b147-106">A read-only database has been detected.</span></span> <span data-ttu-id="2b147-107">Le programme d'installation doit pouvoir écrire dans la base de données pour la mettre à niveau.</span><span class="sxs-lookup"><span data-stu-id="2b147-107">To upgrade the database, Setup must be able to write to the database.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="2b147-108">Action corrective</span><span class="sxs-lookup"><span data-stu-id="2b147-108">Corrective Action</span></span>  
 <span data-ttu-id="2b147-109">Lorsque personne n’utilise la base de données, utilisez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise Manager, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] ou l’instruction ALTER DATABASE pour modifier la base de données en lecture-écriture.</span><span class="sxs-lookup"><span data-stu-id="2b147-109">When no one is using the database, use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise Manager, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], or the ALTER DATABASE statement to change the database to read-write.</span></span> <span data-ttu-id="2b147-110">L'instruction suivante affecte à la base de données l'attribut lecture-écriture.</span><span class="sxs-lookup"><span data-stu-id="2b147-110">The following statement changes the database to read-write.</span></span>  
  
```  
USE master;  
GO  
ALTER DATABASE <database name>  
SET READ_WRITE;  
GO  
```  
  
 <span data-ttu-id="2b147-111">Pour plus d'informations sur l'instruction ALTER DATABASE, consultez la rubrique « ALTER DATABASE ([!INCLUDE[tsql](../../includes/tsql-md.md)]) » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b147-111">For more information about the ALTER DATABASE statement, see the "ALTER DATABASE ([!INCLUDE[tsql](../../includes/tsql-md.md)])" topic in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b147-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2b147-112">See Also</span></span>  
 <span data-ttu-id="2b147-113">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="2b147-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="2b147-114">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="2b147-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
