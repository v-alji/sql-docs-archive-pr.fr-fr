---
title: Élément KeepExisting, (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- KeepExisting element
ms.assetid: e67aae61-d06d-4a03-85ba-6516c3502dce
author: stevestein
ms.author: sstein
ms.openlocfilehash: cde9b3091b75f55e4b9c79137853fbd7d4e0daf9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703628"
---
# <a name="keepexisting-element-dta"></a><span data-ttu-id="9365d-102">KeepExisting, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="9365d-102">KeepExisting Element (DTA)</span></span>
  <span data-ttu-id="9365d-103">Spécifie les structures PDS (index, vues indexées ou partitions) que l'Assistant Paramétrage du moteur de base de données doit conserver lors de la génération de sa recommandation.</span><span class="sxs-lookup"><span data-stu-id="9365d-103">Specifies the physical design structures (indexes, indexed views, or partitioning) that Database Engine Tuning Advisor must retain when generating its recommendation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9365d-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="9365d-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <KeepExisting>...</KeepExisting>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="9365d-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="9365d-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="9365d-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="9365d-106">Characteristic</span></span>|<span data-ttu-id="9365d-107">Description</span><span class="sxs-lookup"><span data-stu-id="9365d-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="9365d-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="9365d-108">**Data type and length**</span></span>|<span data-ttu-id="9365d-109">`string`, limite de longueur appliquée par le serveur.</span><span class="sxs-lookup"><span data-stu-id="9365d-109">`string`, length limit enforced by the server.</span></span>|  
|<span data-ttu-id="9365d-110">**Valeurs autorisées**</span><span class="sxs-lookup"><span data-stu-id="9365d-110">**Allowed values**</span></span>|<span data-ttu-id="9365d-111">**NONE**</span><span class="sxs-lookup"><span data-stu-id="9365d-111">**NONE**</span></span><br /> <span data-ttu-id="9365d-112">Aucune structure existante.</span><span class="sxs-lookup"><span data-stu-id="9365d-112">No existing structures.</span></span><br /><br /> <span data-ttu-id="9365d-113">**ALL**</span><span class="sxs-lookup"><span data-stu-id="9365d-113">**ALL**</span></span><br /> <span data-ttu-id="9365d-114">Toutes les structures existantes.</span><span class="sxs-lookup"><span data-stu-id="9365d-114">All existing structures.</span></span><br /><br /> <span data-ttu-id="9365d-115">**ALIGNED**</span><span class="sxs-lookup"><span data-stu-id="9365d-115">**ALIGNED**</span></span><br /> <span data-ttu-id="9365d-116">Toutes les structures alignées sur les partitions.</span><span class="sxs-lookup"><span data-stu-id="9365d-116">All partition-aligned structures.</span></span><br /><br /> <span data-ttu-id="9365d-117">**CL_IDX**</span><span class="sxs-lookup"><span data-stu-id="9365d-117">**CL_IDX**</span></span><br /> <span data-ttu-id="9365d-118">Tous les index cluster sur les tables.</span><span class="sxs-lookup"><span data-stu-id="9365d-118">All clustered indexes on tables.</span></span><br /><br /> <span data-ttu-id="9365d-119">**IDX**</span><span class="sxs-lookup"><span data-stu-id="9365d-119">**IDX**</span></span><br /> <span data-ttu-id="9365d-120">Tous les index cluster et non cluster sur les tables.</span><span class="sxs-lookup"><span data-stu-id="9365d-120">All clustered and nonclustered indexes on tables.</span></span><br /><br /> <span data-ttu-id="9365d-121">Utilisez une seule de ces valeurs avec cet élément.</span><span class="sxs-lookup"><span data-stu-id="9365d-121">Use only one of these values with this element.</span></span>|  
|<span data-ttu-id="9365d-122">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="9365d-122">**Default value**</span></span>|<span data-ttu-id="9365d-123">Aucun.</span><span class="sxs-lookup"><span data-stu-id="9365d-123">None.</span></span>|  
|<span data-ttu-id="9365d-124">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="9365d-124">**Occurrence**</span></span>|<span data-ttu-id="9365d-125">facultatif.</span><span class="sxs-lookup"><span data-stu-id="9365d-125">Optional.</span></span> <span data-ttu-id="9365d-126">Ne peut être utilisé qu'une seule fois pour chaque élément `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="9365d-126">Can use only once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="9365d-127">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="9365d-127">Element Relationships</span></span>  
  
|<span data-ttu-id="9365d-128">Relation</span><span class="sxs-lookup"><span data-stu-id="9365d-128">Relationship</span></span>|<span data-ttu-id="9365d-129">Éléments</span><span class="sxs-lookup"><span data-stu-id="9365d-129">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="9365d-130">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="9365d-130">**Parent element**</span></span>|[<span data-ttu-id="9365d-131">Élément TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="9365d-131">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="9365d-132">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="9365d-132">**Child elements**</span></span>|<span data-ttu-id="9365d-133">Aucun.</span><span class="sxs-lookup"><span data-stu-id="9365d-133">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9365d-134">Exemple</span><span class="sxs-lookup"><span data-stu-id="9365d-134">Example</span></span>  
 <span data-ttu-id="9365d-135">Pour obtenir un exemple d’utilisation de cet élément, consultez [Exemple de fichier d’entrée XML simple &#40;Assistant Paramétrage de base de données&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="9365d-135">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9365d-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9365d-136">See Also</span></span>  
 [<span data-ttu-id="9365d-137">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="9365d-137">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
