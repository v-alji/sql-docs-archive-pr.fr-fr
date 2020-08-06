---
title: Spécifier la clé et le type de la dimension (Assistant Dimension) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionkeyandtype.f1
ms.assetid: d7d5db55-36c3-45f6-ade3-29aa516589c1
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc08584ed12de8597b8289fd223cc47945d7d087
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612518"
---
# <a name="specify-dimension-key-and-type-dimension-wizard"></a><span data-ttu-id="27373-102">Spécifier la clé et le type de la dimension (Assistant Dimension)</span><span class="sxs-lookup"><span data-stu-id="27373-102">Specify Dimension Key and Type (Dimension Wizard)</span></span>
  <span data-ttu-id="27373-103">Utilisez la page **Spécifier la clé et le type de la dimension** pour définir l’attribut de clé de la dimension et indiquer si celle-ci est une dimension à variation lente (SCD).</span><span class="sxs-lookup"><span data-stu-id="27373-103">Use the **Specify Dimension Key and Type** page to define the key attribute of the dimension and to indicate whether the dimension is a slowly changing dimension (SCD).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27373-104">Cette page s’affiche uniquement si vous avez sélectionné **Construire la dimension sans utiliser de source de données** dans la page **Sélectionner la méthode de construction** et **Dimension standard** dans la page **Sélectionner le type de la dimension** .</span><span class="sxs-lookup"><span data-stu-id="27373-104">This page is displayed only if you selected **Build the dimension without using a data source** on the **Select Build Method** page and if you selected **Standard dimension** on the **Select the Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="27373-105">Options</span><span class="sxs-lookup"><span data-stu-id="27373-105">Options</span></span>  
 <span data-ttu-id="27373-106">**Attribut clé**</span><span class="sxs-lookup"><span data-stu-id="27373-106">**Key attribute**</span></span>  
 <span data-ttu-id="27373-107">Sélectionnez l'attribut clé de la dimension.</span><span class="sxs-lookup"><span data-stu-id="27373-107">Select the attribute that will be the key attribute for the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27373-108">Si aucun attribut n’est défini pour la dimension, la seule valeur disponible pour cette option est **Créez automatiquement l’attribut clé**.</span><span class="sxs-lookup"><span data-stu-id="27373-108">If no attributes have been defined for the dimension, the only value available for this option is **Create key attribute automatically.**</span></span> <span data-ttu-id="27373-109">Cette valeur n'est pas disponible si un ou plusieurs attributs sont définis pour la dimension.</span><span class="sxs-lookup"><span data-stu-id="27373-109">This value is not available if any attributes are defined for the dimension.</span></span>  
  
 <span data-ttu-id="27373-110">**Il s'agit d'une dimension variable**</span><span class="sxs-lookup"><span data-stu-id="27373-110">**This is a changing dimension**</span></span>  
 <span data-ttu-id="27373-111">Indique que la dimension est une dimension à variation lente.</span><span class="sxs-lookup"><span data-stu-id="27373-111">Select to indicate that the dimension is a slowly changing dimension.</span></span> <span data-ttu-id="27373-112">Cette option crée des colonnes et des attributs supplémentaires utilisables pour suivre dans le temps le mouvement des membres dans les hiérarchies de la dimension.</span><span class="sxs-lookup"><span data-stu-id="27373-112">Selecting this option will create additional columns and attributes that can be used to track the movement of members within the hierarchies of the dimension over time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27373-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="27373-113">See Also</span></span>  
 <span data-ttu-id="27373-114">[Aide (F1) de l’Assistant Dimension](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="27373-114">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="27373-115">[Dimensions &#40;Analysis Services-données multidimensionnelles&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="27373-115">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="27373-116">Dimensions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="27373-116">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
