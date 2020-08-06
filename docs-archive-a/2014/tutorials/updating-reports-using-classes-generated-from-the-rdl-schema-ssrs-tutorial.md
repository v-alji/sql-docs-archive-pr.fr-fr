---
title: Mise à jour des rapports à l’aide de classes générées à partir du schéma RDL (didacticiel SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RDL [Reporting Services], generating
- RDL [Reporting Services], tutorials
- RDL [Reporting Services], serializing
ms.assetid: 8f81d48f-7ab9-4ef8-bce0-7d16d9a47fbd
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: f3972b8e1af6d50ccc6f5188c8f671fe333ebce8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601813"
---
# <a name="updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial"></a><span data-ttu-id="28a0a-102">Mise à jour des rapports à l'aide des classes générées à partir du schéma RDL (didacticiel SSRS)</span><span class="sxs-lookup"><span data-stu-id="28a0a-102">Updating Reports Using Classes Generated from the RDL Schema (SSRS Tutorial)</span></span>
  <span data-ttu-id="28a0a-103">Ce didacticiel explique comment utiliser l’outil XML Schema Definition (Xsd.exe) pour générer des classes qui vous permettent de sérialiser et de désérialiser des fichiers de définition de rapport (. rdl et. rdlc) avec la [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] <xref:System.Xml.Serialization.XmlSerializer> classe.</span><span class="sxs-lookup"><span data-stu-id="28a0a-103">This tutorial illustrates how to use the XML Schema Definition Tool (Xsd.exe) to generate classes that allow you to serialize and deserialize report definition files (.rdl and .rdlc) with the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="28a0a-104">Contenu du didacticiel</span><span class="sxs-lookup"><span data-stu-id="28a0a-104">What You Will Learn</span></span>  
 <span data-ttu-id="28a0a-105">Au cours de l'étude de ce didacticiel, vous allez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="28a0a-105">During the course of this tutorial, you will complete the following activities:</span></span>  
  
-   <span data-ttu-id="28a0a-106">Créez une application à l’aide du [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] modèle de projet d’application console.</span><span class="sxs-lookup"><span data-stu-id="28a0a-106">Create an application using the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Console Application project template.</span></span>  
  
-   <span data-ttu-id="28a0a-107">Générez des classes à partir du schéma Report Definition Language (RDL) à l’aide de l’outil **xsd** .</span><span class="sxs-lookup"><span data-stu-id="28a0a-107">Generate classes from the Report Definition Language (RDL) schema using the **xsd** tool.</span></span>  
  
-   <span data-ttu-id="28a0a-108">Se connecter à un serveur de rapports et extraire une définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="28a0a-108">Connect to a report server and retrieve a report definition.</span></span>  
  
-   <span data-ttu-id="28a0a-109">Écrire le code de mise à jour du fichier de définition du rapport.</span><span class="sxs-lookup"><span data-stu-id="28a0a-109">Write code to update the report definition file.</span></span>  
  
-   <span data-ttu-id="28a0a-110">Réenregistrer la définition mise à jour du rapport sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="28a0a-110">Save the updated report definition back to the report server.</span></span>  
  
-   <span data-ttu-id="28a0a-111">Exécutez l'application de schéma RDL (VB/C#).</span><span class="sxs-lookup"><span data-stu-id="28a0a-111">Run the RDL Schema Application (VB/C#).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28a0a-112">Les exemples de code fournis dans ce didacticiel risquent d'échouer pour les rapports ne comportant aucune description.</span><span class="sxs-lookup"><span data-stu-id="28a0a-112">The code samples provided in this tutorial might fail for reports having no description.</span></span> <span data-ttu-id="28a0a-113">L'échec s'explique par l'absence de la propriété de description pour les rapports pour lesquels aucune description n'est spécifiée.</span><span class="sxs-lookup"><span data-stu-id="28a0a-113">The failure is because the description property does not exist for the reports with description not specified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28a0a-114">Spécifications</span><span class="sxs-lookup"><span data-stu-id="28a0a-114">Requirements</span></span>  
 <span data-ttu-id="28a0a-115">Pour exécuter ce didacticiel, vous devez disposer des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="28a0a-115">To complete the tutorial, you must have the following:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="28a0a-116">[!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28a0a-116">[!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="28a0a-117">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28a0a-117">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span></span>  
  
-   <span data-ttu-id="28a0a-118">Autorisations suffisantes pour accéder au service Web Report Server et y publier des rapports sur l'ordinateur sur lequel se trouve le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="28a0a-118">Sufficient permissions to be able to access and publish reports to the Report Server Web service on the computer where your report server is located.</span></span>  
  
-   <span data-ttu-id="28a0a-119">Exemple de base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] installé sur une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28a0a-119">The [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database installed to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="28a0a-120">Un rapport installé sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="28a0a-120">A report installed on your report server.</span></span> <span data-ttu-id="28a0a-121">Ce didacticiel utilise l'exemple de rapport intitulé Company Sales 2012.</span><span class="sxs-lookup"><span data-stu-id="28a0a-121">This tutorial uses the sample report, Company Sales 2012.</span></span> <span data-ttu-id="28a0a-122">Pour plus d’informations sur les exemples de rapports, consultez [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="28a0a-122">For more information about sample reports, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28a0a-123">Les exemples ne sont pas installés automatiquement, mais peuvent l'être à tout moment.</span><span class="sxs-lookup"><span data-stu-id="28a0a-123">The samples are not installed automatically during setup, but you can install them at any time.</span></span> <span data-ttu-id="28a0a-124">Pour plus d’informations sur les exemples, consultez [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span><span class="sxs-lookup"><span data-stu-id="28a0a-124">For information about samples, see [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span></span>  
  
 <span data-ttu-id="28a0a-125">**Durée estimée pour effectuer ce didacticiel :** 30 minutes</span><span class="sxs-lookup"><span data-stu-id="28a0a-125">**Estimated time to complete the tutorial:** 30 minutes</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="28a0a-126">Tâches</span><span class="sxs-lookup"><span data-stu-id="28a0a-126">Tasks</span></span>  
 [<span data-ttu-id="28a0a-127">Leçon 1 : Créer le projet Visual Studio du schéma RDL</span><span class="sxs-lookup"><span data-stu-id="28a0a-127">Lesson 1: Create the RDL Schema Visual Studio Project</span></span>](../../2014/tutorials/lesson-1-create-the-rdl-schema-visual-studio-project.md)  
  
 [<span data-ttu-id="28a0a-128">Leçon 2 : Générer des classes à partir du schéma RDL à l’aide de l’outil xsd</span><span class="sxs-lookup"><span data-stu-id="28a0a-128">Lesson 2: Generate Classes from the RDL Schema using the xsd Tool</span></span>](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md)  
  
 [<span data-ttu-id="28a0a-129">Leçon 3 : Charger une définition de rapport à partir du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="28a0a-129">Lesson 3: Load a Report Definition from the Report Server</span></span>](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md)  
  
 [<span data-ttu-id="28a0a-130">Leçon 4 : Mettre à jour la définition du rapport par programmation</span><span class="sxs-lookup"><span data-stu-id="28a0a-130">Lesson 4: Update the Report Definition Programmatically</span></span>](../../2014/tutorials/lesson-4-update-the-report-definition-programmatically.md)  
  
 [<span data-ttu-id="28a0a-131">Leçon 5 : Publier la définition du rapport sur le serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="28a0a-131">Lesson 5: Publish the Report Definition to the Report Server</span></span>](../../2014/tutorials/lesson-5-publish-the-report-definition-to-the-report-server.md)  
  
 [<span data-ttu-id="28a0a-132">Leçon 6 : exécuter l’application de schéma RDL &#40;VB-C&#35;&#41;</span><span class="sxs-lookup"><span data-stu-id="28a0a-132">Lesson 6: Run the RDL Schema Application &#40;VB-C&#35;&#41;</span></span>](../../2014/tutorials/lesson-6-run-the-rdl-schema-application-vb-csharp.md)  
  
## <a name="see-also"></a><span data-ttu-id="28a0a-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28a0a-133">See Also</span></span>  
 [<span data-ttu-id="28a0a-134">RDL (Report Definition Language) &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="28a0a-134">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
