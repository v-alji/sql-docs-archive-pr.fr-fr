---
title: Créer un rapport de tableau de base (didacticiel SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- walkthroughs [Reporting Services]
- tutorials [Reporting Services]
- reports [Reporting Services], creating
ms.assetid: 3b539b4b-26f2-4c0b-b506-80f175679a46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02e0f42869a3bfa88e0c6646fd447968c8ba3a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599795"
---
# <a name="create-a-basic-table-report-ssrs-tutorial"></a><span data-ttu-id="9e98f-102">Créer un rapport de tableau de base (didacticiel SSRS)</span><span class="sxs-lookup"><span data-stu-id="9e98f-102">Create a Basic Table Report (SSRS Tutorial)</span></span>
  <span data-ttu-id="9e98f-103">Ce didacticiel est conçu pour vous aider à créer un rapport de table de base à l’aide du Concepteur de rapports, à partir de la base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9e98f-103">This tutorial is designed to help you create a basic table report based on the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database using Report Designer.</span></span> <span data-ttu-id="9e98f-104">Pour créer des rapports, vous pouvez également utiliser le Générateur de rapports et l'Assistant Rapport.</span><span class="sxs-lookup"><span data-stu-id="9e98f-104">You can also use Report Builder or the Report Wizard to create reports.</span></span> <span data-ttu-id="9e98f-105">Dans ce didacticiel, vous allez créer un projet de rapport, configurer des informations de connexion, définir une requête, ajouter une région de données de table, regrouper certains champs et calculer leurs totaux et afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="9e98f-105">In this tutorial, you will create a report project, set up connection information, define a query, add a Table data region, group and total some fields, and preview the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9e98f-106">Pour suivre ce didacticiel, vous devez exécuter [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] en mode natif.</span><span class="sxs-lookup"><span data-stu-id="9e98f-106">To complete this tutorial, you must be running [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in native mode.</span></span> <span data-ttu-id="9e98f-107">Si vous exécutez [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] en mode intégré SharePoint, les étapes faisant appel aux URL de serveur de rapports ne fonctionnent pas.</span><span class="sxs-lookup"><span data-stu-id="9e98f-107">If you are running [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in SharePoint integrated mode, the steps that use report server URLs do not work.</span></span> <span data-ttu-id="9e98f-108">Pour plus d’informations sur les [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] modes, consultez [Reporting Services serveur de rapports](reporting-services-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="9e98f-108">For more information about [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] modes, see [Reporting Services Report Server](reporting-services-report-server.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e98f-109">Spécifications</span><span class="sxs-lookup"><span data-stu-id="9e98f-109">Requirements</span></span>  
 <span data-ttu-id="9e98f-110">Les éléments suivants doivent cependant être installés sur votre système :</span><span class="sxs-lookup"><span data-stu-id="9e98f-110">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="9e98f-111">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="9e98f-111">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database engine.</span></span>  
  
-   <span data-ttu-id="9e98f-112">La base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9e98f-112">The [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  <span data-ttu-id="9e98f-113">Pour plus d’informations, consultez [Adventure Works pour SQL Server 2012 (Adventure Works pour SQL Server 2012)](https://go.microsoft.com/fwlink/?LinkId=245471) ( https://go.microsoft.com/fwlink/?LinkId=245471). .</span><span class="sxs-lookup"><span data-stu-id="9e98f-113">For more information, see [Adventure Works for SQL Server 2012 (Adventure Works for SQL Server 2012)](https://go.microsoft.com/fwlink/?LinkId=245471) (https://go.microsoft.com/fwlink/?LinkId=245471)..</span></span> <span data-ttu-id="9e98f-114">Pour plus d’informations sur la prise en charge des [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] exemples de bases de données et d’exemples de code pour [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] , consultez [vue d’ensemble des bases de données et exemples](https://go.microsoft.com/fwlink/?LinkId=110391) sur le site Web CodePlex.</span><span class="sxs-lookup"><span data-stu-id="9e98f-114">For more information about support for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sample databases and sample code for [!INCLUDE[ssExpress](../includes/ssexpress-md.md)], see [Databases and Samples Overview](https://go.microsoft.com/fwlink/?LinkId=110391) on the CodePlex Web site.</span></span>  
  
-   [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)]<span data-ttu-id="9e98f-115">.</span><span class="sxs-lookup"><span data-stu-id="9e98f-115">.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="9e98f-116">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e98f-116">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNote64Samp](../includes/ssnote64samp-md.md)]  
  
 <span data-ttu-id="9e98f-117">Vous devez également disposer d’autorisations en lecture seule pour pouvoir récupérer les données de la base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9e98f-117">You must also have read-only permissions to retrieve data from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="9e98f-118">Tâches</span><span class="sxs-lookup"><span data-stu-id="9e98f-118">Tasks</span></span>  
 [<span data-ttu-id="9e98f-119">Leçon 1 : Création d’un projet Report Server &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9e98f-119">Lesson 1: Creating a Report Server Project &#40;Reporting Services&#41;</span></span>](lesson-1-creating-a-report-server-project-reporting-services.md)  
  
 [<span data-ttu-id="9e98f-120">Leçon 2 : Spécification des informations de connexion &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9e98f-120">Lesson 2: Specifying Connection Information &#40;Reporting Services&#41;</span></span>](lesson-2-specifying-connection-information-reporting-services.md)  
  
 [<span data-ttu-id="9e98f-121">Leçon 3 : Définition d’un dataset destiné à un rapport de table &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9e98f-121">Lesson 3: Defining a Dataset for the Table Report &#40;Reporting Services&#41;</span></span>](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md)  
  
 [<span data-ttu-id="9e98f-122">Leçon 4 : Ajout d’une table au rapport &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9e98f-122">Lesson 4: Adding a Table to the Report &#40;Reporting Services&#41;</span></span>](lesson-4-adding-a-table-to-the-report-reporting-services.md)  
  
 [<span data-ttu-id="9e98f-123">Leçon 5 : Mise en forme d’un rapport &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9e98f-123">Lesson 5: Formatting a Report &#40;Reporting Services&#41;</span></span>](lesson-5-formatting-a-report-reporting-services.md)  
  
 [<span data-ttu-id="9e98f-124">Leçon 6 : Ajout d’un regroupement et de totaux &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9e98f-124">Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;</span></span>](lesson-6-adding-grouping-and-totals-reporting-services.md)  
  
> [!NOTE]  
>  <span data-ttu-id="9e98f-125">Lorsque vous examinez des didacticiels, nous vous recommandons d’ajouter les boutons **suivant** et **précédent** dans la barre d’outils de la visionneuse de documents.</span><span class="sxs-lookup"><span data-stu-id="9e98f-125">When reviewing tutorials, we recommend that you add **Next** and **Previous** buttons to the document viewer toolbar.</span></span> <span data-ttu-id="9e98f-126">Pour plus d'informations, consultez</span><span class="sxs-lookup"><span data-stu-id="9e98f-126">For more information, see.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e98f-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9e98f-127">See Also</span></span>  
 [<span data-ttu-id="9e98f-128">Didacticiels sur Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9e98f-128">Reporting Services Tutorials &#40;SSRS&#41;</span></span>](reporting-services-tutorials-ssrs.md)  
  
  
