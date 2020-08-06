---
title: Utilisation des rapports | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- displaying reports
- overriding reports
- Upgrade Advisor Report Viewer
- reports [Upgrade Advisor], about reports
- formatting reports
- resolved issues [Upgrade Advisor]
- distributing reports [Reporting Services]
- filtering reports [Reporting Services]
- removing report items
- viewing reports
- rerunning analysis
- information issues [Upgrade Advisor]
- deleting report items
- icons [Upgrade Advisor]
- Upgrade Advisor [SQL Server], reports
- sending reports
- blocking issues [Upgrade Advisor]
- sharing reports
- reports [Upgrade Advisor]
- SQL Server Upgrade Advisor, reports
- modifying reports
- distributing reports [Reporting Services], about report distribution
- warnings [Upgrade Advisor]
- analyzing system [Upgrade Advisor], reports
ms.assetid: 4a3cb94a-a7ac-4cec-94c7-db26fcf6d161
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f52afcfdaa7de33d83d64a049f9a350f0463b4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710116"
---
# <a name="using-reports"></a><span data-ttu-id="6aafc-102">Utilisation de rapports</span><span class="sxs-lookup"><span data-stu-id="6aafc-102">Using Reports</span></span>
  <span data-ttu-id="6aafc-103">Un rapport distinct est généré pour chaque composant et, si nécessaire, pour chaque instance, que l'Assistant Analyse du Conseiller de mise à niveau analyse sur un serveur.</span><span class="sxs-lookup"><span data-stu-id="6aafc-103">A separate report is generated for each component, and, where necessary, each instance, that the Upgrade Advisor Analysis Wizard analyzes on a server.</span></span> <span data-ttu-id="6aafc-104">Le rapport contient des détails sur les problèmes connus qui affectent une mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="6aafc-104">The report provides details about known issues that affect an upgrade.</span></span> <span data-ttu-id="6aafc-105">Il fournit également des liens vers des informations et des actions suggérées pour traiter les problèmes identifiés.</span><span class="sxs-lookup"><span data-stu-id="6aafc-105">It also provides links to information and suggested actions for addressing the identified issues.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6aafc-106">Si la visionneuse de rapports du conseiller de mise à niveau ne trouve pas de rapports dans le répertoire des rapports par défaut, vous pouvez charger un rapport à partir d’un répertoire différent à l’aide du lien **ouvrir le rapport** .</span><span class="sxs-lookup"><span data-stu-id="6aafc-106">If the Upgrade Advisor Report Viewer does not find any reports in the default reports directory, you can load a report from a different directory by using the **Open Report** link.</span></span>  
  
## <a name="viewing-reports"></a><span data-ttu-id="6aafc-107">Affichage de rapports</span><span class="sxs-lookup"><span data-stu-id="6aafc-107">Viewing Reports</span></span>  
 <span data-ttu-id="6aafc-108">La visionneuse de rapports vous permet d'afficher les rapports du Conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="6aafc-108">You use the Upgrade Advisor Report Viewer to view Upgrade Advisor reports.</span></span> <span data-ttu-id="6aafc-109">Pour afficher les rapports, sur la page de démarrage du conseiller de mise à niveau, cliquez sur **lancer le conseiller de mise à niveau**.</span><span class="sxs-lookup"><span data-stu-id="6aafc-109">To view reports, on the Upgrade Advisor start page, click **Launch Upgrade Advisor Report Viewer**.</span></span>  
  
 <span data-ttu-id="6aafc-110">Après avoir chargé le rapport d'un serveur, vous pouvez sélectionner un composant pour consulter les problèmes de mise à niveau le concernant.</span><span class="sxs-lookup"><span data-stu-id="6aafc-110">After you load a report for a server, you can select a component for which you want to see upgrade issues.</span></span> <span data-ttu-id="6aafc-111">Vous pouvez appliquer un filtre à partir de la zone **Filtrer par** pour afficher les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6aafc-111">You can apply a filter from the **Filter By** box to see the following:</span></span>  
  
-   <span data-ttu-id="6aafc-112">Tous les problèmes</span><span class="sxs-lookup"><span data-stu-id="6aafc-112">All issues</span></span>  
  
-   <span data-ttu-id="6aafc-113">Tous les problèmes de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="6aafc-113">All upgrade issues</span></span>  
  
-   <span data-ttu-id="6aafc-114">Problèmes de pré-mise à niveau</span><span class="sxs-lookup"><span data-stu-id="6aafc-114">Pre-upgrade issues</span></span>  
  
-   <span data-ttu-id="6aafc-115">Tous les problèmes de migration</span><span class="sxs-lookup"><span data-stu-id="6aafc-115">All migration issues</span></span>  
  
-   <span data-ttu-id="6aafc-116">Problèmes résolus</span><span class="sxs-lookup"><span data-stu-id="6aafc-116">Resolved issues</span></span>  
  
-   <span data-ttu-id="6aafc-117">Problèmes non résolus</span><span class="sxs-lookup"><span data-stu-id="6aafc-117">Unresolved issues</span></span>  
  
 <span data-ttu-id="6aafc-118">Si votre rapport contient plus de 20 problèmes, vous pouvez passer au groupe de problèmes suivant ou précédent en cliquant sur **20 suivants** ou **20 précédents** en haut ou en bas de la liste des problèmes.</span><span class="sxs-lookup"><span data-stu-id="6aafc-118">If your report has more than 20 issues, you can move to the next or previous group of issues by clicking **Next 20** or **Previous 20** at the top or bottom of the issues list.</span></span>  
  
 <span data-ttu-id="6aafc-119">Vous pouvez afficher jusqu’à cinq rapports enregistrés en sélectionnant les rapports dans la zone de liste déroulante **rapport** .</span><span class="sxs-lookup"><span data-stu-id="6aafc-119">You can view up to five saved reports by selecting the reports from the **Report** drop-down list box.</span></span> <span data-ttu-id="6aafc-120">Les rapports sont répertoriés selon le horodateur à partir du moment où ils ont été générés.</span><span class="sxs-lookup"><span data-stu-id="6aafc-120">The reports are listed by the timestamp from when they were generated.</span></span>  
  
## <a name="report-format"></a><span data-ttu-id="6aafc-121">Format de rapport</span><span class="sxs-lookup"><span data-stu-id="6aafc-121">Report Format</span></span>  
 <span data-ttu-id="6aafc-122">La visionneuse de rapports affiche les problèmes répertoriés dans trois colonnes.</span><span class="sxs-lookup"><span data-stu-id="6aafc-122">The report viewer displays report issues in three columns.</span></span> <span data-ttu-id="6aafc-123">Chaque problème est réductible afin que vous puissiez masquer la description et afficher uniquement les informations importantes.</span><span class="sxs-lookup"><span data-stu-id="6aafc-123">Each issue is collapsible so that you can hide the description and view only the key information.</span></span>  
  
 <span data-ttu-id="6aafc-124">La première colonne est la colonne **importance** .</span><span class="sxs-lookup"><span data-stu-id="6aafc-124">The first column is the **Importance** column.</span></span> <span data-ttu-id="6aafc-125">Des icônes indiquent l'importance de chaque problème en affichant un cercle rouge avec un X pour signifier des problèmes importants ou entraînant un blocage ou un triangle jaune avec un point d'exclamation pour signifier des problèmes faisant l'objet d'un avertissement ou d'une information.</span><span class="sxs-lookup"><span data-stu-id="6aafc-125">Icons indicate the importance for each issue by displaying either a red circle with an X for blocking or important issues or a yellow triangle with an exclamation mark for Warning and Information issues.</span></span> <span data-ttu-id="6aafc-126">La deuxième colonne, **quand elle est à corriger**, indique quand vous devez résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="6aafc-126">The second column, **When to fix**, indicates when you must resolve the issue.</span></span> <span data-ttu-id="6aafc-127">Vous pouvez trier le rapport en fonction de l' **importance** ou **de la correction de** la colonne.</span><span class="sxs-lookup"><span data-stu-id="6aafc-127">You can sort the report on either the **Importance** or **When to fix** column.</span></span> <span data-ttu-id="6aafc-128">La troisième colonne, **Description**, répertorie le titre du problème.</span><span class="sxs-lookup"><span data-stu-id="6aafc-128">The third column, **Description**, lists the title of the issue.</span></span>  
  
 <span data-ttu-id="6aafc-129">Vous pouvez développer un problème pour afficher des informations supplémentaires, un lien vers des informations détaillées à propos de la résolution du problème et un lien pour afficher les détails du problème.</span><span class="sxs-lookup"><span data-stu-id="6aafc-129">You can expand an issue to display additional information, a link to detailed information about resolving the issue, and a link to show issue details.</span></span> <span data-ttu-id="6aafc-130">Lorsque vous cliquez sur le lien pour obtenir des précisions concernant le problème, une rubrique d'aide s'affiche avec des informations sur le problème et des instructions pour le résoudre.</span><span class="sxs-lookup"><span data-stu-id="6aafc-130">When you click the link to get detailed information for the issue, a Help topic with information about the issue and instructions for addressing the issue is displayed.</span></span> <span data-ttu-id="6aafc-131">Une fois que vous avez corrigé un problème ou géré vos éléments d’action, vous pouvez marquer les problèmes comme terminés en activant la case à cocher **ce problème a été résolu** .</span><span class="sxs-lookup"><span data-stu-id="6aafc-131">After you have fixed an issue, or to manage your action items, you can mark issues as complete by selecting the **This issue has been resolved** check box.</span></span> <span data-ttu-id="6aafc-132">Si vous souhaitez supprimer les problèmes résolus de la liste des problèmes de mise à niveau, cliquez sur **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="6aafc-132">If you want to remove the resolved issues from the list of upgrade issues, click **Refresh**.</span></span> <span data-ttu-id="6aafc-133">Le problème ne s’affiche plus tant que vous n’avez pas exécuté l’Assistant analyse du conseiller de mise à niveau sur le même composant, ou appliqué le filtre **problèmes résolus** à partir de l’option **Filtrer par** .</span><span class="sxs-lookup"><span data-stu-id="6aafc-133">The issue is not displayed again until you either run the Upgrade Advisor Analysis Wizard against the same component or apply the **Resolved Issues** filter from the **Filter By** option.</span></span>  
  
## <a name="report-files"></a><span data-ttu-id="6aafc-134">Fichiers de rapport</span><span class="sxs-lookup"><span data-stu-id="6aafc-134">Report Files</span></span>  
 <span data-ttu-id="6aafc-135">L’Assistant analyse du conseiller de mise à niveau crée des rapports dans le répertoire Mes documents \\ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor\110\Reports et crée un sous-répertoire pour chaque serveur que vous analysez.</span><span class="sxs-lookup"><span data-stu-id="6aafc-135">The Upgrade Advisor Analysis Wizard creates reports in the My Documents\\[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor\110\Reports directory and creates a subdirectory for each server that you analyze.</span></span> <span data-ttu-id="6aafc-136">Les fichiers de rapport sont des fichiers XML qui respectent une convention d'affectation de noms spécifique.</span><span class="sxs-lookup"><span data-stu-id="6aafc-136">The report files are XML files that follow a specific naming convention.</span></span> <span data-ttu-id="6aafc-137">Lorsque vous lancez la visionneuse de rapports du Conseiller de mise à niveau, les fichiers de rapport dans le répertoire par défaut sont affichés.</span><span class="sxs-lookup"><span data-stu-id="6aafc-137">When you launch the Upgrade Advisor Report Viewer, the report files in the default directory are displayed.</span></span> <span data-ttu-id="6aafc-138">Lorsque vous copiez des fichiers de rapport dans ce dossier, ceux-ci doivent respecter la convention d'affectation de noms sinon la visionneuse de rapports ne les affiche pas automatiquement.</span><span class="sxs-lookup"><span data-stu-id="6aafc-138">If you copy report files into this folder, they must adhere to the naming convention or the report viewer will not display them automatically.</span></span>  
  
 <span data-ttu-id="6aafc-139">Si vous souhaitez partager les informations avec d'autres personnes, vous pouvez leur envoyer le rapport XML.</span><span class="sxs-lookup"><span data-stu-id="6aafc-139">If you want to share the information with other people, you can send them the XML report.</span></span> <span data-ttu-id="6aafc-140">Ou, si vous souhaitez utiliser une autre application, vous pouvez exporter le rapport dans un fichier de valeurs séparées par des virgules (CSV) qui vous permettra de créer une feuille de calcul, un fichier texte ou un message électronique.</span><span class="sxs-lookup"><span data-stu-id="6aafc-140">Or, if you want to use another application, you can export the report into a comma-separated value file that you can use to create a spreadsheet, text file, or e-mail message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aafc-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6aafc-141">See Also</span></span>  
 <span data-ttu-id="6aafc-142">[Procédure : afficher un rapport du conseiller de mise à niveau](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md) </span><span class="sxs-lookup"><span data-stu-id="6aafc-142">[How to: View an Upgrade Advisor Report](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md) </span></span>  
 <span data-ttu-id="6aafc-143">[Procédure : exporter des rapports](../../../2014/sql-server/install/how-to-export-reports.md) </span><span class="sxs-lookup"><span data-stu-id="6aafc-143">[How to: Export Reports](../../../2014/sql-server/install/how-to-export-reports.md) </span></span>  
 <span data-ttu-id="6aafc-144">[Comment : filtrer des rapports](../../../2014/sql-server/install/how-to-filter-reports.md) </span><span class="sxs-lookup"><span data-stu-id="6aafc-144">[How to: Filter Reports](../../../2014/sql-server/install/how-to-filter-reports.md) </span></span>  
 <span data-ttu-id="6aafc-145">[Résolution des problèmes de mise à niveau](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="6aafc-145">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="6aafc-146">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="6aafc-146">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
