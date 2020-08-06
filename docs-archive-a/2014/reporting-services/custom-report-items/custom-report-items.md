---
title: Éléments de rapport personnalisés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- extending Reporting Services
- Reporting Services, extending
- custom report items
ms.assetid: 64dcaf2c-1af5-4937-8ff7-98f1ec3b367e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 86b819cb4d305e537a52a2e7f25cdfa3aefa5f9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708995"
---
# <a name="custom-report-items"></a><span data-ttu-id="d695d-102">Éléments de rapport personnalisés</span><span class="sxs-lookup"><span data-stu-id="d695d-102">Custom Report Items</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="d695d-103">propose un ensemble d'outils permettant de générer et de publier des rapports d'entreprise, de gérer la sécurité et les abonnements et d'étendre les fonctionnalités de création de rapports par le biais d'une API complète.</span><span class="sxs-lookup"><span data-stu-id="d695d-103">provides a rich set of tools for building and publishing enterprise reports, managing security and subscriptions, and extending the reporting functionality through a comprehensive API.</span></span> <span data-ttu-id="d695d-104">Les rapports sont définis au moyen d'un langage XML appelé RDL (Report Definition Language).</span><span class="sxs-lookup"><span data-stu-id="d695d-104">Reports are defined using an XML-based language called Report Definition Language (RDL).</span></span> <span data-ttu-id="d695d-105">Ce langage fournit un ensemble d'instructions qui décrivent la disposition, les informations de requête et les types d'éléments d'un rapport.</span><span class="sxs-lookup"><span data-stu-id="d695d-105">RDL provides a set of instructions that describe layout, query information, and item types for a report.</span></span> <span data-ttu-id="d695d-106">Il est possible d'étendre le langage RDL en écrivant un élément de rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="d695d-106">It is possible to extend RDL by writing a custom report item.</span></span> <span data-ttu-id="d695d-107">L'élément de rapport personnalisé regroupe un composant runtime, qui est appelé par le processeur de rapports au moment de l'exécution, et un composant design, qui permet à l'élément de rapport personnalisé d'être disponible dans le Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d695d-107">The custom report item consists of a run-time component, which is called by the report processor at run time, and a design-time component, which allows the custom report item to be available in Report Designer.</span></span>  
  
 <span data-ttu-id="d695d-108">Pour un exemple d’élément de rapport personnalisé totalement implémenté, consultez [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889) (Exemples Reporting Services pour le produit SQL Server).</span><span class="sxs-lookup"><span data-stu-id="d695d-108">For a sample of a fully implemented custom report item, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="custom-report-item-scenarios"></a><span data-ttu-id="d695d-109">Scénarios d'utilisation d'éléments de rapport personnalisés</span><span class="sxs-lookup"><span data-stu-id="d695d-109">Custom Report Item Scenarios</span></span>  
 <span data-ttu-id="d695d-110">Les développeurs qui doivent intégrer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans leurs applications peuvent avoir besoin de fonctionnalités qui ne sont pas prises en charge en mode natif dans le langage RDL.</span><span class="sxs-lookup"><span data-stu-id="d695d-110">Developers who need to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into their applications may require functionality that is not natively supported in RDL.</span></span> <span data-ttu-id="d695d-111">Il peut s'agir d'éléments comme des contrôles de plan, des listes horizontales, des listes en colonnes ou encore des matrices pivotables.</span><span class="sxs-lookup"><span data-stu-id="d695d-111">This may include items such as: map controls, horizontal lists, columnar lists, and repivotable matrixes.</span></span> <span data-ttu-id="d695d-112">Un composant runtime d'élément de rapport personnalisé peut être développé et distribué avec une application pour répondre à ce besoin.</span><span class="sxs-lookup"><span data-stu-id="d695d-112">A run-time custom report item component can be developed and distributed with an application to fill this need.</span></span>  
  
 <span data-ttu-id="d695d-113">En plus de fournir des fonctionnalités qui ne sont pas prises en charge en mode natif, certains développeurs voudront étendre les fonctionnalités existantes en proposant d’autres versions des contrôles qui sont déjà inclus avec [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d695d-113">In addition to providing functionality that isn't natively supported, some developers may want to extend existing functionality with alternative versions of controls that are already included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="d695d-114">Dans ce scénario, un développeur peut fournir trois composants : un composant runtime, un composant design et un composant runtime de conversion d'éléments de rapport qui convertit un élément de rapport existant en élément de rapport personnalisé à la demande.</span><span class="sxs-lookup"><span data-stu-id="d695d-114">In this scenario, a developer could provide three components: a run-time component, a design-time component, and a design-time report item conversion component that converts an existing report item into a custom report item on demand.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d695d-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d695d-115">In This Section</span></span>  
 [<span data-ttu-id="d695d-116">Architecture des éléments de rapports personnalisés</span><span class="sxs-lookup"><span data-stu-id="d695d-116">Custom Report Item Architecture</span></span>](custom-report-item-architecture.md)  
 <span data-ttu-id="d695d-117">Décrit les composants d'un élément de rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="d695d-117">Describes the components that make up a custom report item.</span></span>  
  
 [<span data-ttu-id="d695d-118">Conditions d'implémentation des éléments de rapports personnalisés</span><span class="sxs-lookup"><span data-stu-id="d695d-118">Custom Report Item Implementation Requirements</span></span>](custom-report-item-implementation-requirements.md)  
 <span data-ttu-id="d695d-119">Décrit les conditions requises pour créer un élément de rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="d695d-119">Describes prerequisites for creating a custom report item.</span></span>  
  
 [<span data-ttu-id="d695d-120">Création d'un composant d'exécution d'élément de rapport personnalisé</span><span class="sxs-lookup"><span data-stu-id="d695d-120">Creating a Custom Report Item Run-Time Component</span></span>](creating-a-custom-report-item-run-time-component.md)  
 <span data-ttu-id="d695d-121">Décrit comment créer un composant runtime d'élément de rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="d695d-121">Describes how to create a custom report item run-time component.</span></span>  
  
 [<span data-ttu-id="d695d-122">Création d'un composant au moment de la conception d'élément de rapport personnalisé</span><span class="sxs-lookup"><span data-stu-id="d695d-122">Creating a Custom Report Item Design-Time Component</span></span>](creating-a-custom-report-item-design-time-component.md)  
 <span data-ttu-id="d695d-123">Décrit comment créer un composant design d'élément de rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="d695d-123">Describes how to create a custom report item design-time component.</span></span>  
  
 [<span data-ttu-id="d695d-124">Procédure : déployer un élément de rapport personnalisé</span><span class="sxs-lookup"><span data-stu-id="d695d-124">How to: Deploy a Custom Report Item</span></span>](how-to-deploy-a-custom-report-item.md)  
 <span data-ttu-id="d695d-125">Décrit comment déployer un élément de rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="d695d-125">Describes how to deploy a custom report item.</span></span>  
  
 [<span data-ttu-id="d695d-126">Bibliothèques de classes d'éléments de rapport personnalisés</span><span class="sxs-lookup"><span data-stu-id="d695d-126">Custom Report Item Class Libraries</span></span>](custom-report-item-class-libraries.md)  
 <span data-ttu-id="d695d-127">Décrit les classes d'infrastructure d'éléments de rapport personnalisés et les classes wrapper managées dans l'espace de noms `Microsoft.ReportDesigner`.</span><span class="sxs-lookup"><span data-stu-id="d695d-127">Describes the custom report item infrastructure classes and managed wrapper classes in the `Microsoft.ReportDesigner` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d695d-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d695d-128">See Also</span></span>  
 [<span data-ttu-id="d695d-129">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d695d-129">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
