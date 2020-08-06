---
title: Accès au service Web Report Server à l’aide de Visual Basic ou Visual C# (didacticiel SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- walkthroughs [Reporting Services]
- Reporting Services, Web service
- Web service [Reporting Services], tutorials
ms.assetid: cf688163-4ac0-475b-b6dd-6f2f05b553c6
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 3dc2599b4fafe682d74089d637918e04db9ed219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704516"
---
# <a name="accessing-the-report-server-web-service-using-visual-basic-or-visual-c-ssrs-tutorial"></a><span data-ttu-id="46fd2-102">Accès au service Web Report Server avec Visual Basic ou Visual C# (didacticiel SSRS)</span><span class="sxs-lookup"><span data-stu-id="46fd2-102">Accessing the Report Server Web Service Using Visual Basic or Visual C# (SSRS Tutorial)</span></span>
  <span data-ttu-id="46fd2-103">Le didacticiel suivant vous montre comment accéder au service Web Report Server à partir d’une application créée avec [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ou [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[csprcs](../includes/csprcs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="46fd2-103">The following tutorial shows you how to access the Report Server Web service from an application created with [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] or [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[csprcs](../includes/csprcs-md.md)].</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="46fd2-104">Contenu du didacticiel</span><span class="sxs-lookup"><span data-stu-id="46fd2-104">What You Will Learn</span></span>  
 <span data-ttu-id="46fd2-105">Au cours de l'étude de ce didacticiel, vous allez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="46fd2-105">During the course of this tutorial, you will complete the following:</span></span>  
  
-   <span data-ttu-id="46fd2-106">Créez une application cliente à l’aide du [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] modèle de projet application console.</span><span class="sxs-lookup"><span data-stu-id="46fd2-106">Create a client application using the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] Console Application project template.</span></span>  
  
-   <span data-ttu-id="46fd2-107">Ajouter une référence Web pour le service Web Report Server.</span><span class="sxs-lookup"><span data-stu-id="46fd2-107">Add a Web reference for the Report Server Web service.</span></span>  
  
-   <span data-ttu-id="46fd2-108">Écrire du code pour accéder au service Web.</span><span class="sxs-lookup"><span data-stu-id="46fd2-108">Write code to access the Web service.</span></span>  
  
-   <span data-ttu-id="46fd2-109">Exécuter l'application console en mode débogage.</span><span class="sxs-lookup"><span data-stu-id="46fd2-109">Run the console application in debug mode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46fd2-110">Spécifications</span><span class="sxs-lookup"><span data-stu-id="46fd2-110">Requirements</span></span>  
 <span data-ttu-id="46fd2-111">Pour exécuter ce didacticiel, vous devez disposer des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="46fd2-111">To complete the tutorial, you must have the following:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="46fd2-112">[!INCLUDE[ssSQL11](../includes/sssql11-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46fd2-112">[!INCLUDE[ssSQL11](../includes/sssql11-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="46fd2-113">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)]ou similaire [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] -outil de développement compatible.</span><span class="sxs-lookup"><span data-stu-id="46fd2-113">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] or a similar [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]-compatible development tool.</span></span>  
  
-   <span data-ttu-id="46fd2-114">Des autorisations suffisantes pour accéder au service Web Report Server de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sur l'ordinateur sur lequel se trouve le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="46fd2-114">Sufficient permissions to be able to access the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Report Server Web service on the computer where your report server is located.</span></span>  
  
-   <span data-ttu-id="46fd2-115">Un rapport installé sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="46fd2-115">A report installed on your report server.</span></span> <span data-ttu-id="46fd2-116">Ce didacticiel utilise l'exemple de rapport intitulé Company Sales.</span><span class="sxs-lookup"><span data-stu-id="46fd2-116">This tutorial uses the sample report, Company Sales.</span></span> <span data-ttu-id="46fd2-117">Pour plus d’informations sur les exemples de rapports, consultez [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="46fd2-117">For more information about sample reports, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="46fd2-118">Les exemples ne sont pas installés automatiquement, mais peuvent l'être à tout moment.</span><span class="sxs-lookup"><span data-stu-id="46fd2-118">The samples are not installed automatically during setup, but you can install them at any time.</span></span> <span data-ttu-id="46fd2-119">Pour plus d’informations sur les exemples, consultez [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span><span class="sxs-lookup"><span data-stu-id="46fd2-119">For information about samples, see [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span></span>  
  
 <span data-ttu-id="46fd2-120">**Durée estimée pour suivre le didacticiel :** 60 minutes</span><span class="sxs-lookup"><span data-stu-id="46fd2-120">**Estimated time to complete the tutorial:** 60 minutes</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="46fd2-121">Tâches</span><span class="sxs-lookup"><span data-stu-id="46fd2-121">Tasks</span></span>  
 [<span data-ttu-id="46fd2-122">Leçon 1 : Création du projet client du service web</span><span class="sxs-lookup"><span data-stu-id="46fd2-122">Lesson 1: Creating the Web Service Client Project</span></span>](../../2014/tutorials/lesson-1-creating-the-web-service-client-project.md)  
  
 [<span data-ttu-id="46fd2-123">Leçon 2 : Ajout d’une référence web</span><span class="sxs-lookup"><span data-stu-id="46fd2-123">Lesson 2: Adding a Web Reference</span></span>](../../2014/tutorials/lesson-2-adding-a-web-reference.md)  
  
 [<span data-ttu-id="46fd2-124">Leçon 3 : Accès au service web</span><span class="sxs-lookup"><span data-stu-id="46fd2-124">Lesson 3: Accessing the Web Service</span></span>](../../2014/tutorials/lesson-3-accessing-the-web-service.md)  
  
 [<span data-ttu-id="46fd2-125">Leçon 4 : exécution de l’application &#40;VB-VC&#35;&#41;</span><span class="sxs-lookup"><span data-stu-id="46fd2-125">Lesson 4: Running the Application &#40;VB-VC&#35;&#41;</span></span>](../../2014/tutorials/lesson-4-running-the-application-vb-vcsharp.md)  
  
  
