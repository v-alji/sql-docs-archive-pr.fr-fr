---
title: Contrôle des sauts de page, des en-têtes, des colonnes et des lignes (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b8fa41f-a727-4f23-8efb-fd9bb0d4cd1d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7dae06129ee5dc9962538e8d025dca9966325f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612164"
---
# <a name="controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs"></a><span data-ttu-id="99524-102">Contrôle des sauts de page, des en-têtes, des colonnes et des lignes (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="99524-102">Controlling Page Breaks, Headings, Columns, and Rows (Report Builder and SSRS)</span></span>
  <span data-ttu-id="99524-103">Un saut de page divise un rapport en pages distinctes à des fins d'affichage et d'impression.</span><span class="sxs-lookup"><span data-stu-id="99524-103">A page break divides a report into separate pages for viewing and printing.</span></span> <span data-ttu-id="99524-104">Les sauts de page déterminent la façon dont le contenu est ajusté sur une page de rapport pour un affichage optimal lorsque affichez l'aperçu d'un rapport ou que vous l'exportez dans un format de fichier différent.</span><span class="sxs-lookup"><span data-stu-id="99524-104">Page breaks determine how the content is fitted to a report page for optimal viewing when you preview a report or export it to a different file format.</span></span>  
  
 <span data-ttu-id="99524-105">L'ajout de sauts de pages a également pour effet d'améliorer les performances de traitement des rapports volumineux.</span><span class="sxs-lookup"><span data-stu-id="99524-105">Adding page breaks also improves the performance of large reports when the are processed.</span></span> <span data-ttu-id="99524-106">Une page rendue s'affiche pendant le rendu en arrière-plan des pages restantes.</span><span class="sxs-lookup"><span data-stu-id="99524-106">A rendered page is displayed while the rest of the pages are rendered in the background.</span></span> <span data-ttu-id="99524-107">Vous pouvez ainsi commencer à visualiser les pages initiales du rapport en attendant que d'autres pages soient disponibles.</span><span class="sxs-lookup"><span data-stu-id="99524-107">This allows you to begin viewing the initial pages of the report while waiting for additional pages to become available.</span></span>  
  
 <span data-ttu-id="99524-108">Des sauts de page peuvent être ajoutés à des éléments de rapport tels que tableaux, matrices, listes, graphiques, jauges et autres images.</span><span class="sxs-lookup"><span data-stu-id="99524-108">Page breaks can be added to report items such as a table, matrix, list, chart, gauge, or image.</span></span> <span data-ttu-id="99524-109">Vous pouvez également ajouter des sauts de page à des groupes dans un tableau, une matrice ou une liste.</span><span class="sxs-lookup"><span data-stu-id="99524-109">You can also add page breaks to groups in a table, matrix, or list.</span></span> <span data-ttu-id="99524-110">Les sauts de page peuvent être ajoutés avant, après et entre des groupes.</span><span class="sxs-lookup"><span data-stu-id="99524-110">Page breaks can be added before, after, and between groups.</span></span> <span data-ttu-id="99524-111">Par défaut, les sauts de page entre les groupes ne sont pas ajoutés au rapport.</span><span class="sxs-lookup"><span data-stu-id="99524-111">Page breaks between groups are not added to the report by default.</span></span>  
  
 <span data-ttu-id="99524-112">Pour plus d’informations, consultez [Afficher des en-têtes de ligne et de colonne sur plusieurs pages &#40;Générateur de rapports et SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) et [Laisser les en-têtes visibles lors du défilement d’un rapport &#40;Générateur de rapports et SSRS&#41;](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="99524-112">For more information, see [Display Row and Column Headers on Multiple Pages &#40;Report Builder and SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) and [Keep Headers Visible When Scrolling Through a Report &#40;Report Builder and SSRS&#41;](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="99524-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="99524-113">See Also</span></span>  
 <span data-ttu-id="99524-114">[Répertorie &#40;Générateur de rapports et SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="99524-114">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="99524-115">[Contrôle de l’affichage de la région de données de tableau matriciel sur une page de rapport &#40;Générateur de rapports et SSRS&#41;](controlling-the-tablix-data-region-display-on-a-report-page.md) </span><span class="sxs-lookup"><span data-stu-id="99524-115">[Controlling the Tablix Data Region Display on a Report Page &#40;Report Builder and SSRS&#41;](controlling-the-tablix-data-region-display-on-a-report-page.md) </span></span>  
 <span data-ttu-id="99524-116">[Volet de regroupement &#40;Générateur de rapports&#41;](grouping-pane-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="99524-116">[Grouping Pane &#40;Report Builder&#41;](grouping-pane-report-builder.md) </span></span>  
 [<span data-ttu-id="99524-117">Afficher des en-têtes et des pieds de page de groupe &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="99524-117">Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;</span></span>](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md)  
  
  
