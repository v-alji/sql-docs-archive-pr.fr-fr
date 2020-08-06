---
title: Progression du conseiller de mise à niveau | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], analysis progress status
- analyzing system [Upgrade Advisor], progress information
- SQL Server Upgrade Advisor, analysis progress status
- monitoring analysis progress
- progress information [Upgrade Advisor]
- status information [Upgrade Advisor]
ms.assetid: a9e3d1c8-d492-4beb-93c7-f1bc40d4a910
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b504b8f1c8392ad2cf55837dc65bbb2f019d6f48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604861"
---
# <a name="upgrade-advisor-progress"></a><span data-ttu-id="3f518-102">Progression du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="3f518-102">Upgrade Advisor Progress</span></span>
  <span data-ttu-id="3f518-103">L'analyse du Conseiller de mise à niveau commence par une analyse de chaque composant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sélectionné exécutée par un analyseur dédié.</span><span class="sxs-lookup"><span data-stu-id="3f518-103">Upgrade Advisor analysis starts with a dedicated analyzer that performs an analysis of each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component that you selected.</span></span> <span data-ttu-id="3f518-104">À mesure que les composants sont analysés, la progression est signalée dans la boîte de dialogue de **progression** .</span><span class="sxs-lookup"><span data-stu-id="3f518-104">As components are analyzed, progress is reported in the **Progress** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3f518-105">Options</span><span class="sxs-lookup"><span data-stu-id="3f518-105">Options</span></span>  
 <span data-ttu-id="3f518-106">**Action**</span><span class="sxs-lookup"><span data-stu-id="3f518-106">**Action**</span></span>  
 <span data-ttu-id="3f518-107">Spécifie le composant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui est sélectionné pour l'analyse.</span><span class="sxs-lookup"><span data-stu-id="3f518-107">Specifies the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component that is selected for analysis.</span></span>  
  
 <span data-ttu-id="3f518-108">**État**</span><span class="sxs-lookup"><span data-stu-id="3f518-108">**Status**</span></span>  
 <span data-ttu-id="3f518-109">Affiche la valeur d'état retournée par l'interface de progression du composant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f518-109">Displays the status value returned from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component progress interface.</span></span>  
  
 <span data-ttu-id="3f518-110">**Message**</span><span class="sxs-lookup"><span data-stu-id="3f518-110">**Message**</span></span>  
 <span data-ttu-id="3f518-111">Affiche les messages d'erreur, d'échec ou de réussite retournés par l'analyseur individuel de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f518-111">Displays error, failure, or success messages returned from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] individual analyzer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f518-112">Si l'analyse dure trop longtemps, vous pouvez l'arrêter, quitter l'Assistant Analyse du Conseiller de mise à niveau, puis réexécuter l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="3f518-112">If the analysis is taking too long, you can stop the analysis, exit the Upgrade Advisor Analysis Wizard, and then rerun the wizard.</span></span> <span data-ttu-id="3f518-113">Pour réduire le temps d'analyse, limitez le nombre de composants à analyser.</span><span class="sxs-lookup"><span data-stu-id="3f518-113">To reduce analysis time, select fewer components to scan.</span></span>  
  
 <span data-ttu-id="3f518-114">À la fin de l'analyse, le rapport est écrit dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="3f518-114">When analysis is complete, the report is written to a file.</span></span> <span data-ttu-id="3f518-115">Vous pouvez afficher le rapport en cliquant sur **lancer le rapport** pour lancer la visionneuse de rapports à partir de cette page.</span><span class="sxs-lookup"><span data-stu-id="3f518-115">You can view the report by clicking **Launch Report** to launch the report viewer from this page.</span></span> <span data-ttu-id="3f518-116">Si vous souhaitez afficher le rapport ultérieurement, vous pouvez ouvrir la **visionneuse de rapports du conseiller de mise à niveau** à partir de la page de démarrage du conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="3f518-116">If you want to view the report later, you can open the **Upgrade Advisor Report Viewer** from the Upgrade Advisor start page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f518-117">Les rapports précédents sont enregistrés chaque fois que vous analysez un serveur.</span><span class="sxs-lookup"><span data-stu-id="3f518-117">Previous reports are saved every time you analyze a server.</span></span> <span data-ttu-id="3f518-118">Les rapports sont enregistrés en utilisant le timestamp pour le nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="3f518-118">The reports are saved using the timestamp for the file name.</span></span> <span data-ttu-id="3f518-119">La visionneuse de rapports affiche les cinq derniers rapports enregistrés.</span><span class="sxs-lookup"><span data-stu-id="3f518-119">The report viewer displays the latest five saved reports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f518-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3f518-120">See Also</span></span>  
 <span data-ttu-id="3f518-121">[Procédure : lancer le conseiller de mise à niveau](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="3f518-121">[How to: Launch Upgrade Advisor](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="3f518-122">[Procédure : exécuter l’Assistant analyse du conseiller de mise à niveau](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="3f518-122">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="3f518-123">[Composants SQL Server](../../../2014/sql-server/install/sql-server-components.md) </span><span class="sxs-lookup"><span data-stu-id="3f518-123">[SQL Server Components](../../../2014/sql-server/install/sql-server-components.md) </span></span>  
 <span data-ttu-id="3f518-124">[Référence de l’interface utilisateur du conseiller de mise à niveau](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span><span class="sxs-lookup"><span data-stu-id="3f518-124">[Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span></span>  
 [<span data-ttu-id="3f518-125">Utilisation du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="3f518-125">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
