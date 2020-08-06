---
title: Multidiffusion, transformation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multicasttrans.f1
helpviewer_keywords:
- multiple outputs
- Multicast transformation
- datasets [Integration Services], multiple outputs
- multiple transformations
ms.assetid: 32194784-1684-40cd-9f91-1aba4d8360d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7b5c0a38c966c89f426a213f302b45c390b77cfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710787"
---
# <a name="multicast-transformation"></a><span data-ttu-id="22b42-102">transformation de multidiffusion</span><span class="sxs-lookup"><span data-stu-id="22b42-102">Multicast Transformation</span></span>
  <span data-ttu-id="22b42-103">La transformation de multidiffusion distribue son entrée vers une ou plusieurs sorties.</span><span class="sxs-lookup"><span data-stu-id="22b42-103">The Multicast transformation distributes its input to one or more outputs.</span></span> <span data-ttu-id="22b42-104">Cette transformation est similaire à la transformation de fractionnement conditionnel.</span><span class="sxs-lookup"><span data-stu-id="22b42-104">This transformation is similar to the Conditional Split transformation.</span></span> <span data-ttu-id="22b42-105">Les deux transformations dirigent une entrée vers plusieurs sorties.</span><span class="sxs-lookup"><span data-stu-id="22b42-105">Both transformations direct an input to multiple outputs.</span></span> <span data-ttu-id="22b42-106">Leur différence réside dans le fait que la transformation de multidiffusion dirige chaque ligne vers chaque sortie, tandis que la transformation de fractionnement conditionnel dirige une ligne vers une seule sortie.</span><span class="sxs-lookup"><span data-stu-id="22b42-106">The difference between the two is that the Multicast transformation directs every row to every output, and the Conditional Split directs a row to a single output.</span></span> <span data-ttu-id="22b42-107">Pour plus d'informations, consultez [Conditional Split Transformation](conditional-split-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="22b42-107">For more information, see [Conditional Split Transformation](conditional-split-transformation.md).</span></span>  
  
 <span data-ttu-id="22b42-108">Vous configurez la transformation de multidiffusion en ajoutant des sorties.</span><span class="sxs-lookup"><span data-stu-id="22b42-108">You configure the Multicast transformation by adding outputs.</span></span>  
  
 <span data-ttu-id="22b42-109">À l'aide de la transformation de multidiffusion, un package peut créer des copies logiques des données.</span><span class="sxs-lookup"><span data-stu-id="22b42-109">Using the Multicast transformation, a package can create logical copies of data.</span></span> <span data-ttu-id="22b42-110">Cette fonctionnalité est utile lorsque le package doit appliquer plusieurs ensembles de transformations aux mêmes données.</span><span class="sxs-lookup"><span data-stu-id="22b42-110">This capability is useful when the package needs to apply multiple sets of transformations to the same data.</span></span> <span data-ttu-id="22b42-111">Par exemple, une copie des données est agrégée et seules les informations de résumé sont chargées à leur emplacement de destination, tandis qu'une autre copie des données est enrichie de valeurs recherchées et de colonnes dérivées avant d'être chargée à son emplacement de destination.</span><span class="sxs-lookup"><span data-stu-id="22b42-111">For example, one copy of the data is aggregated and only the summary information is loaded into its destination, while another copy of the data is extended with lookup values and derived columns before it is loaded into its destination.</span></span>  
  
 <span data-ttu-id="22b42-112">Cette transformation a une entrée et plusieurs sorties.</span><span class="sxs-lookup"><span data-stu-id="22b42-112">This transformation has one input and multiple outputs.</span></span> <span data-ttu-id="22b42-113">Elle ne prend pas en charge de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="22b42-113">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-multicast-transformation"></a><span data-ttu-id="22b42-114">Configuration de la transformation de multidiffusion</span><span class="sxs-lookup"><span data-stu-id="22b42-114">Configuration of the Multicast Transformation</span></span>  
 <span data-ttu-id="22b42-115">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="22b42-115">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="22b42-116">Pour plus d’informations sur les propriétés que vous pouvez définir dans la boîte de dialogue **Éditeur de transformation de multidiffusion** , consultez [Éditeur de transformation de multidiffusion](../../multicast-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="22b42-116">For information about the properties that you can set in the **Multicast Transformation Editor** dialog box, see [Multicast Transformation Editor](../../multicast-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="22b42-117">Pour plus d’informations sur les propriétés que vous pouvez définir par programmation, consultez [Propriétés communes](../../common-properties.md).</span><span class="sxs-lookup"><span data-stu-id="22b42-117">For information about the properties that you can set programmatically, see [Common Properties](../../common-properties.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="22b42-118">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="22b42-118">Related Tasks</span></span>  
 <span data-ttu-id="22b42-119">Pour plus d’informations sur la définition des propriétés de ce composant, consultez [Définir les propriétés d’un composant de flux de données](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="22b42-119">For information about how to set properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22b42-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="22b42-120">See Also</span></span>  
 <span data-ttu-id="22b42-121">[Flux de données](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="22b42-121">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="22b42-122">Transformations Integration Services</span><span class="sxs-lookup"><span data-stu-id="22b42-122">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
