---
title: Gestion des packages en cours d’exécution par programmation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- packages [Integration Services], managing
- running packages [Integration Services]
ms.assetid: 0e91f4ac-6f29-40d7-8c28-9b82e4802c35
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 95c5f9c28b407631764d64523b37a6295870542a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707668"
---
# <a name="managing-running-packages-programmatically"></a><span data-ttu-id="04cc0-102">Gestion des packages en cours d'exécution par programme</span><span class="sxs-lookup"><span data-stu-id="04cc0-102">Managing Running Packages Programmatically</span></span>
  <span data-ttu-id="04cc0-103">Lors de l'utilisation de packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] par programme, il peut être utile d'identifier les packages en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="04cc0-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine which packages are currently running.</span></span> <span data-ttu-id="04cc0-104">La classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> de l'espace de noms <xref:Microsoft.SqlServer.Dts.Runtime> fournit des méthodes et des classes pour répondre à ces impératifs.</span><span class="sxs-lookup"><span data-stu-id="04cc0-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides methods and classes to satisfy these requirements.</span></span>  
  
 <span data-ttu-id="04cc0-105">Pour plus d’informations sur la surveillance des packages, consultez [Gestion de packages &#40;Service SSIS&#41;](../service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="04cc0-105">For more information about monitoring packages, see [Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md).</span></span>  
  
 <span data-ttu-id="04cc0-106">Toutes les méthodes décrites dans cette rubrique requièrent une référence à l'assembly `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="04cc0-106">All the methods discussed in this topic require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="04cc0-107">Après avoir ajouté la référence dans un nouveau projet, importez l' <xref:Microsoft.SqlServer.Dts.Runtime> espace de noms avec une `using` `Imports` instruction ou.</span><span class="sxs-lookup"><span data-stu-id="04cc0-107">After you add the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="04cc0-108">Les méthodes de la classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> qui permettent d’utiliser le magasin de packages SSIS prennent uniquement en charge « . », localhost ou le nom du serveur local.</span><span class="sxs-lookup"><span data-stu-id="04cc0-108">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store support only ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="04cc0-109">Vous ne pouvez pas utiliser « (local) ».</span><span class="sxs-lookup"><span data-stu-id="04cc0-109">You cannot use "(local)".</span></span>  
  
## <a name="determining-which-packages-are-currently-running"></a><span data-ttu-id="04cc0-110">Identification des packages en cours d'exécution</span><span class="sxs-lookup"><span data-stu-id="04cc0-110">Determining Which Packages Are Currently Running</span></span>  
 <span data-ttu-id="04cc0-111">Pour identifier les packages en cours d'exécution sur le serveur spécifié, appelez la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetRunningPackages%2A>.</span><span class="sxs-lookup"><span data-stu-id="04cc0-111">To determine which packages are currently running on the specified server, call the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetRunningPackages%2A> method.</span></span> <span data-ttu-id="04cc0-112">Cette méthode retourne une collection <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> d'objets <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage>.</span><span class="sxs-lookup"><span data-stu-id="04cc0-112">This method returns a <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> collection of <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04cc0-113">Les administrateurs peuvent afficher tous les packages en cours d'exécution sur l'ordinateur ; alors que les autres utilisateurs ne voient que les packages qu'ils ont lancés.</span><span class="sxs-lookup"><span data-stu-id="04cc0-113">Administrators see all packages that are currently executing on the computer; other users see only those packages that they have launched.</span></span>  
  
## <a name="working-with-running-packages"></a><span data-ttu-id="04cc0-114">Utilisation de packages en cours d'exécution</span><span class="sxs-lookup"><span data-stu-id="04cc0-114">Working with Running Packages</span></span>  
 <span data-ttu-id="04cc0-115">Après avoir identifié les packages en cours d'exécution, vous pouvez extraire des informations relatives aux packages et demander l'arrêt d'un package.</span><span class="sxs-lookup"><span data-stu-id="04cc0-115">After you have determined which packages are currently running, you can retrieve information about the packages and request that a package be stopped.</span></span>  
  
### <a name="getting-information-about-a-running-package"></a><span data-ttu-id="04cc0-116">Obtention d'informations sur un package en cours d'exécution</span><span class="sxs-lookup"><span data-stu-id="04cc0-116">Getting Information about a Running Package</span></span>  
 <span data-ttu-id="04cc0-117">Pendant que vous parcourez la collection <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages>, vous pouvez utiliser les propriétés de l'objet <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> pour rechercher un package ou obtenir des informations supplémentaires sur les packages en cours d'exécution :</span><span class="sxs-lookup"><span data-stu-id="04cc0-117">As you iterate through the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> collection, you can use the properties of the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> object to locate a package or to obtain additional information about the packages that are running:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.ExecutionDuration%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.ExecutionStartTime%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.InstanceID%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageDescription%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageID%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageName%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.UserName%2A>  
  
### <a name="stopping-a-running-package"></a><span data-ttu-id="04cc0-118">Arrêt d'un package en cours d'exécution</span><span class="sxs-lookup"><span data-stu-id="04cc0-118">Stopping a Running Package</span></span>  
 <span data-ttu-id="04cc0-119">Vous pouvez appeler la méthode <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.Stop%2A> d'un objet <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> pour demander l'arrêt du package.</span><span class="sxs-lookup"><span data-stu-id="04cc0-119">You can call the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.Stop%2A> method of a <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> object to request that the package be stopped.</span></span> <span data-ttu-id="04cc0-120">Il peut y avoir un délai entre le moment où l'arrêt est demandé et le moment où le package s'arrête réellement.</span><span class="sxs-lookup"><span data-stu-id="04cc0-120">There may be a delay between the time that a stop request is issued and the time that the package actually stops.</span></span>  
  
<span data-ttu-id="04cc0-121">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="04cc0-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="04cc0-122">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="04cc0-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="04cc0-123">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="04cc0-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="04cc0-124">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="04cc0-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04cc0-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="04cc0-125">See Also</span></span>  
 <span data-ttu-id="04cc0-126">[Package Management &#40;service SSIS&#41;](../service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="04cc0-126">[Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="04cc0-127">Énumération des packages disponibles par programme</span><span class="sxs-lookup"><span data-stu-id="04cc0-127">Enumerating Available Packages Programmatically</span></span>](../run-manage-packages-programmatically/enumerating-available-packages-programmatically.md)  
  
  
