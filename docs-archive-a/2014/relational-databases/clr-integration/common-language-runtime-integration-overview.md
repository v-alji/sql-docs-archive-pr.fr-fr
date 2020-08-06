---
title: Vue d’ensemble de l’intégration du Common Language Runtime (CLR) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- managed code [SQL Server]
- common language runtime [SQL Server], about CLR integration
- cross-language integration
- integrating CLR [SQL Server]
- .NET Framework [SQL Server], common language runtime
- code access security [CLR integration]
- managed code [SQL Server], CLR integration
ms.assetid: 7be9e644-36a2-48fc-9206-faf59fdff4d7
author: rothja
ms.author: jroth
ms.openlocfilehash: 25345fd39fb8a77f62e4e352b75629a98cb9d7af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604569"
---
# <a name="common-language-runtime-clr-integration-overview"></a><span data-ttu-id="9f169-102">Vue d'ensemble de l'intégration du CLR (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="9f169-102">Common Language Runtime (CLR) Integration Overview</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="9f169-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]intègre désormais l’intégration du composant Common Language Runtime (CLR) des .NET Framework pour [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="9f169-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] now features the integration of the common language runtime (CLR) component of the .NET Framework for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="9f169-104">Le CLR fournit le code managé avec des services tels que l'intégration interlangage, la sécurité d'accès du code, la gestion de la durée de vie des objets et la prise en charge du débogage et des profils.</span><span class="sxs-lookup"><span data-stu-id="9f169-104">The CLR supplies managed code with services such as cross-language integration, code access security, object lifetime management, and debugging and profiling support.</span></span> <span data-ttu-id="9f169-105">Pour les utilisateurs et les développeurs d'applications [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], l'intégration du CLR permet désormais d'écrire des procédures stockées, des déclencheurs, des types définis par l'utilisateur, des fonctions définies par l'utilisateur (fonctions scalaires et fonctions table) et des fonctions d'agrégation définies par l'utilisateur, à l'aide de langages du .NET Framework, tels que [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET et [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="9f169-105">For [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] users and application developers, CLR integration means that you can now write stored procedures, triggers, user-defined types, user-defined functions (scalar and table-valued), and user-defined aggregate functions using any .NET Framework language, including [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="9f169-106">inclut la version 4 préinstallée du .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9f169-106">includes the .NET Framework version 4 pre-installed.</span></span>  
  
 <span data-ttu-id="9f169-107">Citons quelques-uns des avantages majeurs de cette intégration :</span><span class="sxs-lookup"><span data-stu-id="9f169-107">Among the major benefits of this integration are:</span></span>  
  
-   <span data-ttu-id="9f169-108">**Un meilleur modèle de programmation.**</span><span class="sxs-lookup"><span data-stu-id="9f169-108">**A better programming model.**</span></span> <span data-ttu-id="9f169-109">Les langages .NET Framework sont à bien des égards plus riches que Transact-SQL, en proposant des constructions et des fonctions qui n'étaient pas jusque-là accessibles aux développeurs [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f169-109">The .NET Framework languages are in many respects richer than Transact-SQL, offering constructs and capabilities previously not available to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] developers.</span></span> <span data-ttu-id="9f169-110">Les développeurs peuvent aussi tirer parti de la puissance de la bibliothèque du .NET Framework, qui propose un ensemble complet de classes pour résoudre rapidement et efficacement les problèmes de programmation.</span><span class="sxs-lookup"><span data-stu-id="9f169-110">Developers may also leverage the power of the .NET Framework Library, which provides an extensive set of classes that can be used to quickly and efficiently solve programming problems.</span></span>  
  
-   <span data-ttu-id="9f169-111">**Sécurité améliorée.**</span><span class="sxs-lookup"><span data-stu-id="9f169-111">**Improved safety and security.**</span></span> <span data-ttu-id="9f169-112">Le code managé s'exécute dans un environnement CLR, hébergé par le moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="9f169-112">Managed code runs in a common language run-time environment, hosted by the Database Engine.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="9f169-113">met celui-ci à profit pour fournir une alternative plus sûre et plus sécurisée aux procédures stockées étendues disponibles dans les versions antérieures de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f169-113">leverages this to provide a safer and more secure alternative to the extended stored procedures available in earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="9f169-114">**Possibilité de définir des types de données et des fonctions d'agrégation.**</span><span class="sxs-lookup"><span data-stu-id="9f169-114">**Ability to define data types and aggregate functions.**</span></span> <span data-ttu-id="9f169-115">Les types et les agrégats définis par l'utilisateur sont deux nouveaux objets de base de données managés qui étendent les fonctions de stockage et d'interrogation de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f169-115">User defined types and user defined aggregates are two new managed database objects which expand the storage and querying capabilities of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="9f169-116">**Développement simplifié via un environnement standardisé.**</span><span class="sxs-lookup"><span data-stu-id="9f169-116">**Streamlined development through a standardized environment.**</span></span> <span data-ttu-id="9f169-117">Le développement de bases de données est intégré aux prochaines versions de l'environnement de développement  [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio .NET.</span><span class="sxs-lookup"><span data-stu-id="9f169-117">Database development is integrated into future releases of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio .NET development environment.</span></span> <span data-ttu-id="9f169-118">Les développeurs se servent des mêmes outils pour développer et déboguer les objets de base de données et les scripts que ceux qu'ils utilisent pour écrire des composants et services .NET Framework de couche intermédiaire ou client.</span><span class="sxs-lookup"><span data-stu-id="9f169-118">Developers use the same tools for developing and debugging database objects and scripts as they use to write middle-tier or client-tier .NET Framework components and services.</span></span>  
  
-   <span data-ttu-id="9f169-119">**Potentiel pour des performances et une extensibilité améliorées.**</span><span class="sxs-lookup"><span data-stu-id="9f169-119">**Potential for improved performance and scalability.**</span></span> <span data-ttu-id="9f169-120">Dans de nombreux cas, la compilation du langage .NET Framework et les modèles d'exécution offrent des performances améliorées par rapport à Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="9f169-120">In many situations, the .NET Framework language compilation and execution models deliver improved performance over Transact-SQL.</span></span>  
  
 <span data-ttu-id="9f169-121">Le tableau ci-dessous répertorie les rubriques de cette section.</span><span class="sxs-lookup"><span data-stu-id="9f169-121">This following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="9f169-122">Vue d'ensemble de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="9f169-122">Overview of CLR Integration</span></span>](clr-integration-overview.md)  
 <span data-ttu-id="9f169-123">Décrit les types d'objets qui peuvent être créés à l'aide de l'intégration du CLR et passe en revue les spécifications requises pour générer des objets de base de données à l'aide de l'intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="9f169-123">Describes the kinds of objects that can be built using CLR integration, and reviews the requirements for building database objects using CLR integration.</span></span>  
  
 [<span data-ttu-id="9f169-124">Nouveautés dans l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="9f169-124">What's New in CLR Integration</span></span>](clr-integration-what-s-new.md)  
 <span data-ttu-id="9f169-125">Décrit les nouvelles fonctionnalités de cette version.</span><span class="sxs-lookup"><span data-stu-id="9f169-125">Describes the new features in this release.</span></span>  
  
 [<span data-ttu-id="9f169-126">Architecture d'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="9f169-126">Architecture of CLR Integration</span></span>](../../database-engine/dev-guide/architecture-of-clr-integration.md)  
 <span data-ttu-id="9f169-127">Décrit les objectifs de conception de l'intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="9f169-127">Describes the design goals of CLR integration.</span></span>  
  
 [<span data-ttu-id="9f169-128">Activation de l’intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="9f169-128">Enabling CLR Integration</span></span>](clr-integration-enabling.md)  
 <span data-ttu-id="9f169-129">Décrit comment activer l'intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="9f169-129">Describes how to enable CLR integration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f169-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9f169-130">See Also</span></span>  
 <span data-ttu-id="9f169-131">[Installation du .NET Framework](https://technet.microsoft.com/library/ms166014\(v=SQL.105\).aspx) </span><span class="sxs-lookup"><span data-stu-id="9f169-131">[Installing the .NET Framework](https://technet.microsoft.com/library/ms166014\(v=SQL.105\).aspx) </span></span>  
 [<span data-ttu-id="9f169-132">Performances de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="9f169-132">Performance of CLR Integration</span></span>](clr-integration-architecture-performance.md)  
  
  
