---
title: Ajouter ou supprimer un en-tête ou un pied de page (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 72988623-fee8-4a05-9f72-8fcb8e668576
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b29db3f72323c460360c872a0f60d13a808e3e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703868"
---
# <a name="add-or-remove-a-page-header-or-footer-report-builder-and-ssrs"></a><span data-ttu-id="45e4b-102">Ajouter ou supprimer un en-tête ou un pied de page (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="45e4b-102">Add or Remove a Page Header or Footer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="45e4b-103">Vous pouvez ajouter du texte statique, des images, des lignes, des rectangles et des bordures aux en-têtes ou aux pieds de page.</span><span class="sxs-lookup"><span data-stu-id="45e4b-103">You can add static text, images, lines, rectangles, and borders to page headers or footers.</span></span> <span data-ttu-id="45e4b-104">Vous pouvez placer des expressions et des images liées aux données dans une zone de texte si vous souhaitez qu'un en-tête ou pied de page contienne des données variables ou calculées.</span><span class="sxs-lookup"><span data-stu-id="45e4b-104">You can place expressions and data-bound images in a textbox if you want variable or computed data in a header or footer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45e4b-105">Chaque extension de rendu traite les en-têtes et les pieds de page différemment.</span><span class="sxs-lookup"><span data-stu-id="45e4b-105">Each rendering extension processes page headers and footers differently.</span></span> <span data-ttu-id="45e4b-106">Pour plus d’informations, consultez [En-têtes et pieds de page &#40;Générateur de rapports et SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) et [Pagination dans Reporting Services &#40;Générateur de rapports et SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="45e4b-106">For more information, see [Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) and [Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-header-or-footer"></a><span data-ttu-id="45e4b-107">Pour ajouter un en-tête ou pied de page</span><span class="sxs-lookup"><span data-stu-id="45e4b-107">To add a page header or footer</span></span>  
  
1.  <span data-ttu-id="45e4b-108">Ouvrez un rapport.</span><span class="sxs-lookup"><span data-stu-id="45e4b-108">Open a report.</span></span>  
  
2.  <span data-ttu-id="45e4b-109">Dans l’aire de conception, cliquez avec le bouton droit sur le rapport, pointez sur **Insérer**, puis cliquez sur **En-tête** ou sur **Pied de page**.</span><span class="sxs-lookup"><span data-stu-id="45e4b-109">On the design surface, right-click the report, point to **Insert**, and then click **Header** or **Footer**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45e4b-110">Les options **En-tête** et **Pied de page** s’affichent uniquement si aucun en-tête ou pied de page ne fait encore partie du rapport.</span><span class="sxs-lookup"><span data-stu-id="45e4b-110">The **Header** and **Footer** options appear only when a header or footer is not already part of the report.</span></span>  
  
### <a name="to-configure-a-page-header-or-footer"></a><span data-ttu-id="45e4b-111">Pour configurer un en-tête ou un pied de page</span><span class="sxs-lookup"><span data-stu-id="45e4b-111">To configure a page header or footer</span></span>  
  
1.  <span data-ttu-id="45e4b-112">Dans l'aire de conception, cliquez avec le bouton droit sur l'en-tête ou le pied de page.</span><span class="sxs-lookup"><span data-stu-id="45e4b-112">On the design surface, right-click the page header or footer.</span></span>  
  
2.  <span data-ttu-id="45e4b-113">Pointez sur **Insérer**, puis cliquez sur l'un des éléments suivants pour l'ajouter à la zone d'en-tête ou de pied de page :</span><span class="sxs-lookup"><span data-stu-id="45e4b-113">Point to **Insert**, and then click one of the following items to add it to the header or footer area:</span></span>  
  
    -   <span data-ttu-id="45e4b-114">**Zone de texte**</span><span class="sxs-lookup"><span data-stu-id="45e4b-114">**Textbox**</span></span>  
  
    -   <span data-ttu-id="45e4b-115">**Ligne**</span><span class="sxs-lookup"><span data-stu-id="45e4b-115">**Line**</span></span>  
  
    -   <span data-ttu-id="45e4b-116">**Rectangle**</span><span class="sxs-lookup"><span data-stu-id="45e4b-116">**Rectangle**</span></span>  
  
    -   <span data-ttu-id="45e4b-117">**Image**</span><span class="sxs-lookup"><span data-stu-id="45e4b-117">**Image**</span></span>  
  
3.  <span data-ttu-id="45e4b-118">Cliquez avec le bouton droit sur l’en-tête de page, puis cliquez sur **Propriétés d’en-tête** pour ajouter des bordures, des images ou des couleurs d’arrière-plan ou pour ajuster la largeur de l’en-tête.</span><span class="sxs-lookup"><span data-stu-id="45e4b-118">Right-click the page header, and then click **Header Properties** to add borders, background images, or colors, or to adjust the width of the header.</span></span> <span data-ttu-id="45e4b-119">Cliquez ensuite sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="45e4b-119">Then click **OK**.</span></span>  
  
4.  <span data-ttu-id="45e4b-120">Cliquez avec le bouton droit sur le pied de page, puis cliquez sur **Propriétés du pied de page** pour ajouter des bordures, des images ou des couleurs d’arrière-plan ou pour ajuster la largeur du pied de page.</span><span class="sxs-lookup"><span data-stu-id="45e4b-120">Right-click the page footer, and then click **Footer Properties** to add borders, background images, or colors, or to adjust the width of the footer.</span></span> <span data-ttu-id="45e4b-121">Cliquez ensuite sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="45e4b-121">Then click **OK**.</span></span>  
  
### <a name="to-remove-a-page-header-or-footer"></a><span data-ttu-id="45e4b-122">Pour supprimer un en-tête ou pied de page</span><span class="sxs-lookup"><span data-stu-id="45e4b-122">To remove a page header or footer</span></span>  
  
1.  <span data-ttu-id="45e4b-123">Ouvrez un rapport.</span><span class="sxs-lookup"><span data-stu-id="45e4b-123">Open a report.</span></span>  
  
2.  <span data-ttu-id="45e4b-124">Dans l’aire de conception, cliquez avec le bouton droit sur l’en-tête ou le pied de page, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="45e4b-124">On the design surface, right-click the page header or footer, and then click **Delete**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45e4b-125">La suppression d'un en-tête ou d'un pied de page entraîne sa suppression du rapport.</span><span class="sxs-lookup"><span data-stu-id="45e4b-125">When you remove a page header or footer, you delete it from the report.</span></span> <span data-ttu-id="45e4b-126">Les éléments que vous avez précédemment ajoutés à l'en-tête ou au pied de page ne réapparaissent pas si vous le rajoutez.</span><span class="sxs-lookup"><span data-stu-id="45e4b-126">Any items that you previously added to the page header or footer will not reappear if you subsequently add the header or footer again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e4b-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="45e4b-127">See Also</span></span>  
 [<span data-ttu-id="45e4b-128">En-têtes et pieds de page &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="45e4b-128">Page Headers and Footers &#40;Report Builder and SSRS&#41;</span></span>](page-headers-and-footers-report-builder-and-ssrs.md)  
  
  
