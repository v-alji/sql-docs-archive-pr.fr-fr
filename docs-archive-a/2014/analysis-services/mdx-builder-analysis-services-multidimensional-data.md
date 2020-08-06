---
title: Générateur MDX (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.mdxbuilderdialof.f1
helpviewer_keywords:
- MDX Builder dialog box
ms.assetid: fecbf093-65ea-4e1b-b637-f04876f1cb0f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 391f4abe953184470be60cca41d53ee20e965423
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610897"
---
# <a name="mdx-builder-analysis-services---multidimensional-data"></a><span data-ttu-id="0476a-102">Générateur MDX (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="0476a-102">MDX Builder (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="0476a-103">Utilisez la boîte de dialogue **Générateur MDX** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] ou [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour créer une expression MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="0476a-103">Use the **MDX Builder** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] or [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to build a Multidimensional Expressions (MDX) expression.</span></span> <span data-ttu-id="0476a-104">Pour afficher la boîte de dialogue **Générateur MDX** , cliquez sur le bouton **modifier** les points de suspension MDX (**...**) de l’option autoriser la lecture **du contenu du cube** , puis sur l’option autoriser la **lecture du contingent de contenu des cellules sur la sécurité des cellules** ou sur l’option autoriser la **lecture et l’écriture du contenu du cube** sur la page **données des cellules** du **Concepteur de rôle**.</span><span class="sxs-lookup"><span data-stu-id="0476a-104">You can display the **MDX Builder** dialog box by clicking the **Edit MDX** ellipsis button (**...**) for the **Allow reading of cube content** option, the **Allow reading of cell content contingent on cell security** option, or the **Allow reading and writing of cube content** option on the **Cell Data** page of **Role Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0476a-105">Options</span><span class="sxs-lookup"><span data-stu-id="0476a-105">Options</span></span>  
  
|<span data-ttu-id="0476a-106">Terme</span><span class="sxs-lookup"><span data-stu-id="0476a-106">Term</span></span>|<span data-ttu-id="0476a-107">Définition</span><span class="sxs-lookup"><span data-stu-id="0476a-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="0476a-108">**Expression**</span><span class="sxs-lookup"><span data-stu-id="0476a-108">**Expression**</span></span>|<span data-ttu-id="0476a-109">Tapez l'expression MDX à utiliser.</span><span class="sxs-lookup"><span data-stu-id="0476a-109">Type the MDX expression to be used.</span></span>|  
|<span data-ttu-id="0476a-110">**Vérification**</span><span class="sxs-lookup"><span data-stu-id="0476a-110">**Check**</span></span>|<span data-ttu-id="0476a-111">Teste \*\*\*\* l'expression MDX définie dans **Expression**.</span><span class="sxs-lookup"><span data-stu-id="0476a-111">Click **Check** to test the MDX expression defined in **Expression**.</span></span>|  
|<span data-ttu-id="0476a-112">**Métadonnées**</span><span class="sxs-lookup"><span data-stu-id="0476a-112">**Metadata**</span></span>|<span data-ttu-id="0476a-113">Affiche les métadonnées de l'objet actif [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] qu'il est possible d'inclure dans l'expression MDX définie dans **Expression**.</span><span class="sxs-lookup"><span data-stu-id="0476a-113">Displays metadata for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object that can be included in the MDX expression defined in **Expression**.</span></span><br /><br /> <span data-ttu-id="0476a-114">Pour copier la syntaxe MDX de l’élément sélectionné, cliquez sur l’élément avec le bouton droit et sélectionnez **Copier** dans le menu contextuel ou faites glisser l’élément sélectionné dans **Expression**.</span><span class="sxs-lookup"><span data-stu-id="0476a-114">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy** from the context menu, or by dragging the selected item to **Expression**.</span></span>|  
|<span data-ttu-id="0476a-115">**Fonctions**</span><span class="sxs-lookup"><span data-stu-id="0476a-115">**Functions**</span></span>|<span data-ttu-id="0476a-116">Affiche les fonctions MDX disponibles dans l'instance active [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0476a-116">Displays available MDX functions for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="0476a-117">La liste des éléments est extraite de l'ensemble de lignes du schéma MDSCHEMA_FUNCTIONS.</span><span class="sxs-lookup"><span data-stu-id="0476a-117">The items listed are retrieved from the MDSCHEMA_FUNCTIONS schema rowset.</span></span><br /><br /> <span data-ttu-id="0476a-118">Pour copier la syntaxe MDX de l’élément sélectionné, cliquez sur l’élément avec le bouton droit et sélectionnez **Copier** dans le menu contextuel ou faites glisser l’élément sélectionné dans **Expression**.</span><span class="sxs-lookup"><span data-stu-id="0476a-118">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy** from the context menu, or by dragging the selected item to **Expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0476a-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0476a-119">See Also</span></span>  
 <span data-ttu-id="0476a-120">[Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0476a-120">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 <span data-ttu-id="0476a-121">[Données de cellule &#40;concepteur de rôle&#41; &#40;Analysis Services-données multidimensionnelles&#41;](https://msdn.microsoft.com/library/ms177279(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="0476a-121">[Cell Data &#40;Role Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](https://msdn.microsoft.com/library/ms177279(v=sql.120).aspx)</span></span>  
  
  
