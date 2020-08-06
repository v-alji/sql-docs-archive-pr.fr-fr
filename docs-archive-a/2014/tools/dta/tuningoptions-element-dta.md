---
title: Élément TuningOptions (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TuningOptions element
ms.assetid: 58a22ba1-8e03-411f-bd46-85e4540f217a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2fab1c55c9d036424142b2692e8335ea65c22340
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704556"
---
# <a name="tuningoptions-element-dta"></a><span data-ttu-id="576e3-102">TuningOptions, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="576e3-102">TuningOptions Element (DTA)</span></span>
  <span data-ttu-id="576e3-103">Contient les options de paramétrage pour une session de paramétrage spécifique.</span><span class="sxs-lookup"><span data-stu-id="576e3-103">Contains the tuning options for a specific tuning session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="576e3-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="576e3-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
...code removed...  
    <Workload>...</Workload>  
    <TuningOptions>...</TuningOptions>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="576e3-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="576e3-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="576e3-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="576e3-106">Characteristic</span></span>|<span data-ttu-id="576e3-107">Description</span><span class="sxs-lookup"><span data-stu-id="576e3-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="576e3-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="576e3-108">**Data type and length**</span></span>|<span data-ttu-id="576e3-109">Aucun.</span><span class="sxs-lookup"><span data-stu-id="576e3-109">None.</span></span>|  
|<span data-ttu-id="576e3-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="576e3-110">**Default value**</span></span>|<span data-ttu-id="576e3-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="576e3-111">None.</span></span>|  
|<span data-ttu-id="576e3-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="576e3-112">**Occurrence**</span></span>|<span data-ttu-id="576e3-113">facultatif.</span><span class="sxs-lookup"><span data-stu-id="576e3-113">Optional.</span></span> <span data-ttu-id="576e3-114">Si cet élément est utilisé, il ne peut être utilisé qu'une seule fois pour l'élément `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="576e3-114">If used, can only be used once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="576e3-115">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="576e3-115">Element Relationships</span></span>  
  
|<span data-ttu-id="576e3-116">Relation</span><span class="sxs-lookup"><span data-stu-id="576e3-116">Relationship</span></span>|<span data-ttu-id="576e3-117">Éléments</span><span class="sxs-lookup"><span data-stu-id="576e3-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="576e3-118">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="576e3-118">**Parent element**</span></span>|[<span data-ttu-id="576e3-119">DTAInput, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="576e3-119">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="576e3-120">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="576e3-120">**Child elements**</span></span>|<span data-ttu-id="576e3-121">Élément `ReportSet`.</span><span class="sxs-lookup"><span data-stu-id="576e3-121">`ReportSet` element.</span></span> <span data-ttu-id="576e3-122">Pour plus d'informations, consultez l'article [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="576e3-122">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="576e3-123">Élément `TuningLogTable`.</span><span class="sxs-lookup"><span data-stu-id="576e3-123">`TuningLogTable` element.</span></span> <span data-ttu-id="576e3-124">Pour plus d'informations, consultez l'article [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="576e3-124">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="576e3-125">Élément `NumberOfEvents`.</span><span class="sxs-lookup"><span data-stu-id="576e3-125">`NumberOfEvents` element.</span></span> <span data-ttu-id="576e3-126">Pour plus d'informations, consultez l'article [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="576e3-126">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> [<span data-ttu-id="576e3-127">TuningTimeInMin, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="576e3-127">TuningTimeInMin Element &#40;DTA&#41;</span></span>](tuningtimeinmin-element-dta.md)<br /><br /> [<span data-ttu-id="576e3-128">StorageBoundInMB, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="576e3-128">StorageBoundInMB Element &#40;DTA&#41;</span></span>](storageboundinmb-element-dta.md)<br /><br /> <span data-ttu-id="576e3-129">Élément `MaxKeyColumnsInIndex`.</span><span class="sxs-lookup"><span data-stu-id="576e3-129">`MaxKeyColumnsInIndex` element.</span></span> <span data-ttu-id="576e3-130">Pour plus d'informations, consultez l'article [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="576e3-130">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="576e3-131">Élément `MaxColumnsInIndex`.</span><span class="sxs-lookup"><span data-stu-id="576e3-131">`MaxColumnsInIndex` element.</span></span> <span data-ttu-id="576e3-132">Pour plus d'informations, consultez l'article [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="576e3-132">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="576e3-133">Élément `MinPercentageImprovement`.</span><span class="sxs-lookup"><span data-stu-id="576e3-133">`MinPercentageImprovement` element.</span></span> <span data-ttu-id="576e3-134">Pour plus d'informations, consultez le [schéma XML de l'Assistant Paramétrage du moteur de base de données](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="576e3-134">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100)</span></span><br /><br /> [<span data-ttu-id="576e3-135">TestServer, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="576e3-135">TestServer Element &#40;DTA&#41;</span></span>](server-element-dta.md)<br /><br /> [<span data-ttu-id="576e3-136">FeatureSet, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="576e3-136">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)<br /><br /> [<span data-ttu-id="576e3-137">Partitioning, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="576e3-137">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)<br /><br /> [<span data-ttu-id="576e3-138">DropOnlyMode, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="576e3-138">DropOnlyMode Element &#40;DTA&#41;</span></span>](droponlymode-element-dta.md)<br /><br /> [<span data-ttu-id="576e3-139">KeepExisting, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="576e3-139">KeepExisting Element &#40;DTA&#41;</span></span>](keepexisting-element-dta.md)<br /><br /> [<span data-ttu-id="576e3-140">OnlineIndexOperation, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="576e3-140">OnlineIndexOperation Element &#40;DTA&#41;</span></span>](onlineindexoperation-element-dta.md)<br /><br /> [<span data-ttu-id="576e3-141">DatabaseToConnect, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="576e3-141">DatabaseToConnect Element &#40;DTA&#41;</span></span>](databasetoconnect-element-dta.md)<br /><br /> <span data-ttu-id="576e3-142">Élément `IgnoreConstantsInWorkload`.</span><span class="sxs-lookup"><span data-stu-id="576e3-142">`IgnoreConstantsInWorkload` element.</span></span> <span data-ttu-id="576e3-143">Pour plus d'informations, consultez l'article [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="576e3-143">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="576e3-144">Élément `RetainShellDB`.</span><span class="sxs-lookup"><span data-stu-id="576e3-144">`RetainShellDB` element.</span></span> <span data-ttu-id="576e3-145">Pour plus d'informations, consultez l'article [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="576e3-145">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="576e3-146">Exemple</span><span class="sxs-lookup"><span data-stu-id="576e3-146">Example</span></span>  
 <span data-ttu-id="576e3-147">Pour obtenir des exemples de l' `TuningOptions` élément, consultez les [exemples de fichiers d’entrée XML &#40;DTA&#41;](xml-input-file-samples-dta.md).</span><span class="sxs-lookup"><span data-stu-id="576e3-147">For examples of the `TuningOptions` element, see the [XML Input File Samples &#40;DTA&#41;](xml-input-file-samples-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="576e3-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="576e3-148">See Also</span></span>  
 [<span data-ttu-id="576e3-149">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="576e3-149">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
