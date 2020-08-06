---
title: Boîte de dialogue Propriétés de la dimension (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.dimensionproperties.f1
helpviewer_keywords:
- Dimension Properties dialog box
ms.assetid: 7235d443-b2ce-4c53-b2eb-abceb28394bb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0523220c76c11280165bc825c5c00c5eb9e23be6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614893"
---
# <a name="dimension-properties-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="31caa-102">Boîte de dialogue Propriétés de la dimension (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="31caa-102">Dimension Properties Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="31caa-103">Utilisez la boîte de dialogue **Propriétés de la dimension** dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour définir les propriétés d'une dimension dans la base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="31caa-103">Use the **Dimension Properties** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to set the properties of a dimension in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="31caa-104">Vous pouvez afficher la boîte de dialogue **Propriétés de la dimension** en cliquant avec le bouton droit sur une dimension dans l’Explorateur d'objets et en sélectionnant **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="31caa-104">You can display the **Dimension Properties** dialog box by right-clicking a dimension in Object Explorer and selecting **Properties**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="31caa-105">Options</span><span class="sxs-lookup"><span data-stu-id="31caa-105">Options</span></span>  
  
|<span data-ttu-id="31caa-106">Terme</span><span class="sxs-lookup"><span data-stu-id="31caa-106">Term</span></span>|<span data-ttu-id="31caa-107">Définition</span><span class="sxs-lookup"><span data-stu-id="31caa-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="31caa-108">**Nom**</span><span class="sxs-lookup"><span data-stu-id="31caa-108">**Name**</span></span>|<span data-ttu-id="31caa-109">Affiche le nom de la dimension.</span><span class="sxs-lookup"><span data-stu-id="31caa-109">Displays the name of the dimension.</span></span>|  
|<span data-ttu-id="31caa-110">**Identifiant**</span><span class="sxs-lookup"><span data-stu-id="31caa-110">**ID**</span></span>|<span data-ttu-id="31caa-111">Affiche l'identificateur de la dimension.</span><span class="sxs-lookup"><span data-stu-id="31caa-111">Displays the identifier of the dimension.</span></span>|  
|<span data-ttu-id="31caa-112">**Description**</span><span class="sxs-lookup"><span data-stu-id="31caa-112">**Description**</span></span>|<span data-ttu-id="31caa-113">Affiche la description de la dimension.</span><span class="sxs-lookup"><span data-stu-id="31caa-113">Displays the description of the dimension.</span></span>|  
|<span data-ttu-id="31caa-114">**Créer un horodateur**</span><span class="sxs-lookup"><span data-stu-id="31caa-114">**Create Timestamp**</span></span>|<span data-ttu-id="31caa-115">Affiche la date et l'heure de création de la dimension.</span><span class="sxs-lookup"><span data-stu-id="31caa-115">Displays the date and time the dimension was created.</span></span>|  
|<span data-ttu-id="31caa-116">**Dernière mise à jour du schéma**</span><span class="sxs-lookup"><span data-stu-id="31caa-116">**Last Schema Update**</span></span>|<span data-ttu-id="31caa-117">Affiche la date et l'heure de la dernière mise à jour des métadonnées de la dimension.</span><span class="sxs-lookup"><span data-stu-id="31caa-117">Displays the date and time the metadata for the dimension was last updated.</span></span>|  
|<span data-ttu-id="31caa-118">**Mode de traitement**</span><span class="sxs-lookup"><span data-stu-id="31caa-118">**Processing Mode**</span></span>|<span data-ttu-id="31caa-119">Sélectionnez le mode de traitement à utiliser pour la dimension.</span><span class="sxs-lookup"><span data-stu-id="31caa-119">Select the processing mode to use for the dimension.</span></span> <span data-ttu-id="31caa-120">Pour plus d'informations sur les valeurs que peuvent prendre cette propriété, consultez <xref:Microsoft.AnalysisServices.Dimension.ProcessingMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="31caa-120">For more information about the values for this property, see <xref:Microsoft.AnalysisServices.Dimension.ProcessingMode%2A>.</span></span>|  
|<span data-ttu-id="31caa-121">**State**</span><span class="sxs-lookup"><span data-stu-id="31caa-121">**State**</span></span>|<span data-ttu-id="31caa-122">Affiche l'état du traitement de la dimension.</span><span class="sxs-lookup"><span data-stu-id="31caa-122">Displays the processing state of the dimension.</span></span> <span data-ttu-id="31caa-123">Pour plus d'informations sur les valeurs que peuvent prendre cette propriété, consultez <xref:Microsoft.AnalysisServices.ProcessableMajorObject.State%2A>.</span><span class="sxs-lookup"><span data-stu-id="31caa-123">For more information about the values for this property, see <xref:Microsoft.AnalysisServices.ProcessableMajorObject.State%2A>.</span></span>|  
|<span data-ttu-id="31caa-124">**Dernier traitement**</span><span class="sxs-lookup"><span data-stu-id="31caa-124">**Last Processed**</span></span>|<span data-ttu-id="31caa-125">Affiche la date et l'heure du dernier traitement de la dimension.</span><span class="sxs-lookup"><span data-stu-id="31caa-125">Displays the date and time the dimension was last processed.</span></span>|  
|<span data-ttu-id="31caa-126">**Mode de stockage actuel**</span><span class="sxs-lookup"><span data-stu-id="31caa-126">**Current Storage Mode**</span></span>|<span data-ttu-id="31caa-127">Affiche le mode de stockage actuel de la dimension.</span><span class="sxs-lookup"><span data-stu-id="31caa-127">Displays the current storage mode for the dimension.</span></span> <span data-ttu-id="31caa-128">Pour plus d'informations sur les valeurs que peuvent prendre cette propriété, consultez <xref:Microsoft.AnalysisServices.Dimension.CurrentStorageMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="31caa-128">For more information about the values for this property, see <xref:Microsoft.AnalysisServices.Dimension.CurrentStorageMode%2A>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31caa-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="31caa-129">See Also</span></span>  
 <span data-ttu-id="31caa-130">[Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="31caa-130">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="31caa-131">Dimensions &#40;Analysis Services - Données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="31caa-131">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)  
  
  
