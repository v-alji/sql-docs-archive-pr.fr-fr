---
title: Exécution du conseiller de mise à niveau (interface utilisateur) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor Report Viewer
- Upgrade Advisor [SQL Server], running
- launching Upgrade Advisor
- Upgrade Advisor Analysis Wizard
- starting Upgrade Advisor
- SQL Server Upgrade Advisor, running
ms.assetid: 7f47c9b3-88d3-43d6-837e-f157b49a55ac
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a5e47ef2b8183823dff884e114adc420e371adf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614341"
---
# <a name="running-upgrade-advisor-user-interface"></a><span data-ttu-id="87f6b-102">Exécution du Conseiller de mise à niveau (interface utilisateur)</span><span class="sxs-lookup"><span data-stu-id="87f6b-102">Running Upgrade Advisor (User Interface)</span></span>
  <span data-ttu-id="87f6b-103">Vous pouvez exécuter le Conseiller de mise à niveau pour analyser des composants locaux ou distants à tout moment pendant la planification de la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="87f6b-103">You can run Upgrade Advisor to analyze local or remote components during upgrade planning.</span></span> <span data-ttu-id="87f6b-104">Le conseiller de mise à niveau génère un rapport pour chaque composant et instance analysés.</span><span class="sxs-lookup"><span data-stu-id="87f6b-104">Upgrade Advisor produces a report for each component and instance that is analyzed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="87f6b-105">Le Conseiller de mise à niveau n'analyse pas les instances distantes de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87f6b-105">Upgrade Advisor does not analyze remote instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="87f6b-106">Pour analyser une instance de [!INCLUDE[ssRS](../../includes/ssrs.md)], le Conseiller de mise à niveau doit être installé sur l'ordinateur sur lequel [!INCLUDE[ssRS](../../includes/ssrs.md)] est installé.</span><span class="sxs-lookup"><span data-stu-id="87f6b-106">To analyze an instance of [!INCLUDE[ssRS](../../includes/ssrs.md)], Upgrade Advisor must be installed on the computer where [!INCLUDE[ssRS](../../includes/ssrs.md)] is installed.</span></span>  
>   
>  <span data-ttu-id="87f6b-107">Pour analyser [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services, vous devez avoir [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] installé et [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installé sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="87f6b-107">To analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services, you must have the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] installed and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed on the same computer.</span></span>  
  
## <a name="running-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="87f6b-108">Exécution de l’Assistant analyse du conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="87f6b-108">Running the Upgrade Advisor Analysis Wizard</span></span>  
 <span data-ttu-id="87f6b-109">L’exécution de l’Assistant analyse du conseiller de mise à niveau comprend six étapes :</span><span class="sxs-lookup"><span data-stu-id="87f6b-109">Running the Upgrade Advisor Analysis Wizard has six steps:</span></span>  
  
1.  <span data-ttu-id="87f6b-110">Lancer l'Assistant à partir de la page de démarrage du Conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="87f6b-110">Launch the wizard from the Upgrade Advisor start page.</span></span>  
  
2.  <span data-ttu-id="87f6b-111">Identifier le serveur et les composants à analyser.</span><span class="sxs-lookup"><span data-stu-id="87f6b-111">Identify server and components to analyze.</span></span>  
  
3.  <span data-ttu-id="87f6b-112">Rassembler des informations d'authentification.</span><span class="sxs-lookup"><span data-stu-id="87f6b-112">Gather authentication information.</span></span>  
  
4.  <span data-ttu-id="87f6b-113">Rassembler des paramètres supplémentaires selon le type de composant.</span><span class="sxs-lookup"><span data-stu-id="87f6b-113">Gather additional parameters based on component type.</span></span>  
  
5.  <span data-ttu-id="87f6b-114">Analyser les composants sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="87f6b-114">Analyze selected components.</span></span>  
  
6.  <span data-ttu-id="87f6b-115">Générer un rapport sur les problèmes de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="87f6b-115">Generate report of upgrade issues.</span></span>  
  
 <span data-ttu-id="87f6b-116">Pour plus d’informations sur l’Assistant analyse du conseiller de mise à niveau, consultez [procédure : exécuter l’Assistant analyse du conseiller de mise à niveau](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="87f6b-116">For more information about the Upgrade Advisor Analysis Wizard, see [How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md).</span></span>  
  
 <span data-ttu-id="87f6b-117">Pour obtenir des informations spécifiques requises pour chaque étape, consultez [référence de l’interface utilisateur du conseiller de mise à niveau](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span><span class="sxs-lookup"><span data-stu-id="87f6b-117">For specific information that is required for each step, see [Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span></span>  
  
## <a name="running-the-upgrade-advisor-report-viewer"></a><span data-ttu-id="87f6b-118">Exécution de la visionneuse de rapports du conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="87f6b-118">Running the Upgrade Advisor Report Viewer</span></span>  
 <span data-ttu-id="87f6b-119">Vous utilisez la visionneuse de rapports du conseiller de mise à niveau pour afficher les rapports générés par l’Assistant analyse du conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="87f6b-119">You use the Upgrade Advisor Report Viewer to view reports generated by the Upgrade Advisor Analysis Wizard.</span></span> <span data-ttu-id="87f6b-120">Une fois le rapport chargé, vous pouvez filtrer les composants du rapport en fonction des critères suivants :</span><span class="sxs-lookup"><span data-stu-id="87f6b-120">When the report is loaded, you can filter the components of the report by the following factors:</span></span>  
  
-   <span data-ttu-id="87f6b-121">Tous les problèmes</span><span class="sxs-lookup"><span data-stu-id="87f6b-121">All issues</span></span>  
  
-   <span data-ttu-id="87f6b-122">Tous les problèmes de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="87f6b-122">All upgrade issues</span></span>  
  
-   <span data-ttu-id="87f6b-123">Problèmes de pré-mise à niveau</span><span class="sxs-lookup"><span data-stu-id="87f6b-123">Pre-upgrade issues</span></span>  
  
-   <span data-ttu-id="87f6b-124">Tous les problèmes de migration</span><span class="sxs-lookup"><span data-stu-id="87f6b-124">All migration issues</span></span>  
  
-   <span data-ttu-id="87f6b-125">Problèmes résolus</span><span class="sxs-lookup"><span data-stu-id="87f6b-125">Resolved issues</span></span>  
  
-   <span data-ttu-id="87f6b-126">Problèmes non résolus</span><span class="sxs-lookup"><span data-stu-id="87f6b-126">Unresolved issues</span></span>  
  
 <span data-ttu-id="87f6b-127">Pour obtenir des instructions pas à pas sur l'utilisation de la visionneuse de rapports, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="87f6b-127">For step-by-step instructions for using the report viewer, see the following topics:</span></span>  
  
-   [<span data-ttu-id="87f6b-128">Procédure : afficher un rapport du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="87f6b-128">How to: View an Upgrade Advisor Report</span></span>](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md)  
  
-   [<span data-ttu-id="87f6b-129">Procédure : filtrer des rapports</span><span class="sxs-lookup"><span data-stu-id="87f6b-129">How to: Filter Reports</span></span>](../../../2014/sql-server/install/how-to-filter-reports.md)  
  
-   [<span data-ttu-id="87f6b-130">Procédure : Export Reports</span><span class="sxs-lookup"><span data-stu-id="87f6b-130">How to: Export Reports</span></span>](../../../2014/sql-server/install/how-to-export-reports.md)  
  
## <a name="see-also"></a><span data-ttu-id="87f6b-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="87f6b-131">See Also</span></span>  
 <span data-ttu-id="87f6b-132">[Procédure : exécuter l’Assistant analyse du conseiller de mise à niveau](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="87f6b-132">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="87f6b-133">[Référence de l’interface utilisateur du conseiller de mise à niveau](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span><span class="sxs-lookup"><span data-stu-id="87f6b-133">[Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span></span>  
 <span data-ttu-id="87f6b-134">[Résolution des problèmes de mise à niveau](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="87f6b-134">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="87f6b-135">Utilisation du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="87f6b-135">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
