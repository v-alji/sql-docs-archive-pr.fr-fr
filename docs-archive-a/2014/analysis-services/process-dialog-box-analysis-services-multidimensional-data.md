---
title: Boîte de dialogue traiter (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.processdialog.f1
ms.assetid: c065248c-9001-4f0c-928f-9c59eccb618b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 369c121713894bba9b2ce6c40aa2869de49eaa72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708720"
---
# <a name="process-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="56140-102">Boîte de dialogue Traiter (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="56140-102">Process Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="56140-103">Utilisez la boîte de dialogue **Traiter** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] et [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour traiter les objets [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="56140-103">Use the **Process** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to process [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects.</span></span> <span data-ttu-id="56140-104">Pour ouvrir la boîte de dialogue **Traiter** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="56140-104">You can display the **Process** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] by:</span></span>  
  
-   <span data-ttu-id="56140-105">cliquez avec le bouton droit sur un projet, un cube, une dimension ou une structure d’exploration de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dans l’ **Explorateur de solutions** et sélectionnez **Traiter**;</span><span class="sxs-lookup"><span data-stu-id="56140-105">Right-clicking an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, cube, dimension, or mining structure in **Solution Explorer** and selecting **Process**.</span></span>  
  
-   <span data-ttu-id="56140-106">sélectionnez **Traiter** dans la barre d'outils de chaque page du **Cube Designer**ou du **Concepteur de dimensions**, ou dans les pages **Structure d'exploration de données** et **Modèles d'exploration de données** du **Concepteur de modèle d'exploration de données**;</span><span class="sxs-lookup"><span data-stu-id="56140-106">Selecting **Process** from the toolbar on every page of **Cube Designer**, every page of **Dimension Designer**, or the **Mining Structure** and **Mining Models** pages of **Data Mining Model Designer**.</span></span>  
  
-   <span data-ttu-id="56140-107">cliquez avec le bouton droit sur un modèle de la page **Modèles d’exploration de données** du **Concepteur de modèle d’exploration de données** et sélectionnez **Traiter l’exploration de données et tous les modèles** ou **Traiter le modèle**.</span><span class="sxs-lookup"><span data-stu-id="56140-107">Right-clicking a mining model in the **Mining Models** page of **Data Mining Model Designer** and selecting **Process Mining Structure and All Models** or **Process Model**.</span></span>  
  
 <span data-ttu-id="56140-108">Pour ouvrir la boîte de dialogue **Traiter** de **SQL Server Management Studio** :</span><span class="sxs-lookup"><span data-stu-id="56140-108">You can display the **Process** dialog box in **SQL Server Management Studio** by:</span></span>  
  
-   <span data-ttu-id="56140-109">cliquez avec le bouton droit sur une base de données, un cube, un groupe de mesures, une partition, une dimension ou une structure d’exploration de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dans l’ **Explorateur d’objets** et sélectionnez **Traiter**.</span><span class="sxs-lookup"><span data-stu-id="56140-109">Right-clicking an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, cube, measure group, partition, dimension, mining structure, or mining model in **Object Explorer** and selecting **Process**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="56140-110">Options</span><span class="sxs-lookup"><span data-stu-id="56140-110">Options</span></span>  
 <span data-ttu-id="56140-111">**Liste d’objets**</span><span class="sxs-lookup"><span data-stu-id="56140-111">**Object list**</span></span>  
 <span data-ttu-id="56140-112">Sélectionnez les objets [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] à traiter, ainsi que les options et les paramètres à appliquer.</span><span class="sxs-lookup"><span data-stu-id="56140-112">Select the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects to be processed and the processing options and settings to be applied.</span></span> <span data-ttu-id="56140-113">Cette grille comporte les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="56140-113">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="56140-114">**Nom de l’objet**</span><span class="sxs-lookup"><span data-stu-id="56140-114">**Object Name**</span></span>  
 <span data-ttu-id="56140-115">Affiche le nom de l'objet à traiter.</span><span class="sxs-lookup"><span data-stu-id="56140-115">Displays the name of the object to be processed.</span></span> <span data-ttu-id="56140-116">L'icône à gauche du nom indique le type de l'objet.</span><span class="sxs-lookup"><span data-stu-id="56140-116">The icon to the left of the name indicates the object type.</span></span>  
  
 <span data-ttu-id="56140-117">**Type**</span><span class="sxs-lookup"><span data-stu-id="56140-117">**Type**</span></span>  
 <span data-ttu-id="56140-118">Affiche le type de l'objet à traiter.</span><span class="sxs-lookup"><span data-stu-id="56140-118">Displays the type of the object to be processed.</span></span>  
  
 <span data-ttu-id="56140-119">**Options de traitement**</span><span class="sxs-lookup"><span data-stu-id="56140-119">**Process Options**</span></span>  
 <span data-ttu-id="56140-120">Sélectionnez le type de traitement à effectuer sur l'objet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="56140-120">Select the type of processing to perform on the selected object.</span></span> <span data-ttu-id="56140-121">Pour plus d’informations sur les options de traitement disponibles, consultez [traitement des objets de modèle multidimensionnel](multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="56140-121">For more information about available processing options, see [Multidimensional Model Object Processing](multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
 <span data-ttu-id="56140-122">**Paramètres**</span><span class="sxs-lookup"><span data-stu-id="56140-122">**Settings**</span></span>  
 <span data-ttu-id="56140-123">Affiche le lien hypertexte **Configurer** quand vous choisissez **Traitement incrémentiel** dans les **Options de traitement** des cubes, des groupes de mesures ou des partitions.</span><span class="sxs-lookup"><span data-stu-id="56140-123">Displays the **Configure** hyperlink when you choose **Process Incremental** in **Process Options** for cubes, measure groups, or partitions.</span></span> <span data-ttu-id="56140-124">Cliquez sur **Configurer** pour ouvrir la boîte de dialogue **Mise à jour incrémentielle** .</span><span class="sxs-lookup"><span data-stu-id="56140-124">Click **Configure** to launch the **Incremental Update** dialog box.</span></span> <span data-ttu-id="56140-125">Pour plus d’informations sur la boîte de dialogue **Mise à jour incrémentielle**, consultez [Boîte de dialogue Mise à jour incrémentielle &#40;Analysis Services - Données multidimensionnelles&#41;](incremental-update-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="56140-125">For more information about the **Incremental Update** dialog box, see [Incremental Update Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](incremental-update-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="56140-126">**Remove**</span><span class="sxs-lookup"><span data-stu-id="56140-126">**Remove**</span></span>  
 <span data-ttu-id="56140-127">Supprime les éléments sélectionnés de la **Liste d’objets**.</span><span class="sxs-lookup"><span data-stu-id="56140-127">Click to remove the selected items from **Object list**.</span></span>  
  
 <span data-ttu-id="56140-128">**Analyse d'impact**</span><span class="sxs-lookup"><span data-stu-id="56140-128">**Impact Analysis**</span></span>  
 <span data-ttu-id="56140-129">Ouvre la boîte de dialogue **Analyse d’impact** et affiche les objets affectés par le traitement.</span><span class="sxs-lookup"><span data-stu-id="56140-129">Click to open the **Impact Analysis** dialog box and display the objects that will be affected by the processing task.</span></span> <span data-ttu-id="56140-130">Pour plus d’informations sur la boîte de dialogue **Analyse d’impact**, consultez [Boîte de dialogue Analyse d’impact &#40;Analysis Services - Données multidimensionnelles&#41;](impact-analysis-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="56140-130">For more information about the **Impact Analysis** dialog box, see [Impact Analysis Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](impact-analysis-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56140-131">Cette option est désactivée quand l’option **Traiter les objets affectés** est sélectionnée dans la boîte de dialogue **Modifier les paramètres** .</span><span class="sxs-lookup"><span data-stu-id="56140-131">This option is disabled when the **Process affected objects** option is selected in the **Change Settings** dialog box.</span></span>  
  
 <span data-ttu-id="56140-132">**Modifier les paramètres**</span><span class="sxs-lookup"><span data-stu-id="56140-132">**Change Settings**</span></span>  
 <span data-ttu-id="56140-133">Ouvre la boîte de dialogue **Modifier les paramètres** et permet de modifier les paramètres qui régissent le traitement des objets sélectionnés, notamment les paramètres de traitement par lot, d’écriture différée et des erreurs de clé de dimension.</span><span class="sxs-lookup"><span data-stu-id="56140-133">Click to open the **Change Settings** dialog box and change the settings that govern processing of the selected objects, including batch processing settings, writeback settings, and dimension key error settings.</span></span> <span data-ttu-id="56140-134">Pour plus d’informations sur la boîte de dialogue **Modifier les paramètres**, consultez [Boîte de dialogue Modifier les paramètres &#40;Analysis Services - Données multidimensionnelles&#41;](change-settings-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="56140-134">For more information about the **Change Settings** dialog box, see [Change Settings Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](change-settings-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="56140-135">**Exécuter**</span><span class="sxs-lookup"><span data-stu-id="56140-135">**Run**</span></span>  
 <span data-ttu-id="56140-136">Traite les objets.</span><span class="sxs-lookup"><span data-stu-id="56140-136">Click to process the objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56140-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="56140-137">See Also</span></span>  
 <span data-ttu-id="56140-138">[Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="56140-138">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="56140-139">Boîte de dialogue État d’avancement du traitement &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="56140-139">Process Progress Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-progress-dialog-box-analysis-services-multidimensional-data.md)  
  
  
