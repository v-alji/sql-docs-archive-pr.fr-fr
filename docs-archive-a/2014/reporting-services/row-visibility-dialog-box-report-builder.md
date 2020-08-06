---
title: Boîte de dialogue visibilité de ligne (Générateur de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10126"
ms.assetid: 117fb20c-2fda-437e-bcc5-9010d6d4b53b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 748cf1612f04e02a90a5d8579b56d3856dea0388
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602729"
---
# <a name="row-visibility-dialog-box-report-builder"></a><span data-ttu-id="f2218-102">Boîte de dialogue Visibilité de ligne (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="f2218-102">Row Visibility Dialog Box (Report Builder)</span></span>
  <span data-ttu-id="f2218-103">Utilisez la boîte de dialogue **Visibilité de ligne** pour afficher ou masquer la ligne sélectionnée lorsque le rapport est exécuté pour la première fois ou pour utiliser un autre élément de rapport pour activer/désactiver la visibilité de la ligne.</span><span class="sxs-lookup"><span data-stu-id="f2218-103">Use the **Row Visibility** dialog box to show or hide the selected row when the report is first run or to use another report item to toggle the visibility of the row.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f2218-104">Options</span><span class="sxs-lookup"><span data-stu-id="f2218-104">Options</span></span>  
 <span data-ttu-id="f2218-105">**Lors de la première exécution du rapport**</span><span class="sxs-lookup"><span data-stu-id="f2218-105">**When the report is initially run**</span></span>  
 <span data-ttu-id="f2218-106">Sélectionnez une option pour indiquer comment la ligne s'affiche initialement dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="f2218-106">Select an option to indicate how the row is initially displayed in the report.</span></span>  
  
 <span data-ttu-id="f2218-107">**Afficher**</span><span class="sxs-lookup"><span data-stu-id="f2218-107">**Show**</span></span>  
 <span data-ttu-id="f2218-108">Sélectionnez cette option pour afficher la ligne.</span><span class="sxs-lookup"><span data-stu-id="f2218-108">Select this option to show the row.</span></span>  
  
 <span data-ttu-id="f2218-109">**Masquer**</span><span class="sxs-lookup"><span data-stu-id="f2218-109">**Hide**</span></span>  
 <span data-ttu-id="f2218-110">Sélectionnez cette option pour masquer la ligne.</span><span class="sxs-lookup"><span data-stu-id="f2218-110">Select this option to hide the row.</span></span>  
  
 <span data-ttu-id="f2218-111">**Afficher ou masquer en fonction d'une expression**</span><span class="sxs-lookup"><span data-stu-id="f2218-111">**Show or hide based on an expression**</span></span>  
 <span data-ttu-id="f2218-112">Sélectionnez cette option pour faire varier la visibilité initiale à l'aide d'une expression.</span><span class="sxs-lookup"><span data-stu-id="f2218-112">Select this option to vary the initial visibility using an expression.</span></span>  
  
 <span data-ttu-id="f2218-113">Tapez une expression prenant la valeur `Boolean``True` pour masquer l'élément et la valeur `False` pour l'afficher.</span><span class="sxs-lookup"><span data-stu-id="f2218-113">Type an expression that evaluates to a `Boolean` value of `True` to hide the item and `False` to show the item.</span></span> <span data-ttu-id="f2218-114">Cliquez sur le bouton **Expression** (*fx*) pour modifier l’expression.</span><span class="sxs-lookup"><span data-stu-id="f2218-114">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="f2218-115">**L'affichage peut être activé ou désactivé par cet élément de rapport**</span><span class="sxs-lookup"><span data-stu-id="f2218-115">**Display can be toggled by this report item**</span></span>  
 <span data-ttu-id="f2218-116">Choisissez cette option pour afficher une image bascule qui permet à l'utilisateur d'afficher ou de masquer la ligne de rapport dans une visionneuse de rapports HTML.</span><span class="sxs-lookup"><span data-stu-id="f2218-116">Choose this option to display a toggle image that enables the user to show or hide this row in an HTML report viewer.</span></span>  
  
 <span data-ttu-id="f2218-117">Tapez ou sélectionnez le nom d'une zone de texte du rapport dans laquelle afficher une image bascule, par exemple Textbox1.</span><span class="sxs-lookup"><span data-stu-id="f2218-117">Type or select the name of a text box in the report in which to display a toggle image; for example, Textbox1.</span></span> <span data-ttu-id="f2218-118">La zone de texte que vous choisissez doit figurer dans l'étendue actuelle ou contenante de cet élément de rapport.</span><span class="sxs-lookup"><span data-stu-id="f2218-118">The text box that you choose must be in the current or containing scope for this report item.</span></span> <span data-ttu-id="f2218-119">Par exemple, pour afficher ou masquer les lignes associées à un groupe enfant, sélectionnez une zone de texte dans une ligne associée au groupe parent.</span><span class="sxs-lookup"><span data-stu-id="f2218-119">For example, to toggle visibility of rows associated with a child group, select a text box in a row associated with the parent group.</span></span> <span data-ttu-id="f2218-120">Pour afficher ou masquer un graphique, sélectionnez une zone de texte qui est dans la même étendue contenante que le graphique, par exemple le corps du rapport ou un rectangle.</span><span class="sxs-lookup"><span data-stu-id="f2218-120">To toggle visibility of a chart, select a text box that is in the same containing scope as the chart; for example, the report body or a rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2218-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f2218-121">See Also</span></span>  
 <span data-ttu-id="f2218-122">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f2218-122">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f2218-123">[Ajouter une action développer ou réduire à un élément &#40;Générateur de rapports et SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f2218-123">[Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f2218-124">[Images &#40;Générateur de rapports et SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f2218-124">[Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f2218-125">[Aide Générateur de rapports pour les boîtes de dialogue, les volets et les assistants](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="f2218-125">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 [<span data-ttu-id="f2218-126">Boîte de dialogue Propriétés de l’image, Général &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f2218-126">Image Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
