---
title: Assemblys (Moteur de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration]
- assemblies [CLR integration], about assemblies
- managed code [SQL Server], assemblies
ms.assetid: 4b146437-3061-47f6-9e8c-26eeea10b54e
author: rothja
ms.author: jroth
ms.openlocfilehash: 7edb18ccfa9954fe52093f87948f956c2eacc1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704195"
---
# <a name="assemblies-database-engine"></a><span data-ttu-id="1b523-102">Assemblys (moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="1b523-102">Assemblies (Database Engine)</span></span>
  <span data-ttu-id="1b523-103">Toutes les rubriques de cette section vous aident à mieux comprendre, concevoir et mettre en œuvre les assemblys.</span><span class="sxs-lookup"><span data-stu-id="1b523-103">The topics in this section provide information to help you understand, design, and implement assemblies.</span></span>  
  
 <span data-ttu-id="1b523-104">Les assemblys sont des fichiers DLL utilisés dans une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour déployer des fonctions, des procédures stockées, des déclencheurs, des agrégats définis par l’utilisateur et des types définis par l’utilisateur qui sont écrits dans l’un des langages de code managé hébergés par le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Common Language Runtime (CLR) au lieu de [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1b523-104">Assemblies are DLL files used in an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to deploy functions, stored procedures, triggers, user-defined aggregates, and user-defined types that are written in one of the managed code languages hosted by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] common language runtime (CLR), instead of in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="1b523-105">Dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], un assembly est un objet qui fait référence à un module d'applications managées (fichier .dll) qui a été créé dans le Common Language Runtime (CLR) [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b523-105">An assembly in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is an object that references a managed application module (.dll file) that was created in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] common language runtime.</span></span> <span data-ttu-id="1b523-106">Un assembly contient des métadonnées de classe et du code managé.</span><span class="sxs-lookup"><span data-stu-id="1b523-106">An assembly contains class metadata and managed code.</span></span> <span data-ttu-id="1b523-107">Le téléchargement d'un assembly dans une instance SQL Server constitue la première étape nécessaire à la création des objets de base de données suivants :</span><span class="sxs-lookup"><span data-stu-id="1b523-107">Uploading an assembly to an instance of SQL Server is the first step toward creating any of the following database objects:</span></span>  
  
-   <span data-ttu-id="1b523-108">Fonctions CLR.</span><span class="sxs-lookup"><span data-stu-id="1b523-108">CLR functions.</span></span> <span data-ttu-id="1b523-109">Pour plus d’informations, consultez [créer des fonctions CLR](../user-defined-functions/create-clr-functions.md).</span><span class="sxs-lookup"><span data-stu-id="1b523-109">For more information, see [Create CLR Functions](../user-defined-functions/create-clr-functions.md).</span></span>  
  
-   <span data-ttu-id="1b523-110">Procédures stockées CLR.</span><span class="sxs-lookup"><span data-stu-id="1b523-110">CLR stored procedures.</span></span> <span data-ttu-id="1b523-111">Pour plus d’informations, consultez [procédures stockées CLR](../../database-engine/dev-guide/clr-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1b523-111">For more information, see [CLR Stored Procedures](../../database-engine/dev-guide/clr-stored-procedures.md).</span></span>  
  
-   <span data-ttu-id="1b523-112">Déclencheurs CLR.</span><span class="sxs-lookup"><span data-stu-id="1b523-112">CLR triggers.</span></span> <span data-ttu-id="1b523-113">Pour plus d’informations, consultez [créer des déclencheurs CLR](../triggers/create-clr-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="1b523-113">For more information, see [Create CLR Triggers](../triggers/create-clr-triggers.md).</span></span>  
  
-   <span data-ttu-id="1b523-114">Fonctions d'agrégation définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1b523-114">User-defined aggregate functions.</span></span> <span data-ttu-id="1b523-115">Pour plus d’informations, consultez [créer des agrégats définis par l’utilisateur](../user-defined-functions/create-user-defined-aggregates.md).</span><span class="sxs-lookup"><span data-stu-id="1b523-115">For more information, see [Create User-defined Aggregates](../user-defined-functions/create-user-defined-aggregates.md).</span></span>  
  
-   <span data-ttu-id="1b523-116">Types définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1b523-116">User-defined types.</span></span> <span data-ttu-id="1b523-117">Pour plus d’informations, consultez [Types CLR définis par l’utilisateur](../native-client/features/using-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="1b523-117">For more information, see [Using User-Defined Types](../native-client/features/using-user-defined-types.md).</span></span>  
  
 <span data-ttu-id="1b523-118">Les assemblys sont chargés des fonctions suivantes dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="1b523-118">Assemblies perform the following functions in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="1b523-119">Contenir le code managé qui exécute la fonctionnalité d'un ou de plusieurs objets de données CLR mentionnés précédemment.</span><span class="sxs-lookup"><span data-stu-id="1b523-119">Contain the managed code that runs the functionality of one or more of the CLR database objects previously listed.</span></span>  
  
-   <span data-ttu-id="1b523-120">Contenir les métadonnées décrivant le numéro de version et la culture de l'assembly, une clé publique facultative qui identifie de manière unique la liste des classes de l'assembly, les méthodes définies dans l'assembly et l'architecture de processeur de l'assembly.</span><span class="sxs-lookup"><span data-stu-id="1b523-120">Contain metadata that includes the version number and culture of the assembly, an optional public key that uniquely identifies the list of classes of the assembly, the methods that are defined in the assembly, and the processor architecture of the assembly.</span></span>  
  
-   <span data-ttu-id="1b523-121">Gérer le niveau d'accès du code managé aux ressources extérieures en régulant les autorisations d'accès au code.</span><span class="sxs-lookup"><span data-stu-id="1b523-121">Manage the degree to which managed code can access outside resources by regulating code access permissions.</span></span>  
  
-   <span data-ttu-id="1b523-122">Contenir les métadonnées relatives aux dépendances avec les autres assemblys auxquelles fait référence l'assembly.</span><span class="sxs-lookup"><span data-stu-id="1b523-122">Contain metadata about dependencies on other assemblies that are referenced by the assembly.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b523-123">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="1b523-123">In This Section</span></span>  
  
|<span data-ttu-id="1b523-124">Rubrique</span><span class="sxs-lookup"><span data-stu-id="1b523-124">Topic</span></span>|<span data-ttu-id="1b523-125">Description</span><span class="sxs-lookup"><span data-stu-id="1b523-125">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="1b523-126">Conception d'assemblys</span><span class="sxs-lookup"><span data-stu-id="1b523-126">Designing Assemblies</span></span>](assemblies-designing.md)|<span data-ttu-id="1b523-127">Explique les points à prendre en considération avant la création d'un assembly, notamment :</span><span class="sxs-lookup"><span data-stu-id="1b523-127">Explains what you have to consider before creating an assembly.</span></span> <span data-ttu-id="1b523-128">assemblys à inclure, autorisations d'accès au code et autres restrictions.</span><span class="sxs-lookup"><span data-stu-id="1b523-128">This includes packaging assemblies, code access permissions, and other restrictions.</span></span>|  
|[<span data-ttu-id="1b523-129">Implémentation d'assemblys</span><span class="sxs-lookup"><span data-stu-id="1b523-129">Implementing Assemblies</span></span>](assemblies-implementing.md)|<span data-ttu-id="1b523-130">Explique comment créer et supprimer des assemblys, comment et quand modifier des assemblys et comment récupérer les métadonnées relatives aux assemblys.</span><span class="sxs-lookup"><span data-stu-id="1b523-130">Explains how to create and drop assemblies, how and when to modify assemblies, and how to retrieve metadata about assemblies.</span></span>|  
|[<span data-ttu-id="1b523-131">Obtention d'informations sur les assemblys</span><span class="sxs-lookup"><span data-stu-id="1b523-131">Getting Information About Assemblies</span></span>](assemblies-getting-information.md)|<span data-ttu-id="1b523-132">Répertorie les affichages catalogue et les fonctions qu'il est possible d'interroger pour récupérer les métadonnées relatives aux assemblys.</span><span class="sxs-lookup"><span data-stu-id="1b523-132">Lists the catalog views and functions that can be queried for metadata about assemblies.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b523-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1b523-133">See Also</span></span>  
 [<span data-ttu-id="1b523-134">Concepts de programmation pour l’intégration du CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="1b523-134">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](common-language-runtime-clr-integration-programming-concepts.md)  
  
  
