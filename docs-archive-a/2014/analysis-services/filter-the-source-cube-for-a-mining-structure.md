---
title: Filtrer le cube source d’une structure d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slice cubes [Analysis Services]
- mining structures [Analysis Services], filtering source cube
- cubes [Analysis Services], slicing
- filtering data [Analysis Services]
ms.assetid: 05dce7e1-2fe5-4500-bacf-c1a8a76e1424
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61409b4803f43d3ff2634daaba65a92bc343db36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602436"
---
# <a name="filter-the-source-cube-for-a-mining-structure"></a><span data-ttu-id="b8383-102">Filtrer le cube source d'une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="b8383-102">Filter the Source Cube for a Mining Structure</span></span>
  <span data-ttu-id="b8383-103">Lorsque vous créez une structure d’exploration de données basée sur des données dans un modèle multidimensionnel (un cube OLAP), vous pouvez *découper* le cube sur lequel la structure d’exploration de données est basée.</span><span class="sxs-lookup"><span data-stu-id="b8383-103">When you create a mining structure that is based on data in a multidimensional model (an OLAP cube), you can *slice* the cube that the mining structure is based on.</span></span> <span data-ttu-id="b8383-104">Le découpage vous permet de créer des sous-ensembles de données, comme un genre de filtre sur les données utilisées pour l'apprentissage du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="b8383-104">Slicing lets you create subsets of data, as a kind of filter on the data that is used to train the mining model.</span></span>  
  
### <a name="to-slice-a-cube"></a><span data-ttu-id="b8383-105">Pour découper un cube</span><span class="sxs-lookup"><span data-stu-id="b8383-105">To slice a cube</span></span>  
  
1.  <span data-ttu-id="b8383-106">Dans le concepteur d’exploration de données de [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , sélectionnez l’onglet **structure d’exploration** de données ou l’onglet **modèles d’exploration** de données.</span><span class="sxs-lookup"><span data-stu-id="b8383-106">In Data Mining Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], select the **Mining Structure** tab or the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="b8383-107">Dans le menu **modèle d’exploration de données** , sélectionnez définir la structure d’exploration de **données tranche de cube**.</span><span class="sxs-lookup"><span data-stu-id="b8383-107">On the **Mining Model** menu, select **Define Mining Structure Cube Slice**.</span></span>  
  
     <span data-ttu-id="b8383-108">La boîte de dialogue **découper le cube** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="b8383-108">The **Slice Cube** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="b8383-109">Dans la colonne **dimension** de la boîte de dialogue **découper le cube** , sélectionnez la dimension que vous souhaitez filtrer.</span><span class="sxs-lookup"><span data-stu-id="b8383-109">In the **Dimension** column of the **Slice Cube** dialog box, select the dimension that you want to filter.</span></span>  
  
4.  <span data-ttu-id="b8383-110">Sélectionnez un niveau d’une hiérarchie à l’aide de la liste dans la colonne **hiérarchie** .</span><span class="sxs-lookup"><span data-stu-id="b8383-110">Select a level of a hierarchy, using the list in the **Hierarchy** column.</span></span>  
  
5.  <span data-ttu-id="b8383-111">Sélectionnez un opérateur dans la liste de la colonne **opérateur** , à utiliser lors de la création de la condition de filtre.</span><span class="sxs-lookup"><span data-stu-id="b8383-111">Select an operator from the list in the **Operator** column, to use in building the filter condition.</span></span>  
  
6.  <span data-ttu-id="b8383-112">Cliquez sur la zone dans la colonne **filtre** .</span><span class="sxs-lookup"><span data-stu-id="b8383-112">Click the box in the **Filter** column.</span></span>  
  
     <span data-ttu-id="b8383-113">Une boîte de dialogue s'ouvre avec tous les membres au niveau spécifié de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="b8383-113">A dialog box opens that contains all the members at the specified level of the hierarchy.</span></span>  
  
7.  <span data-ttu-id="b8383-114">Sélectionnez le membre ou les membres à filtrer.</span><span class="sxs-lookup"><span data-stu-id="b8383-114">Select the member or members on which you want to filter.</span></span>  
  
8.  <span data-ttu-id="b8383-115">Cliquez sur **OK** dans la boîte de dialogue membre.</span><span class="sxs-lookup"><span data-stu-id="b8383-115">Click **OK** in the member dialog box.</span></span>  
  
9. <span data-ttu-id="b8383-116">Cliquez sur **OK** dans la boîte de dialogue **découper le cube** .</span><span class="sxs-lookup"><span data-stu-id="b8383-116">Click **OK** in the **Slice Cube** dialog box.</span></span>  
  
     <span data-ttu-id="b8383-117">Le cube source est filtré comme défini par la coupe de cube.</span><span class="sxs-lookup"><span data-stu-id="b8383-117">The source cube is now filtered as defined by the cube slice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8383-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b8383-118">See Also</span></span>  
 <span data-ttu-id="b8383-119">[Tâches de la structure d’exploration de données et procédures](data-mining/mining-structure-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="b8383-119">[Mining Structure Tasks and How-tos](data-mining/mining-structure-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="b8383-120">Créer une structure d’exploration de données OLAP</span><span class="sxs-lookup"><span data-stu-id="b8383-120">Create a New OLAP Mining Structure</span></span>](data-mining/create-a-new-olap-mining-structure.md)  
  
  
