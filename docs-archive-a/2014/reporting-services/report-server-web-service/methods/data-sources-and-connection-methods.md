---
title: Sources de données et méthodes de connexion | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- connections [Reporting Services], data sources
- reports [Reporting Services], data
- data sources [Reporting Services], methods
ms.assetid: 50999b52-fc7c-4333-9fb0-d04c37a4c90f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 29dd8dd1c002ab3b7d4594a4e25ec44bdb2cc8ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704872"
---
# <a name="data-sources-and-connection-methods"></a><span data-ttu-id="d066b-102">Sources de données et méthodes de connexion</span><span class="sxs-lookup"><span data-stu-id="d066b-102">Data Sources and Connection Methods</span></span>
  <span data-ttu-id="d066b-103">Vous pouvez utiliser les méthodes suivantes pour définir et gérer les connexions et les informations d'identification des sources de données.</span><span class="sxs-lookup"><span data-stu-id="d066b-103">You can use these methods to set and manage data source connections and credentials.</span></span>  
  
|<span data-ttu-id="d066b-104">Méthode</span><span class="sxs-lookup"><span data-stu-id="d066b-104">Method</span></span>|<span data-ttu-id="d066b-105">Action</span><span class="sxs-lookup"><span data-stu-id="d066b-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateDataSource%2A>|<span data-ttu-id="d066b-106">Crée une source de données dans la base de données du serveur de rapports ou la bibliothèque SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d066b-106">Creates a new data source in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DisableDataSource%2A>|<span data-ttu-id="d066b-107">Désactive une source de données activée.</span><span class="sxs-lookup"><span data-stu-id="d066b-107">Disables a data source that is enabled.</span></span>|  
|<xref:ReportService2010.ReportingService2010.EnableDataSource%2A>|<span data-ttu-id="d066b-108">Active une source de données désactivée.</span><span class="sxs-lookup"><span data-stu-id="d066b-108">Enables a data source that is disabled.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetDataSourceContents%2A>|<span data-ttu-id="d066b-109">Retourne le contenu d'une source de données.</span><span class="sxs-lookup"><span data-stu-id="d066b-109">Returns the contents of a data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetItemDataSourcePrompts%2A>|<span data-ttu-id="d066b-110">Reçoit les invites de source de données pour un élément spécifié.</span><span class="sxs-lookup"><span data-stu-id="d066b-110">Gets the data source prompts for a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetItemDataSources%2A>|<span data-ttu-id="d066b-111">Retourne les sources de données pour un élément du catalogue.</span><span class="sxs-lookup"><span data-stu-id="d066b-111">Returns the data sources for an item in the catalog.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListDependentItems%2A>|<span data-ttu-id="d066b-112">Retourne une liste des éléments du catalogue qui référencent un élément de catalogue spécifié.</span><span class="sxs-lookup"><span data-stu-id="d066b-112">Returns a list of catalog items that reference a specified catalog item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListSubscriptionsUsingDataSource%2A>|<span data-ttu-id="d066b-113">Retourne une liste des abonnements associés à une certaine source de données.</span><span class="sxs-lookup"><span data-stu-id="d066b-113">Returns a list of subscriptions that are associated with a given data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetDataSourceContents%2A>|<span data-ttu-id="d066b-114">Définit les propriétés de connexion associées à une source de données.</span><span class="sxs-lookup"><span data-stu-id="d066b-114">Sets the connection properties that are associated with a data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetItemDataSources%2A>|<span data-ttu-id="d066b-115">Définit les sources de données d'un élément dans une base de données du serveur de rapports ou la bibliothèque SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d066b-115">Sets the data sources for an item in a report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.TestConnectForDataSourceDefinition%2A>|<span data-ttu-id="d066b-116">Teste la connexion pour y trouver une source de données.</span><span class="sxs-lookup"><span data-stu-id="d066b-116">Tests the connection for a data source.</span></span> <span data-ttu-id="d066b-117">Cette méthode prend en charge le test direct de la source de données.</span><span class="sxs-lookup"><span data-stu-id="d066b-117">This method supports the direct testing of the data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.TestConnectForItemDataSource%2A>|<span data-ttu-id="d066b-118">Teste la connexion pour y trouver une source de données.</span><span class="sxs-lookup"><span data-stu-id="d066b-118">Tests the connection for a data source.</span></span> <span data-ttu-id="d066b-119">Cette méthode prend en charge le test des sources de données publiées utilisées par les rapports, les modèles ou les sources de données partagées.</span><span class="sxs-lookup"><span data-stu-id="d066b-119">This method supports the testing of published data sources that are used by reports or models and shared data sources.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d066b-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d066b-120">See Also</span></span>  
 <span data-ttu-id="d066b-121">[Création d’applications à l’aide du service web et du .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="d066b-121">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="d066b-122">[Service web Report Server](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="d066b-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="d066b-123">[Méthodes du service web Report Server](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="d066b-123">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="d066b-124">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d066b-124">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
