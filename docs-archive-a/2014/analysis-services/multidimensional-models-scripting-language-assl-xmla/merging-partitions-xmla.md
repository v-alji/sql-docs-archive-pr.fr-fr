---
title: Fusion de partitions (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- merging partitions [XMLA]
- XMLA, partitions
- partitions [Analysis Services], XML for Analysis
- XML for Analysis, partitions
ms.assetid: 657e1d4d-6d50-40f8-a771-7b20c9d865f8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 65840066d3e95571db511a2015a1bee64aa8d922
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604212"
---
# <a name="merging-partitions-xmla"></a><span data-ttu-id="3eacd-102">Fusion de partitions (XMLA)</span><span class="sxs-lookup"><span data-stu-id="3eacd-102">Merging Partitions (XMLA)</span></span>
  <span data-ttu-id="3eacd-103">Si les partitions ont la même conception d’agrégation et la même structure, vous pouvez fusionner la partition à l’aide de la commande [MergePartitions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/mergepartitions-element-xmla) dans XML for Analysis (XMLA).</span><span class="sxs-lookup"><span data-stu-id="3eacd-103">If partitions have the same aggregation design and structure, you can merge the partition by using the [MergePartitions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/mergepartitions-element-xmla) command in XML for Analysis (XMLA).</span></span> <span data-ttu-id="3eacd-104">Dans le cadre de la gestion des partitions, il est important de fusionner les partitions, plus particulièrement les partitions qui contiennent des données historiques partitionnées par date.</span><span class="sxs-lookup"><span data-stu-id="3eacd-104">Merging partitions is an important action to perform when you manage partitions, especially those partitions that contain historical data partitioned by date.</span></span>  
  
 <span data-ttu-id="3eacd-105">Par exemple, un cube financier peut utiliser deux partitions :</span><span class="sxs-lookup"><span data-stu-id="3eacd-105">For example, a financial cube may use two partitions:</span></span>  
  
-   <span data-ttu-id="3eacd-106">une partition qui représente les données financières de l'exercice en cours, utilisant des paramètres de stockage ROLAP (Relational ROLAP) en temps réel pour les performances ;</span><span class="sxs-lookup"><span data-stu-id="3eacd-106">One partition represents financial data for the current year, using real-time relational OLAP (ROLAP) storage settings for performance.</span></span>  
  
-   <span data-ttu-id="3eacd-107">une autre partition qui contient les données financières des exercices précédents, utilisant des paramètres de stockage MOLAP (Multidimensional OLAP) pour le stockage.</span><span class="sxs-lookup"><span data-stu-id="3eacd-107">Another partition contains financial data for previous years, using multidimensional OLAP (MOLAP) storage settings for storage.</span></span>  
  
 <span data-ttu-id="3eacd-108">Les deux partitions utilisent des paramètres de stockage différents, mais elles partagent la même conception d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="3eacd-108">Both partitions use different storage settings, but use the same aggregation design.</span></span> <span data-ttu-id="3eacd-109">Au lieu de traiter le cube avec plusieurs années de données historiques à la fin de l'exercice, vous pouvez utiliser la commande `MergePartitions` pour fusionner la partition de l'exercice en cours dans la partition des exercices précédents.</span><span class="sxs-lookup"><span data-stu-id="3eacd-109">Instead of processing the cube across years of historical data at the end of the year, you can instead use the `MergePartitions` command to merge the partition for the current year into the partition for previous years.</span></span> <span data-ttu-id="3eacd-110">Cela préserve les données d'agrégation sans qu'il soit nécessaire de traiter entièrement le cube, une opération qui peut s'avérer fastidieuse.</span><span class="sxs-lookup"><span data-stu-id="3eacd-110">This preserves the aggregation data without requiring a potentially time-consuming full processing of the cube.</span></span>  
  
## <a name="specifying-partitions-to-merge"></a><span data-ttu-id="3eacd-111">Spécification des partitions à fusionner</span><span class="sxs-lookup"><span data-stu-id="3eacd-111">Specifying Partitions to Merge</span></span>  
 <span data-ttu-id="3eacd-112">Lorsque la `MergePartitions` commande s’exécute, les données d’agrégation stockées dans les partitions sources spécifiées dans la propriété [source](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla) sont ajoutées à la partition cible spécifiée dans la propriété [cible](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/target-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="3eacd-112">When the `MergePartitions` command runs, the aggregation data stored in the source partitions specified in the [Source](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla) property is added to the target partition specified in the [Target](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/target-element-xmla) property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3eacd-113">La propriété `Source` peut contenir plusieurs références d'objet partition.</span><span class="sxs-lookup"><span data-stu-id="3eacd-113">The `Source` property can contain more than one partition object reference.</span></span> <span data-ttu-id="3eacd-114">En revanche, la propriété `Target` ne le peut pas.</span><span class="sxs-lookup"><span data-stu-id="3eacd-114">However, the `Target` property cannot.</span></span>  
  
 <span data-ttu-id="3eacd-115">Pour que la fusion aboutisse, les partitions spécifiées à la fois dans `Source` et `Target` doivent être contenues dans le même groupe de mesures et utiliser la même conception d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="3eacd-115">To be successfully merged, the partitions specified in both the `Source` and `Target` must be contained by the same measure group and use the same aggregation design.</span></span> <span data-ttu-id="3eacd-116">Sinon, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="3eacd-116">Otherwise, an error occurs.</span></span>  
  
 <span data-ttu-id="3eacd-117">Les partitions spécifiées dans `Source` sont supprimées une fois que la commande `MergePartitions` a abouti.</span><span class="sxs-lookup"><span data-stu-id="3eacd-117">The partitions specified in the `Source` are deleted after the `MergePartitions` command is successfully completed.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3eacd-118">Exemples</span><span class="sxs-lookup"><span data-stu-id="3eacd-118">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="3eacd-119">Description</span><span class="sxs-lookup"><span data-stu-id="3eacd-119">Description</span></span>  
 <span data-ttu-id="3eacd-120">L’exemple suivant fusionne toutes les partitions du groupe de mesures **Customer Counts** du cube **Adventure Works** de l’exemple de base de données **Adventure Works DW** dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] la partition **Customers_2004** .</span><span class="sxs-lookup"><span data-stu-id="3eacd-120">The following example merges all the partitions in the **Customer Counts** measure group of the **Adventure Works** cube in the **Adventure Works DW** sample [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database into the **Customers_2004** partition.</span></span>  
  
### <a name="code"></a><span data-ttu-id="3eacd-121">Code</span><span class="sxs-lookup"><span data-stu-id="3eacd-121">Code</span></span>  
  
```  
<MergePartitions xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Sources>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2001</PartitionID>  
    </Source>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2002</PartitionID>  
    </Source>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2003</PartitionID>  
    </Source>  
  </Sources>  
  <Target>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    <CubeID>Adventure Works DW</CubeID>  
    <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
    <PartitionID>Internet_Sales_2004</PartitionID>  
  </Target>  
</MergePartitions>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3eacd-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3eacd-122">See Also</span></span>  
 [<span data-ttu-id="3eacd-123">Développement avec XMLA dans Analysis Services</span><span class="sxs-lookup"><span data-stu-id="3eacd-123">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
