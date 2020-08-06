---
title: Configurer les propriétés d’exécution d’un rapport (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report execution properties [Reporting Services]
- reports [Reporting Services], properties
- reports [Reporting Services], execution options
ms.assetid: 73cc8dcc-ef80-40d7-9739-d33bba0eb28a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 51cd7b5db225b39f5a061ed750b2ef5cdd265b9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615009"
---
# <a name="configure-execution-properties-for-a-report--report-manager"></a><span data-ttu-id="b89d9-102">Configurer les propriétés d’exécution d’un rapport (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="b89d9-102">Configure Execution Properties for a Report  (Report Manager)</span></span>
  <span data-ttu-id="b89d9-103">Vous pouvez définir les options de traitement d'un rapport afin de spécifier le moment où les données d'un rapport sont récupérées.</span><span class="sxs-lookup"><span data-stu-id="b89d9-103">You can set report processing options to specify when data is retrieved for a report.</span></span> <span data-ttu-id="b89d9-104">Il est utile de planifier le traitement des données d'un rapport si la source de données externe est actualisée à des heures spécifiques (par exemple un entrepôt de données actualisé chaque jour ou chaque semaine) et si vous souhaitez éviter le temps de traitement lié à la récupération des mêmes données chaque fois qu'un rapport est demandé.</span><span class="sxs-lookup"><span data-stu-id="b89d9-104">It is useful to schedule data processing for a report if the external data source is refreshed at specific times (for example, a data warehouse that is refreshed daily or weekly) and you want to avoid the overhead of retrieving the same data each time a report is requested.</span></span> <span data-ttu-id="b89d9-105">La planification du traitement des données est également utile lorsque vous souhaitez contrôler la charge de traitement du serveur de base de données externe, ou lorsque vous souhaitez fournir des résultats cohérents pour plusieurs utilisateurs qui doivent travailler avec des jeux de données identiques.</span><span class="sxs-lookup"><span data-stu-id="b89d9-105">Scheduling data processing is also useful if you want to control the processing load on the external database server or when you want to provide consistent results for multiple users who must work with identical sets of data.</span></span> <span data-ttu-id="b89d9-106">Avec des données volatiles, un rapport à la demande peut produire des résultats différents en l'espace d'une minute.</span><span class="sxs-lookup"><span data-stu-id="b89d9-106">With volatile data, an on-demand report can produce different results from one minute to the next.</span></span> <span data-ttu-id="b89d9-107">En revanche, un instantané de rapport vous permet d'effectuer des comparaisons valides par rapport à d'autres rapports ou peut servir d'outil d'analyse contenant des données toutes datées d'un même point dans le temps.</span><span class="sxs-lookup"><span data-stu-id="b89d9-107">A report snapshot, by contrast, allows you to make valid comparisons against other reports or analytical tools that contain data from the same point in time.</span></span>  
  
 <span data-ttu-id="b89d9-108">Un instantané de rapport est un rapport qui contient des instructions de mise en page et des résultats de requêtes récupérés à un moment précis.</span><span class="sxs-lookup"><span data-stu-id="b89d9-108">A report snapshot is a report that contains layout instructions and query results that were retrieved at a specific point in time.</span></span> <span data-ttu-id="b89d9-109">Contrairement aux rapports à la demande, qui récupèrent les résultats des requêtes récentes lorsque vous les sélectionnez, les instantanés de rapport sont traités par planification, puis enregistrés sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b89d9-109">Unlike on-demand reports, which get up-to-date query results when you select the report, report snapshots are processed on a schedule and then saved to a report server.</span></span> <span data-ttu-id="b89d9-110">Lorsque vous sélectionnez un instantané de rapport pour le visualiser, le serveur de rapports récupère le rapport stocké dans la base de données du serveur de rapports, puis affiche les données et la mise en page telles qu'elles étaient lors de la création de l'instantané.</span><span class="sxs-lookup"><span data-stu-id="b89d9-110">When you select a report snapshot for viewing, the report server retrieves the stored report from the report server database and shows the data and layout that were current for the report at the time the snapshot was created.</span></span>  
  
 <span data-ttu-id="b89d9-111">Les instantanés de rapport ne sont pas enregistrés dans un format de rendu particulier.</span><span class="sxs-lookup"><span data-stu-id="b89d9-111">Report snapshots are not saved in a particular rendering format.</span></span> <span data-ttu-id="b89d9-112">Ils sont générés dans un format d'affichage final (par exemple, au format HTML) uniquement à la demande d'un utilisateur ou d'une application.</span><span class="sxs-lookup"><span data-stu-id="b89d9-112">Instead, report snapshots are rendered in a final viewing format (such as HTML) only when a user or an application requests it.</span></span> <span data-ttu-id="b89d9-113">Le rendu différé permet de disposer d'un instantané portable.</span><span class="sxs-lookup"><span data-stu-id="b89d9-113">Deferred rendering makes a snapshot portable.</span></span> <span data-ttu-id="b89d9-114">Le rendu du rapport peut être effectué dans le format approprié pour le périphérique ou le navigateur Web à l'origine de la demande.</span><span class="sxs-lookup"><span data-stu-id="b89d9-114">The report can be rendered in the correct format for the requesting device or Web browser.</span></span>  
  
### <a name="to-configure-report-processing-options"></a><span data-ttu-id="b89d9-115">Pour configurer les options de traitement d'un rapport</span><span class="sxs-lookup"><span data-stu-id="b89d9-115">To configure report processing options</span></span>  
  
1.  <span data-ttu-id="b89d9-116">Démarrez le [Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="b89d9-116">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="b89d9-117">Accédez au rapport dont vous souhaitez définir les options de traitement et ouvrez-le.</span><span class="sxs-lookup"><span data-stu-id="b89d9-117">Navigate to and open the report for which you want to set processing options.</span></span>  
  
 <span data-ttu-id="b89d9-118">Pointez sur le rapport et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="b89d9-118">Hover over the report, and click the drop-down arrow.</span></span>  
  
1.  <span data-ttu-id="b89d9-119">Dans le menu déroulant, cliquez sur **Gérer** , puis sélectionnez l’onglet **Options de traitement** .</span><span class="sxs-lookup"><span data-stu-id="b89d9-119">In the drop-down menu, click **Manage** and then select the **Processing Options** tab.</span></span>  
  
2.  <span data-ttu-id="b89d9-120">Cliquez sur **Effectuer le rendu de ce rapport à partir d’un instantané d’exécution, puis sélectionnez l’une des options suivantes :**</span><span class="sxs-lookup"><span data-stu-id="b89d9-120">Click **Render this report from an execution snapshot, and then select one of the following options:**</span></span>  
  
    -   <span data-ttu-id="b89d9-121">Si vous voulez créer un instantané, sélectionnez l’option **Utiliser la planification suivante pour créer des instantanés d’exécution du rapport**, puis définissez une planification spécifique aux rapports ou sélectionnez-en une dans la liste **Planification partagée** .</span><span class="sxs-lookup"><span data-stu-id="b89d9-121">If you want to create a snapshot, select **Use the following schedule to create report execution snapshots**, and then either define a report-specific schedule or select from the **Shared schedule** list.</span></span>  
  
    -   <span data-ttu-id="b89d9-122">Si vous voulez créer immédiatement un instantané, sélectionnez l’option **Créer un instantané du rapport lorsque vous cliquez sur le bouton Appliquer de cette page**.</span><span class="sxs-lookup"><span data-stu-id="b89d9-122">If you want to create a snapshot immediately, select **Create a report snapshot when you click the Apply button on this page**.</span></span>  
  
3.  <span data-ttu-id="b89d9-123">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="b89d9-123">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b89d9-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b89d9-124">See Also</span></span>  
 <span data-ttu-id="b89d9-125">[Définir les propriétés de traitement d’un rapport](../report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b89d9-125">[Set Report Processing Properties](../report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="b89d9-126">[Ouvrir et fermer un rapport &#40;Gestionnaire de rapports&#41;](../reports/open-and-close-a-report-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="b89d9-126">[Open and Close a Report &#40;Report Manager&#41;](../reports/open-and-close-a-report-report-manager.md) </span></span>  
 <span data-ttu-id="b89d9-127">[Page Contenu &#40;Gestionnaire de rapports&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="b89d9-127">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="b89d9-128">[Gestion du contenu du serveur de rapports &#40;SSRS en mode natif&#41;](../report-server/report-server-content-management-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="b89d9-128">[Report Server Content Management &#40;SSRS Native Mode&#41;](../report-server/report-server-content-management-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="b89d9-129">Page de propriétés Options de traitement &#40;Gestionnaire de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="b89d9-129">Processing Options Properties Page &#40;Report Manager&#41;</span></span>](../processing-options-properties-page-report-manager.md)  
  
  
