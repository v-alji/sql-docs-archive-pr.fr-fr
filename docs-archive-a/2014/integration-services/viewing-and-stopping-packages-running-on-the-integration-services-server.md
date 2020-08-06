---
title: Affichage et arrêt des packages en cours d’exécution sur le serveur Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], managing
- managing running packages [Integration Services]
- packages [Integration Services], running
- running package [Integration Services], managing
ms.assetid: 11bf44e6-f6b0-475f-b816-40e914dbac80
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6e63839d4ab5d8d50f7d86eea05c8d58107d6799
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613522"
---
# <a name="viewing-and-stopping-packages-running-on-the-integration-services-server"></a><span data-ttu-id="608e9-102">Affichage et arrêt des packages exécutés sur le serveur Integration Services</span><span class="sxs-lookup"><span data-stu-id="608e9-102">Viewing and Stopping Packages Running on the Integration Services Server</span></span>
  <span data-ttu-id="608e9-103">La base de données `SSISDB` stocke l'historique de l'exécution dans des tables internes qui ne sont pas visibles par les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="608e9-103">The `SSISDB` database stores execution history in internal tables that are not visible to users.</span></span> <span data-ttu-id="608e9-104">Cependant, elle expose les informations dont vous avez besoin via des vues publiques que vous pouvez interroger.</span><span class="sxs-lookup"><span data-stu-id="608e9-104">However it exposes the information that you need through public views that you can query.</span></span> <span data-ttu-id="608e9-105">Elle fournit également des procédures stockées que vous pouvez appeler pour effectuer des tâches courantes liées aux packages.</span><span class="sxs-lookup"><span data-stu-id="608e9-105">It also provides stored procedures that you can call to perform common tasks related to packages.</span></span>  
  
 <span data-ttu-id="608e9-106">En général, vous gérez des objets [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur le serveur dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="608e9-106">Typically you manage [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects on the server in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="608e9-107">Cependant, vous pouvez également interroger les vues de base de données et appeler les procédures stockées directement, ou écrire du code personnalisé qui appelle l'API managé.</span><span class="sxs-lookup"><span data-stu-id="608e9-107">However you can also query the database views and call the stored procedures directly, or write custom code that calls the managed API.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="608e9-108">et l'API managé interrogent les vues et appellent les procédures stockées pour effectuer de nombreuses tâches.</span><span class="sxs-lookup"><span data-stu-id="608e9-108">and the managed API query the views and call the stored procedures to perform many of their tasks.</span></span> <span data-ttu-id="608e9-109">Par exemple, vous pouvez afficher la liste des packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui sont en cours d'exécution sur le serveur, et demander l'arrêt de packages si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="608e9-109">For example, you can view the list of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages that are currently running on the server, and request packages to stop if you have to.</span></span>  
  
## <a name="viewing-the-list-of-running-packages"></a><span data-ttu-id="608e9-110">Affichage de la liste de packages en cours d'exécution</span><span class="sxs-lookup"><span data-stu-id="608e9-110">Viewing the List of Running Packages</span></span>  
 <span data-ttu-id="608e9-111">Vous pouvez afficher la liste des packages en cours d'exécution sur le serveur dans la boîte de dialogue **Opérations actives** .</span><span class="sxs-lookup"><span data-stu-id="608e9-111">You can view the list of packages that are currently running on the server in the **Active Operations** dialog box.</span></span> <span data-ttu-id="608e9-112">Pour plus d'informations, consultez [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="608e9-112">For more information, see [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span></span>  
  
 <span data-ttu-id="608e9-113">Pour plus d'informations sur les autres méthodes que vous pouvez utiliser pour afficher la liste de packages en cours d'exécution, consultez les rubriques suivantes.</span><span class="sxs-lookup"><span data-stu-id="608e9-113">For information about the other methods that you can use to view the list of running packages, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="608e9-114">Accès Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="608e9-114">access</span></span>  
 <span data-ttu-id="608e9-115">Pour afficher la liste des packages qui s’exécutent sur le serveur, interrogez la vue, [catalog.executions &#40;base de données SSISDB&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database) pour les packages qui ont l’état 2.</span><span class="sxs-lookup"><span data-stu-id="608e9-115">To view the list of packages that are running on the server, query the view, [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database) for packages that have a status of 2.</span></span>  
  
 <span data-ttu-id="608e9-116">Accès par programmation via l'API managé</span><span class="sxs-lookup"><span data-stu-id="608e9-116">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="608e9-117">Consultez l’espace de noms <xref:Microsoft.SqlServer.Management.IntegrationServices> et ses classes.</span><span class="sxs-lookup"><span data-stu-id="608e9-117">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="stopping-a-running-package"></a><span data-ttu-id="608e9-118">Arrêt d'un package en cours d'exécution</span><span class="sxs-lookup"><span data-stu-id="608e9-118">Stopping a Running Package</span></span>  
 <span data-ttu-id="608e9-119">Vous pouvez demander l'arrêt d'un package en cours d’exécution dans la boîte de dialogue **Opérations actives** .</span><span class="sxs-lookup"><span data-stu-id="608e9-119">You can request a running package to stop in the **Active Operations** dialog box.</span></span> <span data-ttu-id="608e9-120">Pour plus d'informations, consultez [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="608e9-120">For more information, see [Active Operations Dialog Box](../../2014/integration-services/active-operations-dialog-box.md).</span></span>  
  
 <span data-ttu-id="608e9-121">Pour plus d'informations sur les autres méthodes que vous pouvez utiliser pour arrêter l'exécution d'un package, consultez les rubriques suivantes.</span><span class="sxs-lookup"><span data-stu-id="608e9-121">For information about the other methods that you can use to stop a running package, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="608e9-122">Accès Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="608e9-122">access</span></span>  
 <span data-ttu-id="608e9-123">Pour arrêter un package en cours d’exécution sur le serveur, appelez la procédure stockée, [catalog.stop_operation &#40;base de données SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-stop-operation-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="608e9-123">To stop a package that is running on the server, call the stored procedure, [catalog.stop_operation &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-stop-operation-ssisdb-database).</span></span>  
  
 <span data-ttu-id="608e9-124">Accès par programmation via l'API managé</span><span class="sxs-lookup"><span data-stu-id="608e9-124">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="608e9-125">Consultez l’espace de noms <xref:Microsoft.SqlServer.Management.IntegrationServices> et ses classes.</span><span class="sxs-lookup"><span data-stu-id="608e9-125">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="viewing-the-history-of-packages-that-have-run"></a><span data-ttu-id="608e9-126">Affichage de l'historique des packages qui ont été exécutés</span><span class="sxs-lookup"><span data-stu-id="608e9-126">Viewing the History of Packages That Have Run</span></span>  
 <span data-ttu-id="608e9-127">Pour afficher l’historique des packages exécutés dans [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], utilisez le rapport **Toutes les exécutions** .</span><span class="sxs-lookup"><span data-stu-id="608e9-127">To view the history of packages that have run in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], use the **All Executions** report.</span></span> <span data-ttu-id="608e9-128">Pour plus d’informations sur le rapport **Toutes les exécutions** et d’autres rapports standard, consultez [Rapports du serveur Integration Services](../../2014/integration-services/reports-for-the-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="608e9-128">For more information on the **All Executions** report and other standard reports, see [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="608e9-129">Pour plus d'informations sur les autres méthodes que vous pouvez utiliser pour afficher l'historique des packages en cours d'exécution, consultez les rubriques suivantes.</span><span class="sxs-lookup"><span data-stu-id="608e9-129">For information about the other methods that you can use to view the history of running packages, see the following topics.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="608e9-130">Accès Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="608e9-130">access</span></span>  
 <span data-ttu-id="608e9-131">Pour afficher des informations relatives aux packages qui ont été exécutés, interrogez la vue, [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="608e9-131">To view information about packages that have run, query the view, [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database).</span></span>  
  
 <span data-ttu-id="608e9-132">Accès par programmation via l'API managé</span><span class="sxs-lookup"><span data-stu-id="608e9-132">Programmatic access through the managed API</span></span>  
 <span data-ttu-id="608e9-133">Consultez l’espace de noms <xref:Microsoft.SqlServer.Management.IntegrationServices> et ses classes.</span><span class="sxs-lookup"><span data-stu-id="608e9-133">See the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace and its classes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="608e9-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="608e9-134">See Also</span></span>  
 <span data-ttu-id="608e9-135">[Exécution de projets et de packages](packages/run-integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="608e9-135">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="608e9-136">Rapports de dépannage pour l’exécution des packages</span><span class="sxs-lookup"><span data-stu-id="608e9-136">Troubleshooting Reports for Package Execution</span></span>](troubleshooting/troubleshooting-reports-for-package-execution.md)  
  
  
