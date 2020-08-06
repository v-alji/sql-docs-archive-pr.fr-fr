---
title: Masquer un en-tête ou un pied de page sur la première ou la dernière page (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f87ce79b-00d7-4458-a17e-e253a20f720d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 60c8789fd098df7347e9cc0f583426478aee06e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695319"
---
# <a name="hide-a-page-header-or-footer-on-the-first-or-last-page-report-builder-and-ssrs"></a><span data-ttu-id="4b3de-102">Masquer un en-tête ou un pied de page sur la première ou la dernière page (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="4b3de-102">Hide a Page Header or Footer on the First or Last Page (Report Builder and SSRS)</span></span>
  <span data-ttu-id="4b3de-103">Un rapport peut contenir un en-tête et un pied de page qui s'affichent dans la partie supérieure ou inférieure de chaque page.</span><span class="sxs-lookup"><span data-stu-id="4b3de-103">A report can contain a page header and page footer that run along the top and bottom of each page, respectively.</span></span> <span data-ttu-id="4b3de-104">Après avoir ajouté un en-tête ou un pied de page, vous pouvez le masquer de manière sélective sur la première et la dernière page d'un rapport.</span><span class="sxs-lookup"><span data-stu-id="4b3de-104">After you a add a header or footer, you can selectively hide it on the first and last pages of a report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-hide-a-page-header-on-the-first-or-last-page"></a><span data-ttu-id="4b3de-105">Pour masquer un en-tête de page sur la première ou la dernière page</span><span class="sxs-lookup"><span data-stu-id="4b3de-105">To hide a page header on the first or last page</span></span>  
  
1.  <span data-ttu-id="4b3de-106">Ouvrez un rapport en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="4b3de-106">Open a report in Design view.</span></span>  
  
2.  <span data-ttu-id="4b3de-107">Cliquez avec le bouton droit sur l’en-tête de page, puis cliquez sur **Propriétés d’en-tête**.</span><span class="sxs-lookup"><span data-stu-id="4b3de-107">Right-click the page header, and then click **Header Properties**.</span></span> <span data-ttu-id="4b3de-108">La boîte de dialogue **Propriétés d'en-tête du rapport** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="4b3de-108">The **Report Header Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="4b3de-109">Vérifiez que l'option **Afficher l'en-tête pour ce rapport** n'est pas sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4b3de-109">Verify that **Display header for this report** is not selected.</span></span>  
  
4.  <span data-ttu-id="4b3de-110">Dans la section **Options d'impression** , désactivez la case à cocher correspondant à chaque option pour masquer l'affichage sur la première ou la dernière page du rapport.</span><span class="sxs-lookup"><span data-stu-id="4b3de-110">In the **Print options** section, clear the check box for each option to hide the display on the first or last page of the report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-hide-a-page-footer-on-the-first-or-last-page"></a><span data-ttu-id="4b3de-111">Pour masquer un pied de page sur la première ou la dernière page</span><span class="sxs-lookup"><span data-stu-id="4b3de-111">To hide a page footer on the first or last page</span></span>  
  
1.  <span data-ttu-id="4b3de-112">Ouvrez un rapport en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="4b3de-112">Open a report in Design view.</span></span>  
  
2.  <span data-ttu-id="4b3de-113">Cliquez avec le bouton droit sur le pied de page, puis cliquez sur **Propriétés du pied de page**.</span><span class="sxs-lookup"><span data-stu-id="4b3de-113">Right-click the page footer, and then click **Footer Properties**.</span></span> <span data-ttu-id="4b3de-114">La boîte de dialogue **Propriétés de pied de page du rapport** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="4b3de-114">The **Report Footer Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="4b3de-115">Vérifiez que l'option **Afficher le pied de page pour ce rapport** n'est pas sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4b3de-115">Verify that **Display footer for this report** is not selected.</span></span>  
  
4.  <span data-ttu-id="4b3de-116">Dans la section **Options d'impression** , désactivez la case à cocher correspondant à chaque option pour masquer l'affichage sur la première ou la dernière page du rapport.</span><span class="sxs-lookup"><span data-stu-id="4b3de-116">In the **Print options** section, clear the check box for each option to hide the display on the first or last page of the report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4b3de-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4b3de-117">See Also</span></span>  
 <span data-ttu-id="4b3de-118">[En-têtes et pieds de page &#40;Générateur de rapports et SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4b3de-118">[Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4b3de-119">[Pagination dans Reporting Services &#40;Générateur de rapports et SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4b3de-119">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="4b3de-120">Ajouter ou supprimer un en-tête ou un pied de page &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4b3de-120">Add or Remove a Page Header or Footer &#40;Report Builder and SSRS&#41;</span></span>](add-or-remove-a-page-header-or-footer-report-builder-and-ssrs.md)  
  
  
