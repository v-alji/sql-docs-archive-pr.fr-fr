---
title: Tri interactif, Explorateurs de documents et liens (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: cc6ef408-4a76-408a-9d3f-033481fe21cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 35d88e89ed14a205153374d44562e6d3fda92e02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707107"
---
# <a name="interactive-sort-document-maps-and-links-report-builder-and-ssrs"></a><span data-ttu-id="cb74e-102">Tri interactif, Explorateurs de documents et liens (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="cb74e-102">Interactive Sort, Document Maps, and Links (Report Builder and SSRS)</span></span>
  <span data-ttu-id="cb74e-103">Dans les environnements Web, vous pouvez ajouter un certain nombre de fonctionnalités qui permettent à vos utilisateurs d'intervenir sur les rapports.</span><span class="sxs-lookup"><span data-stu-id="cb74e-103">In Web-based environments, you can add a number of features that let your users interact with reports.</span></span> <span data-ttu-id="cb74e-104">Vos utilisateurs peuvent modifier l'ordre de tri des valeurs dans votre rapport, afficher ou masquer des éléments du rapport ou cliquer sur les liens pointant vers d'autres rapports ou des pages Web.</span><span class="sxs-lookup"><span data-stu-id="cb74e-104">Your users can change the sort order of values in your report, show or hide items in the report, or click links that go to other reports or Web pages.</span></span> <span data-ttu-id="cb74e-105">Vous pouvez également ajouter une table des matières ou un Explorateur de documents.</span><span class="sxs-lookup"><span data-stu-id="cb74e-105">You can also add a table of contents or document map.</span></span> <span data-ttu-id="cb74e-106">Vos utilisateurs de rapport peuvent cliquer sur des éléments de la table des matières ou de l'Explorateur de documents pour accéder instantanément aux sections voulues du rapport.</span><span class="sxs-lookup"><span data-stu-id="cb74e-106">Your report users can click items in the table of contents or document map to jump to areas within a report.</span></span>  
  
 <span data-ttu-id="cb74e-107">Le Générateur de rapports et le Concepteur de rapports prend en charge trois types de liens avec les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="cb74e-107">Report Builder and Report Designer support three types of links with the following actions:</span></span>  
  
-   <span data-ttu-id="cb74e-108">**Liens de signet** Accès à d'autres zones dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="cb74e-108">**Bookmark links** Jump to other areas within the report.</span></span>  
  
-   <span data-ttu-id="cb74e-109">**Liens hypertexte** Accès à des URL qui spécifient l'adresse de pages Web ou de rapports sur un serveur de rapports en utilisant l'accès URL.</span><span class="sxs-lookup"><span data-stu-id="cb74e-109">**Hyperlinks** Jump to URLs that specify the address of Web pages or reports on a report server by using URL access.</span></span>  
  
-   <span data-ttu-id="cb74e-110">**Liens de rapport d'extraction** Accès à d'autres rapports sur le même serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="cb74e-110">**Drillthrough report links** Jump to other reports on the same report server.</span></span> <span data-ttu-id="cb74e-111">Pour plus d’informations, consultez [Rapports d’extraction &#40;Générateur de rapports et SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cb74e-111">For more information, see [Drillthrough Reports &#40;Report Builder and SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cb74e-112">Les liens qui sont associés à des champs de dataset peuvent être vulnérables à des opérations de falsification à des fins malveillantes.</span><span class="sxs-lookup"><span data-stu-id="cb74e-112">Links that are bound to dataset fields can be vulnerable to tampering for malicious purposes.</span></span> <span data-ttu-id="cb74e-113">Pour plus d’informations, consultez [Sécuriser des rapports et des ressources](../security/secure-reports-and-resources.md) dans la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][documentation en ligne](https://go.microsoft.com/fwlink/?LinkId=154888) sur msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="cb74e-113">For more information, see [Secure Reports and Resources](../security/secure-reports-and-resources.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][Books Online](https://go.microsoft.com/fwlink/?LinkId=154888) on msdn.microsoft.com.</span></span>  
  
 <span data-ttu-id="cb74e-114">Vous pouvez aussi permettre aux utilisateurs de contrôler le contenu et l'affichage du rapport en concevant des expressions qui incluent des références de paramètre pour le tri, le filtrage et la visibilité.</span><span class="sxs-lookup"><span data-stu-id="cb74e-114">You can also let your users control report display and content by designing expressions that include parameter references for sort, filter, and visibility.</span></span> <span data-ttu-id="cb74e-115">Pour plus d’informations, consultez [Paramètres des rapports &#40;Générateur de rapports et Concepteur de rapports&#41;](report-parameters-report-builder-and-report-designer.md), [Filtrer, regrouper et trier des données &#40;Générateur de rapports et SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) et [Ajouter des filtres de datasets, des filtres de régions de données et des filtres de groupes &#40;Générateur de rapports et SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md).</span><span class="sxs-lookup"><span data-stu-id="cb74e-115">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md), [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md), and [Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="cb74e-116">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="cb74e-116">In This Section</span></span>  
 [<span data-ttu-id="cb74e-117">Tri interactif &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cb74e-117">Interactive Sort &#40;Report Builder and SSRS&#41;</span></span>](interactive-sort-report-builder-and-ssrs.md)  
 <span data-ttu-id="cb74e-118">Explique comment ajouter des boutons de tri interactifs à des en-têtes de colonne.</span><span class="sxs-lookup"><span data-stu-id="cb74e-118">Explains how to add interactive sort buttons to column headers.</span></span>  
  
 [<span data-ttu-id="cb74e-119">Créer un explorateur de documents &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cb74e-119">Create a Document Map &#40;Report Builder and SSRS&#41;</span></span>](create-a-document-map-report-builder-and-ssrs.md)  
 <span data-ttu-id="cb74e-120">Explique comment ajouter une table des matières pour prendre en charge la navigation dans un rapport volumineux.</span><span class="sxs-lookup"><span data-stu-id="cb74e-120">Explains how to add a table of contents to support navigation in a large report.</span></span>  
  
 [<span data-ttu-id="cb74e-121">Ajouter un signet à un rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cb74e-121">Add a Bookmark to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-bookmark-to-a-report-report-builder-and-ssrs.md)  
 <span data-ttu-id="cb74e-122">Explique comment ajouter des signets pour créer des liens dans un rapport.</span><span class="sxs-lookup"><span data-stu-id="cb74e-122">Explains how to add bookmarks to create links within a report.</span></span>  
  
 [<span data-ttu-id="cb74e-123">Ajouter un lien hypertexte à une URL &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cb74e-123">Add a Hyperlink to a URL &#40;Report Builder and SSRS&#41;</span></span>](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md)  
 <span data-ttu-id="cb74e-124">Explique comment ajouter un lien de votre rapport à une URL</span><span class="sxs-lookup"><span data-stu-id="cb74e-124">Explains how to add a link from your report to a URL</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb74e-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cb74e-125">See Also</span></span>  
 [<span data-ttu-id="cb74e-126">Extraction, exploration, sous-rapports et régions de données imbriquées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cb74e-126">Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;</span></span>](drillthrough-drilldown-subreports-and-nested-data-regions.md)  
  
  
