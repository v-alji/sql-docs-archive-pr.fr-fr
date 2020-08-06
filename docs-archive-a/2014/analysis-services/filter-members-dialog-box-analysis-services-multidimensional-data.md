---
title: Boîte de dialogue Filtrer les membres (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.filtermembers.f1
helpviewer_keywords:
- Filter Members dialog box
ms.assetid: 52c6da1d-9fb5-4dbc-bffa-248d11cd337c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 66980b1afe9d4eed353ae18c37ed1fdd052e62b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600307"
---
# <a name="filter-members-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="2d7ad-102">Boîte de dialogue Filtrer les membres (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="2d7ad-102">Filter Members Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="2d7ad-103">Utilisez la boîte de dialogue **Filtrer les membres** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour filtrer les membres d'une dimension en fonction du sous-titre des membres, du nom des membres, du nom unique des membres, de la valeur de colonne de clé ou de la valeur de colonne de valeurs du niveau actuel lors de la consultation d'une dimension dans l'onglet **Navigateur** du **Concepteur de dimensions**.</span><span class="sxs-lookup"><span data-stu-id="2d7ad-103">Use the **Filter Members** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to filter dimension members by member caption, member name, member unique name, key column value, or value column value for the current level while browsing a dimension in the **Browser** tab of **Dimension Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2d7ad-104">Options</span><span class="sxs-lookup"><span data-stu-id="2d7ad-104">Options</span></span>  
  
|<span data-ttu-id="2d7ad-105">Terme</span><span class="sxs-lookup"><span data-stu-id="2d7ad-105">Term</span></span>|<span data-ttu-id="2d7ad-106">Définition</span><span class="sxs-lookup"><span data-stu-id="2d7ad-106">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="2d7ad-107">**Expression filter**</span><span class="sxs-lookup"><span data-stu-id="2d7ad-107">**Filter expression**</span></span>|<span data-ttu-id="2d7ad-108">Affiche une grille de propriétés, d'opérateurs et de valeurs utilisés pour créer une expression de filtrage.</span><span class="sxs-lookup"><span data-stu-id="2d7ad-108">Displays a grid of properties, operators, and values used to construct a filter expression.</span></span> <span data-ttu-id="2d7ad-109">Note qu’une fois qu’une ligne est ajoutée, elle ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="2d7ad-109">Note that after a row is added, it cannot be removed.</span></span> <span data-ttu-id="2d7ad-110">Vous devez fermer et rouvrir la boîte de dialogue pour définir une nouvelle expression de filtrage.</span><span class="sxs-lookup"><span data-stu-id="2d7ad-110">You must close and reopen the dialog box to specify a new filter expression.</span></span> <span data-ttu-id="2d7ad-111">Cette grille comporte les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="2d7ad-111">The grid contains the following columns:</span></span><br /><br /> <span data-ttu-id="2d7ad-112">**Propriété**: sélectionnez la propriété du membre à utiliser pour l’expression de filtre.</span><span class="sxs-lookup"><span data-stu-id="2d7ad-112">**Property**: Select the property of the member to use for the filter expression.</span></span><br /><br /> <span data-ttu-id="2d7ad-113">**Opérateur**: sélectionnez l’opérateur à utiliser pour l’expression de filtre.</span><span class="sxs-lookup"><span data-stu-id="2d7ad-113">**Operator**: Select the operator to use for the filter expression.</span></span><br /><br /> <span data-ttu-id="2d7ad-114">**Valeur**: tapez la valeur de la propriété sélectionnée dans **propriété** à évaluer à l’aide de l’opérateur spécifié dans **opérateur**.</span><span class="sxs-lookup"><span data-stu-id="2d7ad-114">**Value**: Type the value of the property selected in **Property** to evaluate using the operator specified in **Operator**.</span></span>|  
|<span data-ttu-id="2d7ad-115">**Volet de test**</span><span class="sxs-lookup"><span data-stu-id="2d7ad-115">**Test pane**</span></span>|<span data-ttu-id="2d7ad-116">Lorsque vous cliquez sur **Tester** , ce volet affiche les membres retournés par l'expression de filtrage.</span><span class="sxs-lookup"><span data-stu-id="2d7ad-116">When **Test** is clicked, this pane displays the members returned by the filter expression.</span></span> <span data-ttu-id="2d7ad-117">Si aucun membre n'est retourné en utilisant les critères définis dans **Expression de filtre**, un avertissement s'affiche.</span><span class="sxs-lookup"><span data-stu-id="2d7ad-117">If no members are returned using the criteria specified in **Filter expression**, a warning is displayed.</span></span>|  
|<span data-ttu-id="2d7ad-118">**Test**</span><span class="sxs-lookup"><span data-stu-id="2d7ad-118">**Test**</span></span>|<span data-ttu-id="2d7ad-119">Cliquez pour tester les critères définis dans **Expression de filtre**.</span><span class="sxs-lookup"><span data-stu-id="2d7ad-119">Click to test the criteria specified in **Filter expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d7ad-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2d7ad-120">See Also</span></span>  
 <span data-ttu-id="2d7ad-121">[Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="2d7ad-121">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="2d7ad-122">Navigateur &#40;concepteur de dimensions&#41; &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="2d7ad-122">Browser &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browser-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
