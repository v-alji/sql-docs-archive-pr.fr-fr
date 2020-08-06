---
title: Élément FeatureSet, (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- FeatureSet element
ms.assetid: f2070c53-4a5c-4c11-ac38-96ee200c84f0
author: stevestein
ms.author: sstein
ms.openlocfilehash: d36c28b24a56ef2dcdf69578fb7e8c196306a416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705767"
---
# <a name="featureset-element-dta"></a><span data-ttu-id="c332c-102">FeatureSet, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="c332c-102">FeatureSet Element (DTA)</span></span>
  <span data-ttu-id="c332c-103">Contient les structures PDS (index ou vues indexées) que vous aimeriez que l'Assistant Paramétrage du moteur de base de données utilise durant l'analyse.</span><span class="sxs-lookup"><span data-stu-id="c332c-103">Contains the physical design structures (indexes or indexed views) that you would like Database Engine Tuning Advisor to use during analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c332c-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c332c-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <FeatureSet>...</FeatureSet>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="c332c-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="c332c-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="c332c-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="c332c-106">Characteristic</span></span>|<span data-ttu-id="c332c-107">Description</span><span class="sxs-lookup"><span data-stu-id="c332c-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="c332c-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="c332c-108">**Data type and length**</span></span>|<span data-ttu-id="c332c-109">`string`, aucune longueur maximale.</span><span class="sxs-lookup"><span data-stu-id="c332c-109">`string`, no maximum length.</span></span>|  
|<span data-ttu-id="c332c-110">**Valeurs autorisées**</span><span class="sxs-lookup"><span data-stu-id="c332c-110">**Allowed values**</span></span>|<span data-ttu-id="c332c-111">**IDX_IV**</span><span class="sxs-lookup"><span data-stu-id="c332c-111">**IDX_IV**</span></span><br /> <span data-ttu-id="c332c-112">Index et vues indexées.</span><span class="sxs-lookup"><span data-stu-id="c332c-112">Indexes and indexed views.</span></span><br /><br /> <span data-ttu-id="c332c-113">**IDX**</span><span class="sxs-lookup"><span data-stu-id="c332c-113">**IDX**</span></span><br /> <span data-ttu-id="c332c-114">Index uniquement.</span><span class="sxs-lookup"><span data-stu-id="c332c-114">Indexes only.</span></span><br /><br /> <span data-ttu-id="c332c-115">**IV**</span><span class="sxs-lookup"><span data-stu-id="c332c-115">**IV**</span></span><br /> <span data-ttu-id="c332c-116">Vues indexées uniquement.</span><span class="sxs-lookup"><span data-stu-id="c332c-116">Indexed views only.</span></span><br /><br /> <span data-ttu-id="c332c-117">**NCL_IDX**</span><span class="sxs-lookup"><span data-stu-id="c332c-117">**NCL_IDX**</span></span><br /> <span data-ttu-id="c332c-118">Index non-cluster uniquement.</span><span class="sxs-lookup"><span data-stu-id="c332c-118">Nonclustered indexes only.</span></span><br /><br /> <span data-ttu-id="c332c-119">Utilisez une de ces valeurs avec cet élément.</span><span class="sxs-lookup"><span data-stu-id="c332c-119">Use one of these values with this element.</span></span>|  
|<span data-ttu-id="c332c-120">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="c332c-120">**Default value**</span></span>|<span data-ttu-id="c332c-121">**IDX**</span><span class="sxs-lookup"><span data-stu-id="c332c-121">**IDX**</span></span>|  
|<span data-ttu-id="c332c-122">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="c332c-122">**Occurrence**</span></span>|<span data-ttu-id="c332c-123">Obligatoire une fois pour chaque élément `TuningOptions`, excepté si l'élément `DropOnlyMode` est utilisé.</span><span class="sxs-lookup"><span data-stu-id="c332c-123">Required once for each `TuningOptions` element, unless the `DropOnlyMode` element is used.</span></span> <span data-ttu-id="c332c-124">Si l'élément `DropOnlyMode` est utilisé, vous ne pouvez pas utiliser l'élément `FeatureSet`.</span><span class="sxs-lookup"><span data-stu-id="c332c-124">If `DropOnlyMode` is used, you cannot use `FeatureSet`.</span></span> <span data-ttu-id="c332c-125">Ces éléments s'excluent mutuellement.</span><span class="sxs-lookup"><span data-stu-id="c332c-125">These elements are mutually exclusive.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="c332c-126">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="c332c-126">Element Relationships</span></span>  
  
|<span data-ttu-id="c332c-127">Relation</span><span class="sxs-lookup"><span data-stu-id="c332c-127">Relationship</span></span>|<span data-ttu-id="c332c-128">Éléments</span><span class="sxs-lookup"><span data-stu-id="c332c-128">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="c332c-129">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="c332c-129">**Parent element**</span></span>|[<span data-ttu-id="c332c-130">Élément TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="c332c-130">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="c332c-131">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="c332c-131">**Child elements**</span></span>|<span data-ttu-id="c332c-132">Aucun.</span><span class="sxs-lookup"><span data-stu-id="c332c-132">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c332c-133">Exemple</span><span class="sxs-lookup"><span data-stu-id="c332c-133">Example</span></span>  
 <span data-ttu-id="c332c-134">Pour obtenir un exemple d’utilisation de cet élément, consultez [Exemple de fichier d’entrée XML simple &#40;Assistant Paramétrage de base de données&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="c332c-134">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c332c-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c332c-135">See Also</span></span>  
 [<span data-ttu-id="c332c-136">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="c332c-136">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
