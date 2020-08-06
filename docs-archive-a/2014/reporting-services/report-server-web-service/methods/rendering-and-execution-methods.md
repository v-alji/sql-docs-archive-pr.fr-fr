---
title: Méthodes de rendu et d’exécution | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendered reports [Reporting Services]
- reports [Reporting Services], execution options
- methods [Reporting Services], execution options
- methods [Reporting Services], rendering
ms.assetid: 12626aad-f0be-4653-87d0-60eb3a3fff78
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0bc793e9a18e993989563fd3526ff12272f775c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704859"
---
# <a name="rendering-and-execution-methods"></a><span data-ttu-id="7bfb0-102">Méthodes de rendu et d'exécution</span><span class="sxs-lookup"><span data-stu-id="7bfb0-102">Rendering and Execution Methods</span></span>
  <span data-ttu-id="7bfb0-103">Vous pouvez utiliser ces méthodes pour gérer l'exécution et la mise en cache des éléments, ainsi que la génération des rapports.</span><span class="sxs-lookup"><span data-stu-id="7bfb0-103">You can use these methods to manage item execution and caching, and report rendering.</span></span>  
  
|<span data-ttu-id="7bfb0-104">Méthode</span><span class="sxs-lookup"><span data-stu-id="7bfb0-104">Method</span></span>|<span data-ttu-id="7bfb0-105">Action</span><span class="sxs-lookup"><span data-stu-id="7bfb0-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.FlushCache%2A>|<span data-ttu-id="7bfb0-106">Invalide le cache pour un élément.</span><span class="sxs-lookup"><span data-stu-id="7bfb0-106">Invalidates the cache for an item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetCacheOptions%2A>|<span data-ttu-id="7bfb0-107">Retourne la configuration de mise en cache pour un élément et les paramètres qui décrivent à quel moment la copie de l'élément mise en cache arrive à expiration.</span><span class="sxs-lookup"><span data-stu-id="7bfb0-107">Returns the cache configuration for an item and the settings that describe when the cached copy of the item expires.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetExecutionOptions%2A>|<span data-ttu-id="7bfb0-108">Retourne l'option d'exécution et les paramètres associés pour un élément individuel.</span><span class="sxs-lookup"><span data-stu-id="7bfb0-108">Returns the execution option and associated settings for an individual item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListExecutionSettings%2A>|<span data-ttu-id="7bfb0-109">Retourne une liste de paramètres d'exécution pris en charge.</span><span class="sxs-lookup"><span data-stu-id="7bfb0-109">Returns a list of supported execution settings.</span></span>|  
|<xref:ReportExecution2005.ReportExecutionService.Render%2A>|<span data-ttu-id="7bfb0-110">Traite le rapport spécifié et effectue le rendu du rapport dans un format spécifié.</span><span class="sxs-lookup"><span data-stu-id="7bfb0-110">Processes the specified report and renders it in a specified format.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetCacheOptions%2A>|<span data-ttu-id="7bfb0-111">Configure la mise en cache d'un élément et fournit des paramètres qui spécifient à quel moment la copie de l'élément mise en cache arrive à expiration.</span><span class="sxs-lookup"><span data-stu-id="7bfb0-111">Configures an item to be cached and provides settings that specify when the cached copy of the item expires.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetExecutionOptions%2A>|<span data-ttu-id="7bfb0-112">Définit des options et des propriétés d'exécution associées pour un élément spécifié.</span><span class="sxs-lookup"><span data-stu-id="7bfb0-112">Sets execution options and associated execution properties for a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.UpdateItemExecutionSnapshot%2A>|<span data-ttu-id="7bfb0-113">Génère un instantané de l'exécution de l'élément pour un élément spécifié.</span><span class="sxs-lookup"><span data-stu-id="7bfb0-113">Generates an item execution snapshot for a specified item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7bfb0-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7bfb0-114">See Also</span></span>  
 <span data-ttu-id="7bfb0-115">[Création d’applications à l’aide du service web et du .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="7bfb0-115">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="7bfb0-116">[Service web Report Server](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="7bfb0-116">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="7bfb0-117">[Méthodes du service web Report Server](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="7bfb0-117">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="7bfb0-118">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7bfb0-118">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
