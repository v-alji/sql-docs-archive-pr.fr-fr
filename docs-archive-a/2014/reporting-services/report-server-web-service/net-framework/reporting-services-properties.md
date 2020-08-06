---
title: Propriétés de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- report servers [Reporting Services], properties
- properties [Reporting Services], about properties
- reports [Reporting Services], properties
- Report Server Web service, properties
- report properties [Reporting Services]
- XML Web service [Reporting Services], properties
- Web service [Reporting Services], properties
- properties [Reporting Services]
ms.assetid: 8c855194-4c20-4ecc-a328-5137d54b560c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61f1f50ea7a49acc616a36a4eaf1d3d5fcdf269a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697464"
---
# <a name="reporting-services-properties"></a><span data-ttu-id="b4978-102">Propriétés de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b4978-102">Reporting Services Properties</span></span>
  <span data-ttu-id="b4978-103">Le serveur de rapports définit un jeu de propriétés système qui sont communes au serveur de rapports et un jeu de propriétés des éléments associées à un élément individuel stocké dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b4978-103">The report server defines a set of system properties that are global to the report server and a set of item properties that are associated with an individual item stored in the report server database.</span></span> <span data-ttu-id="b4978-104">Les propriétés définies par le serveur de rapports ne peuvent pas être supprimées, et sont dans certains cas en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="b4978-104">Properties defined by the report server cannot be deleted, and in some cases they are read-only.</span></span> <span data-ttu-id="b4978-105">Une application peut étendre des propriétés système et des propriétés des éléments en ajoutant aux propriétés système et des éléments d'autres propriétés définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b4978-105">An application can extend system properties and item properties by adding additional user-defined properties to the system and item properties.</span></span>  
  
 <span data-ttu-id="b4978-106">Les méthodes de service Web suivantes récupèrent et définissent des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Propriétés.</span><span class="sxs-lookup"><span data-stu-id="b4978-106">The following Web service methods retrieve and set [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] properties.</span></span>  
  
|<span data-ttu-id="b4978-107">Méthode</span><span class="sxs-lookup"><span data-stu-id="b4978-107">Method</span></span>|<span data-ttu-id="b4978-108">Action</span><span class="sxs-lookup"><span data-stu-id="b4978-108">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.GetProperties%2A>|<span data-ttu-id="b4978-109">Retourne les valeurs d'une ou plusieurs propriétés sur un élément dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b4978-109">Returns the values of one or more properties on an item in the report server database.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemProperties%2A>|<span data-ttu-id="b4978-110">Retourne une ou plusieurs propriétés système.</span><span class="sxs-lookup"><span data-stu-id="b4978-110">Returns one or more system properties.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetProperties%2A>|<span data-ttu-id="b4978-111">Définit une ou plusieurs propriétés d'un élément dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b4978-111">Sets one or more properties of an item in the report server database.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetSystemProperties%2A>|<span data-ttu-id="b4978-112">Définit une ou plusieurs propriétés système.</span><span class="sxs-lookup"><span data-stu-id="b4978-112">Sets one or more system properties.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="b4978-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b4978-113">In This Section</span></span>  
  
|<span data-ttu-id="b4978-114">Rubrique</span><span class="sxs-lookup"><span data-stu-id="b4978-114">Topic</span></span>|<span data-ttu-id="b4978-115">Description</span><span class="sxs-lookup"><span data-stu-id="b4978-115">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b4978-116">Propriétés d'élément du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="b4978-116">Report Server Item Properties</span></span>](reporting-services-properties-report-server-item-properties.md)|<span data-ttu-id="b4978-117">Décrit les propriétés spécifiques à l'élément dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4978-117">Describes the item-specific properties in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="b4978-118">Propriétés système de Report Server</span><span class="sxs-lookup"><span data-stu-id="b4978-118">Report Server System Properties</span></span>](reporting-services-properties-report-server-system-properties.md)|<span data-ttu-id="b4978-119">Décrit les propriétés spécifiques au système dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4978-119">Describes the system-specific properties in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4978-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b4978-120">See Also</span></span>  
 <span data-ttu-id="b4978-121">[Création d’applications à l’aide du service web et du .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="b4978-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="b4978-122">[Service web Report Server](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="b4978-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="b4978-123">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b4978-123">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
