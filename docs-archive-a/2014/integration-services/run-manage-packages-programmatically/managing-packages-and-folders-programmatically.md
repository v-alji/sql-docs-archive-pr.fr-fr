---
title: Gestion des packages et des dossiers par programmation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- enumerators [Integration Services]
- packages [Integration Services], managing
- custom enumerators [Integration Services]
ms.assetid: ec59b75d-ba09-44ac-9039-9d593bb462d9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 695ff4ad020dbdfb2564b4964a55324db4248517
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707663"
---
# <a name="managing-packages-and-folders-programmatically"></a><span data-ttu-id="6d3f5-102">Gestion des packages et des dossiers par programme</span><span class="sxs-lookup"><span data-stu-id="6d3f5-102">Managing Packages and Folders Programmatically</span></span>
  <span data-ttu-id="6d3f5-103">Lorsque vous travaillez par programme avec des packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], vous pouvez avoir besoin de déterminer si un package ou un dossier individuel existe, ou de gérer les dossiers dans lesquels les packages sont stockés.</span><span class="sxs-lookup"><span data-stu-id="6d3f5-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine whether an individual package or folder exists, or to manage the folders in which packages are stored.</span></span> <span data-ttu-id="6d3f5-104">La classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> de l'espace de noms <xref:Microsoft.SqlServer.Dts.Runtime> fournit différentes méthodes pour répondre à ces impératifs.</span><span class="sxs-lookup"><span data-stu-id="6d3f5-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides a variety of methods to satisfy these requirements.</span></span>  
  
##  <a name="determining-whether-a-package-or-folder-exists"></a><a name="exists"></a> <span data-ttu-id="6d3f5-105">Détermination de l’existence d’un package ou dossier</span><span class="sxs-lookup"><span data-stu-id="6d3f5-105">Determining Whether a Package or Folder Exists</span></span>  
 <span data-ttu-id="6d3f5-106">Pour déterminer par programmation si un package enregistré existe, appelez l’une des méthodes suivantes avant de tenter de le charger et l’exécuter :</span><span class="sxs-lookup"><span data-stu-id="6d3f5-106">To determine programmatically whether a saved package exists, call one of the following methods before attempting to load and run the package:</span></span>  
  
|<span data-ttu-id="6d3f5-107">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="6d3f5-107">Storage Location</span></span>|<span data-ttu-id="6d3f5-108">Méthode à appeler</span><span class="sxs-lookup"><span data-stu-id="6d3f5-108">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="6d3f5-109">Magasin de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="6d3f5-109">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnSqlServer%2A>|  
  
 <span data-ttu-id="6d3f5-110">Pour déterminer par programme si un dossier existe, appelez l'une des méthodes suivantes avant de tenter de répertorier les packages stockés dans ce dossier :</span><span class="sxs-lookup"><span data-stu-id="6d3f5-110">To determine programmatically whether a folder exists, call one of the following methods before attempting to list the packages stored in the folder, :</span></span>  
  
|<span data-ttu-id="6d3f5-111">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="6d3f5-111">Storage Location</span></span>|<span data-ttu-id="6d3f5-112">Méthode à appeler</span><span class="sxs-lookup"><span data-stu-id="6d3f5-112">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="6d3f5-113">Magasin de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="6d3f5-113">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnSqlServer%2A>|  
  

  
##  <a name="managing-packages-and-folders"></a><a name="managing"></a> <span data-ttu-id="6d3f5-114">Gestion des packages et des dossiers</span><span class="sxs-lookup"><span data-stu-id="6d3f5-114">Managing Packages and Folders</span></span>  
 <span data-ttu-id="6d3f5-115">La classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> de l'espace de noms <xref:Microsoft.SqlServer.Dts.Runtime> fournit des méthodes supplémentaires pour gérer les packages et les dossiers dans lesquels ils sont stockés.</span><span class="sxs-lookup"><span data-stu-id="6d3f5-115">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides additional methods for managing packages and the folders in which they are stored.</span></span>  
  
###  <a name="removing-a-package"></a><a name="managing_rempkg"></a> <span data-ttu-id="6d3f5-116">Suppression d’un package</span><span class="sxs-lookup"><span data-stu-id="6d3f5-116">Removing a Package</span></span>  
 <span data-ttu-id="6d3f5-117">Pour supprimer un package enregistré par programme, appelez l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="6d3f5-117">To remove a saved package programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="6d3f5-118">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="6d3f5-118">Storage Location</span></span>|<span data-ttu-id="6d3f5-119">Méthode à appeler</span><span class="sxs-lookup"><span data-stu-id="6d3f5-119">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="6d3f5-120">Magasin de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="6d3f5-120">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFromSqlServer%2A>|  
  

  
###  <a name="creating-a-folder"></a><a name="managing_create"></a> <span data-ttu-id="6d3f5-121">Création d’un dossier</span><span class="sxs-lookup"><span data-stu-id="6d3f5-121">Creating a Folder</span></span>  
 <span data-ttu-id="6d3f5-122">Pour créer un dossier de stockage par programme, appelez l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="6d3f5-122">To create a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="6d3f5-123">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="6d3f5-123">Storage Location</span></span>|<span data-ttu-id="6d3f5-124">Méthode à appeler</span><span class="sxs-lookup"><span data-stu-id="6d3f5-124">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="6d3f5-125">Magasin de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="6d3f5-125">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.CreateFolderOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.CreateFolderOnSqlServer%2A>|  
  

  
###  <a name="removing-a-folder"></a><a name="managing_remfldr"></a> <span data-ttu-id="6d3f5-126">Suppression d’un dossier</span><span class="sxs-lookup"><span data-stu-id="6d3f5-126">Removing a Folder</span></span>  
 <span data-ttu-id="6d3f5-127">Pour supprimer un dossier de stockage par programme, appelez l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="6d3f5-127">To remove a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="6d3f5-128">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="6d3f5-128">Storage Location</span></span>|<span data-ttu-id="6d3f5-129">Méthode à appeler</span><span class="sxs-lookup"><span data-stu-id="6d3f5-129">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="6d3f5-130">Magasin de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="6d3f5-130">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFolderFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFolderFromSqlServer%2A>|  
  
  
  
###  <a name="renaming-a-folder"></a><a name="managing_rename"></a> <span data-ttu-id="6d3f5-131">Renommage d’un dossier</span><span class="sxs-lookup"><span data-stu-id="6d3f5-131">Renaming a Folder</span></span>  
 <span data-ttu-id="6d3f5-132">Pour renommer un dossier de stockage par programme, appelez l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="6d3f5-132">To rename a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="6d3f5-133">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="6d3f5-133">Storage Location</span></span>|<span data-ttu-id="6d3f5-134">Méthode à appeler</span><span class="sxs-lookup"><span data-stu-id="6d3f5-134">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="6d3f5-135">Magasin de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="6d3f5-135">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RenameFolderOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RenameFolderOnSqlServer%2A>|  
  

  
<span data-ttu-id="6d3f5-136">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="6d3f5-136">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6d3f5-137">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="6d3f5-137">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6d3f5-138">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="6d3f5-138">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6d3f5-139">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="6d3f5-139">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d3f5-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d3f5-140">See Also</span></span>  
 <span data-ttu-id="6d3f5-141">[Package Management &#40;service SSIS&#41;](../service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="6d3f5-141">[Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="6d3f5-142">Énumération des packages disponibles par programme</span><span class="sxs-lookup"><span data-stu-id="6d3f5-142">Enumerating Available Packages Programmatically</span></span>](../run-manage-packages-programmatically/enumerating-available-packages-programmatically.md)  
  
  
