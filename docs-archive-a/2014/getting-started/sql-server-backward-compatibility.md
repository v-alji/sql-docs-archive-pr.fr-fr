---
title: Compatibilité descendante SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ac47cb74-5578-417d-bcef-f970d9527705
author: rothja
ms.author: jroth
ms.openlocfilehash: a4d38041ce4daa12911dc706d382460324931c90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698459"
---
# <a name="sql-server-backward-compatibility"></a><span data-ttu-id="55c9e-102">Compatibilité descendante SQL Server</span><span class="sxs-lookup"><span data-stu-id="55c9e-102">SQL Server Backward Compatibility</span></span>
  <span data-ttu-id="55c9e-103">Les rubriques de la section consacrée à la compatibilité descendante décrivent les changements de comportement de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] entre les différentes versions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55c9e-103">Topics in the backward compatibility section describe changes in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] behavior between versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="55c9e-104">Les fonctionnalités incluses dans cette rubrique incluent la programmabilité des données, les outils de configuration de la surface d'exposition, le programme d'installation de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , les services [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] et autres modifications de fonctionnalités générales.</span><span class="sxs-lookup"><span data-stu-id="55c9e-104">Features included in this topic area include data programmability, surface area configuration tools, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Setup, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] services, and other broad functionality changes.</span></span>  
  
|<span data-ttu-id="55c9e-105">Rubrique</span><span class="sxs-lookup"><span data-stu-id="55c9e-105">Topic</span></span>|<span data-ttu-id="55c9e-106">Description</span><span class="sxs-lookup"><span data-stu-id="55c9e-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="55c9e-107">Fonctionnalités SQL Server dépréciées dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="55c9e-107">Deprecated SQL Server Features in SQL Server 2014</span></span>](../../2014/getting-started/deprecated-sql-server-features-in-sql-server-2014.md)|<span data-ttu-id="55c9e-108">Fonctionnalités [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] déconseillées dans cette version.</span><span class="sxs-lookup"><span data-stu-id="55c9e-108">Deprecated [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] features in this release.</span></span> <span data-ttu-id="55c9e-109">Cette rubrique couvre la configuration de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , et les fonctionnalités du programme d'installation.</span><span class="sxs-lookup"><span data-stu-id="55c9e-109">This topic covers [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration, and Setup functionality.</span></span>|  
|[<span data-ttu-id="55c9e-110">Fonctionnalités SQL Server supprimées dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="55c9e-110">Discontinued SQL Server Features in SQL Server 2014</span></span>](../../2014/getting-started/discontinued-sql-server-features-in-sql-server-2014.md)|<span data-ttu-id="55c9e-111">Fonctionnalité [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] abandonnée dans cette version.</span><span class="sxs-lookup"><span data-stu-id="55c9e-111">Discontinued [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] functionality in this release.</span></span> <span data-ttu-id="55c9e-112">Cette rubrique couvre la configuration de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , et les fonctionnalités du programme d'installation.</span><span class="sxs-lookup"><span data-stu-id="55c9e-112">This topic covers [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration, and Setup functionality.</span></span>|  
|[<span data-ttu-id="55c9e-113">Modifications avec rupture dans les fonctionnalités SQL Server de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="55c9e-113">Breaking Changes to SQL Server Features in SQL Server 2014</span></span>](../../2014/getting-started/breaking-changes-to-sql-server-features-in-sql-server-2014.md)|<span data-ttu-id="55c9e-114">Changements qui peuvent imposer des modifications dans les applications.</span><span class="sxs-lookup"><span data-stu-id="55c9e-114">Changes that might require changes to applications.</span></span> <span data-ttu-id="55c9e-115">Cette rubrique couvre la configuration de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , et les fonctionnalités du programme d'installation.</span><span class="sxs-lookup"><span data-stu-id="55c9e-115">This topic covers [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration, and Setup functionality.</span></span>|  
|[<span data-ttu-id="55c9e-116">Changements de comportement dans les fonctionnalités SQL Server de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="55c9e-116">Behavior Changes to SQL Server Features in SQL Server 2014</span></span>](../../2014/getting-started/behavior-changes-to-sql-server-features-in-sql-server-2014.md)|<span data-ttu-id="55c9e-117">Modifications comportementales aux fonctionnalités [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] dans cette version finale.</span><span class="sxs-lookup"><span data-stu-id="55c9e-117">Behavioral  changes to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] features in this release.</span></span> <span data-ttu-id="55c9e-118">Cette rubrique couvre la configuration de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , et les fonctionnalités du programme d'installation.</span><span class="sxs-lookup"><span data-stu-id="55c9e-118">This topic covers [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration, and Setup functionality.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55c9e-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="55c9e-119">See Also</span></span>  
 [<span data-ttu-id="55c9e-120">Compatibilité descendante</span><span class="sxs-lookup"><span data-stu-id="55c9e-120">Backward Compatibility</span></span>](../../2014/getting-started/backward-compatibility.md)  
  
  
