---
title: Rapports de dépannage pour l’exécution des packages | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8fc476ac-bd69-434e-9636-70776e0b3b6c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b20d9c9c02af3f3df96e2ef46a7b25251793fa55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611856"
---
# <a name="troubleshooting-reports-for-package-execution"></a><span data-ttu-id="d9133-102">Dépannage des rapports pour l'exécution des packages</span><span class="sxs-lookup"><span data-stu-id="d9133-102">Troubleshooting Reports for Package Execution</span></span>
  <span data-ttu-id="d9133-103">Dans la version actuelle de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], deux rapports standard sont disponibles dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour vous aider à analyser et à dépanner les packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] déployés dans le catalogue [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d9133-103">In the current release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], standard reports are available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to help you monitor and troubleshoot [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that have been deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] catalog.</span></span> <span data-ttu-id="d9133-104">Deux types de rapports de package peuvent notamment vous aider à consulter l'état d'exécution du package et à identifier la cause des erreurs d'exécution.</span><span class="sxs-lookup"><span data-stu-id="d9133-104">Two of these package reports in particular help you to view package execution status and identify the cause of execution failures.</span></span>  
  
-   <span data-ttu-id="d9133-105">**Tableau de bord Integration Services** - Ce rapport fournit une vue d’ensemble de toutes les exécutions de package sur l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] au cours des dernières 24 heures.</span><span class="sxs-lookup"><span data-stu-id="d9133-105">**Integration Services Dashboard** - This report provides an overview of all the package executions on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance in the past 24 hours.</span></span> <span data-ttu-id="d9133-106">Le rapport affiche des informations telles que l'état, le type d'opération, le nom du package, etc., pour chaque package.</span><span class="sxs-lookup"><span data-stu-id="d9133-106">The report displays information such as Status, Operation Type, Package Name, etc., for each package.</span></span>  
  
     <span data-ttu-id="d9133-107">L'heure de début, l'heure de fin et la durée peuvent être interprétées comme suit :</span><span class="sxs-lookup"><span data-stu-id="d9133-107">The Start Time, End Time, and Duration can be interpreted as follows:</span></span>  
  
    -   <span data-ttu-id="d9133-108">Si le package fonctionne toujours, alors Durée = heure actuelle - heure de début</span><span class="sxs-lookup"><span data-stu-id="d9133-108">If the package is still running, then Duration = current time - Start Time</span></span>  
  
    -   <span data-ttu-id="d9133-109">Si le package est terminé, alors Durée = heure de fin - heure de début</span><span class="sxs-lookup"><span data-stu-id="d9133-109">If the package has completed, then Duration = End Time - Start Time</span></span>  
  
     <span data-ttu-id="d9133-110">Pour chaque package qui s'est exécuté sur le serveur, le tableau de bord vous permet de « zoomer » pour rechercher des détails spécifiques sur les erreurs d'exécution du package qui se sont produites.</span><span class="sxs-lookup"><span data-stu-id="d9133-110">For each package that has run on the server, the dashboard allows you to "zoom in" to find specific details on package execution errors that may have occurred.</span></span> <span data-ttu-id="d9133-111">Pour un exemple, cliquez sur **Vue d’ensemble** pour afficher un aperçu détaillé de l’état des tâches dans l’exécution, ou **Tous les messages** pour afficher les messages détaillés capturés dans le cadre de l’exécution du package.</span><span class="sxs-lookup"><span data-stu-id="d9133-111">For example, click **Overview** to display a high-level overview of the status of the tasks in the execution, or **All Messages** to display the detailed messages that were captured as part of the package execution.</span></span>  
  
     <span data-ttu-id="d9133-112">Vous pouvez filtrer la table affichée dans une page en cliquant sur **Filtrer** et en sélectionnant des critères dans la boîte de dialogue **Paramètres du filtre** .</span><span class="sxs-lookup"><span data-stu-id="d9133-112">You can filter the table displayed on any page by clicking **Filter** and then selecting criteria in the **Filter Settings** dialog.</span></span> <span data-ttu-id="d9133-113">Les critères de filtre disponibles dépendent des données qui sont affichées.</span><span class="sxs-lookup"><span data-stu-id="d9133-113">The filter criteria available depends on the data being displayed.</span></span> <span data-ttu-id="d9133-114">Vous pouvez modifier l’ordre de tri du rapport en cliquant sur l’icône de tri dans la boîte de dialogue **Paramètres du filtre** .</span><span class="sxs-lookup"><span data-stu-id="d9133-114">You can change the sort order of the report by clicking the sort icon in the **Filter Settings** dialog.</span></span>  
  
-   <span data-ttu-id="d9133-115">**Activité - Rapport Toutes les exécutions** - Ce rapport affiche un résumé de toutes les exécutions de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] exécutées sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="d9133-115">**Activity - All Executions Report** - This report displays a summary of all [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] executions that have been performed on the server.</span></span> <span data-ttu-id="d9133-116">Le résumé affiche les informations relatives à chaque exécution telles que l'état, l'heure de début et l'heure de fin.</span><span class="sxs-lookup"><span data-stu-id="d9133-116">The summary displays information for each execution such as status, start time, and end time.</span></span> <span data-ttu-id="d9133-117">Chaque entrée de résumé inclut des liens vers des informations concernant l'exécution, notamment les messages générés pendant l'exécution et les données de performances.</span><span class="sxs-lookup"><span data-stu-id="d9133-117">Each summary entry includes links to more information about the execution including messages generated during execution and performance data.</span></span> <span data-ttu-id="d9133-118">Comme avec le Tableau de bord Integration Services, vous pouvez appliquer un filtre à la table afin de réduire les informations affichées.</span><span class="sxs-lookup"><span data-stu-id="d9133-118">As with the Integration Services Dashboard, you can apply a filter to the table to narrow down the information displayed.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d9133-119">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="d9133-119">Related Tasks</span></span>  
 [<span data-ttu-id="d9133-120">Afficher les rapports du serveur Integration Services</span><span class="sxs-lookup"><span data-stu-id="d9133-120">View Reports for the Integration Services Server</span></span>](../view-reports-for-the-integration-services-server.md)  
  
## <a name="related-content"></a><span data-ttu-id="d9133-121">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="d9133-121">Related Content</span></span>  
 [<span data-ttu-id="d9133-122">Rapports pour le serveur de Integration Services</span><span class="sxs-lookup"><span data-stu-id="d9133-122">Reports for the Integration Services Server</span></span>](../reports-for-the-integration-services-server.md)  
  
 [<span data-ttu-id="d9133-123">Outils de dépannage pour l’exécution des packages</span><span class="sxs-lookup"><span data-stu-id="d9133-123">Troubleshooting Tools for Package Execution</span></span>](troubleshooting-tools-for-package-execution.md)  
  
  
