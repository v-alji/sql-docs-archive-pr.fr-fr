---
title: Élément OnlineIndexOperation, (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- OnlineIndexOperation element
ms.assetid: 7c5614cd-09aa-4a59-9591-347aa7d36473
author: stevestein
ms.author: sstein
ms.openlocfilehash: 48943c1b31d7a0a24ae939050d44494476e50034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612052"
---
# <a name="onlineindexoperation-element-dta"></a><span data-ttu-id="7b11d-102">OnlineIndexOperation, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="7b11d-102">OnlineIndexOperation Element (DTA)</span></span>
  <span data-ttu-id="7b11d-103">Spécifie si les index, les vues indexées ou les partitions recommandées par l'Assistant Paramétrage du moteur de base de données peuvent être créés en ligne.</span><span class="sxs-lookup"><span data-stu-id="7b11d-103">Specifies whether the indexes, indexed views, or partitions that Database Engine Tuning Advisor recommends can be created online.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b11d-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="7b11d-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <OnlineIndexOperation>...</OnlineIndexOperation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="7b11d-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="7b11d-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="7b11d-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="7b11d-106">Characteristic</span></span>|<span data-ttu-id="7b11d-107">Description</span><span class="sxs-lookup"><span data-stu-id="7b11d-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7b11d-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="7b11d-108">**Data type and length**</span></span>|<span data-ttu-id="7b11d-109">`string`, aucune longueur maximale.</span><span class="sxs-lookup"><span data-stu-id="7b11d-109">`string`, no maximum length.</span></span>|  
|<span data-ttu-id="7b11d-110">**Valeurs autorisées**</span><span class="sxs-lookup"><span data-stu-id="7b11d-110">**Allowed values**</span></span>|<span data-ttu-id="7b11d-111">**OFF**</span><span class="sxs-lookup"><span data-stu-id="7b11d-111">**OFF**</span></span><br /> <span data-ttu-id="7b11d-112">Aucune PDS ne peut être créée en ligne.</span><span class="sxs-lookup"><span data-stu-id="7b11d-112">No recommended physical design structures can be created online.</span></span><br /><br /> <span data-ttu-id="7b11d-113">**ON**</span><span class="sxs-lookup"><span data-stu-id="7b11d-113">**ON**</span></span><br /> <span data-ttu-id="7b11d-114">Toutes les PDS recommandées peuvent être créées en ligne.</span><span class="sxs-lookup"><span data-stu-id="7b11d-114">All recommended physical design structures can be created online.</span></span><br /><br /> <span data-ttu-id="7b11d-115">**CONDITIONS MIXTES**</span><span class="sxs-lookup"><span data-stu-id="7b11d-115">**MIXED**</span></span><br /> <span data-ttu-id="7b11d-116">L'Assistant Paramétrage du moteur de base de données tente de recommander des PDS pouvant être créées en ligne lorsque cela est possible.</span><span class="sxs-lookup"><span data-stu-id="7b11d-116">Database Engine Tuning Advisor attempts to recommend physical design structures that can be created online when possible.</span></span><br /><br /> <span data-ttu-id="7b11d-117">Utilisez une de ces valeurs avec cet élément.</span><span class="sxs-lookup"><span data-stu-id="7b11d-117">Use one of these values with this element.</span></span> <span data-ttu-id="7b11d-118">Si les index sont créés en ligne, le mot clé **ONLINE = ON** est ajouté à sa définition d’objet.</span><span class="sxs-lookup"><span data-stu-id="7b11d-118">If indexes are created online, the keyword **ONLINE = ON** is appended to its object definition.</span></span>|  
|<span data-ttu-id="7b11d-119">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="7b11d-119">**Default value**</span></span>|<span data-ttu-id="7b11d-120">Aucun.</span><span class="sxs-lookup"><span data-stu-id="7b11d-120">None.</span></span>|  
|<span data-ttu-id="7b11d-121">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="7b11d-121">**Occurrence**</span></span>|<span data-ttu-id="7b11d-122">facultatif.</span><span class="sxs-lookup"><span data-stu-id="7b11d-122">Optional.</span></span> <span data-ttu-id="7b11d-123">S’il est utilisé, ne peut être utilisé qu’une seule fois pour l' `TuningOptions` élément.</span><span class="sxs-lookup"><span data-stu-id="7b11d-123">If used, can only be used once for the `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="7b11d-124">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="7b11d-124">Element Relationships</span></span>  
  
|<span data-ttu-id="7b11d-125">Relation</span><span class="sxs-lookup"><span data-stu-id="7b11d-125">Relationship</span></span>|<span data-ttu-id="7b11d-126">Éléments</span><span class="sxs-lookup"><span data-stu-id="7b11d-126">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="7b11d-127">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="7b11d-127">**Parent element**</span></span>|[<span data-ttu-id="7b11d-128">Élément TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="7b11d-128">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="7b11d-129">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="7b11d-129">**Child elements**</span></span>|<span data-ttu-id="7b11d-130">Aucun.</span><span class="sxs-lookup"><span data-stu-id="7b11d-130">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7b11d-131">Exemple</span><span class="sxs-lookup"><span data-stu-id="7b11d-131">Example</span></span>  
 <span data-ttu-id="7b11d-132">Pour obtenir un exemple d’utilisation de cet élément, consultez [Exemple de fichier d’entrée XML simple &#40;Assistant Paramétrage de base de données&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="7b11d-132">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b11d-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7b11d-133">See Also</span></span>  
 [<span data-ttu-id="7b11d-134">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="7b11d-134">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
