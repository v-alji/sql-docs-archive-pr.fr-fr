---
title: Analyse des exécutions de packages et d’autres opérations | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cbbcd79f-ab9b-46ec-84cb-4821c1d16b99
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 628b62d9c8e01d0dc0bf641551de67c3838a4504
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614730"
---
# <a name="monitoring-for-package-executions-and-other-operations"></a><span data-ttu-id="f8b44-102">Analyse des exécutions de packages et d'autres opérations</span><span class="sxs-lookup"><span data-stu-id="f8b44-102">Monitoring for Package Executions and Other Operations</span></span>
  <span data-ttu-id="f8b44-103">Vous pouvez surveiller les exécutions des packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , les validations de projet et d’autres opérations en utilisant un ou plusieurs des outils suivants.</span><span class="sxs-lookup"><span data-stu-id="f8b44-103">You can monitor [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package executions, project validations, and other operations by using one of more of the following tools.</span></span> <span data-ttu-id="f8b44-104">Certains outils tels que les drainages de données ne sont disponibles que pour les projets déployés sur le serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8b44-104">Certain tools such as data taps are available only for projects that are deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
-   <span data-ttu-id="f8b44-105">Journaux d’activité</span><span class="sxs-lookup"><span data-stu-id="f8b44-105">Logs</span></span>  
  
     <span data-ttu-id="f8b44-106">Pour plus d’informations, consultez [Journalisation Integration Services &#40;SSIS&#41;](integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="f8b44-106">For more information, see [Integration Services &#40;SSIS&#41; Logging](integration-services-ssis-logging.md).</span></span>  
  
-   <span data-ttu-id="f8b44-107">Rapports</span><span class="sxs-lookup"><span data-stu-id="f8b44-107">Reports</span></span>  
  
     <span data-ttu-id="f8b44-108">Pour plus d'informations, consultez [Reports for the Integration Services Server](../reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="f8b44-108">For more information, see [Reports for the Integration Services Server](../reports-for-the-integration-services-server.md).</span></span>  
  
-   <span data-ttu-id="f8b44-109">Les vues</span><span class="sxs-lookup"><span data-stu-id="f8b44-109">Views</span></span>  
  
     <span data-ttu-id="f8b44-110">Pour plus d’informations, consultez [Vues &#40;Catalogue Integration Services&#41;](/sql/integration-services/system-views/views-integration-services-catalog).</span><span class="sxs-lookup"><span data-stu-id="f8b44-110">For more information, see [Views &#40;Integration Services Catalog&#41;](/sql/integration-services/system-views/views-integration-services-catalog).</span></span>  
  
-   <span data-ttu-id="f8b44-111">Compteurs de performance</span><span class="sxs-lookup"><span data-stu-id="f8b44-111">Performance counters</span></span>  
  
     <span data-ttu-id="f8b44-112">Pour plus d’informations, consultez [Compteurs de performances](performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="f8b44-112">For more information, see [Performance Counters](performance-counters.md).</span></span>  
  
-   <span data-ttu-id="f8b44-113">Drainages de données</span><span class="sxs-lookup"><span data-stu-id="f8b44-113">Data taps</span></span>  
  
## <a name="operation-types"></a><span data-ttu-id="f8b44-114">Types d'opération</span><span class="sxs-lookup"><span data-stu-id="f8b44-114">Operation Types</span></span>  
 <span data-ttu-id="f8b44-115">Plusieurs types d'opérations différents sont surveillés dans le catalogue `SSISDB`, sur le serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8b44-115">Several different types of operations are monitored in the `SSISDB` catalog, on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="f8b44-116">Plusieurs messages peuvent être associés à chaque opération.</span><span class="sxs-lookup"><span data-stu-id="f8b44-116">Each operation can have multiple messages associated with it.</span></span> <span data-ttu-id="f8b44-117">Chaque message peut être classifié dans l'un des différents types.</span><span class="sxs-lookup"><span data-stu-id="f8b44-117">Each message can be classified into one of several different types.</span></span> <span data-ttu-id="f8b44-118">Par exemple, un message peut être de type Informations, Warning ou Error.</span><span class="sxs-lookup"><span data-stu-id="f8b44-118">For example, a message can be of type Information, Warning, or Error.</span></span> <span data-ttu-id="f8b44-119">Pour obtenir la liste complète des types de messages, consultez la documentation de la vue Transact-SQL [catalog.operation_messages &#40;Base de données SSISDB&#41;](/sql/integration-services/system-views/catalog-operation-messages-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="f8b44-119">For the full list of message types, see the documentation for the Transact-SQL [catalog.operation_messages &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operation-messages-ssisdb-database) view.</span></span> <span data-ttu-id="f8b44-120">Pour obtenir une liste complète des types d’opérations, consultez [catalog.operations &#40;Base de données SSISDB&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="f8b44-120">For a full list of the operations types, see [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span></span>  
  
 <span data-ttu-id="f8b44-121">Neuf types d'état différents sont utilisés pour indiquer l'état d'une opération.</span><span class="sxs-lookup"><span data-stu-id="f8b44-121">Nine different status types are used to indicate the status of an operation.</span></span> <span data-ttu-id="f8b44-122">Pour obtenir une liste complète des types de statuts, consultez la vue [catalog.operations &#40;Base de données SSISDB&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="f8b44-122">For a full list of the status types, see the [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database) view.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="f8b44-123">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="f8b44-123">Related Content</span></span>  
 <span data-ttu-id="f8b44-124">Entrée de blog [Vue d’ensemble de l’API SSIS T-SQL](https://go.microsoft.com/fwlink/?LinkId=249051), sur blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="f8b44-124">Blog entry, [SSIS T-SQL API Overview](https://go.microsoft.com/fwlink/?LinkId=249051), on blogs.msdn.com.</span></span>  
  
  
