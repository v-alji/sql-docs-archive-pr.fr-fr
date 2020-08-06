---
title: Vérification de l’exécution d’un rapport | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- auditing [Reporting Services]
- verifying report execution
- logs [Reporting Services], verifying report run
- report execution data [Reporting Services]
- status information [Reporting Services]
- report processing [Reporting Services], verifying execution
- checking report execution
ms.assetid: 18a98f2f-6b40-454e-9b37-568ed1a96458
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c11c57f7c5f67b2557f5637ad10658abc9f80606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605064"
---
# <a name="verifying-a-report-run"></a><span data-ttu-id="2c371-102">Vérification de l'exécution d'un rapport</span><span class="sxs-lookup"><span data-stu-id="2c371-102">Verifying a Report Run</span></span>
  <span data-ttu-id="2c371-103">Pour afficher des informations sur l'état du traitement d'un rapport, vous pouvez utiliser les fichiers journaux ou vous référer aux informations d'état qui s'affichent avec le rapport dans le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="2c371-103">To view information about the status of report processing, you can use log files or refer to status information that is displayed with the report in Report Manager.</span></span>  
  
## <a name="sources-of-report-execution-data"></a><span data-ttu-id="2c371-104">Sources de données d'exécution d'un rapport</span><span class="sxs-lookup"><span data-stu-id="2c371-104">Sources of Report Execution Data</span></span>  
 <span data-ttu-id="2c371-105">Les journaux d'exécution de rapports fournissent des informations complètes sur l'exécution d'un rapport, y compris le nom du rapport, le nom de l'utilisateur ayant exécuté le rapport, l'heure d'exécution du rapport ainsi que l'extension de remise utilisée pour distribuer le rapport.</span><span class="sxs-lookup"><span data-stu-id="2c371-105">The report execution logs provide comprehensive information about report execution, including the name of the report, the name of the user who ran the report, report execution time, and the delivery extension used to distribute the report.</span></span> <span data-ttu-id="2c371-106">Pour afficher et analyser ces données, vous pouvez copier le journal d'exécution du rapport dans des tables de base de données qui sont faciles à interroger et à éditer.</span><span class="sxs-lookup"><span data-stu-id="2c371-106">To view and analyze this data, you can copy the report execution log into database tables that are easy to query and report on.</span></span>  
  
 <span data-ttu-id="2c371-107">Les fichiers journaux contiennent de nombreuses entrées concernant l'exécution du rapport et d'autres activités liées au serveur.</span><span class="sxs-lookup"><span data-stu-id="2c371-107">Log files contain many entries about report execution and other server activity.</span></span> <span data-ttu-id="2c371-108">Si vous souhaitez vérifier uniquement le moment de la dernière exécution d'un rapport, comme les fichiers journaux contiennent beaucoup de données, vous pouvez opter pour l'utilisation du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="2c371-108">Because log files contain so much data, you may want to use Report Manager if you only want to verify when the report last ran.</span></span> <span data-ttu-id="2c371-109">Si vous avez besoin d'informations supplémentaires, vous devez afficher les fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="2c371-109">If you require additional information, you must view the log files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c371-110">Le Gestionnaire de rapports n'affiche pas les horaires de traitement des rapports qui s'exécutent à la demande.</span><span class="sxs-lookup"><span data-stu-id="2c371-110">Report Manager does not show the processing times of reports that run on demand.</span></span>  
  
 <span data-ttu-id="2c371-111">Le tableau suivant indique comment afficher la date et l'heure de traitement des divers types de rapports.</span><span class="sxs-lookup"><span data-stu-id="2c371-111">The following table describes how to view the processing date and time for various types of reports.</span></span>  
  
|<span data-ttu-id="2c371-112">Pour ce type de rapport</span><span class="sxs-lookup"><span data-stu-id="2c371-112">For this type of report</span></span>|<span data-ttu-id="2c371-113">Les informations de date et d'heure se situent ici</span><span class="sxs-lookup"><span data-stu-id="2c371-113">Date and time information is located here</span></span>|<span data-ttu-id="2c371-114">Pour afficher ces informations, procédez comme suit</span><span class="sxs-lookup"><span data-stu-id="2c371-114">To view the information, do the following</span></span>|  
|-----------------------------|-----------------------------------------------|-----------------------------------------------|  
|<span data-ttu-id="2c371-115">Rapport s'exécutant en tant qu'instantané de rapport.</span><span class="sxs-lookup"><span data-stu-id="2c371-115">A report that runs as a report snapshot.</span></span>|<span data-ttu-id="2c371-116">Dans la page Contenu.</span><span class="sxs-lookup"><span data-stu-id="2c371-116">On the Contents page.</span></span> <span data-ttu-id="2c371-117">Pour plus d’informations, consultez [Page Contenu &#40;Gestionnaire de rapports&#41;](../contents-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2c371-117">For more information, see [Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md).</span></span>|<span data-ttu-id="2c371-118">1) Localisez le dossier contenant le rapport.</span><span class="sxs-lookup"><span data-stu-id="2c371-118">1) Locate the folder that contains the report.</span></span><br /><span data-ttu-id="2c371-119">2) Choisissez d’afficher le contenu du dossier en mode Détails.</span><span class="sxs-lookup"><span data-stu-id="2c371-119">2) Set the folder in Details view.</span></span><br /><span data-ttu-id="2c371-120">3) 3) Notez la date et l’heure dans la colonne lors de l' **exécution** .</span><span class="sxs-lookup"><span data-stu-id="2c371-120">3) 3) Note the date and time in the **When Run** column.</span></span>|  
|<span data-ttu-id="2c371-121">Instantané dans l'historique de rapport.</span><span class="sxs-lookup"><span data-stu-id="2c371-121">A snapshot in report history.</span></span>|<span data-ttu-id="2c371-122">Dans la page des propriétés de l'historique.</span><span class="sxs-lookup"><span data-stu-id="2c371-122">On the History Properties page.</span></span> <span data-ttu-id="2c371-123">Pour plus d’informations, consultez [Page de propriétés Options d’instantanés &#40;Gestionnaire de rapports&#41;](../snapshot-options-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2c371-123">For more information, see [Snapshot Options Properties Page &#40;Report Manager&#41;](../snapshot-options-properties-page-report-manager.md).</span></span>|<span data-ttu-id="2c371-124">1) Ouvrez le rapport.</span><span class="sxs-lookup"><span data-stu-id="2c371-124">1) Open the report.</span></span><br /><span data-ttu-id="2c371-125">2) Cliquez sur la page **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="2c371-125">2) Click the **Properties** page.</span></span><br /><span data-ttu-id="2c371-126">3) Cliquez sur l’onglet **Historique** .</span><span class="sxs-lookup"><span data-stu-id="2c371-126">3) Click the **History** tab.</span></span><br /><span data-ttu-id="2c371-127">4) Notez la date et l’heure figurant dans la colonne **Lors de l’exécution** .</span><span class="sxs-lookup"><span data-stu-id="2c371-127">4) Note the date and time in the **When Run** column.</span></span>|  
|<span data-ttu-id="2c371-128">Rapport mis en cache.</span><span class="sxs-lookup"><span data-stu-id="2c371-128">A cached report.</span></span>|<span data-ttu-id="2c371-129">Dans la planification utilisée pour créer et actualiser le rapport mis en cache.</span><span class="sxs-lookup"><span data-stu-id="2c371-129">In the schedule used to create and refresh the cached report.</span></span>|<span data-ttu-id="2c371-130">1) Ouvrez le rapport.</span><span class="sxs-lookup"><span data-stu-id="2c371-130">1) Open the report.</span></span><br /><span data-ttu-id="2c371-131">2) Cliquez sur la page **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="2c371-131">2) Click the **Properties** page.</span></span><br /><span data-ttu-id="2c371-132">3) Cliquez sur l’onglet **Exécution** .</span><span class="sxs-lookup"><span data-stu-id="2c371-132">3) Click the **Execution** tab.</span></span><br /><span data-ttu-id="2c371-133">4) Ouvrez la planification.</span><span class="sxs-lookup"><span data-stu-id="2c371-133">4) Open the schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c371-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c371-134">See Also</span></span>  
 <span data-ttu-id="2c371-135">[Fichiers journaux et sources de Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="2c371-135">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 <span data-ttu-id="2c371-136">[Définir les propriétés de traitement d’un rapport](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="2c371-136">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="2c371-137">Gestionnaire de rapports &#40;SSRS en mode natif&#41;</span><span class="sxs-lookup"><span data-stu-id="2c371-137">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)  
  
  
