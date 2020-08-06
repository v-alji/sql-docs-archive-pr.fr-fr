---
title: Distributions de colonnes (exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- normal distribution type [data mining]
- uniform distribution type [data mining]
- columns [data mining], distributions
- log normal distribution type [data mining]
- continuous columns
- distributions [data mining]
ms.assetid: 87e700de-32be-4bc8-b01d-ba4ee1ab48de
author: minewiskan
ms.author: owend
ms.openlocfilehash: 29aad33535c4cc4d9baf4c453249ce3b51595e78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614923"
---
# <a name="column-distributions-data-mining"></a><span data-ttu-id="adc9a-102">Distributions de colonnes (exploration de données)</span><span class="sxs-lookup"><span data-stu-id="adc9a-102">Column Distributions (Data Mining)</span></span>
  <span data-ttu-id="adc9a-103">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , vous pouvez définir des distributions de colonnes dans une structure d’exploration de données, pour affecter la façon dont les algorithmes traitent les données dans ces colonnes lorsque vous créez des modèles d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="adc9a-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can define column distributions in a mining structure, to affect how algorithms process the data in those columns when you create mining models.</span></span> <span data-ttu-id="adc9a-104">Pour certains algorithmes, il est judicieux de définir la distribution des colonnes continues avant de traiter le modèle, s'il est établi que les colonnes contiennent des distributions de valeurs communes.</span><span class="sxs-lookup"><span data-stu-id="adc9a-104">For some algorithms, it is useful to define the distribution of any continuous columns before you process the model, if the columns are known to contain common distributions of values.</span></span> <span data-ttu-id="adc9a-105">Si vous ne définissez pas de distributions, les modèles d'exploration de données obtenus risquent de générer des prévisions moins précises, car les algorithmes disposent dans ce cas d'une moins grande quantité d'informations pour interpréter les données.</span><span class="sxs-lookup"><span data-stu-id="adc9a-105">If you do not define the distributions, the resulting mining models may produce less accurate predictions than if the distributions were defined, because the algorithms will have less information from which to interpret the data.</span></span>

 <span data-ttu-id="adc9a-106">Les algorithmes disponibles dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] prennent en charge les types de distribution suivants :</span><span class="sxs-lookup"><span data-stu-id="adc9a-106">The algorithms that are available in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] support the following distribution types:</span></span>

 <span data-ttu-id="adc9a-107">`Normal`Les valeurs de la colonne continue forment un histogramme avec une distribution normale.</span><span class="sxs-lookup"><span data-stu-id="adc9a-107">`Normal` The values for the continuous column form a histogram with a normal distribution.</span></span>

 <span data-ttu-id="adc9a-108">![Histogramme avec distribution normale](../media/normal-distribution.gif "Histogramme avec distribution normale")</span><span class="sxs-lookup"><span data-stu-id="adc9a-108">![Histogram with normal distribution](../media/normal-distribution.gif "Histogram with normal distribution")</span></span>

 <span data-ttu-id="adc9a-109">`Log Normal`Les valeurs de la colonne continue forment un histogramme, dans lequel la courbe est allongée à l’extrémité supérieure et est inclinée vers l’extrémité inférieure.</span><span class="sxs-lookup"><span data-stu-id="adc9a-109">`Log Normal` The values for the continuous column form a histogram, where the curve is elongated at the upper end and is skewed toward the lower end.</span></span>

 <span data-ttu-id="adc9a-110">![Histogramme avec distribution normale logarithmique](../media/log-normal-distribution.gif "Histogramme avec distribution normale logarithmique")</span><span class="sxs-lookup"><span data-stu-id="adc9a-110">![Histogram with log normal distribution](../media/log-normal-distribution.gif "Histogram with log normal distribution")</span></span>

 <span data-ttu-id="adc9a-111">`Uniform`Les valeurs de la colonne continue forment une courbe plate, dans laquelle toutes les valeurs sont également probables.</span><span class="sxs-lookup"><span data-stu-id="adc9a-111">`Uniform` The values for the continuous column form a flat curve, in which all values are equally likely.</span></span>

 <span data-ttu-id="adc9a-112">![Histogramme avec distribution uniforme](../media/uniform-distribution.gif "Histogramme avec distribution uniforme")</span><span class="sxs-lookup"><span data-stu-id="adc9a-112">![Histogram with uniform distribution](../media/uniform-distribution.gif "Histogram with uniform distribution")</span></span>

 <span data-ttu-id="adc9a-113">Pour plus d’informations sur les algorithmes fournis par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], consultez [Algorithmes d’exploration de données &#40;Analysis Services - Exploration de données&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="adc9a-113">For more information about the algorithms that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="adc9a-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="adc9a-114">See Also</span></span>
 <span data-ttu-id="adc9a-115">[Les types de contenu &#40;](content-types-data-mining.md) les structures d’exploration de données&#41;l’exploration [de données &#40;les méthodes de discrétisation d’exploration de données Analysis Services](mining-structures-analysis-services-data-mining.md)&#41;d' [exploration](discretization-methods-data-mining.md) de données &#40;les distributions&#41;les colonnes [DMX &#40;](/sql/dmx/distributions-dmx) [exploration](mining-structure-columns.md) de données</span><span class="sxs-lookup"><span data-stu-id="adc9a-115">[Content Types &#40;Data Mining&#41;](content-types-data-mining.md) [Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) [Discretization Methods &#40;Data Mining&#41;](discretization-methods-data-mining.md) [Distributions &#40;DMX&#41;](/sql/dmx/distributions-dmx) [Mining Structure Columns](mining-structure-columns.md)</span></span>


