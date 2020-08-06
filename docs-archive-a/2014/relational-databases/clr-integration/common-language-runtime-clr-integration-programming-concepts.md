---
title: Concepts de programmation de l’intégration du Common Language Runtime (CLR) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- CLR [SQL Server] See common language runtime [SQL Server]
- Database Engine [SQL Server], .NET Framework
- .NET Framework [SQL Server], Database Engine programming
- common language runtime [SQL Server]
- .NET Framework [SQL Server]
ms.assetid: 951bf851-3e6e-4361-ae6a-2bcd5b837ebd
author: rothja
ms.author: jroth
ms.openlocfilehash: 38323b0145132ad60d59c001d5147a7d19942462
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604036"
---
# <a name="common-language-runtime-clr-integration-programming-concepts"></a><span data-ttu-id="034b0-102">Concepts de programmation pour l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="034b0-102">Common Language Runtime (CLR) Integration Programming Concepts</span></span>
  <span data-ttu-id="034b0-103">Depuis [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] propose désormais l'intégration du composant CLR (Common Language Runtime) du .NET Framework pour [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="034b0-103">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features the integration of the common language runtime (CLR) component of the .NET Framework for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="034b0-104">Cela signifie que vous pouvez désormais écrire des procédures stockées, des déclencheurs, des types définis par l'utilisateur, des fonctions définies par l'utilisateur, des agrégats définis par l'utilisateur et des fonctions table d'accès en continu, à l'aide de n'importe quel langage du .NET Framework, notamment [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET et [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="034b0-104">This means that you can now write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="034b0-105">L'espace de noms Microsoft.SqlServer.Server inclut les fonctionnalités principales relatives à la programmation CLR dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="034b0-105">The Microsoft.SqlServer.Server namespace includes core functionality for CLR programming in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="034b0-106">Toutefois, l'espace de noms Microsoft.SqlServer.Server est documenté dans le Kit de développement logiciel (SDK) du .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="034b0-106">However, the Microsoft.SqlServer.Server namespace is documented in the .NET Framework SDK.</span></span> <span data-ttu-id="034b0-107">Cette documentation n'est pas incluse dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="034b0-107">This documentation is not included in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="034b0-108">Par défaut, le .NET Framework est installé avec [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], alors que le Kit de développement .NET Framework SDK ne l'est pas.</span><span class="sxs-lookup"><span data-stu-id="034b0-108">By default, the .NET Framework is installed with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], but the .NET Framework SDK is not.</span></span> <span data-ttu-id="034b0-109">Si le Kit de développement .NET Framework SDK n'est pas installé sur votre ordinateur et inclus dans l'ensemble de la documentation en ligne, les liens vers son contenu dans cette section ne fonctionnent pas.</span><span class="sxs-lookup"><span data-stu-id="034b0-109">Without the SDK installed on your computer and included in the Books Online collection, links to SDK content in this section do not work.</span></span> <span data-ttu-id="034b0-110">Installez le Kit de développement .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="034b0-110">Install the .NET Framework SDK.</span></span> <span data-ttu-id="034b0-111">Une fois installé, ajoutez le kit de développement logiciel (SDK) au regroupement et à la table des matières de la documentation en suivant les instructions fournies dans [installation du kit de développement logiciel (SDK) .NET Framework](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx).</span><span class="sxs-lookup"><span data-stu-id="034b0-111">Once installed, add the SDK to the Books Online collection and table of contents by following the instructions in [Installing the .NET Framework SDK](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx).</span></span>  
  
 <span data-ttu-id="034b0-112">Le tableau suivant décrit les rubriques de cette section.</span><span class="sxs-lookup"><span data-stu-id="034b0-112">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="034b0-113">Vue d’ensemble de l’intégration du Common Language Runtime &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="034b0-113">Common Language Runtime &#40;CLR&#41; Integration Overview</span></span>](common-language-runtime-integration-overview.md)  
 <span data-ttu-id="034b0-114">Fournit une brève vue d'ensemble du CLR et explique comment et pourquoi cette technologie a été utilisée dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="034b0-114">Provides a brief overview of the CLR, and describes how and why this technology has been used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="034b0-115">Décrit les avantages liés à l'utilisation du CLR pour créer des objets de base de données.</span><span class="sxs-lookup"><span data-stu-id="034b0-115">Describes the benefits of using the CLR to create database objects.</span></span>  
  
 [<span data-ttu-id="034b0-116">Assemblys &#40;moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="034b0-116">Assemblies &#40;Database Engine&#41;</span></span>](assemblies-database-engine.md)  
 <span data-ttu-id="034b0-117">Décrit l'utilisation d'assemblys dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] afin de déployer des fonctions, des procédures stockées, des déclencheurs, des agrégats définis par l'utilisateur et des types définis par l'utilisateur écrits dans l'un des langages de code managé hébergés par le CLR (Common Language Runtime) [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework, et non écrits en [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="034b0-117">Describes how assemblies are used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to deploy functions, stored procedures, triggers, user-defined aggregates, and user-defined types that are written in one of the managed code languages hosted by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework common language runtime (CLR), and not written in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 [<span data-ttu-id="034b0-118">Génération d’objets de base de données avec Common Language Runtime &#40;l’intégration du CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="034b0-118">Building Database Objects with Common Language Runtime &#40;CLR&#41; Integration</span></span>](database-objects/building-database-objects-with-common-language-runtime-clr-integration.md)  
 <span data-ttu-id="034b0-119">Décrit les types d'objets qui peuvent être créés à l'aide du CLR et examine les spécifications requises pour générer des objets de base de données CLR.</span><span class="sxs-lookup"><span data-stu-id="034b0-119">Describes the kinds of objects that can be built using the CLR, and reviews the requirements for building CLR database objects.</span></span>  
  
 [<span data-ttu-id="034b0-120">Accès aux données à partir d'objets de base de données CLR</span><span class="sxs-lookup"><span data-stu-id="034b0-120">Data Access from CLR Database Objects</span></span>](data-access/data-access-from-clr-database-objects.md)  
 <span data-ttu-id="034b0-121">Explique comment une routine CLR peut accéder aux données stockées dans une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="034b0-121">Describes how a CLR routine can access data stored in an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="034b0-122">Sécurité de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="034b0-122">CLR Integration Security</span></span>](security/clr-integration-security.md)  
 <span data-ttu-id="034b0-123">Décrit le modèle de sécurité de l'intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="034b0-123">Describes the CLR integration security model.</span></span>  
  
 [<span data-ttu-id="034b0-124">Débogage d'objets de base de données CLR</span><span class="sxs-lookup"><span data-stu-id="034b0-124">Debugging CLR Database Objects</span></span>](debugging-clr-database-objects.md)  
 <span data-ttu-id="034b0-125">Décrit les limitations et les exigences relatives au débogage des objets de base de données CLR.</span><span class="sxs-lookup"><span data-stu-id="034b0-125">Describes limitations of and requirements for debugging CLR database objects.</span></span>  
  
 [<span data-ttu-id="034b0-126">Déploiement d'objets de base de données CLR</span><span class="sxs-lookup"><span data-stu-id="034b0-126">Deploying CLR Database Objects</span></span>](deploying-clr-database-objects.md)  
 <span data-ttu-id="034b0-127">Décrit le déploiement des assemblys sur les serveurs de production.</span><span class="sxs-lookup"><span data-stu-id="034b0-127">Describes deploying assemblies to production servers.</span></span>  
  
 [<span data-ttu-id="034b0-128">Gestion des assemblys d'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="034b0-128">Managing CLR Integration Assemblies</span></span>](assemblies/managing-clr-integration-assemblies.md)  
 <span data-ttu-id="034b0-129">Explique comment créer et supprimer des assemblys d'intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="034b0-129">Describes how to create and drop CLR integration assemblies.</span></span>  
  
 [<span data-ttu-id="034b0-130">Surveillance et dépannage des objets de base de données managés</span><span class="sxs-lookup"><span data-stu-id="034b0-130">Monitoring and Troubleshooting Managed Database Objects</span></span>](monitoring-and-troubleshooting-managed-database-objects.md)  
 <span data-ttu-id="034b0-131">Fournit des informations sur les outils à l'aide desquels vous pouvez surveiller et dépanner les objets de base de données et les assemblys managés s'exécutant dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="034b0-131">Provides information about the tools that can be used to monitor and troubleshoot managed database objects and assemblies running in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="034b0-132">Scénarios et exemples d’utilisation pour l’intégration du CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="034b0-132">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
 <span data-ttu-id="034b0-133">Décrit des scénarios d'usage et des exemples de code à l'aide d'objets CLR.</span><span class="sxs-lookup"><span data-stu-id="034b0-133">Describes usage scenarios and code samples using CLR objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="034b0-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="034b0-134">See Also</span></span>  
 <span data-ttu-id="034b0-135">[Assemblys &#40;Moteur de base de données&#41;](assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="034b0-135">[Assemblies &#40;Database Engine&#41;](assemblies-database-engine.md) </span></span>  
 <span data-ttu-id="034b0-136">[Installation du SDK .NET Framework](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="034b0-136">[Installing the .NET Framework SDK](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx)</span></span>  
  
  
