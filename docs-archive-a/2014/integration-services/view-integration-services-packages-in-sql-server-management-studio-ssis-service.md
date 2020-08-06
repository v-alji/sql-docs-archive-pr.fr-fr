---
title: Afficher les packages de Integration Services dans SQL Server Management Studio (service SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- viewing packages
- connections [Integration Services], packages
ms.assetid: 783e653c-0f1f-45ed-b3ef-5ba07b019f27
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4ba86320f1b1a685eab6e80399f3e8c21bd110eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695803"
---
# <a name="view-integration-services-packages-in-sql-server-management-studio-ssis-service"></a><span data-ttu-id="708e3-102">Afficher les packages Integration Services dans SQL Server Management Studio (Service SSIS)</span><span class="sxs-lookup"><span data-stu-id="708e3-102">View Integration Services Packages in SQL Server Management Studio (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="708e3-103">Cette rubrique présente le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , un service Windows qui permet de gérer les packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="708e3-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="708e3-104">prend en charge le service pour la compatibilité avec les versions antérieures de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="708e3-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="708e3-105">À compter de [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], vous pouvez gérer des objets tels que des packages sur le serveur Integration Services.</span><span class="sxs-lookup"><span data-stu-id="708e3-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="708e3-106">Cette procédure explique comment se connecter à [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] et visualiser la liste des packages gérés par le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="708e3-106">This procedure describes how to connect to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and view a list of the packages that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span>  
  
### <a name="to-connect-to-integration-services"></a><span data-ttu-id="708e3-107">Pour se connecter à Integration Services</span><span class="sxs-lookup"><span data-stu-id="708e3-107">To connect to Integration Services</span></span>  
  
1.  <span data-ttu-id="708e3-108">Cliquez sur **Démarrer**, pointez sur **Tous les programmes**, puis sur **Microsoft SQL Server 2005**et cliquez sur **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="708e3-108">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="708e3-109">Dans la boîte de dialogue **Se connecter au serveur** , sélectionnez **Integration Services** dans la liste **Type de serveur** , indiquez un nom de serveur dans la zone **Nom du serveur** , puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="708e3-109">In the **Connect to Server** dialog box, select **Integration Services** in the **Server type** list, provide a server name in the **Server name** box, and then click **Connect**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="708e3-110">Si vous ne pouvez pas vous connecter à [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], il est probable que le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ne soit pas en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="708e3-110">If you cannot connect to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is likely not running.</span></span> <span data-ttu-id="708e3-111">Pour connaître l'état du service, cliquez sur **Démarrer**, pointez sur **Tous les programmes**, sur **Microsoft SQL Server**, sur **Outils de configuration**, puis cliquez sur **Gestionnaire de configuration SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="708e3-111">To learn the status of the service, click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="708e3-112">Dans le volet gauche, cliquez sur **Services SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="708e3-112">In the left pane, click **SQL Server Services**.</span></span> <span data-ttu-id="708e3-113">Dans le volet droit, recherchez le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="708e3-113">In the right pane, find the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="708e3-114">Démarrez le service, il n'est pas déjà en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="708e3-114">Start the service if it is not already running.</span></span>  
  
     [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="708e3-115">s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="708e3-115">opens.</span></span> <span data-ttu-id="708e3-116">Par défaut, la fenêtre Explorateur d'objets est ouverte et positionnée dans l'angle inférieur gauche de SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="708e3-116">By default the Object Explorer window is open and positioned in the lower-left corner of the studio.</span></span> <span data-ttu-id="708e3-117">Si l'Explorateur d'objets n'est pas ouvert, dans le menu **Affichage** , cliquez sur **Explorateur d'objets** .</span><span class="sxs-lookup"><span data-stu-id="708e3-117">If Object Explorer is not open, click **Object Explorer** on the **View** menu.</span></span>  
  
### <a name="to-view-the-packages-that-integration-services-service-manages"></a><span data-ttu-id="708e3-118">Pour visualiser les packages gérés par le service Integration Services</span><span class="sxs-lookup"><span data-stu-id="708e3-118">To view the packages that Integration Services service manages</span></span>  
  
1.  <span data-ttu-id="708e3-119">Dans l'Explorateur d'objets, développez le dossier Packages stockés.</span><span class="sxs-lookup"><span data-stu-id="708e3-119">In Object Explorer, expand the Stored Packages folder.</span></span>  
  
2.  <span data-ttu-id="708e3-120">Développez les sous-dossiers du dossier Packages stockés afin d'afficher les packages.</span><span class="sxs-lookup"><span data-stu-id="708e3-120">Expand the Stored Packages subfolders to show packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="708e3-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="708e3-121">See Also</span></span>  
 <span data-ttu-id="708e3-122">[Package Management &#40;service SSIS&#41;](service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="708e3-122">[Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="708e3-123">Utiliser SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="708e3-123">Use SQL Server Management Studio</span></span>](../database-engine/use-sql-server-management-studio.md)  
  
  
