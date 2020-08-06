---
title: Destination de traitement de dimension | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimensionprocessingdest.f1
helpviewer_keywords:
- Dimension Processing destination
- loading dimensions
- destinations [Integration Services], Dimension Processing
- dimensions [Analysis Services], processing
ms.assetid: 4c49bb95-7259-42f4-a785-bb6aaf5f8566
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 61cde87ac4fa5fcb1352491d787674447dd404b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602942"
---
# <a name="dimension-processing-destination"></a><span data-ttu-id="1abc1-102">Destination de traitement de dimension</span><span class="sxs-lookup"><span data-stu-id="1abc1-102">Dimension Processing Destination</span></span>
  <span data-ttu-id="1abc1-103">La destination de traitement de dimension charge et traite une dimension [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1abc1-103">The Dimension Processing destination loads and processes an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dimension.</span></span> <span data-ttu-id="1abc1-104">Pour plus d’informations sur les dimensions, consultez [Dimensions &#40;Analysis Services - Données multidimensionnelles&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data).</span><span class="sxs-lookup"><span data-stu-id="1abc1-104">For more information about dimensions, see [Dimensions &#40;Analysis Services - Multidimensional Data&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data).</span></span>  
  
 <span data-ttu-id="1abc1-105">La destination de traitement de dimension regroupe les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="1abc1-105">The Dimension Processing destination includes the following features:</span></span>  
  
-   <span data-ttu-id="1abc1-106">options permettant de choisir entre un traitement incrémentiel, un traitement complet ou un traitement de mise à jour ;</span><span class="sxs-lookup"><span data-stu-id="1abc1-106">Options to perform incremental, full, or update processing.</span></span>  
  
-   <span data-ttu-id="1abc1-107">configuration d'erreur, permettant de spécifier si le traitement de dimension ignore les erreurs ou s'arrête après un nombre spécifique d'erreurs ;</span><span class="sxs-lookup"><span data-stu-id="1abc1-107">Error configuration, to specify whether dimension processing ignores errors or stops after a specified number of errors.</span></span>  
  
-   <span data-ttu-id="1abc1-108">mappage des colonnes d'entrée aux colonnes des tables de dimension.</span><span class="sxs-lookup"><span data-stu-id="1abc1-108">Mapping of input columns to columns in dimension tables.</span></span>  
  
 <span data-ttu-id="1abc1-109">Pour plus d’informations sur le traitement des objets [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], consultez [Options et paramètres de traitement &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="1abc1-109">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Processing Options and Settings &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span></span>  
  
## <a name="configuration-of-the-dimension-processing-destination"></a><span data-ttu-id="1abc1-110">Configuration de la destination de traitement de dimension</span><span class="sxs-lookup"><span data-stu-id="1abc1-110">Configuration of the Dimension Processing Destination</span></span>  
 <span data-ttu-id="1abc1-111">La destination de traitement de dimension utilise un gestionnaire de connexions [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour se connecter au projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou à l'instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui contient les dimensions traitées par la destination.</span><span class="sxs-lookup"><span data-stu-id="1abc1-111">The Dimension Processing destination uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the dimensions the destination processes.</span></span> <span data-ttu-id="1abc1-112">Pour plus d'informations, consultez [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1abc1-112">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="1abc1-113">Cette destination comporte une entrée.</span><span class="sxs-lookup"><span data-stu-id="1abc1-113">This destination has one input.</span></span> <span data-ttu-id="1abc1-114">Elle ne prend pas en charge de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="1abc1-114">It does not support an error output.</span></span>  
  
 <span data-ttu-id="1abc1-115">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="1abc1-115">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="1abc1-116">Pour plus d’informations sur les propriétés définissables dans la boîte de dialogue **Éditeur de destination de traitement de dimension** , cliquez sur l’une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="1abc1-116">For more information about the properties that you can set in the **Dimension Processing Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="1abc1-117">Éditeur de destination de traitement de dimension &#40;page Gestionnaire de connexions&#41;</span><span class="sxs-lookup"><span data-stu-id="1abc1-117">Dimension Processing Destination Editor &#40;Connection Manager Page&#41;</span></span>](../dimension-processing-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="1abc1-118">Éditeur de destination de traitement de dimension &#40;page Mappages&#41;</span><span class="sxs-lookup"><span data-stu-id="1abc1-118">Dimension Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../dimension-processing-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="1abc1-119">Éditeur de destination de traitement de dimension &#40;page Avancé&#41;</span><span class="sxs-lookup"><span data-stu-id="1abc1-119">Dimension Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../dimension-processing-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="1abc1-120">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="1abc1-120">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="1abc1-121">Pour plus d’informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l’une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="1abc1-121">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topic:</span></span>  
  
-   [<span data-ttu-id="1abc1-122">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="1abc1-122">Common Properties</span></span>](../common-properties.md)  
  
 <span data-ttu-id="1abc1-123">Pour plus d’informations sur la façon de définir des propriétés, consultez [Définir les propriétés d’un composant de flux de données](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="1abc1-123">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1abc1-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1abc1-124">See Also</span></span>  
 <span data-ttu-id="1abc1-125">[Flux de données](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="1abc1-125">[Data Flow](data-flow.md) </span></span>  
 [<span data-ttu-id="1abc1-126">Transformations Integration Services</span><span class="sxs-lookup"><span data-stu-id="1abc1-126">Integration Services Transformations</span></span>](transformations/integration-services-transformations.md)  
  
  
