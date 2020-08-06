---
title: Cause et résolution des erreurs Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- messages [Reporting Services]
- errors [Reporting Services]
- troubleshooting [Reporting Services], errors
ms.assetid: 3db0fef3-37f8-40d0-acc7-1928760dc0e9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fa98b9f760485b80f4fa4ac74f3b8008dc3bbec3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700650"
---
# <a name="cause-and-resolution-of-reporting-services-errors"></a><span data-ttu-id="83aab-102">Cause et résolution des erreurs Reporting Services</span><span class="sxs-lookup"><span data-stu-id="83aab-102">Cause and Resolution of Reporting Services Errors</span></span>
  <span data-ttu-id="83aab-103">Cette rubrique contient des informations relatives à la cause et à la résolution de plusieurs erreurs concernant [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83aab-103">This topic contains cause and resolution information for a number of errors related to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="83aab-104">Les rubriques de message d'erreur dans cette section fournissent une explication du message d'erreur, des causes possibles et des actions que vous pouvez entreprendre pour corriger le problème.</span><span class="sxs-lookup"><span data-stu-id="83aab-104">The error message topics in this section provide an explanation of the error message, possible causes, and any actions you can take to correct the problem.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83aab-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="83aab-105">In This Section</span></span>  
  
|<span data-ttu-id="83aab-106">Error</span><span class="sxs-lookup"><span data-stu-id="83aab-106">Error</span></span>|<span data-ttu-id="83aab-107">Message</span><span class="sxs-lookup"><span data-stu-id="83aab-107">Message</span></span>|  
|-----------|-------------|  
|[<span data-ttu-id="83aab-108">rsAccessedDenied - erreur Reporting Services</span><span class="sxs-lookup"><span data-stu-id="83aab-108">rsAccessedDenied - Reporting Services Error</span></span>](rsaccesseddenied-reporting-services-error.md)|<span data-ttu-id="83aab-109">Les autorisations accordées à l'utilisateur 'mon_domaine\mon_compte' sont insuffisantes pour vous permettre d'accomplir cette opération.</span><span class="sxs-lookup"><span data-stu-id="83aab-109">The permissions granted to user 'mydomain\myAccount' are insufficient for performing this operation.</span></span> <span data-ttu-id="83aab-110">(rsAccessDenied) (ReportingServicesLibrary).</span><span class="sxs-lookup"><span data-stu-id="83aab-110">(rsAccessDenied) (ReportingServicesLibrary).</span></span>|  
|[<span data-ttu-id="83aab-111">rsInternalError - Erreur Reporting Services</span><span class="sxs-lookup"><span data-stu-id="83aab-111">rsInternalError - Reporting Services Error</span></span>](rsinternalerror-reporting-services-error.md)|<span data-ttu-id="83aab-112">Une erreur interne s'est produite sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="83aab-112">An internal error occurred on the report server.</span></span> <span data-ttu-id="83aab-113">Consultez le journal des erreurs pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="83aab-113">See the error log for more details.</span></span>|  
|[<span data-ttu-id="83aab-114">rsModelGenerationError - erreur Reporting Services</span><span class="sxs-lookup"><span data-stu-id="83aab-114">rsModelGenerationError - Reporting Services Error</span></span>](rsmodelgenerationerror-reporting-services-error.md)|<span data-ttu-id="83aab-115">Une erreur s'est produite lors de la génération du modèle.</span><span class="sxs-lookup"><span data-stu-id="83aab-115">An error occurred while generating model.</span></span> <span data-ttu-id="83aab-116">(rsModelGenerationError) (ReportingServicesLibrary) %1.</span><span class="sxs-lookup"><span data-stu-id="83aab-116">(rsModelGenerationError) (ReportingServicesLibrary) %1.</span></span>|  
|[<span data-ttu-id="83aab-117">rsProcessingError - erreur Reporting Services</span><span class="sxs-lookup"><span data-stu-id="83aab-117">rsProcessingError - Reporting Services Error</span></span>](rsprocessingerror-reporting-services-error.md)|<span data-ttu-id="83aab-118">Des erreurs se sont produites lors du traitement du rapport.</span><span class="sxs-lookup"><span data-stu-id="83aab-118">Errors have occurred in report processing.</span></span>|  
|[<span data-ttu-id="83aab-119">rsServerConfigurationError - erreur Reporting Services</span><span class="sxs-lookup"><span data-stu-id="83aab-119">rsServerConfigurationError - Reporting Services Error</span></span>](rsserverconfigurationerror-reporting-services-error.md)|<span data-ttu-id="83aab-120">Le serveur de rapports a rencontré une erreur de configuration.</span><span class="sxs-lookup"><span data-stu-id="83aab-120">The report server has encountered a configuration error.</span></span>|  
|[<span data-ttu-id="83aab-121">rrRenderingError - erreur Reporting Services</span><span class="sxs-lookup"><span data-stu-id="83aab-121">rrRenderingError - Reporting Services Error</span></span>](rrrenderingerror-reporting-services-error.md)|<span data-ttu-id="83aab-122">Une erreur s'est produite lors du rendu du rapport.</span><span class="sxs-lookup"><span data-stu-id="83aab-122">An error occurred during rendering of the report.</span></span> <span data-ttu-id="83aab-123">(rrRenderingError) %1.</span><span class="sxs-lookup"><span data-stu-id="83aab-123">(rrRenderingError) %1.</span></span>|  
|[<span data-ttu-id="83aab-124">Service Windows Report Server &#40;MSSQLServer&#41; 107</span><span class="sxs-lookup"><span data-stu-id="83aab-124">Report Server Windows Service &#40;MSSQLServer&#41; 107</span></span>](../../relational-databases/errors-events/mssqlserver-107-database-engine-error.md)|<span data-ttu-id="83aab-125">Le service Windows Report Server (MSSQLSERVER) ne peut pas se connecter à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="83aab-125">Report Server Windows service (MSSQLSERVER) cannot connect to the report server database.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="83aab-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="83aab-126">See Also</span></span>  
 <span data-ttu-id="83aab-127">[Fichiers journaux et sources de Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="83aab-127">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 [<span data-ttu-id="83aab-128">Guide de référence des erreurs et des événements &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="83aab-128">Errors and Events Reference &#40;Reporting Services&#41;</span></span>](errors-and-events-reference-reporting-services.md)  
  
  
