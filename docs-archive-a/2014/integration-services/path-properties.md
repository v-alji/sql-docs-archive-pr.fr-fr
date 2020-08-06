---
title: Propriétés du chemin d’accès | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- paths [Integration Services], properties
ms.assetid: 89b1e347-9579-4f6b-af74-c6519ea08eea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ca263b866fb6d5d7ceb6352f708f387d79cad4f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601544"
---
# <a name="path-properties"></a><span data-ttu-id="bd241-102">Propriétés du chemin d'accès</span><span class="sxs-lookup"><span data-stu-id="bd241-102">Path Properties</span></span>
  <span data-ttu-id="bd241-103">Les objets de Data Flow dans le [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] modèle objet ont des propriétés communes et des propriétés personnalisées au niveau du composant, des entrées et des sorties, ainsi que des colonnes d’entrée et de sortie.</span><span class="sxs-lookup"><span data-stu-id="bd241-103">The data flow objects in the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model have common properties and custom properties at the level of the component, inputs and outputs, and input columns and output columns.</span></span> <span data-ttu-id="bd241-104">De nombreuses propriétés ont des valeurs en lecture seule qui sont assignées au moment de l'exécution par le moteur de flux de données.</span><span class="sxs-lookup"><span data-stu-id="bd241-104">Many properties have read-only values that are assigned at run time by the data flow engine.</span></span>  
  
 <span data-ttu-id="bd241-105">Cette rubrique répertorie et décrit les propriétés personnalisées des chemins d'accès qui connectent des objets de flux de données.</span><span class="sxs-lookup"><span data-stu-id="bd241-105">This topic lists and describes the custom properties of the paths that connect data flow objects.</span></span>  
  
## <a name="path-properties"></a><span data-ttu-id="bd241-106">Propriétés du chemin d'accès</span><span class="sxs-lookup"><span data-stu-id="bd241-106">Path Properties</span></span>  
 <span data-ttu-id="bd241-107">Dans le modèle objet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], un chemin d'accès qui connecte des composants dans le flux de données implémente l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>.</span><span class="sxs-lookup"><span data-stu-id="bd241-107">In the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model, a path that connects components in the data flow implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> interface.</span></span>  
  
 <span data-ttu-id="bd241-108">Le tableau suivant décrit les propriétés configurables des chemins d'accès dans un flux de données.</span><span class="sxs-lookup"><span data-stu-id="bd241-108">The following table describes the configurable properties of the paths in a data flow.</span></span> <span data-ttu-id="bd241-109">Le moteur de flux de données assigne également des valeurs à d'autres propriétés en lecture seule qui ne sont pas répertoriées ici.</span><span class="sxs-lookup"><span data-stu-id="bd241-109">The data flow engine also assigns values to additional read-only properties that are not listed here.</span></span>  
  
|<span data-ttu-id="bd241-110">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="bd241-110">Property name</span></span>|<span data-ttu-id="bd241-111">Type de données</span><span class="sxs-lookup"><span data-stu-id="bd241-111">Data Type</span></span>|<span data-ttu-id="bd241-112">Description</span><span class="sxs-lookup"><span data-stu-id="bd241-112">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="bd241-113">PathAnnotation</span><span class="sxs-lookup"><span data-stu-id="bd241-113">PathAnnotation</span></span>|<span data-ttu-id="bd241-114">Integer (énumération)</span><span class="sxs-lookup"><span data-stu-id="bd241-114">Integer (enumeration)</span></span>|<span data-ttu-id="bd241-115">Valeur qui indique si une annotation doit être affichée avec le chemin d'accès sur l'aire du concepteur.</span><span class="sxs-lookup"><span data-stu-id="bd241-115">A value that indicates whether an annotation should be displayed with the path on the designer surface.</span></span> <span data-ttu-id="bd241-116">Les valeurs possibles sont `AsNeeded`, `SourceName`, `PathName` et `Never`.</span><span class="sxs-lookup"><span data-stu-id="bd241-116">The possible values are `AsNeeded`, `SourceName`, `PathName`, and `Never`.</span></span> <span data-ttu-id="bd241-117">La valeur par défaut est `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="bd241-117">The default value is `AsNeeded`.</span></span>|  
|<span data-ttu-id="bd241-118">DestinationName</span><span class="sxs-lookup"><span data-stu-id="bd241-118">DestinationName</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100>|<span data-ttu-id="bd241-119">Entrée associée au chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="bd241-119">The input associated with the path.</span></span>|  
|<span data-ttu-id="bd241-120">SourceName</span><span class="sxs-lookup"><span data-stu-id="bd241-120">SourceName</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100>|<span data-ttu-id="bd241-121">Sortie associée au chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="bd241-121">The output associated with the path.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd241-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bd241-122">See Also</span></span>  
 <span data-ttu-id="bd241-123">[Chemins Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="bd241-123">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 <span data-ttu-id="bd241-124">[Propriétés communes](../../2014/integration-services/common-properties.md) </span><span class="sxs-lookup"><span data-stu-id="bd241-124">[Common Properties](../../2014/integration-services/common-properties.md) </span></span>  
 <span data-ttu-id="bd241-125">[Transformation, propriétés personnalisées](data-flow/transformations/transformation-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="bd241-125">[Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md) </span></span>  
 [<span data-ttu-id="bd241-126">Propriétés du flux de données pouvant être définies à l’aide d’expressions</span><span class="sxs-lookup"><span data-stu-id="bd241-126">Data Flow Properties that Can Be Set by Using Expressions</span></span>](../../2014/integration-services/data-flow-properties-that-can-be-set-by-using-expressions.md)  
  
  
