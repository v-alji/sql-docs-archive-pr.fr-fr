---
title: Modifier l’ordre d’un paramètre de rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: abd61e19-dba3-423c-a26c-e8bc43197d3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ad9dd25be7a87fee089a48849fcc716e682e4c64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706199"
---
# <a name="change-the-order-of-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="9b4d9-102">Modifier l'ordre d'un paramètre de rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="9b4d9-102">Change the Order of a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="9b4d9-103">Modifiez l'ordre des paramètres de rapport lorsqu'un paramètre dépendant figure dans la liste avant le paramètre dont il dépend.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-103">Change the order of report parameters when you have a dependent parameter that is listed before the parameter it is dependent on.</span></span> <span data-ttu-id="9b4d9-104">L'ordre des paramètres est important lorsque vous avez des paramètres en cascade ou lorsque vous souhaitez montrer aux utilisateurs la valeur par défaut d'un paramètre avant qu'ils ne choisissent des valeurs pour d'autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-104">Parameter order is important when you have cascading parameters, or when you want to show users the default value for one parameter before they choose values for other parameters.</span></span> <span data-ttu-id="9b4d9-105">Un paramètre de rapport dépendant contient une référence, dans sa requête de valeurs par défaut ou de valeurs valides, à un paramètre de requête qui pointe vers un autre paramètre du rapport situé plus loin dans la liste des paramètres du volet Données du rapport.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-105">A dependent report parameter contains a reference, in either its default values query or valid values query, to a query parameter that points to a report parameter that is after it in the parameter list in the Report Data pane.</span></span>  
  
 <span data-ttu-id="9b4d9-106">L'ordre d'affichage des paramètres dans la barre d'outils de la visionneuse de rapports dépend de l'ordre des paramètres dans le volet Données du rapport.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-106">The order that you see parameters display on the report viewer toolbar is determined by the order of the parameters in the Report Data pane.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-order-of-report-parameters"></a><span data-ttu-id="9b4d9-107">Pour modifier l'ordre des paramètres d'un rapport</span><span class="sxs-lookup"><span data-stu-id="9b4d9-107">To change the order of report parameters</span></span>  
  
1.  <span data-ttu-id="9b4d9-108">Dans le volet Données du rapport, développez le nœud Paramètres.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-108">In the Report Data pane, expand the Parameters node.</span></span>  
  
2.  <span data-ttu-id="9b4d9-109">Cliquez sur un paramètre et utilisez les flèches de direction Haut et Bas de la barre d'outils du volet des données de rapportpour faire monter ou descendre le paramètre dans la liste.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-109">Click a parameter and use the up and down arrow buttons on the Report Data pane toolbar to move the parameter higher or lower in the list.</span></span> <span data-ttu-id="9b4d9-110">L'illustration suivante montre le volet des données de rapport du Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="9b4d9-110">The following image shows the Report Data pane in Report Builder.</span></span>  
  
     <span data-ttu-id="9b4d9-111">![Volet des données de rapport](../media/reportdatapane.png "Volet des données de rapport")</span><span class="sxs-lookup"><span data-stu-id="9b4d9-111">![Report Data Pane](../media/reportdatapane.png "Report Data Pane")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b4d9-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b4d9-112">See Also</span></span>  
 <span data-ttu-id="9b4d9-113">[Paramètres de rapport &#40;Générateur de rapports et de Concepteur de rapports&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="9b4d9-113">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="9b4d9-114">[Aide Générateur de rapports pour les boîtes de dialogue, les volets et les assistants](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="9b4d9-114">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="9b4d9-115">[Ajouter des paramètres en cascade à un rapport &#40;Générateur de rapports et SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9b4d9-115">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="9b4d9-116">[Didacticiel : ajouter un paramètre à votre rapport &#40;Générateur de rapports&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="9b4d9-116">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="9b4d9-117">[Ajouter des filtres de datasets, des filtres de régions de données et des filtres de groupe &#40;Générateur de rapports et SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="9b4d9-117">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 [<span data-ttu-id="9b4d9-118">Références à la collection Parameters &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9b4d9-118">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-parameters-collection-references-report-builder.md)  
  
  
