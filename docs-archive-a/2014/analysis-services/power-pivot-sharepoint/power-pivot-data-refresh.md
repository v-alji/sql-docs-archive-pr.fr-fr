---
title: Actualisation des données PowerPivot | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- unattended data refresh [Analysis Services with SharePoint]
- scheduled data refresh [Analysis Services with SharePoint]
- data refresh [Analysis Services with SharePoint]
ms.assetid: ac8358a3-ee71-44c7-8ee6-ac7afe3ebaa4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f7d5ed5c2f8882cbc0c47a1c711748d26e0193c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605779"
---
# <a name="powerpivot-data-refresh"></a><span data-ttu-id="1655b-102">Actualisation des données PowerPivot</span><span class="sxs-lookup"><span data-stu-id="1655b-102">PowerPivot Data Refresh</span></span>
  <span data-ttu-id="1655b-103">Une fois que vous avez créé un classeur contenant des données PowerPivot, vous pouvez actualiser périodiquement les données en réexécutant une requête ou une commande afin d'obtenir les informations mises à jour des sources utilisées initialement pour créer le classeur.</span><span class="sxs-lookup"><span data-stu-id="1655b-103">After you create a workbook that contains PowerPivot data, you might want to periodically refresh the data by rerunning a query or command to get updated information from the sources you used originally to create the workbook.</span></span> <span data-ttu-id="1655b-104">Ce processus est appelé `data refresh`, et vous pouvez actualiser les données à la demande dans [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], ou de manière planifiée avec un processus [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui s'exécute sur un serveur d'applications dans une batterie de serveurs SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1655b-104">This process is called `data refresh`, and you can refresh data on demand in [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], or as a scheduled operation that runs as an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] process on an application server in a SharePoint farm.</span></span> <span data-ttu-id="1655b-105">Pour plus d'informations, consultez les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="1655b-105">For more information, see:</span></span>  
  
-   [<span data-ttu-id="1655b-106">Actualisation des données PowerPivot avec SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="1655b-106">PowerPivot Data Refresh with SharePoint 2010</span></span>](../powerpivot-data-refresh-with-sharepoint-2010.md)  
  
-   [<span data-ttu-id="1655b-107">Configurez le compte d’actualisation des données PowerPivot sans assistance &#40;PowerPivot pour SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="1655b-107">Configure the PowerPivot Unattended Data Refresh Account &#40;PowerPivot for SharePoint&#41;</span></span>](../configure-unattended-data-refresh-account-powerpivot-sharepoint.md)  
  
-   [<span data-ttu-id="1655b-108">Configurez les informations d’identification stockées pour l’actualisation des données PowerPivot &#40;PowerPivot pour SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="1655b-108">Configure Stored Credentials for PowerPivot Data Refresh &#40;PowerPivot for SharePoint&#41;</span></span>](../configure-stored-credentials-data-refresh-powerpivot-sharepoint.md)  
  
-   [<span data-ttu-id="1655b-109">Planifier une actualisation des données &#40;PowerPivot pour SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="1655b-109">Schedule a Data Refresh &#40;PowerPivot for SharePoint&#41;</span></span>](../schedule-a-data-refresh-powerpivot-for-sharepoint.md)  
  
-   [<span data-ttu-id="1655b-110">Afficher l’historique d’actualisation des données &#40;PowerPivot pour SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="1655b-110">View Data Refresh History &#40;PowerPivot for SharePoint&#41;</span></span>](view-data-refresh-history-power-pivot-for-sharepoint.md)  
  
> [!NOTE]
>  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="1655b-111">et SharePoint Server 2013 Excel Services utilisent une architecture différente pour l'actualisation des données des modèles de données PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="1655b-111">and SharePoint Server 2013 Excel Services use a different architecture for data refresh of PowerPivot data models.</span></span> <span data-ttu-id="1655b-112">L'architecture prise en charge par SharePoint 2013 utilise Excel Services en tant que composant principal pour charger les modèles de données PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="1655b-112">The SharePoint 2013 supported architecture utilizes Excel Services as the primary component to load PowerPivot data models.</span></span> <span data-ttu-id="1655b-113">L'architecture d'actualisation des données précédente reposait sur un serveur exécutant le service système PowerPivot et [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en mode SharePoint afin de charger les modèles de données.</span><span class="sxs-lookup"><span data-stu-id="1655b-113">The previous data refresh architecture used relied on a server running PowerPivot System Service and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in SharePoint mode to load data models.</span></span> <span data-ttu-id="1655b-114">Pour plus d’informations, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="1655b-114">For more information, see the following:</span></span>  
> 
>  -   [<span data-ttu-id="1655b-115">Actualisation des données PowerPivot avec SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="1655b-115">PowerPivot Data Refresh with SharePoint 2013</span></span>](power-pivot-data-refresh-with-sharepoint-2013.md)  
> -   [<span data-ttu-id="1655b-116">Mettre à niveau les classeurs et l’actualisation planifiée des données &#40;SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="1655b-116">Upgrade Workbooks and Scheduled Data Refresh &#40;SharePoint 2013&#41;</span></span>](../instances/install-windows/upgrade-workbooks-and-scheduled-data-refresh-sharepoint-2013.md)  
  
  
