---
title: Éditeur de transformation d’agrégation (onglet Avancé) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.aggregationtransformation.advanced.f1
helpviewer_keywords:
- Aggregate Transformation Editor
ms.assetid: 186a9736-2554-40a0-9cb2-877a8db5fde8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb3742a83f363f74004a5aac0eefc589ee2a5be2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602980"
---
# <a name="aggregate-transformation-editor-advanced-tab"></a><span data-ttu-id="7881c-102">Éditeur de transformation d'agrégation (onglet Avancé)</span><span class="sxs-lookup"><span data-stu-id="7881c-102">Aggregate Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="7881c-103">L’onglet **Avancé** de la boîte de dialogue **Éditeur de transformation d’agrégation** permet de définir les propriétés des composants, de spécifier des agrégations et de définir les propriétés des colonnes d’entrée et de sortie.</span><span class="sxs-lookup"><span data-stu-id="7881c-103">Use the **Advanced** tab of the **Aggregate Transformation Editor** dialog box to set component properties, specify aggregations, and set properties of input and output columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7881c-104">Les options concernant le nombre et l’échelle de clés d’une part, et le nombre et l’échelle de clés distinctes d’autre part, s’appliquent au niveau du composant quand ces options sont indiquées sous l’onglet **Avancé** , au niveau de la sortie quand elles sont précisées dans l’affichage avancé de l’onglet **Agrégations** , ou encore au niveau des colonnes quand elles sont spécifiées dans la liste de colonnes se trouvant dans la partie inférieure de l’onglet **Agrégations** .</span><span class="sxs-lookup"><span data-stu-id="7881c-104">The options for key count, key scale, distinct key count, and distinct key scale apply at the component level when specified on the **Advanced** tab, at the output level when specified in the advanced display of the **Aggregations** tab, and at the column level when specified in the column list at the bottom of the **Aggregations** tab.</span></span>  
>   
>  <span data-ttu-id="7881c-105">Dans la transformation d’agrégation, **Clés** et **Échelle de clé** font référence au nombre de groupes attendus d’une opération **Regrouper par** .</span><span class="sxs-lookup"><span data-stu-id="7881c-105">In the Aggregate transformation, **Keys** and **Keys scale** refer to the number of groups that are expected to result from a **Group by** operation.</span></span> <span data-ttu-id="7881c-106">**Nombre de clés distinctes** et **Échelle de nombre des valeurs distinctes** font référence au nombre de valeurs distinctes attendues d’une opération **Comptage de valeurs** .</span><span class="sxs-lookup"><span data-stu-id="7881c-106">**Count distinct keys** and **Count distinct scale** refer to the number of distinct values that are expected to result from a **Distinct count** operation.</span></span>  
  
 <span data-ttu-id="7881c-107">Pour en savoir plus sur la transformation d’agrégation, consultez [Transformation d’agrégation](data-flow/transformations/aggregate-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="7881c-107">To learn more about the Aggregate transformation, see [Aggregate Transformation](data-flow/transformations/aggregate-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7881c-108">Options</span><span class="sxs-lookup"><span data-stu-id="7881c-108">Options</span></span>  
 <span data-ttu-id="7881c-109">**Échelle de clé**</span><span class="sxs-lookup"><span data-stu-id="7881c-109">**Keys scale**</span></span>  
 <span data-ttu-id="7881c-110">Permet de spécifier le nombre approximatif de clés attendu par l'agrégation (facultatif).</span><span class="sxs-lookup"><span data-stu-id="7881c-110">Optionally specify the approximate number of keys that the aggregation expects.</span></span> <span data-ttu-id="7881c-111">La transformation utilise ces informations afin d'optimiser la taille initiale de son cache.</span><span class="sxs-lookup"><span data-stu-id="7881c-111">The transformation uses this information to optimize its initial cache size.</span></span> <span data-ttu-id="7881c-112">Par défaut, la valeur de cette option est **Non spécifié**.</span><span class="sxs-lookup"><span data-stu-id="7881c-112">By default, the value of this option is **Unspecified**.</span></span> <span data-ttu-id="7881c-113">Si les deux options **Échelle de clé** et **Nombre de clés** sont spécifiées, **Nombre de clés** est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="7881c-113">If both **Keys scale** and **Number of keys** are specified, **Number of keys** takes precedence.</span></span>  
  
|<span data-ttu-id="7881c-114">Valeur</span><span class="sxs-lookup"><span data-stu-id="7881c-114">Value</span></span>|<span data-ttu-id="7881c-115">Description</span><span class="sxs-lookup"><span data-stu-id="7881c-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7881c-116">Non spécifié</span><span class="sxs-lookup"><span data-stu-id="7881c-116">Unspecified</span></span>|<span data-ttu-id="7881c-117">La propriété **KeyScale** n’est pas utilisée.</span><span class="sxs-lookup"><span data-stu-id="7881c-117">The **Keys scale** property is not used.</span></span>|  
|<span data-ttu-id="7881c-118">Faible</span><span class="sxs-lookup"><span data-stu-id="7881c-118">Low</span></span>|<span data-ttu-id="7881c-119">L’agrégation peut écrire environ 500 000 clés.</span><span class="sxs-lookup"><span data-stu-id="7881c-119">Aggregation can write approximately 500,000 keys.</span></span>|  
|<span data-ttu-id="7881c-120">Moyenne</span><span class="sxs-lookup"><span data-stu-id="7881c-120">Medium</span></span>|<span data-ttu-id="7881c-121">L'agrégation peut écrire environ 5 000 000 clés.</span><span class="sxs-lookup"><span data-stu-id="7881c-121">Aggregation can write approximately 5,000,000 keys.</span></span>|  
|<span data-ttu-id="7881c-122">Importante</span><span class="sxs-lookup"><span data-stu-id="7881c-122">High</span></span>|<span data-ttu-id="7881c-123">L'agrégation peut écrire plus de 25 000 000 clés.</span><span class="sxs-lookup"><span data-stu-id="7881c-123">Aggregation can write more than 25,000,000 keys.</span></span>|  
  
 <span data-ttu-id="7881c-124">**Nombre de clés**</span><span class="sxs-lookup"><span data-stu-id="7881c-124">**Number of keys**</span></span>  
 <span data-ttu-id="7881c-125">Permet de spécifier le nombre exact de clés attendu par l'agrégation (facultatif).</span><span class="sxs-lookup"><span data-stu-id="7881c-125">Optionally specify the exact number of keys that the aggregation expects.</span></span> <span data-ttu-id="7881c-126">La transformation utilise ces informations afin d'optimiser la taille initiale de son cache.</span><span class="sxs-lookup"><span data-stu-id="7881c-126">The transformation uses this information to optimize its initial cache size.</span></span> <span data-ttu-id="7881c-127">Si les deux options **Échelle de clé** et **Nombre de clés** sont spécifiées, **Nombre de clés** est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="7881c-127">If both **Keys scale** and **Number of keys** are specified, **Number of keys** takes precedence.</span></span>  
  
 <span data-ttu-id="7881c-128">**Échelle de nombre des valeurs distinctes**</span><span class="sxs-lookup"><span data-stu-id="7881c-128">**Count distinct scale**</span></span>  
 <span data-ttu-id="7881c-129">Permet éventuellement de spécifier le nombre approximatif de valeurs distinctes que l'agrégation peut écrire.</span><span class="sxs-lookup"><span data-stu-id="7881c-129">Optionally specify the approximate number of distinct values that the aggregation can write.</span></span> <span data-ttu-id="7881c-130">Par défaut, la valeur de cette option est **Non spécifié**.</span><span class="sxs-lookup"><span data-stu-id="7881c-130">By default, the value of this option is **Unspecified**.</span></span> <span data-ttu-id="7881c-131">Si les deux options **Échelle de nombre des valeurs distinctes** et **Nombre de clés distinctes** sont spécifiées, **Nombre de clés distinctes** est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="7881c-131">If both **Count distinct scale** and **Count distinct keys** are specified, **Count distinct keys** takes precedence.</span></span>  
  
|<span data-ttu-id="7881c-132">Valeur</span><span class="sxs-lookup"><span data-stu-id="7881c-132">Value</span></span>|<span data-ttu-id="7881c-133">Description</span><span class="sxs-lookup"><span data-stu-id="7881c-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7881c-134">Non spécifié</span><span class="sxs-lookup"><span data-stu-id="7881c-134">Unspecified</span></span>|<span data-ttu-id="7881c-135">La propriété CountDistinctScale n'est pas utilisée.</span><span class="sxs-lookup"><span data-stu-id="7881c-135">The CountDistinctScale property is not used.</span></span>|  
|<span data-ttu-id="7881c-136">Faible</span><span class="sxs-lookup"><span data-stu-id="7881c-136">Low</span></span>|<span data-ttu-id="7881c-137">L'agrégation peut écrire environ 500 000 valeurs distinctes.</span><span class="sxs-lookup"><span data-stu-id="7881c-137">Aggregation can write approximately 500,000 distinct values.</span></span>|  
|<span data-ttu-id="7881c-138">Moyenne</span><span class="sxs-lookup"><span data-stu-id="7881c-138">Medium</span></span>|<span data-ttu-id="7881c-139">L’agrégation peut écrire environ 5 000 000 de valeurs distinctes.</span><span class="sxs-lookup"><span data-stu-id="7881c-139">Aggregation can write approximately 5,000,000 distinct values.</span></span>|  
|<span data-ttu-id="7881c-140">Importante</span><span class="sxs-lookup"><span data-stu-id="7881c-140">High</span></span>|<span data-ttu-id="7881c-141">L'agrégation peut écrire plus de 25 000 000 valeurs distinctes.</span><span class="sxs-lookup"><span data-stu-id="7881c-141">Aggregation can write more than 25,000,000 distinct values.</span></span>|  
  
 <span data-ttu-id="7881c-142">**Nombre de clés distinctes**</span><span class="sxs-lookup"><span data-stu-id="7881c-142">**Count distinct keys**</span></span>  
 <span data-ttu-id="7881c-143">Permet de spécifier éventuellement le nombre exact de valeurs distinctes que l'agrégation peut écrire.</span><span class="sxs-lookup"><span data-stu-id="7881c-143">Optionally specify the exact number of distinct values that the aggregation can write.</span></span> <span data-ttu-id="7881c-144">Si les deux options **Échelle de nombre des valeurs distinctes** et **Nombre de clés distinctes** sont spécifiées, **Nombre de clés distinctes** est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="7881c-144">If both **Count distinct scale** and **Count distinct keys** are specified, **Count distinct keys** takes precedence.</span></span>  
  
 <span data-ttu-id="7881c-145">**Facteur d'extension automatique**</span><span class="sxs-lookup"><span data-stu-id="7881c-145">**Auto extend factor**</span></span>  
 <span data-ttu-id="7881c-146">Utilisez une valeur comprise entre 1 et 100 afin de spécifier le pourcentage selon lequel la mémoire peut être étendue pendant l'agrégation.</span><span class="sxs-lookup"><span data-stu-id="7881c-146">Use a value between 1 and 100 to specify the percentage by which memory can be extended during the aggregation.</span></span> <span data-ttu-id="7881c-147">Par défaut, la valeur de cette option est **25 %**.</span><span class="sxs-lookup"><span data-stu-id="7881c-147">By default, the value of this option is **25%**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7881c-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7881c-148">See Also</span></span>  
 <span data-ttu-id="7881c-149">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7881c-149">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="7881c-150">[Éditeur de transformation d’agrégation &#40;onglet Agrégations&#41;](../../2014/integration-services/aggregate-transformation-editor-aggregations-tab.md) </span><span class="sxs-lookup"><span data-stu-id="7881c-150">[Aggregate Transformation Editor &#40;Aggregations Tab&#41;](../../2014/integration-services/aggregate-transformation-editor-aggregations-tab.md) </span></span>  
 [<span data-ttu-id="7881c-151">Agréger les valeurs dans un dataset à l'aide de la transformation d'agrégation</span><span class="sxs-lookup"><span data-stu-id="7881c-151">Aggregate Values in a Dataset by Using the Aggregate Transformation</span></span>](data-flow/transformations/aggregate-values-in-a-dataset-by-using-the-aggregate-transformation.md)  
  
  
