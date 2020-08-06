---
title: 'Procédure : afficher un rapport du conseiller de mise à niveau | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- displaying reports
- viewing reports
- Upgrade Advisor [SQL Server], reports
- SQL Server Upgrade Advisor, reports
- reports [Upgrade Advisor], viewing
ms.assetid: d13b38af-0ac3-4030-83cd-e7d7825dd09f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9e6df35b869186a601458889c348153093ccbce4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613788"
---
# <a name="how-to-view-an-upgrade-advisor-report"></a><span data-ttu-id="d88b2-102">Procédure : afficher un rapport du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="d88b2-102">How to: View an Upgrade Advisor Report</span></span>
  <span data-ttu-id="d88b2-103">Le Conseiller de mise à niveau crée des rapports pour chaque composant que vous sélectionnez pour analyse.</span><span class="sxs-lookup"><span data-stu-id="d88b2-103">Upgrade Advisor creates reports for each component that you select to analyze.</span></span> <span data-ttu-id="d88b2-104">Cette rubrique décrit comment afficher un rapport du Conseiller de mise à niveau à partir de la page de démarrage du Conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="d88b2-104">This topic describes how to view an Upgrade Advisor report from the Upgrade Advisor start page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d88b2-105">La visionneuse de rapports charge les fichiers en fonction des noms de fichiers standard.</span><span class="sxs-lookup"><span data-stu-id="d88b2-105">The report viewer loads files based on standard file names.</span></span> <span data-ttu-id="d88b2-106">Si les fichiers ont été renommés, la visionneuse de rapports ne les charge pas.</span><span class="sxs-lookup"><span data-stu-id="d88b2-106">If the files have been renamed, the report viewer will not load them.</span></span>  
  
### <a name="to-view-a-report"></a><span data-ttu-id="d88b2-107">Pour afficher un rapport</span><span class="sxs-lookup"><span data-stu-id="d88b2-107">To view a report</span></span>  
  
1.  <span data-ttu-id="d88b2-108">Cliquez sur **Démarrer**, sur **tous les programmes**, sur **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]** , puis sur conseiller de \*\* [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mise à niveau\*\*.</span><span class="sxs-lookup"><span data-stu-id="d88b2-108">Click **Start**, click **All Programs**, click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**, and then click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor**.</span></span>  
  
2.  <span data-ttu-id="d88b2-109">Sur la page de démarrage du conseiller de mise à niveau, cliquez sur **lancer le conseiller de mise à niveau**.</span><span class="sxs-lookup"><span data-stu-id="d88b2-109">On the Upgrade Advisor start page, click **Launch Upgrade Advisor Report Viewer**.</span></span>  
  
3.  <span data-ttu-id="d88b2-110">Pour sélectionner un rapport dans l'emplacement par défaut sur votre ordinateur :</span><span class="sxs-lookup"><span data-stu-id="d88b2-110">To select a report in the default location on your computer:</span></span>  
  
    1.  <span data-ttu-id="d88b2-111">Dans la liste **serveur** , sélectionnez un serveur.</span><span class="sxs-lookup"><span data-stu-id="d88b2-111">In the **Server** list, select a server.</span></span>  
  
    2.  <span data-ttu-id="d88b2-112">Dans la liste **instance ou composant** , sélectionnez une combinaison composant ou composant/instance.</span><span class="sxs-lookup"><span data-stu-id="d88b2-112">In the **Instance or component** list, select a component or component/instance combination.</span></span>  
  
     <span data-ttu-id="d88b2-113">Pour sélectionner un rapport dans un autre emplacement :</span><span class="sxs-lookup"><span data-stu-id="d88b2-113">To select a report at another location:</span></span>  
  
    1.  <span data-ttu-id="d88b2-114">Cliquez sur le lien **ouvrir le rapport** .</span><span class="sxs-lookup"><span data-stu-id="d88b2-114">Click the **Open Report** link.</span></span>  
  
    2.  <span data-ttu-id="d88b2-115">Naviguez jusqu'à l'emplacement du rapport, puis double-cliquez sur le fichier XML.</span><span class="sxs-lookup"><span data-stu-id="d88b2-115">Browse to the report location and then double-click the XML file.</span></span>  
  
     <span data-ttu-id="d88b2-116">Le Conseiller de mise à niveau stocke jusqu'à cinq rapports d'une analyse précédente comme historique.</span><span class="sxs-lookup"><span data-stu-id="d88b2-116">Upgrade Advisor stores up to five reports from previous analysis as history.</span></span> <span data-ttu-id="d88b2-117">Pour afficher ces rapports, cliquez sur la zone de liste déroulante **rapport** , puis sélectionnez un rapport.</span><span class="sxs-lookup"><span data-stu-id="d88b2-117">To view these reports, click the **Report** drop-down list box, and select a report.</span></span> <span data-ttu-id="d88b2-118">Les rapports sont répertoriés selon le horodateur à partir du moment où ils ont été générés.</span><span class="sxs-lookup"><span data-stu-id="d88b2-118">The reports are listed by the timestamp from when they were generated.</span></span>  
  
     <span data-ttu-id="d88b2-119">Le rapport contient les détails suivants pour tous les problèmes détectés :</span><span class="sxs-lookup"><span data-stu-id="d88b2-119">The report contains the following details for all detected issues:</span></span>  
  
    -   <span data-ttu-id="d88b2-120">**Importance**, qui indique à quel point il est important de résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="d88b2-120">**Importance**, which indicates how important it is to fix the issue.</span></span>  
  
    -   <span data-ttu-id="d88b2-121">**Quand corriger**, ce qui indique si vous devez corriger le problème avant ou après la mise à niveau vers [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , avant ou après la migration de l’application ou des données, ou à tout moment.</span><span class="sxs-lookup"><span data-stu-id="d88b2-121">**When to fix**, which indicates if you should (or must) fix the issue before or after upgrading to [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], before or after migrating the application or data, or anytime.</span></span>  
  
    -   <span data-ttu-id="d88b2-122">Brève description du problème.</span><span class="sxs-lookup"><span data-stu-id="d88b2-122">A brief description of the issue.</span></span>  
  
4.  <span data-ttu-id="d88b2-123">Si le rapport contient plus de 20 éléments, cliquez sur la flèche Suivant verte en haut ou en bas du rapport pour afficher l'ensemble d'éléments suivant.</span><span class="sxs-lookup"><span data-stu-id="d88b2-123">If the report contains more than 20 items, click the green forward arrow at the top or bottom of the report to view the next set of items.</span></span> <span data-ttu-id="d88b2-124">Cliquez sur le bouton Précédent vert pour afficher les 20 éléments précédents.</span><span class="sxs-lookup"><span data-stu-id="d88b2-124">Click the green back button to view the previous 20 items.</span></span>  
  
5.  <span data-ttu-id="d88b2-125">Pour trier les données du rapport, cliquez sur l'en-tête d'une colonne.</span><span class="sxs-lookup"><span data-stu-id="d88b2-125">To sort the report, click a column heading.</span></span>  
  
6.  <span data-ttu-id="d88b2-126">Pour afficher des détails pour un élément spécifique, cliquez sur l'élément.</span><span class="sxs-lookup"><span data-stu-id="d88b2-126">To view details for a specific item, click the item.</span></span> <span data-ttu-id="d88b2-127">Une description du problème apparaît, ainsi que des options supplémentaires :</span><span class="sxs-lookup"><span data-stu-id="d88b2-127">A description of the issue appears, along with additional options:</span></span>  
  
    -   <span data-ttu-id="d88b2-128">Pour afficher les objets où ce problème a été trouvé, cliquez sur **afficher les objets affectés**.</span><span class="sxs-lookup"><span data-stu-id="d88b2-128">To view the objects where this issue was found, click **Show affected objects**.</span></span>  
  
    -   <span data-ttu-id="d88b2-129">Pour afficher l’aide pour le problème, cliquez sur en **savoir plus sur ce problème et sur la manière de le résoudre**.</span><span class="sxs-lookup"><span data-stu-id="d88b2-129">To view help for the issue, click **Tell me more about this issue and how to resolve it**.</span></span>  
  
    -   <span data-ttu-id="d88b2-130">Pour marquer le problème comme résolu, ce qui masque le problème lorsque vous affichez de nouveau le rapport, sélectionnez **ce problème a été résolu**.</span><span class="sxs-lookup"><span data-stu-id="d88b2-130">To mark the issue as resolved, which hides the issue when you view the report again, select **This issue has been resolved**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d88b2-131">Le rapport peut contenir un élément pour les problèmes indétectables.</span><span class="sxs-lookup"><span data-stu-id="d88b2-131">The report may contain an item for undetectable issues.</span></span> <span data-ttu-id="d88b2-132">Ce sont des problèmes qui ne peuvent pas être détectés ou qui généreraient trop de résultats faux positifs.</span><span class="sxs-lookup"><span data-stu-id="d88b2-132">These are issues that cannot be detected or that would generate too many false-positive results.</span></span> <span data-ttu-id="d88b2-133">Cliquez sur le lien en **savoir plus sur ce problème et sur la manière de le résoudre** pour afficher une liste des problèmes non détectables pour le composant.</span><span class="sxs-lookup"><span data-stu-id="d88b2-133">Click the **Tell me more about this issue and how to resolve it** link to see a list of undetectable issues for the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d88b2-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d88b2-134">See Also</span></span>  
 <span data-ttu-id="d88b2-135">[Procédure : exporter des rapports](../../../2014/sql-server/install/how-to-export-reports.md) </span><span class="sxs-lookup"><span data-stu-id="d88b2-135">[How to: Export Reports](../../../2014/sql-server/install/how-to-export-reports.md) </span></span>  
 <span data-ttu-id="d88b2-136">[Procédure : exécuter l’Assistant analyse du conseiller de mise à niveau](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="d88b2-136">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="d88b2-137">[Résolution des problèmes de mise à niveau](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="d88b2-137">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 <span data-ttu-id="d88b2-138">[Rubriques de procédures relatives au conseiller de mise à niveau](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="d88b2-138">[Upgrade Advisor How-to Topics](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md) </span></span>  
 [<span data-ttu-id="d88b2-139">Utilisation du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="d88b2-139">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
