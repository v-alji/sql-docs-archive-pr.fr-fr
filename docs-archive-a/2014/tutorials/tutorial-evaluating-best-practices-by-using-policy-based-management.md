---
title: 'Didacticiel : évaluation des meilleures pratiques à l’aide de la gestion basée sur des stratégies | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- best practices analyzer
- Policy-Based Management, best practices policies
- Best Practices [Database Engine]
- Policy-Based Management, evaluating policies
- BPA
- tutorials [Policy-Based Management]
- Policy-Based Management, tutorials
ms.assetid: c7867f9b-7acc-4fae-bde1-63808c403ebc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 42e6b505c71abecce7b56b5cb2544b4e9f4e8f71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702171"
---
# <a name="tutorial-evaluating-best-practices-by-using-policy-based-management"></a><span data-ttu-id="3d7a7-102">Tutoriel : Évaluation des bonnes pratiques à l’aide de la Gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="3d7a7-102">Tutorial: Evaluating Best Practices by Using Policy-Based Management</span></span>
  <span data-ttu-id="3d7a7-103">Bienvenue dans le didacticiel d'évaluation des meilleures pratiques à l'aide de la Gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="3d7a7-103">Welcome to the Evaluating Best Practices by Using Policy-Based Management tutorial.</span></span> <span data-ttu-id="3d7a7-104">Ce didacticiel est destiné aux utilisateurs familiarisés avec [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], mais ne connaissant pas la Gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="3d7a7-104">This tutorial is intended for users who are familiar with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but new to Policy-Based Management.</span></span> <span data-ttu-id="3d7a7-105">Le système de gestion basée sur des stratégies permet de définir des stratégies qui peuvent être utilisées pour appliquer des normes d'administration de site.</span><span class="sxs-lookup"><span data-stu-id="3d7a7-105">Policy-Based Management is a system for defining policies that can be used enforce site administration standards.</span></span> <span data-ttu-id="3d7a7-106">Il comprend un jeu de stratégies des meilleures pratiques que vous pouvez utiliser pour analyser une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] afin de déterminer si l'instance répond aux indications et recommandations des meilleures pratiques.</span><span class="sxs-lookup"><span data-stu-id="3d7a7-106">Policy-Based Management includes a set of best practices policies that you can use to analyze an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to determine whether the instance meets best practices guidelines and recommendations.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="3d7a7-107">Contenu du didacticiel</span><span class="sxs-lookup"><span data-stu-id="3d7a7-107">What You Will Learn</span></span>  
 <span data-ttu-id="3d7a7-108">Dans ce didacticiel, vous allez apprendre à évaluer les stratégies des meilleures pratiques pour le [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] sur une base à la demande (ou « ad hoc ») ou selon une planification.</span><span class="sxs-lookup"><span data-stu-id="3d7a7-108">In this tutorial, you will learn how to evaluate best practices policies for the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on an on-demand (or "ad hoc") basis, or on a scheduled basis.</span></span>  
  
 <span data-ttu-id="3d7a7-109">Ce didacticiel est divisé en deux leçons :</span><span class="sxs-lookup"><span data-stu-id="3d7a7-109">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="3d7a7-110">Leçon 1 : évaluer les bonnes pratiques en fonction des demandes</span><span class="sxs-lookup"><span data-stu-id="3d7a7-110">Lesson 1: Evaluate Best Practices on an On-Demand Basis</span></span>](../../2014/tutorials/lesson-1-evaluate-best-practices-on-an-on-demand-basis.md)  
 <span data-ttu-id="3d7a7-111">Dans cette leçon, vous effectuez une évaluation à la demande des stratégies sur une ou plusieurs instances de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d7a7-111">In this lesson, you perform an on-demand evaluation of the policies against one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="3d7a7-112">Leçon 2 : évaluer les stratégies des bonnes pratiques de façon planifiée</span><span class="sxs-lookup"><span data-stu-id="3d7a7-112">Lesson 2: Evaluate Best Practices Policies on a Scheduled Basis</span></span>](../../2014/tutorials/lesson-2-evaluate-best-practices-policies-on-a-scheduled-basis.md)  
 <span data-ttu-id="3d7a7-113">Dans cette leçon, vous configurez l'exécution des stratégies des meilleures pratiques de façon planifiée.</span><span class="sxs-lookup"><span data-stu-id="3d7a7-113">In this lesson, you configure best practices policies to run on a scheduled basis.</span></span> <span data-ttu-id="3d7a7-114">La leçon indique comment configurer des stratégies planifiées sur une instance unique et comment déployer des stratégies planifiées d'un emplacement centralisé vers plusieurs instances de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d7a7-114">The lesson shows how to configure scheduled policies on a single instance, and how to deploy scheduled policies from a central location to multiple instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d7a7-115">Spécifications</span><span class="sxs-lookup"><span data-stu-id="3d7a7-115">Requirements</span></span>  
 <span data-ttu-id="3d7a7-116">Cette leçon requiert une connaissance élémentaire des bases de données et une compréhension des notions fondamentales de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d7a7-116">This lesson requires basic database knowledge and a basic understanding of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="3d7a7-117">Pour utiliser ce didacticiel, [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] doit être installé sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="3d7a7-117">To use this tutorial, the server must have [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] installed.</span></span>  
  
## <a name="start-the-tutorial"></a><span data-ttu-id="3d7a7-118">Démarrer le didacticiel</span><span class="sxs-lookup"><span data-stu-id="3d7a7-118">Start the Tutorial</span></span>  
 [<span data-ttu-id="3d7a7-119">Leçon 1 : évaluer les bonnes pratiques en fonction des demandes</span><span class="sxs-lookup"><span data-stu-id="3d7a7-119">Lesson 1: Evaluate Best Practices on an On-Demand Basis</span></span>](../../2014/tutorials/lesson-1-evaluate-best-practices-on-an-on-demand-basis.md)  
  
## <a name="see-also"></a><span data-ttu-id="3d7a7-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3d7a7-120">See Also</span></span>  
 [<span data-ttu-id="3d7a7-121">Administrer des serveurs à l'aide de la Gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="3d7a7-121">Administer Servers by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
