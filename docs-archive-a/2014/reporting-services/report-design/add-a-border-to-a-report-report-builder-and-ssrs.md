---
title: Ajouter une bordure à un rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 81412f94-2991-4e58-bc05-5ccc0cbf2a75
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf4a0c2c117774a0f3b25ca0644796fd067bc971
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707163"
---
# <a name="add-a-border-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="a1cd5-102">Ajouter une bordure à un rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="a1cd5-102">Add a Border to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a1cd5-103">Vous pouvez entourer un rapport d'une bordure en plaçant celle-ci dans les en-têtes, les pieds de page et le corps du rapport, sans ajouter de lignes ou de rectangles.</span><span class="sxs-lookup"><span data-stu-id="a1cd5-103">You can add a border to a report by adding borders to the headers, footers, and report body themselves, without adding lines or rectangles.</span></span>  
  
 <span data-ttu-id="a1cd5-104">Si vous ajoutez une bordure de rapport apparaissant dans l'en-tête et le pied de page, ne supprimez pas l'en-tête et le pied de page des première et dernière pages du rapport.</span><span class="sxs-lookup"><span data-stu-id="a1cd5-104">If you add a report border that appears on the page header and footer, do not suppress the header and footer on the first and last pages of the report.</span></span> <span data-ttu-id="a1cd5-105">Sans cela, la bordure pourra être coupée partiellement, en haut et en bas des première et dernières pages du rapport.</span><span class="sxs-lookup"><span data-stu-id="a1cd5-105">If you do, the border may appear cut off at the top or bottom of the first and last pages of the report.</span></span> <span data-ttu-id="a1cd5-106">Pour plus d’informations, consultez [En-têtes et pieds de page &#40;Générateur de rapports et SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a1cd5-106">For more information, see [Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-border-to-a-report"></a><span data-ttu-id="a1cd5-107">Pour ajouter une bordure à un rapport</span><span class="sxs-lookup"><span data-stu-id="a1cd5-107">To add a border to a report</span></span>  
  
1.  <span data-ttu-id="a1cd5-108">Cliquez avec le bouton droit dans l’en-tête en dehors de tout élément de l’en-tête, puis cliquez sur **Propriétés d’en-tête**.</span><span class="sxs-lookup"><span data-stu-id="a1cd5-108">Right-click in the header outside any items in the header, and click **Header Properties**.</span></span> <span data-ttu-id="a1cd5-109">Sous l'onglet **Bordure** , ajoutez une bordure gauche, supérieure et droite avec le style souhaité.</span><span class="sxs-lookup"><span data-stu-id="a1cd5-109">On the **Border** tab, add a left, top, and right border with the style you want.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a1cd5-110">Si vous n'utilisez pas d'en-têtes dans votre rapport, vous pouvez placer des bordures uniquement autour du corps du rapport ; sinon, vous pouvez ajouter des en-têtes à partir de l'onglet **Insérer** .</span><span class="sxs-lookup"><span data-stu-id="a1cd5-110">If you do not use headers in your report, you can place borders around just the report body, or you can add headers from the **Insert** tab.</span></span>  
  
2.  <span data-ttu-id="a1cd5-111">Cliquez avec le bouton droit dans le corps en dehors de tout élément de l’aire de conception, puis cliquez sur **Propriétés du corps**.</span><span class="sxs-lookup"><span data-stu-id="a1cd5-111">Right-click in the body outside any items on the design surface, and click **Body Properties**.</span></span> <span data-ttu-id="a1cd5-112">Sous l'onglet **Bordure** , ajoutez une bordure gauche et droite avec le style souhaité.</span><span class="sxs-lookup"><span data-stu-id="a1cd5-112">On the **Border** tab, add a left and right border with the style you want.</span></span>  
  
3.  <span data-ttu-id="a1cd5-113">Cliquez avec le bouton droit dans le pied de page en dehors de tout élément du pied de page, puis cliquez sur **Propriétés du pied de page**.</span><span class="sxs-lookup"><span data-stu-id="a1cd5-113">Right-click in the footer outside any items in the footer, and click **Footer Properties**.</span></span> <span data-ttu-id="a1cd5-114">Sous l'onglet **Bordure** , ajoutez une bordure gauche, inférieure et droite avec le style souhaité.</span><span class="sxs-lookup"><span data-stu-id="a1cd5-114">On the **Border** tab, add a left, bottom, and right border with the style you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1cd5-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a1cd5-115">See Also</span></span>  
 [<span data-ttu-id="a1cd5-116">Rectangles et lignes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a1cd5-116">Rectangles and Lines &#40;Report Builder and SSRS&#41;</span></span>](rectangles-and-lines-report-builder-and-ssrs.md)  
  
  
