---
title: Colonnes classifiées (exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content types [data mining]
- STDEV column
- VARIANCE column
- PROBABLILITY column
- PROBABILITY_STDEV column
- columns [data mining], classified
- classified columns [data mining]
- PROBABILITY_VARIANCE column
- SUPPORT column
ms.assetid: 68bf3b78-dc12-497c-898f-b43a45646123
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5c264dfb6a97b8b8f576966e8929f6b0dc51e4ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612633"
---
# <a name="classified-columns-data-mining"></a><span data-ttu-id="299ae-102">Colonnes classifiées (exploration de données)</span><span class="sxs-lookup"><span data-stu-id="299ae-102">Classified Columns (Data Mining)</span></span>
  <span data-ttu-id="299ae-103">Lorsque vous définissez une colonne classée, vous créez une relation entre la colonne actuelle et une autre colonne de la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="299ae-103">When you define a classified column, you create a relationship between the current column and another column in the mining structure.</span></span> <span data-ttu-id="299ae-104">Les données de la colonne de structure d'exploration de données que vous désignez comme colonne classée contiennent des informations catégorielles qui décrivent les valeurs dans une autre colonne de la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="299ae-104">The data in the mining structure column that you designate as the classified column contains categorical information that describes the values in another column in the mining structure.</span></span>  
  
 <span data-ttu-id="299ae-105">Par exemple, vous avez deux colonnes avec des données numériques : une colonne, [achats annuels], contient tous les achats annuels par client pour une année civile spécifique, et l’autre colonne, [écarts types], contient les écarts types de ces valeurs.</span><span class="sxs-lookup"><span data-stu-id="299ae-105">For example, suppose you have two columns with numerical data: one column, [Yearly Purchases], contains the total yearly purchases per customer for a specific calendar year, and the other column, [Standard Deviations], contains the standard deviations for those values.</span></span> <span data-ttu-id="299ae-106">Dans ce cas, vous pouvez indiquer la colonne [achats annuels] comme colonne classifiée, et le modèle peut utiliser cette relation dans l’analyse.</span><span class="sxs-lookup"><span data-stu-id="299ae-106">In this case you could designate the [Yearly Purchases] column as the classified column, and the model would be able to use this relationship in analysis.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="299ae-107">Les algorithmes fournis dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ne prennent pas en charge l’utilisation des colonnes classifiées ; cette fonctionnalité est fournie pour une utilisation dans la création d’algorithmes personnalisés.</span><span class="sxs-lookup"><span data-stu-id="299ae-107">The algorithms provided in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] do not support the use of classified columns; this feature is provided for use in creating custom algorithms.</span></span>  
  
## <a name="defining-a-classified-column"></a><span data-ttu-id="299ae-108">Définition d'une colonne classée</span><span class="sxs-lookup"><span data-stu-id="299ae-108">Defining a Classified Column</span></span>  
 <span data-ttu-id="299ae-109">Le type de données d'une colonne classée doit être `Long` ou `Double`.</span><span class="sxs-lookup"><span data-stu-id="299ae-109">The data type of a classified column must be either `Long` or `Double`.</span></span>  
  
 <span data-ttu-id="299ae-110">La liste suivante décrit les types de contenu pris en charge par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour les colonnes classifiées.</span><span class="sxs-lookup"><span data-stu-id="299ae-110">The following list describes the content types that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supports for classified columns.</span></span>  
  
 <span data-ttu-id="299ae-111">**PROBABILITY**</span><span class="sxs-lookup"><span data-stu-id="299ae-111">**PROBABILITY**</span></span>  
 <span data-ttu-id="299ae-112">La valeur de la colonne représente la probabilité de la valeur associée et est comprise entre 0 et 1.</span><span class="sxs-lookup"><span data-stu-id="299ae-112">The value in the column is the probability of the associated value, and is a number between 0 and 1.</span></span>  
  
 <span data-ttu-id="299ae-113">**TABLEAUX**</span><span class="sxs-lookup"><span data-stu-id="299ae-113">**VARIANCE**</span></span>  
 <span data-ttu-id="299ae-114">La valeur de la colonne représente la variance de la valeur associée.</span><span class="sxs-lookup"><span data-stu-id="299ae-114">The value in the column is the variance of the associated value.</span></span>  
  
 <span data-ttu-id="299ae-115">**STDEV**</span><span class="sxs-lookup"><span data-stu-id="299ae-115">**STDEV**</span></span>  
 <span data-ttu-id="299ae-116">La valeur de la colonne représente l'écart type de la valeur associée.</span><span class="sxs-lookup"><span data-stu-id="299ae-116">The value in the column is the standard deviation of the associated value.</span></span>  
  
 <span data-ttu-id="299ae-117">**PROBABILITY_VARIANCE**</span><span class="sxs-lookup"><span data-stu-id="299ae-117">**PROBABILITY_VARIANCE**</span></span>  
 <span data-ttu-id="299ae-118">La valeur de la colonne représente la variance de la probabilité de la valeur associée.</span><span class="sxs-lookup"><span data-stu-id="299ae-118">The value in the column is the variance of the probability for the associated value.</span></span>  
  
 <span data-ttu-id="299ae-119">**PROBABILITY_STDEV**</span><span class="sxs-lookup"><span data-stu-id="299ae-119">**PROBABILITY_STDEV**</span></span>  
 <span data-ttu-id="299ae-120">La valeur de la colonne représente l'écart type de la probabilité de la valeur associée.</span><span class="sxs-lookup"><span data-stu-id="299ae-120">The value in the column is the standard deviation of the probability for the associated value.</span></span>  
  
 <span data-ttu-id="299ae-121">**SUPPORTER**</span><span class="sxs-lookup"><span data-stu-id="299ae-121">**SUPPORT**</span></span>  
 <span data-ttu-id="299ae-122">La valeur de la colonne représente le poids, ou facteur de réplication de cas, de la valeur associée.</span><span class="sxs-lookup"><span data-stu-id="299ae-122">The value in the column is the weight, or case replication factor, of the associated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="299ae-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="299ae-123">See Also</span></span>  
 <span data-ttu-id="299ae-124">[Types de contenu &#40;l’exploration de données&#41;](content-types-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="299ae-124">[Content Types &#40;Data Mining&#41;](content-types-data-mining.md) </span></span>  
 <span data-ttu-id="299ae-125">[Structures d’exploration de données &#40;Analysis Services d’exploration de données&#41;](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="299ae-125">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="299ae-126">Types de données &#40;Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="299ae-126">Data Types &#40;Data Mining&#41;</span></span>](data-types-data-mining.md)  
  
  
