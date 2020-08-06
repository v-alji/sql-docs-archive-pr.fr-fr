---
title: Génération d’objets de base de données avec intégration du Common Language Runtime (CLR) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- routines [CLR integration]
- database objects [CLR integration], building
- common language runtime [SQL Server], building database objects
- managed code [SQL Server], database objects
- building database objects [CLR integration]
- .NET Framework routines [SQL Server]
ms.assetid: ce34132c-bfa3-447b-9131-b6e17c672efe
author: rothja
ms.author: jroth
ms.openlocfilehash: 3c849c095a3be1c590e6fcb3ce87a0725eb795c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611115"
---
# <a name="building-database-objects-with-common-language-runtime-clr-integration"></a><span data-ttu-id="e325b-102">Génération d'objets de base de données à l'aide de l'intégration du CLR (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="e325b-102">Building Database Objects with Common Language Runtime (CLR) Integration</span></span>
  <span data-ttu-id="e325b-103">Vous pouvez créer des objets de base de données à l’aide d [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 'est appelé « routine CLR ».</span><span class="sxs-lookup"><span data-stu-id="e325b-103">You can build database objects using the [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is referred to as a "CLR routine."</span></span> <span data-ttu-id="e325b-104">Ces routines incluent :</span><span class="sxs-lookup"><span data-stu-id="e325b-104">These routines include:</span></span>  
  
-   <span data-ttu-id="e325b-105">Fonctions scalaires définies par l'utilisateur (fonctions UDF scalaires)</span><span class="sxs-lookup"><span data-stu-id="e325b-105">Scalar-valued user-defined functions (scalar UDFs)</span></span>  
  
-   <span data-ttu-id="e325b-106">Fonctions table définies par l'utilisateur (TVF)</span><span class="sxs-lookup"><span data-stu-id="e325b-106">Table-valued user-defined functions (TVFs)</span></span>  
  
-   <span data-ttu-id="e325b-107">Procédures définies par l'utilisateur (UDP)</span><span class="sxs-lookup"><span data-stu-id="e325b-107">User-defined procedures (UDPs)</span></span>  
  
-   <span data-ttu-id="e325b-108">Déclencheurs définis par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="e325b-108">User-defined triggers</span></span>  
  
 <span data-ttu-id="e325b-109">Les routines CLR ont la même structure en code managé.</span><span class="sxs-lookup"><span data-stu-id="e325b-109">CLR routines have the same structure in managed code.</span></span> <span data-ttu-id="e325b-110">Elles sont mappées à des méthodes statiques publiques (partagées dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET) d'une classe.</span><span class="sxs-lookup"><span data-stu-id="e325b-110">They are mapped to public, static (shared in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET) methods of a class.</span></span> <span data-ttu-id="e325b-111">Outre les routines, les types définis par l'utilisateur (UDT) et les fonctions d'agrégation définies par l'utilisateur peuvent également être définies à l'aide du .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e325b-111">In addition to routines, user-defined types (UDTs) and user-defined aggregate functions can also be defined using the .NET Framework.</span></span> <span data-ttu-id="e325b-112">Les types UDT et les agrégats définis par l'utilisateur sont mappés à des classes .NET Framework entières.</span><span class="sxs-lookup"><span data-stu-id="e325b-112">UDTs and user-defined aggregates are mapped to entire .NET Framework classes.</span></span>  
  
 <span data-ttu-id="e325b-113">Chaque type de .NET Framework routine a un [!INCLUDE[tsql](../../../includes/ssnoversion-md.md)] que l' [!INCLUDE[tsql](../../../includes/tsql-md.md)] équivalent peut être utilisé.</span><span class="sxs-lookup"><span data-stu-id="e325b-113">Each type of .NET Framework routine has a [!INCLUDE[tsql](../../../includes/ssnoversion-md.md)] that the [!INCLUDE[tsql](../../../includes/tsql-md.md)] equivalent can be used.</span></span> <span data-ttu-id="e325b-114">Par exemple, les fonctions UDF scalaires peuvent être utilisées dans toute expression scalaire.</span><span class="sxs-lookup"><span data-stu-id="e325b-114">For instance, scalar UDFs can be used in any scalar expression.</span></span> <span data-ttu-id="e325b-115">Une fonction TVF peut être utilisée dans toute clause FROM.</span><span class="sxs-lookup"><span data-stu-id="e325b-115">A TVF can be used in any FROM clause.</span></span> <span data-ttu-id="e325b-116">Une procédure peut être appelée dans une instruction EXEC ou à partir d'une application cliente.</span><span class="sxs-lookup"><span data-stu-id="e325b-116">A procedure can be invoked in an EXEC statement or invoked from a client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e325b-117">L'exécution d'un objet CLR (fonction définie par l'utilisateur, type défini par l'utilisateur ou déclencheur) sur le Common Language Runtime peut concerner plusieurs threads (plan parallèle), si l'optimiseur de requêtes décide que cela est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e325b-117">Execution of a CLR object (user-defined function, user-defined type, or trigger) on the common language runtime can take place on multiple threads (parallel plan), if the query optimizer decides it is beneficial.</span></span> <span data-ttu-id="e325b-118">Toutefois, si une fonction définie par l'utilisateur accède aux données, l'exécution se fera sur un plan en série.</span><span class="sxs-lookup"><span data-stu-id="e325b-118">However, if a user-defined function accesses data, execution will be  on a serial plan.</span></span> <span data-ttu-id="e325b-119">En cas d'exécution sur une version serveur antérieure à [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], si une fonction définie par l'utilisateur contient des paramètres LOB ou des valeurs de retour, l'exécution doit également se faire sur un plan en série.</span><span class="sxs-lookup"><span data-stu-id="e325b-119">When executed on a server version prior to [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], if a user-defined function contains LOB parameters or return values, execution also must be on a serial plan.</span></span>  
  
 <span data-ttu-id="e325b-120">Le tableau ci-dessous répertorie les rubriques traitées dans cette section.</span><span class="sxs-lookup"><span data-stu-id="e325b-120">The following table lists the topics covered in this section.</span></span>  
  
 [<span data-ttu-id="e325b-121">Mise en route avec l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="e325b-121">Getting Started with CLR Integration</span></span>](getting-started-with-clr-integration.md)  
 <span data-ttu-id="e325b-122">Fournit une brève vue d'ensemble des bibliothèques et des espaces de noms requis pour compiler l'objet en utilisant l'intégration du CLR avec [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e325b-122">Provides a brief overview of the libraries and namespaces required to compile object using CLR integration with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e325b-123">Inclut un exemple de procédure stockée CLR "Hello World".</span><span class="sxs-lookup"><span data-stu-id="e325b-123">Includes an example "Hello World" CLR stored procedure.</span></span>  
  
 [<span data-ttu-id="e325b-124">Bibliothèques .NET Framework prises en charge</span><span class="sxs-lookup"><span data-stu-id="e325b-124">Supported .NET Framework Libraries</span></span>](supported-net-framework-libraries.md)  
 <span data-ttu-id="e325b-125">Fournit des informations sur les bibliothèques .NET Framework prises en charge par l'intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="e325b-125">Provides information on the .NET Framework libraries supported by CLR integration.</span></span>  
  
 [<span data-ttu-id="e325b-126">Restrictions du modèle de programmation de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="e325b-126">CLR Integration Programming Model Restrictions</span></span>](clr-integration-programming-model-restrictions.md)  
 <span data-ttu-id="e325b-127">Fournit des informations sur les restrictions du modèle de programmation de l'intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="e325b-127">Provides information about CLR integration programming model restrictions.</span></span>  
  
 [<span data-ttu-id="e325b-128">Types de données SQL Server dans le .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e325b-128">SQL Server Data Types in the .NET Framework</span></span>](../../clr-integration-database-objects-types-net-framework/sql-server-data-types-in-the-net-framework.md)  
 <span data-ttu-id="e325b-129">Vue d'ensemble de types de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et de leurs équivalents .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e325b-129">An overview of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types and their .NET Framework equivalents.</span></span>  
  
 [<span data-ttu-id="e325b-130">Vue d'ensemble des attributs personnalisés de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="e325b-130">Overview of CLR Integration Custom Attributes</span></span>](../../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md)  
 <span data-ttu-id="e325b-131">Fournit des informations sur les attributs personnalisés de l'intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="e325b-131">Provides information about CLR integration custom attributes.</span></span>  
  
 [<span data-ttu-id="e325b-132">Fonctions CLR définies par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="e325b-132">CLR User-Defined Functions</span></span>](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md)  
 <span data-ttu-id="e325b-133">Explique comment implémenter et utiliser les différents types de fonctions CLR : fonctions table, scalaires et d'agrégation définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e325b-133">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="e325b-134">Types CLR définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e325b-134">CLR User-Defined Types</span></span>](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md)  
 <span data-ttu-id="e325b-135">Explique comment implémenter et utiliser les types CLR définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e325b-135">Describes how to implement and use CLR user-defined types.</span></span>  
  
 [<span data-ttu-id="e325b-136">Procédures stockées du CLR</span><span class="sxs-lookup"><span data-stu-id="e325b-136">CLR Stored Procedures</span></span>](../../../database-engine/dev-guide/clr-stored-procedures.md)  
 <span data-ttu-id="e325b-137">Explique comment implémenter et utiliser les procédures stockées CLR.</span><span class="sxs-lookup"><span data-stu-id="e325b-137">Describes how to implement and use CLR stored procedures.</span></span>  
  
 [<span data-ttu-id="e325b-138">Déclencheurs CLR</span><span class="sxs-lookup"><span data-stu-id="e325b-138">CLR Triggers</span></span>](../../../database-engine/dev-guide/clr-triggers.md)  
 <span data-ttu-id="e325b-139">Explique comment implémenter et utiliser les déclencheurs CLR.</span><span class="sxs-lookup"><span data-stu-id="e325b-139">Describes how to implement and use CLR triggers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e325b-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e325b-140">See Also</span></span>  
 [<span data-ttu-id="e325b-141">Vue d’ensemble de l’intégration du Common Language Runtime &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="e325b-141">Common Language Runtime &#40;CLR&#41; Integration Overview</span></span>](../common-language-runtime-integration-overview.md)  
  
  
