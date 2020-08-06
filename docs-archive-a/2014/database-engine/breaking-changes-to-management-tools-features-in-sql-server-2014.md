---
title: Modifications importantes apportées aux fonctionnalités des outils d’administration de SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 11/27/2018
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 3ff3fad8-b569-4516-bd58-5a3efeb537e2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0487b6ab0958e0b83d4e8e34be507b5b3211ac87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611334"
---
# <a name="breaking-changes-to-management-tools-features-in-sql-server-2014"></a><span data-ttu-id="d5f9f-102">Dernières modifications apportées aux fonctionnalités des outils d'administration dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="d5f9f-102">Breaking Changes to Management Tools Features in SQL Server 2014</span></span>
  <span data-ttu-id="d5f9f-103">Cette rubrique décrit les dernières modifications apportées aux fonctionnalités des outils d'administration.</span><span class="sxs-lookup"><span data-stu-id="d5f9f-103">This topic describes breaking changes to management tools features.</span></span> <span data-ttu-id="d5f9f-104">Ces modifications peuvent interrompre les applications, scripts ou fonctionnalités fondés sur les versions antérieures de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5f9f-104">These changes might break applications, scripts, or functionalities that are based on earlier versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d5f9f-105">Il se peut que vous rencontriez ces problèmes lors d'une mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="d5f9f-105">You might encounter these issues when you upgrade.</span></span> <span data-ttu-id="d5f9f-106">Pour plus d'informations, consultez [Use Upgrade Advisor to Prepare for Upgrades](../../2014/sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md).</span><span class="sxs-lookup"><span data-stu-id="d5f9f-106">For more information, see [Use Upgrade Advisor to Prepare for Upgrades](../../2014/sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md).</span></span>  
  
## <a name="breaking-changes-in-sssql14"></a><span data-ttu-id="d5f9f-107">Modifications avec rupture dans [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5f9f-107">Breaking Changes in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span></span>  
 <span data-ttu-id="d5f9f-108">Informations qui seront fournies par la suite.</span><span class="sxs-lookup"><span data-stu-id="d5f9f-108">Information to come later.</span></span>  
  
## <a name="breaking-changes-in-sssql11"></a><span data-ttu-id="d5f9f-109">Modifications avec rupture dans [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5f9f-109">Breaking Changes in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span></span>  
  
### <a name="you-cannot-use-sssql11-management-tools-to-create-a-utility-control-point-on-a-sskilimanjaro-instance-of-sql-server"></a><span data-ttu-id="d5f9f-110">Vous ne pouvez pas utiliser les outils de gestion de [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] pour créer un point de contrôle de l'utilitaire sur une instance de [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5f9f-110">You cannot use [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Management Tools to create a utility control point on a [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] instance of SQL Server</span></span>  
 <span data-ttu-id="d5f9f-111">Pour créer un point de contrôle de l'utilitaire sur une instance de [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)], utilisez les outils de gestion de [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5f9f-111">To create a utility control point on an instance of [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)], use [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] Management Tools.</span></span>  
  
### <a name="smo-has-been-reversioned-in-sssql11"></a><span data-ttu-id="d5f9f-112">SMO a changé de version dans [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5f9f-112">SMO has been reversioned in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span></span>  
 <span data-ttu-id="d5f9f-113">Le code développé avec SMO depuis [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] ou les versions antérieures peut ne pas convenir sur [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] à mois d'y apporter des changements mineurs.</span><span class="sxs-lookup"><span data-stu-id="d5f9f-113">Code developed with SMO from [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] or earlier versions might not build against [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] without minor modifications.</span></span> <span data-ttu-id="d5f9f-114">Pour plus d’informations, consultez [Compatibilité descendante dans SMO](../relational-databases/server-management-objects-smo/backward-compatibility-in-smo.md).</span><span class="sxs-lookup"><span data-stu-id="d5f9f-114">For more information, see [Backward Compatibility in SMO](../relational-databases/server-management-objects-smo/backward-compatibility-in-smo.md).</span></span>  

## <a name="breaking-changes-in-sql-server-2005"></a><a name="previous-versions"></a><span data-ttu-id="d5f9f-115">Modifications avec rupture dans SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="d5f9f-115">Breaking Changes in SQL Server 2005</span></span>  

[!INCLUDE[Archived documentation for very old versions of SQL Server](../includes/paragraph-content/previous-versions-archive-documentation-sql-server.md)]

## <a name="see-also"></a><span data-ttu-id="d5f9f-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d5f9f-116">See Also</span></span>  
 [<span data-ttu-id="d5f9f-117">Compatibilité descendante</span><span class="sxs-lookup"><span data-stu-id="d5f9f-117">Backward Compatibility</span></span>](../../2014/getting-started/backward-compatibility.md)  
 [<span data-ttu-id="d5f9f-118">En savoir plus sur les modifications importantes apportées aux fonctionnalités des outils d’administration de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="d5f9f-118">More about Breaking Changes to Management Tools Features in SQL Server 2014</span></span>](breaking-changes-to-database-engine-features-in-sql-server-2016.md?view=sql-server-2014)  
  
  
