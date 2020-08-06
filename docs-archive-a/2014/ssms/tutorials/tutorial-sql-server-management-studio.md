---
title: 'Didacticiel : SQL Server Management Studio | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.tutorialstart.ssms.f1
helpviewer_keywords:
- projects [SQL Server Management Studio], tutorials
- templates [SQL Server], SQL Server Management Studio
- source controls [SQL Server Management Studio], tutorials
- Help [SQL Server], SQL Server Management Studio
- tutorials [SQL Server Management Studio]
- Transact-SQL tutorials
- solutions [SQL Server Management Studio], tutorials
- SQL Server Management Studio [SQL Server], tutorials
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: d2bade70-07cf-4d94-b5d2-88aecb538ed1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8206fea828d6169975dc1d026a22e18e682f71e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613766"
---
# <a name="tutorial-sql-server-management-studio"></a><span data-ttu-id="354b7-102">Tutoriel : SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="354b7-102">Tutorial: SQL Server Management Studio</span></span>
  <span data-ttu-id="354b7-103">Ce didacticiel [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] vous présente l'environnement intégré pour la gestion de votre infrastructure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="354b7-103">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] tutorial introduces you to the integrated environment for managing your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] infrastructure.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="354b7-104">présente une interface graphique pour configurer, surveiller et administrer les instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="354b7-104">presents a graphical interface for configuring, monitoring, and administering instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="354b7-105">Il vous permet également de déployer, de surveiller et de mettre à niveau les composants de la couche Données utilisés par vos applications, comme les bases de données et les entrepôts de données.</span><span class="sxs-lookup"><span data-stu-id="354b7-105">It also allows you to deploy, monitor, and upgrade the data-tier components used by your applications, such as databases and data warehouses.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="354b7-106">fournit également des éditeurs de langage [!INCLUDE[tsql](../../includes/tsql-md.md)], MDX, DMX et XML pour modifier et déboguer des scripts.</span><span class="sxs-lookup"><span data-stu-id="354b7-106">also provides [!INCLUDE[tsql](../../includes/tsql-md.md)], MDX, DMX, and XML language editors for editing and debugging scripts.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="354b7-107">Contenu du didacticiel</span><span class="sxs-lookup"><span data-stu-id="354b7-107">What You Will Learn</span></span>  
 <span data-ttu-id="354b7-108">Ce didacticiel vous aidera à comprendre la présentation des informations dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] et à tirer parti des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="354b7-108">This tutorial will help you understand the presentation of information in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and how to take advantage of the features.</span></span> <span data-ttu-id="354b7-109">Notez que ce didacticiel s'applique à l'installation complète de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] inclus avec toutes les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], sauf [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="354b7-109">Note that this tutorial applies to the complete installation of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] that is included with all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="354b7-110">Les fonctionnalités pour les installations de base de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] et pour les installations de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] fournies avec [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] sont légèrement différentes de celles présentées dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="354b7-110">Functionality for basic installations of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and for [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] installations that ship with [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] is slightly different than what is presented in this tutorial.</span></span>  
  
 <span data-ttu-id="354b7-111">La meilleure façon de se familiariser avec [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] consiste à effectuer des exercices pratiques.</span><span class="sxs-lookup"><span data-stu-id="354b7-111">The best way to get acquainted with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] is through hands-on practice.</span></span> <span data-ttu-id="354b7-112">Ce didacticiel vous apprendra à gérer les composants de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] et à rechercher les fonctionnalités utilisées régulièrement.</span><span class="sxs-lookup"><span data-stu-id="354b7-112">This tutorial will teach you how to manage the components of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and how to find the features that you use regularly.</span></span>  
  
 <span data-ttu-id="354b7-113">Ce didacticiel est divisé en trois leçons :</span><span class="sxs-lookup"><span data-stu-id="354b7-113">This tutorial is divided into three lessons:</span></span>  
  
 [<span data-ttu-id="354b7-114">Leçon 1 : Navigation de base dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="354b7-114">Lesson 1: Basic Navigation in SQL Server Management Studio</span></span>](lesson-1-basic-navigation-in-sql-server-management-studio.md)  
 <span data-ttu-id="354b7-115">Dans cette leçon, vous allez apprendre à utiliser les composants de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], reconfigurer la disposition d'environnement et restaurer la disposition par défaut.</span><span class="sxs-lookup"><span data-stu-id="354b7-115">In this lesson you will learn how to use the components of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], how to reconfigure the environment layout, and how to restore the default layout.</span></span>  
  
 [<span data-ttu-id="354b7-116">Leçon 2 : Écriture d'instructions Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="354b7-116">Lesson 2: Writing Transact-SQL</span></span>](lesson-2-writing-transact-sql.md)  
 <span data-ttu-id="354b7-117">Dans cette leçon, vous allez apprendre à ouvrir l'éditeur de requête, gérer du code et utiliser les autres nouvelles fonctionnalités de l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="354b7-117">In this lesson, you will learn how to open Query Editor, how to manage code, and how to use the other new features of Query Editor.</span></span>  
  
 [<span data-ttu-id="354b7-118">Leçon 3 : utilisation de modèles, de solutions et de projets de scripts</span><span class="sxs-lookup"><span data-stu-id="354b7-118">Lesson 3: Working with Templates, Solutions, and Script Projects</span></span>](lesson-3-working-with-templates-solutions-and-script-projects.md)  
 <span data-ttu-id="354b7-119">Dans cette leçon, vous allez apprendre à utiliser des modèles et à organiser des scripts dans des solutions et des projets.</span><span class="sxs-lookup"><span data-stu-id="354b7-119">In this lesson you will learn how to use templates, and organize scripts into solutions and projects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="354b7-120">Spécifications</span><span class="sxs-lookup"><span data-stu-id="354b7-120">Requirements</span></span>  
 <span data-ttu-id="354b7-121">Ce didacticiel est destiné aux administrateurs et aux développeurs de base de données expérimentés, qui ne connaissent pas [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], mais qui maîtrisent les concepts de base de données et le langage [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="354b7-121">This tutorial is intended for experienced database administrators and database developers who are not familiar with [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], but who are who are familiar with database concepts and the [!INCLUDE[tsql](../../includes/tsql-md.md)] language.</span></span>  
  
 <span data-ttu-id="354b7-122">Les éléments suivants doivent cependant être installés sur votre système :</span><span class="sxs-lookup"><span data-stu-id="354b7-122">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="354b7-123">ou une version ultérieure avec les exemples de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="354b7-123">or a later version with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample databases.</span></span> <span data-ttu-id="354b7-124">Pour des raisons de sécurité, les exemples de bases de données ne sont pas installés par défaut.</span><span class="sxs-lookup"><span data-stu-id="354b7-124">To enhance security, the sample databases are not installed by default.</span></span> <span data-ttu-id="354b7-125">Pour installer les exemples de bases de données, consultez [Installation des exemples SQL Server et des exemples de bases de données](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="354b7-125">To install the sample databases, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
-   <span data-ttu-id="354b7-126">Internet Explorer 9.0 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="354b7-126">Internet Explorer 9.0 or later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="354b7-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="354b7-127">See Also</span></span>  
 [<span data-ttu-id="354b7-128">Didacticiels sur le moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="354b7-128">Database Engine Tutorials</span></span>](../../relational-databases/database-engine-tutorials.md)  
  
  
