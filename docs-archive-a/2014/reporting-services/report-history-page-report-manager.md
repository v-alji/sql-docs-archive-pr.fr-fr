---
title: Page historique de rapport (Gestionnaire de rapports) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services-native
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 06/13/2017
ms.openlocfilehash: 4070be8c1d6b0633131e96c665d4551c1b676a9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605094"
---
# <a name="report-history-page-report-manager"></a><span data-ttu-id="c800a-102">Page Historique de rapport (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="c800a-102">Report History Page (Report Manager)</span></span>

<span data-ttu-id="c800a-103">La page Historique de rapport vous permet d'afficher des instantanés de rapport qui sont générés et stockés dans le temps.</span><span class="sxs-lookup"><span data-stu-id="c800a-103">Use the Report History page to view report snapshots that are generated and stored over time.</span></span> <span data-ttu-id="c800a-104">Selon les options définies sur le serveur de rapports, l'historique de rapport peut contenir uniquement les instantanés les plus récents.</span><span class="sxs-lookup"><span data-stu-id="c800a-104">Depending on options that are set on the report server, report history may contain only the more recent snapshots.</span></span>  
  

<span data-ttu-id="c800a-105">Un historique de rapport est toujours affiché dans le contexte du rapport dont il est issu.</span><span class="sxs-lookup"><span data-stu-id="c800a-105">Report history is always viewed within the context of the report from which it originates.</span></span> <span data-ttu-id="c800a-106">Vous ne pouvez pas afficher l'historique de tous les rapports sur un serveur de rapports dans un seul emplacement.</span><span class="sxs-lookup"><span data-stu-id="c800a-106">You cannot view the history of all reports on a report server in one place.</span></span>  
  
<span data-ttu-id="c800a-107">Pour générer un historique de rapport, le rapport doit pouvoir s'exécuter sans assistance (c'est-à-dire qu'il doit utiliser les informations d'identification stockées ; les rapports paramétrables doivent contenir des valeurs de paramètres par défaut pour tous les paramètres).</span><span class="sxs-lookup"><span data-stu-id="c800a-107">To generate report history, the report must be able to run unattended (that is, it must use stored credentials; parameterized reports must contain default parameter values for all parameters).</span></span> <span data-ttu-id="c800a-108">Un historique de rapport peut être généré manuellement ou sous forme d'opération planifiée.</span><span class="sxs-lookup"><span data-stu-id="c800a-108">Report history can be generated manually or as a scheduled operation.</span></span> <span data-ttu-id="c800a-109">Les propriétés d'historique du rapport déterminent les modes de création de l'historique de rapport.</span><span class="sxs-lookup"><span data-stu-id="c800a-109">History properties on the report determine the ways in which report history can be created.</span></span>  
  
<span data-ttu-id="c800a-110">Vous pouvez cliquer sur un instantané d'historique de rapport pour l'afficher.</span><span class="sxs-lookup"><span data-stu-id="c800a-110">You can click a report history snapshot to view it.</span></span> <span data-ttu-id="c800a-111">Les instantanés qui apparaissent dans l'historique de rapport ne sont différenciés que par la date et l'heure de leur création.</span><span class="sxs-lookup"><span data-stu-id="c800a-111">Snapshots that appear in report history are distinguished only by the date and time at which they were created.</span></span> <span data-ttu-id="c800a-112">Il n'y a aucun moyen de déterminer si un instantané a été généré par une opération manuelle ou planifiée.</span><span class="sxs-lookup"><span data-stu-id="c800a-112">There is no visual indication to distinguish whether a snapshot was generated in response to a schedule or a manual operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c800a-113">Cette fonctionnalité n'est pas disponible dans toutes les éditions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c800a-113">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c800a-114">Pour obtenir une liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], consultez [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="c800a-114">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="c800a-115">Navigation</span><span class="sxs-lookup"><span data-stu-id="c800a-115">Navigation</span></span>  
 <span data-ttu-id="c800a-116">Utilisez la procédure suivante pour naviguer jusqu'à cet emplacement dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c800a-116">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-report-history-page"></a><span data-ttu-id="c800a-117">Pour ouvrir la page Historique de rapport</span><span class="sxs-lookup"><span data-stu-id="c800a-117">To open the Report History page</span></span>  
  
1.  <span data-ttu-id="c800a-118">Ouvrez le Gestionnaire de rapports et recherchez le rapport pour lequel vous souhaitez consulter des instantanés de rapport.</span><span class="sxs-lookup"><span data-stu-id="c800a-118">Open Report Manager, and locate the report for which you want to view report snapshots.</span></span>  
  
2.  <span data-ttu-id="c800a-119">Pointez sur le rapport et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="c800a-119">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="c800a-120">Dans le menu déroulant, cliquez sur **Afficher l’historique du rapport**.</span><span class="sxs-lookup"><span data-stu-id="c800a-120">In the drop-down menu, click **View Report History**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c800a-121">Options</span><span class="sxs-lookup"><span data-stu-id="c800a-121">Options</span></span>  
 <span data-ttu-id="c800a-122">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="c800a-122">**Delete**</span></span>  
 <span data-ttu-id="c800a-123">Cliquez pour supprimer un ou plusieurs instantanés.</span><span class="sxs-lookup"><span data-stu-id="c800a-123">Click to delete one or more snapshots.</span></span> <span data-ttu-id="c800a-124">Avant de cliquer sur **Supprimer**, activez la case à cocher en regard de l'instantané à supprimer.</span><span class="sxs-lookup"><span data-stu-id="c800a-124">Before clicking **Delete**, select the check box next to the snapshot that you want to delete.</span></span>  
  
 <span data-ttu-id="c800a-125">**Nouvel instantané**</span><span class="sxs-lookup"><span data-stu-id="c800a-125">**New Snapshot**</span></span>  
 <span data-ttu-id="c800a-126">Cliquez pour ajouter un instantané à un historique de rapport.</span><span class="sxs-lookup"><span data-stu-id="c800a-126">Click to add a snapshot to report history.</span></span> <span data-ttu-id="c800a-127">Ce bouton est disponible lorsque vous choisissez l'option **Autoriser la création manuelle de l'historique** dans la page de propriétés de l'historique du rapport.</span><span class="sxs-lookup"><span data-stu-id="c800a-127">This button is available when you choose the option **Allow history to be created manually** on the History properties page of the report.</span></span>  
  
 <span data-ttu-id="c800a-128">**Dernière exécution**</span><span class="sxs-lookup"><span data-stu-id="c800a-128">**Last Run**</span></span>  
 <span data-ttu-id="c800a-129">Affiche la date et l'heure de création de l'instantané.</span><span class="sxs-lookup"><span data-stu-id="c800a-129">Displays the date and time at which the snapshot was created.</span></span> <span data-ttu-id="c800a-130">Cliquez sur une description pour afficher un instantané spécifique.</span><span class="sxs-lookup"><span data-stu-id="c800a-130">Click a description to view a particular snapshot.</span></span>  
  
 <span data-ttu-id="c800a-131">**Taille**</span><span class="sxs-lookup"><span data-stu-id="c800a-131">**Size**</span></span>  
 <span data-ttu-id="c800a-132">Affiche la taille de la définition de rapport et des données contenues dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="c800a-132">Displays the size of the report definition plus the data in the report.</span></span> <span data-ttu-id="c800a-133">Cette valeur indique la quantité d'espace utilisée par la définition de rapport et les données dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="c800a-133">This value indicates how much space in the report server database is used by the report definition and data.</span></span> <span data-ttu-id="c800a-134">La taille du rapport rendu, qui comprend la mise en forme, est plus volumineuse.</span><span class="sxs-lookup"><span data-stu-id="c800a-134">The size of the rendered report, which includes formatting, is actually larger.</span></span> <span data-ttu-id="c800a-135">La taille totale, indiquée entre parenthèses, correspond à la taille de tous les instantanés de l'historique de rapport du rapport actif.</span><span class="sxs-lookup"><span data-stu-id="c800a-135">The total size, indicated in parentheses, sums the sizes of all snapshots in the report history for the current report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c800a-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c800a-136">See Also</span></span>  
 <span data-ttu-id="c800a-137">[Afficher ou supprimer l’historique de rapport &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/view-or-delete-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c800a-137">[View or Delete Report History &#40;Report Manager&#41;](../../2014/reporting-services/view-or-delete-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="c800a-138">[Ajoutez un instantané à l’historique de rapport &#40;Gestionnaire de rapports&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c800a-138">[Add a Snapshot to Report History &#40;Report Manager&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="c800a-139">[Page Propriétés générales, rapports &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c800a-139">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="c800a-140">[Aide (F1) Gestionnaire de rapports](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="c800a-140">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 [<span data-ttu-id="c800a-141">Page de propriétés options d’instantané &#40;Gestionnaire de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="c800a-141">Snapshot Options Properties Page &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/snapshot-options-properties-page-report-manager.md)