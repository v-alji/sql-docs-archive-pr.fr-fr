---
title: Boîte de dialogue visibilité de la colonne | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.columnvisibility.f1
- "10127"
ms.assetid: ca59d1cd-d782-4298-aa61-4f312c32eb50
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1c2e5f4124f987b87f02968282367817d61c3211
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610507"
---
# <a name="column-visibility-dialog-box"></a><span data-ttu-id="a3fac-102">Boîte de dialogue Visibilité de la colonne</span><span class="sxs-lookup"><span data-stu-id="a3fac-102">Column Visibility Dialog Box</span></span>
  <span data-ttu-id="a3fac-103">Utilisez la boîte de dialogue **Visibilité de la colonne** pour afficher ou masquer la colonne sélectionnée lorsque le rapport est exécuté pour la première fois, ou pour utiliser un autre élément de rapport pour activer/désactiver la visibilité de la colonne.</span><span class="sxs-lookup"><span data-stu-id="a3fac-103">Use the **Column Visibility** dialog box to show or hide the selected column when the report is first run or to use another report item to toggle the visibility of the column.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a3fac-104">Options</span><span class="sxs-lookup"><span data-stu-id="a3fac-104">Options</span></span>  
 <span data-ttu-id="a3fac-105">**Lors de la première exécution du rapport**</span><span class="sxs-lookup"><span data-stu-id="a3fac-105">**When the report is initially run**</span></span>  
 <span data-ttu-id="a3fac-106">Sélectionnez une option pour indiquer le mode d'affichage initial de l'élément de rapport dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="a3fac-106">Select an option to indicate how the report item is initially displayed in the report.</span></span>  
  
 <span data-ttu-id="a3fac-107">**Afficher**</span><span class="sxs-lookup"><span data-stu-id="a3fac-107">**Show**</span></span>  
 <span data-ttu-id="a3fac-108">Choisissez cette option pour afficher l'élément de rapport.</span><span class="sxs-lookup"><span data-stu-id="a3fac-108">Choose this option to show the report item.</span></span>  
  
 <span data-ttu-id="a3fac-109">**Masquer**</span><span class="sxs-lookup"><span data-stu-id="a3fac-109">**Hide**</span></span>  
 <span data-ttu-id="a3fac-110">Choisissez cette option pour masquer l'élément de rapport.</span><span class="sxs-lookup"><span data-stu-id="a3fac-110">Choose this option to hide the report item.</span></span>  
  
 <span data-ttu-id="a3fac-111">**Afficher ou masquer en fonction d'une expression**</span><span class="sxs-lookup"><span data-stu-id="a3fac-111">**Show or hide based on an expression**</span></span>  
 <span data-ttu-id="a3fac-112">Choisissez cette option pour modifier la visibilité initiale à l'aide d'une expression.</span><span class="sxs-lookup"><span data-stu-id="a3fac-112">Choose this option to vary the initial visibility using an expression.</span></span>  
  
 <span data-ttu-id="a3fac-113">Tapez une expression prenant la valeur `Boolean``True` pour masquer l'élément et la valeur `False` pour l'afficher.</span><span class="sxs-lookup"><span data-stu-id="a3fac-113">Type an expression that evaluates to a `Boolean` value of `True` to hide the item and `False` to show the item.</span></span> <span data-ttu-id="a3fac-114">Cliquez sur le bouton Expression (*fx*) pour modifier l’expression.</span><span class="sxs-lookup"><span data-stu-id="a3fac-114">Click the Expression (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="a3fac-115">**L'affichage peut être activé ou désactivé par cet élément de rapport**</span><span class="sxs-lookup"><span data-stu-id="a3fac-115">**Display can be toggled by this report item**</span></span>  
 <span data-ttu-id="a3fac-116">Choisissez cette option pour afficher une image bascule qui permet à l'utilisateur d'afficher ou de masquer cet élément de rapport dans une visionneuse de rapports HTML.</span><span class="sxs-lookup"><span data-stu-id="a3fac-116">Choose this option to display a toggle image that enables the user to show or hide this report item in an HTML report viewer.</span></span>  
  
 <span data-ttu-id="a3fac-117">Tapez ou sélectionnez le nom d'une zone de texte du rapport dans laquelle afficher une image bascule, par exemple Textbox1.</span><span class="sxs-lookup"><span data-stu-id="a3fac-117">Type or select the name of a text box in the report in which to display a toggle image; for example, Textbox1.</span></span> <span data-ttu-id="a3fac-118">La zone de texte que vous choisissez doit figurer dans l'étendue actuelle ou contenante de cet élément de rapport.</span><span class="sxs-lookup"><span data-stu-id="a3fac-118">The text box that you choose must be in the current or containing scope for this report item.</span></span> <span data-ttu-id="a3fac-119">Par exemple, pour afficher ou masquer les lignes associées à un groupe enfant, sélectionnez une zone de texte dans une ligne associée au groupe parent.</span><span class="sxs-lookup"><span data-stu-id="a3fac-119">For example, to toggle visibility of rows associated with a child group, select a text box in a row associated with the parent group.</span></span> <span data-ttu-id="a3fac-120">Pour afficher ou masquer un graphique, sélectionnez une zone de texte qui est dans la même étendue contenante que le graphique, par exemple le corps du rapport ou un rectangle.</span><span class="sxs-lookup"><span data-stu-id="a3fac-120">To toggle visibility of a chart, select a text box that is in the same containing scope as the chart; for example, the report body or a rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3fac-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a3fac-121">See Also</span></span>  
 <span data-ttu-id="a3fac-122">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a3fac-122">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a3fac-123">[Ajouter une action développer ou réduire à un élément &#40;Générateur de rapports et SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a3fac-123">[Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a3fac-124">[Images &#40;Générateur de rapports et SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a3fac-124">[Images &#40;Report Builder and SSRS&#41;](report-design/images-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a3fac-125">Aide sur le Concepteur de rapports via la touche F1</span><span class="sxs-lookup"><span data-stu-id="a3fac-125">Report Designer F1 Help</span></span>](tools/report-designer-f1-help.md)  
  
  
