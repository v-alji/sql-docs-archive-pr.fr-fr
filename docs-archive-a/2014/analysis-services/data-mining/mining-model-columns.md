---
title: Colonnes du modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], mining model columns
- columns [data mining]
- REGRESSOR column
- columns [data mining], modeling flags
- modeling flags [data mining]
- MODEL_EXISTENCE_ONLY column
- usage property [data mining]
ms.assetid: fab47643-5bfd-424e-a0f7-69e665db6bab
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f936f3f4e0b8f65326e9a6e84f75e6f4e82657f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700499"
---
# <a name="mining-model-columns"></a><span data-ttu-id="1cd2f-102">Colonnes d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="1cd2f-102">Mining Model Columns</span></span>
  <span data-ttu-id="1cd2f-103">Un modèle d'exploration de données applique un algorithme de modèle d'exploration de données aux données qui sont représentées par une structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-103">A data mining model applies a mining model algorithm to the data that is represented by a mining structure.</span></span> <span data-ttu-id="1cd2f-104">Comme la structure d'exploration de données, le modèle d'exploration de données contient des colonnes.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-104">Like the mining structure, the mining model contains columns.</span></span> <span data-ttu-id="1cd2f-105">Un modèle d'exploration de données est inclus dans la structure d'exploration de données et hérite de toutes les valeurs des propriétés définies par la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-105">A mining model is contained within the mining structure, and inherits all the values of the properties that are defined by the mining structure.</span></span> <span data-ttu-id="1cd2f-106">Le modèle peut utiliser toutes les colonnes que contient la structure d'exploration de données ou un sous-ensemble de ces colonnes.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-106">The model can use all the columns that the mining structure contains or a subset of the columns.</span></span>  
  
 <span data-ttu-id="1cd2f-107">Vous pouvez définir deux éléments d'informations supplémentaires sur une colonne de modèle d'exploration de données : l'utilisation et les indicateurs de modélisation.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-107">You can define two additional pieces of information on a mining model column: usage, and modeling flags.</span></span>  
  
-   <span data-ttu-id="1cd2f-108">**Utilisation** est une propriété qui définit la façon dont le modèle utilise la colonne.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-108">**Usage** is a property that defines how the model uses the column.</span></span> <span data-ttu-id="1cd2f-109">Les colonnes peuvent être utilisées en tant que colonnes d'entrée, que colonnes clés ou que colonnes prédictibles.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-109">Columns can be used as input columns, key columns, or predictable columns.</span></span>  
  
-   <span data-ttu-id="1cd2f-110">Les**indicateurs de modélisation** fournissent à l’algorithme des informations supplémentaires sur les données définies dans la table de cas, de sorte que l’algorithme puisse générer un modèle plus précis.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-110">**Modeling flags** provide the algorithm with additional information about the data that is defined in the case table, so that the algorithm can build a more accurate model.</span></span> <span data-ttu-id="1cd2f-111">Vous pouvez définir des indicateurs de modélisation par programmation en utilisant le langage DMX (Data Mining Extensions) ou le **Concepteur d’exploration de données** dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cd2f-111">You can define modeling flags programmatically by using the Data Mining Extensions (DMX) language, or in **Data Mining Designer** in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="1cd2f-112">La liste ci-dessous décrit les indicateurs de modélisation que vous pouvez définir sur une colonne de modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-112">The following list describes the modeling flags that you can define on a mining model column.</span></span>  
  
 `MODEL_EXISTENCE_ONLY`  
 <span data-ttu-id="1cd2f-113">Indique que la présence de l'attribut est plus importante que les valeurs incluses dans la colonne de l'attribut.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-113">Indicates that the presence of the attribute is more important than the values that are in the attribute column.</span></span> <span data-ttu-id="1cd2f-114">Par exemple, considérez une table de cas qui contient une liste d'articles associés à un client particulier.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-114">For example, consider a case table that contains a list of order items that are associated with a particular customer.</span></span> <span data-ttu-id="1cd2f-115">Les données de la table incluent le type de produit, l'ID et le coût de chaque élément.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-115">The table data includes the product type, ID, and cost of each item.</span></span> <span data-ttu-id="1cd2f-116">Pour la modélisation, le fait que le client ait acheté un article particulier peut être plus important que le coût de l'article.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-116">For modeling purposes, the fact that the customer purchased a particular order item may be more important than the cost of the order item itself.</span></span> <span data-ttu-id="1cd2f-117">Dans ce cas, la colonne de coût doit recevoir l'indicateur `MODEL_EXISTENCE_ONLY`.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-117">In this case, the cost column should be marked as `MODEL_EXISTENCE_ONLY`.</span></span>  
  
 `REGRESSOR`  
 <span data-ttu-id="1cd2f-118">Indique que l'algorithme peut utiliser la colonne spécifiée dans la formule de régression des algorithmes de régression.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-118">Indicates that the algorithm can use the specified column in the regression formula of regression algorithms.</span></span> <span data-ttu-id="1cd2f-119">Cet indicateur est pris en charge par les algorithmes MDT ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Decision Trees) et MTS ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series).</span><span class="sxs-lookup"><span data-stu-id="1cd2f-119">This flag is supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Decision Trees and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series algorithms.</span></span>  
  
 <span data-ttu-id="1cd2f-120">Pour plus d’informations sur la définition de la propriété Utilisation et la définition des indicateurs de modélisation par programmation à l’aide du langage DMX, consultez [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx).</span><span class="sxs-lookup"><span data-stu-id="1cd2f-120">For more information about setting the usage property and defining modeling flags programmatically with DMX, see [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx).</span></span> <span data-ttu-id="1cd2f-121">Pour plus d’informations sur la définition de la propriété Utilisation et la définition des indicateurs de modélisation dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], consultez [Déplacement d’objets d’exploration de données](moving-data-mining-objects.md).</span><span class="sxs-lookup"><span data-stu-id="1cd2f-121">For more information about setting the usage property and defining modeling flags in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Moving Data Mining Objects](moving-data-mining-objects.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd2f-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1cd2f-122">See Also</span></span>  
 <span data-ttu-id="1cd2f-123">[Algorithmes d’exploration de données &#40;Analysis Services d’exploration de données&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="1cd2f-123">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="1cd2f-124">[Structures d’exploration de données &#40;Analysis Services d’exploration de données&#41;](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="1cd2f-124">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="1cd2f-125">[Modifier les propriétés d’un modèle d’exploration de données](change-the-properties-of-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="1cd2f-125">[Change the Properties of a Mining Model](change-the-properties-of-a-mining-model.md) </span></span>  
 <span data-ttu-id="1cd2f-126">[Exclure une colonne d’un modèle d’exploration de données](exclude-a-column-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="1cd2f-126">[Exclude a Column from a Mining Model](exclude-a-column-from-a-mining-model.md) </span></span>  
 [<span data-ttu-id="1cd2f-127">Colonnes de structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="1cd2f-127">Mining Structure Columns</span></span>](mining-structure-columns.md)  
  
  
