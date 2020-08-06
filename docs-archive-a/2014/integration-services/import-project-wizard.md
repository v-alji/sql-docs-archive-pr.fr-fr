---
title: Assistant importation de projet | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.importprojectwizard.f1
ms.assetid: 9247ad6c-4bd1-43ab-b347-583181cb9917
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 81a990995d7e98c21b61f484372d31c9a1773102
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605643"
---
# <a name="import-project-wizard"></a><span data-ttu-id="d3432-102">Assistant Importation de projet</span><span class="sxs-lookup"><span data-stu-id="d3432-102">Import Project Wizard</span></span>
  <span data-ttu-id="d3432-103">Utilisez l'Assistant Importation de projet de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] pour créer un nouveau projet Integration Services en fonction d'un projet existant.</span><span class="sxs-lookup"><span data-stu-id="d3432-103">Use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Import Project Wizard create a new Integration Services project based on an existing one.</span></span> <span data-ttu-id="d3432-104">Importez des projets déjà déployés dans le catalogue [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ou à partir d’un fichier de déploiement de projet (extension .ispac).</span><span class="sxs-lookup"><span data-stu-id="d3432-104">Import projects that have already been deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog or import projects from a project deployment file (.ispac extension).</span></span>  
  
### <a name="to-create-a-project-based-on-a-project-in-ispac-file-or-in-catalog"></a><span data-ttu-id="d3432-105">Pour créer un projet basé sur un projet dans un fichier .ispac ou dans le catalogue</span><span class="sxs-lookup"><span data-stu-id="d3432-105">To create a project based on a project in .ispac file or in catalog</span></span>  
  
1.  <span data-ttu-id="d3432-106">Cliquez sur **fichier**, pointez sur **nouveau**, puis cliquez sur projet.</span><span class="sxs-lookup"><span data-stu-id="d3432-106">Click **File**, point to **New**, and click Project.</span></span>  
  
2.  <span data-ttu-id="d3432-107">Développez **Business Intelligence**, puis cliquez sur **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="d3432-107">Expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="d3432-108">Sélectionnez **Assistant Importation de projet Integration Services** dans le volet central, tapez un **nom** pour la solution, le projet, puis spécifiez le **dossier** du projet et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3432-108">Select **Integration Services Import Wizard** in the middle pane, type a **name** for the solution, project, and specify the **folder** for the project, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d3432-109">Vous devez voir l' **Assistant Importation de projet Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="d3432-109">You should see the **Integration Services Import Project Wizard**.</span></span> <span data-ttu-id="d3432-110">Cet Assistant crée un nouveau projet Integration Services en fonction d'un projet existant</span><span class="sxs-lookup"><span data-stu-id="d3432-110">This wizard creates a new Integration Services project based on an existing one</span></span>  
  
4.  <span data-ttu-id="d3432-111">Cliquez sur **Suivant** sur la page **Introduction** pour afficher la page **Sélectionner une source** .</span><span class="sxs-lookup"><span data-stu-id="d3432-111">Click **Next** on the **Introduction** page to see the **Select Source** page.</span></span>  
  
5.  <span data-ttu-id="d3432-112">Spécifiez si vous souhaitez importer le projet à partir d'un fichier .ispac ou d'un catalogue.</span><span class="sxs-lookup"><span data-stu-id="d3432-112">Specify whether you want to import project from an .ispac file or from a catalog.</span></span>  
  
    -   <span data-ttu-id="d3432-113">Si vous sélectionnez l'option **Fichier de déploiement de projet** , spécifiez le chemin d'accès au fichier .ispac.</span><span class="sxs-lookup"><span data-stu-id="d3432-113">If you select **Project deployment file** option, specify the path to the .ispac file.</span></span>  
  
    -   <span data-ttu-id="d3432-114">Si vous sélectionnez l'option **Catalogue Integration Services** , spécifiez le nom de l'instance du serveur de base de données sur laquelle le catalogue existe et le chemin d'accès au projet dans le catalogue.</span><span class="sxs-lookup"><span data-stu-id="d3432-114">If you select **Integration Services Catalog** option, specify the name of database server instance on which the catalog exists, and the path to the project in the catalog.</span></span>  
  
6.  <span data-ttu-id="d3432-115">Cliquez sur **Suivant** sur la page **Sélectionner une source** pour afficher la page **Révision** .</span><span class="sxs-lookup"><span data-stu-id="d3432-115">Click **Next** on the **Select Source** page to see the **Review** page.</span></span> <span data-ttu-id="d3432-116">Vérifiez les informations affichées dans la page concernant l'opération d'importation que l'Assistant va exécuter.</span><span class="sxs-lookup"><span data-stu-id="d3432-116">Review the information displayed on the page about the import operation the wizard is going to perform.</span></span>  
  
7.  <span data-ttu-id="d3432-117">Cliquez sur **Importer** pour créer un nouveau projet Integration Services selon le projet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d3432-117">Click **Import** to create a new Integration Services project based on the one you selected.</span></span>  
  
8.  <span data-ttu-id="d3432-118">La page **Résultats** doit afficher les résultats de l'opération d'importation exécutée par l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="d3432-118">The **Results** page should display the results from import operation the wizard performed.</span></span> <span data-ttu-id="d3432-119">Cliquez sur **Enregistrer le rapport** pour enregistrer le rapport dans un fichier XML.</span><span class="sxs-lookup"><span data-stu-id="d3432-119">Click **Save Report** to save the report to an XML file.</span></span>  
  
9. <span data-ttu-id="d3432-120">Cliquez sur **Fermer** pour fermer l’assistant.</span><span class="sxs-lookup"><span data-stu-id="d3432-120">Click **Close** to close the wizard.</span></span>  
  
  
