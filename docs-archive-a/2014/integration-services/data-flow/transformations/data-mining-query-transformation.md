---
title: Requête d’exploration de données, transformation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingquerytrans.f1
helpviewer_keywords:
- Data Mining Query transformation
- prediction queries [Integration Services]
ms.assetid: 7960133b-a3e1-48af-ba43-55ed78c38e71
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 278fdc3b1abd38b63f01e967e28d11983a09e682
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601020"
---
# <a name="data-mining-query-transformation"></a><span data-ttu-id="f1e3c-102">transformation de requête d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f1e3c-102">Data Mining Query Transformation</span></span>
  <span data-ttu-id="f1e3c-103">La transformation de requête d'exploration de données effectue des requêtes de prédiction par rapport aux modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="f1e3c-103">The Data Mining Query transformation performs prediction queries against data mining models.</span></span> <span data-ttu-id="f1e3c-104">Cette transformation contient un générateur de requêtes qui permet de créer des requêtes DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="f1e3c-104">This transformation contains a query builder for creating Data Mining Extensions (DMX) queries.</span></span> <span data-ttu-id="f1e3c-105">Le générateur de requêtes vous permet de créer des instructions personnalisées afin d'évaluer les données d'entrée de la transformation par rapport à un modèle d'exploration de données existant à l'aide du langage DMX.</span><span class="sxs-lookup"><span data-stu-id="f1e3c-105">The query builder lets you create custom statements for evaluating the transformation input data against an existing mining model using the DMX language.</span></span> <span data-ttu-id="f1e3c-106">Pour plus d’informations, consultez [Guide de référence du langage DMX & #40;Data Mining Extensions&#41;](/sql/dmx/data-mining-extensions-dmx-reference).</span><span class="sxs-lookup"><span data-stu-id="f1e3c-106">For more information, see [Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference).</span></span>  
  
 <span data-ttu-id="f1e3c-107">Une transformation peut exécuter plusieurs requêtes de prédiction si les modèles sont basés sur la même structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="f1e3c-107">One transformation can execute multiple prediction queries if the models are built on the same data mining structure.</span></span> <span data-ttu-id="f1e3c-108">Pour plus d’informations, consultez [interfaces de requête d’exploration de données](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools).</span><span class="sxs-lookup"><span data-stu-id="f1e3c-108">For more information, see [Data Mining Query Interfaces](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools).</span></span>  
  
## <a name="configuration-of-the-data-mining-query-transformation"></a><span data-ttu-id="f1e3c-109">Configuration de la transformation de requête d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="f1e3c-109">Configuration of the Data Mining Query Transformation</span></span>  
 <span data-ttu-id="f1e3c-110">La transformation de requête d’exploration de données utilise un gestionnaire de connexions [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] pour se connecter au projet [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] ou à l’instance de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] qui contient la structure et les modèles d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="f1e3c-110">The Data Mining Query transformation uses an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] that contains the mining structure and mining models.</span></span> <span data-ttu-id="f1e3c-111">Pour plus d'informations, consultez [Analysis Services Connection Manager](../../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f1e3c-111">For more information, see [Analysis Services Connection Manager](../../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="f1e3c-112">Cette transformation a une entrée et une sortie.</span><span class="sxs-lookup"><span data-stu-id="f1e3c-112">This transformation has one input and one output.</span></span> <span data-ttu-id="f1e3c-113">Elle ne prend pas en charge de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="f1e3c-113">It does not support an error output.</span></span>  
  
 <span data-ttu-id="f1e3c-114">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="f1e3c-114">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="f1e3c-115">Pour plus d’informations sur les propriétés que vous pouvez définir dans la boîte de dialogue **Éditeur de transformation de requête d’exploration de données**, cliquez sur l’une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="f1e3c-115">For more information about the properties that you can set in the **Data Mining Query Transformation Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f1e3c-116">Éditeur de transformation de requête d’exploration de données &#40;onglet Modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f1e3c-116">Data Mining Query Transformation Editor &#40;Mining Model Tab&#41;</span></span>](../../data-mining-query-transformation-editor-mining-model-tab.md)  
  
-   [<span data-ttu-id="f1e3c-117">Éditeur de transformation de requête d’exploration de données &#40;onglet Modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f1e3c-117">Data Mining Query Transformation Editor &#40;Mining Model Tab&#41;</span></span>](../../data-mining-query-transformation-editor-mining-model-tab.md)  
  
 <span data-ttu-id="f1e3c-118">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="f1e3c-118">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="f1e3c-119">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="f1e3c-119">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f1e3c-120">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="f1e3c-120">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="f1e3c-121">Propriétés personnalisées des transformations</span><span class="sxs-lookup"><span data-stu-id="f1e3c-121">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="f1e3c-122">Pour plus d’informations sur la façon de définir les propriétés, consultez [Définir les propriétés d’un composant de flux de données](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="f1e3c-122">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
