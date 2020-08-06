---
title: Boîte de dialogue État d’avancement du traitement (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.processprogress.f1
ms.assetid: f3bd5278-3a83-4fd9-9903-e81bdd4b6892
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4e436eeab21a37ae174a5003c01e77c05240238b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708715"
---
# <a name="process-progress-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="c101f-102">Boîte de dialogue État d'avancement du traitement (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="c101f-102">Process Progress Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="c101f-103">Utilisez la boîte de dialogue **État d'avancement du traitement** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] et [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour contrôler le traitement dans [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c101f-103">Use the **Process Progress** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to monitor processing in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="c101f-104">Cette boîte de dialogue s'affiche \*\*\*\* lorsque le traitement d'un objet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] commence.</span><span class="sxs-lookup"><span data-stu-id="c101f-104">The **Process Progress** dialog box appears when processing begins on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c101f-105">Options</span><span class="sxs-lookup"><span data-stu-id="c101f-105">Options</span></span>  
 <span data-ttu-id="c101f-106">**Arborescence de l’état d’intégrité**</span><span class="sxs-lookup"><span data-stu-id="c101f-106">**Status tree view**</span></span>  
 <span data-ttu-id="c101f-107">Affiche les messages d’état de l’instance [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] à propos des objets en cours de traitement, y compris l’heure de début, l’heure de fin et la progression.</span><span class="sxs-lookup"><span data-stu-id="c101f-107">Displays status messages from the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance regarding the objects being processed, including start time, stop time, and progress information.</span></span> <span data-ttu-id="c101f-108">Cliquez avec le bouton droit sur un élément et sélectionnez **Copier** pour copier les informations d’un message d’état dans le Presse-papiers. Vous pouvez aussi double-cliquer sur un élément pour afficher la boîte de dialogue **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="c101f-108">Right-click an item and select **Copy** to copy the details of a status message to the clipboard, or double-click an item to display the **View Details** dialog box.</span></span> <span data-ttu-id="c101f-109">Pour plus d’informations sur la boîte de dialogue **Afficher les détails**, consultez [Boîte de dialogue Afficher les détails &#40;Analysis Services - Données multidimensionnelles&#41;](view-details-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="c101f-109">For more information about the **View Details** dialog box, see [View Details Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](view-details-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="c101f-110">**Description de l'état**</span><span class="sxs-lookup"><span data-stu-id="c101f-110">**Status description**</span></span>  
 <span data-ttu-id="c101f-111">Affiche l'état actuel du traitement.</span><span class="sxs-lookup"><span data-stu-id="c101f-111">Displays the current status of the processing operation.</span></span>  
  
 <span data-ttu-id="c101f-112">**Stop**</span><span class="sxs-lookup"><span data-stu-id="c101f-112">**Stop**</span></span>  
 <span data-ttu-id="c101f-113">Cliquez sur Arrêter pour interrompre le traitement.</span><span class="sxs-lookup"><span data-stu-id="c101f-113">Click to stop the processing operation.</span></span>  
  
 <span data-ttu-id="c101f-114">**Retraiter**</span><span class="sxs-lookup"><span data-stu-id="c101f-114">**Reprocess**</span></span>  
 <span data-ttu-id="c101f-115">Recommence le traitement affiché dans la boîte de dialogue **État d’avancement du traitement** .</span><span class="sxs-lookup"><span data-stu-id="c101f-115">Click to repeat the processing operation that displayed the **Process Progress** dialog box.</span></span>  
  
 <span data-ttu-id="c101f-116">**Afficher les détails**</span><span class="sxs-lookup"><span data-stu-id="c101f-116">**View Details**</span></span>  
 <span data-ttu-id="c101f-117">Ouvre la boîte de dialogue **Afficher les détails** qui fournit des informations sur l’élément sélectionné dans **l’arborescence de l’état d’intégrité**.</span><span class="sxs-lookup"><span data-stu-id="c101f-117">Click to open the **View Details** dialog box and display details regarding the item selected in **Status tree view**.</span></span> <span data-ttu-id="c101f-118">Pour plus d’informations sur la boîte de dialogue **Afficher les détails**, consultez [Boîte de dialogue Afficher les détails &#40;Analysis Services - Données multidimensionnelles&#41;](view-details-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="c101f-118">For more information about the **View Details** dialog box, see [View Details Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](view-details-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c101f-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c101f-119">See Also</span></span>  
 <span data-ttu-id="c101f-120">[Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="c101f-120">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="c101f-121">Traitement des objets de modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="c101f-121">Multidimensional Model Object Processing</span></span>](multidimensional-models/processing-a-multidimensional-model-analysis-services.md)  
  
  
