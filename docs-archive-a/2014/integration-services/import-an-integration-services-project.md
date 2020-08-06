---
title: Importer un projet de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3301c328-b0f5-4517-915c-93713413e453
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a98219f3a04d11e086957d64a62e7c64cd51418
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601581"
---
# <a name="import-an-integration-services-project"></a><span data-ttu-id="24621-102">Importer un projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="24621-102">Import an Integration Services Project</span></span>
  <span data-ttu-id="24621-103">Utilisez [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]l’Assistant Importation de projet\*\*\*\* pour créer un projet à partir d’un fichier existant de déploiement (.ispac) ou d’un projet déployé sur le catalogue Integration Services.</span><span class="sxs-lookup"><span data-stu-id="24621-103">Use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]**Import Project Wizard** to create a project from an existing deployment file (.ispac) or from a project deployed to Integration services catalog.</span></span> <span data-ttu-id="24621-104">Cette fonctionnalité est particulièrement utile lorsque vous n'avez pas la copie originale du projet, mais que vous voulez en créer un à partir d'un fichier .ispac ou d'un catalogue SSISDB.</span><span class="sxs-lookup"><span data-stu-id="24621-104">This feature is especially useful when you do not have the original copy of the project but you want to create one from an .ispac file or SSISDB catalog.</span></span>  
  
### <a name="to-import-a-project"></a><span data-ttu-id="24621-105">Pour importer un projet</span><span class="sxs-lookup"><span data-stu-id="24621-105">To Import a Project</span></span>  
  
1.  <span data-ttu-id="24621-106">Dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , cliquez sur **nouveau**  >  **projet** dans le menu **fichier** .</span><span class="sxs-lookup"><span data-stu-id="24621-106">In [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], click **New** > **Project** on the **File** menu.</span></span>  
  
2.  <span data-ttu-id="24621-107">Dans la zone **Modèles installés** de la fenêtre **Nouveau projet** , développez **Business Intelligence**, puis cliquez sur **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="24621-107">In the **Installed Templates** area of the **New Project** window, expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="24621-108">Sélectionnez **l’Assistant Importation de projet Integration Services** dans la liste des types de projets.</span><span class="sxs-lookup"><span data-stu-id="24621-108">Select **Integration Services Import Project Wizard** from the project types list.</span></span>  
  
4.  <span data-ttu-id="24621-109">Tapez le nom du nouveau projet à créer dans la zone de texte **Nom** .</span><span class="sxs-lookup"><span data-stu-id="24621-109">Type a name for the new project to be created in the **Name** text box.</span></span>  
  
5.  <span data-ttu-id="24621-110">Tapez le chemin ou l’emplacement du projet dans la zone de texte **Emplacement** ou cliquez sur **Parcourir** pour en sélectionner un.</span><span class="sxs-lookup"><span data-stu-id="24621-110">Type the path or location for the project in the **Location** text box, or click **Browse** to select one.</span></span>  
  
6.  <span data-ttu-id="24621-111">Dans la zone de texte **Nom de solution** , tapez le nom de la solution.</span><span class="sxs-lookup"><span data-stu-id="24621-111">Type a name for the solution in the **Solution name** text box.</span></span>  
  
7.  <span data-ttu-id="24621-112">Cliquez sur **OK** pour ouvrir la boîte de dialogue **Assistant Importation de projet Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="24621-112">Click **OK** to launch the **Integration Services Import Project Wizard** dialog box.</span></span>  
  
8.  <span data-ttu-id="24621-113">Cliquez sur **Suivant** pour basculer vers la page **Sélectionner une source** .</span><span class="sxs-lookup"><span data-stu-id="24621-113">Click **Next** to switch to the **Select Source** page.</span></span>  
  
9. <span data-ttu-id="24621-114">Si vous importez à partir d’un fichier **.ispac** , tapez le chemin avec le nom de fichier dans la zone de texte **Chemin d’accès** .</span><span class="sxs-lookup"><span data-stu-id="24621-114">If you are importing from an **.ispac** file, type the path including file name in the **Path** text box.</span></span> <span data-ttu-id="24621-115">Cliquez sur **Parcourir** pour accéder au dossier où vous souhaitez que la solution soit stockée et tapez le nom de fichier dans la zone de texte **Nom de fichier** , puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="24621-115">Click **Browse** to navigate to the folder where you want the solution to be stored and type file name in the **File name** text box, and click **Open**.</span></span>  
  
     <span data-ttu-id="24621-116">Si vous importez à partir d’un **Catalogue Integration Services**, tapez le nom de l’instance de base de données dans la zone de texte **Nom du serveur** ou cliquez sur **Parcourir** et sélectionnez l’instance de base de données contenant le catalogue.</span><span class="sxs-lookup"><span data-stu-id="24621-116">If you are importing from an **Integration Services Catalog**, type the database instance name in the **Server name** text box or click **Browse** and select the database instance that contains the catalog.</span></span>  
  
     <span data-ttu-id="24621-117">Cliquez sur **Parcourir** en regard de la zone de texte **Chemin d’accès** , développez le dossier dans le catalogue, sélectionnez le projet que vous souhaitez importer, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="24621-117">Click **Browse** next to **Path** text box, expand folder in the catalog, select the project you want to import, and click **OK**.</span></span>  
  
     <span data-ttu-id="24621-118">Cliquez sur **Suivant** pour passer à la page **Vérifier** .</span><span class="sxs-lookup"><span data-stu-id="24621-118">Click **Next** to switch to the **Review** page.</span></span>  
  
10. <span data-ttu-id="24621-119">Vérifiez les informations et cliquez sur **Importer** pour créer un projet basé sur le projet existant sélectionné.</span><span class="sxs-lookup"><span data-stu-id="24621-119">Review the information and click **Import** to create a project based on the existing project you selected.</span></span>  
  
11. <span data-ttu-id="24621-120">Facultatif : cliquez **Enregistrer le rapport** pour enregistrer les résultats dans un fichier</span><span class="sxs-lookup"><span data-stu-id="24621-120">Optional: click **Save Report** to save the results to a file</span></span>  
  
12. <span data-ttu-id="24621-121">Cliquez sur **Fermer** pour fermer la boîte de dialogue **Assistant Importation de projet Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="24621-121">Click **Close** to close the **Integration Services Import Project Wizard** dialog box.</span></span>  
  
  
