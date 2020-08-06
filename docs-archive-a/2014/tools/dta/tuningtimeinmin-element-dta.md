---
title: Élément TuningTimeInMin (Assistant Paramétrage de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TuningTimeInMin element
ms.assetid: 4973d9ac-20fd-4ac3-bc9f-5d60e39fdb7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4dae3fe4e9ac3126f43ec017c34d2bc548fda6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704555"
---
# <a name="tuningtimeinmin-element-dta"></a><span data-ttu-id="05ebb-102">TuningTimeInMin, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="05ebb-102">TuningTimeInMin Element (DTA)</span></span>
  <span data-ttu-id="05ebb-103">Spécifie la durée maximale, en minutes, d'une session de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="05ebb-103">Specifies the maximum length of a tuning session in minutes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05ebb-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="05ebb-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <TuningTimeInMin>...</TuningTimeInMin>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="05ebb-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="05ebb-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="05ebb-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="05ebb-106">Characteristic</span></span>|<span data-ttu-id="05ebb-107">Description</span><span class="sxs-lookup"><span data-stu-id="05ebb-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="05ebb-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="05ebb-108">**Data type and length**</span></span>|<span data-ttu-id="05ebb-109">`unsignedInt`, longueur illimitée.</span><span class="sxs-lookup"><span data-stu-id="05ebb-109">`unsignedInt`, unlimited length.</span></span>|  
|<span data-ttu-id="05ebb-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="05ebb-110">**Default value**</span></span>|<span data-ttu-id="05ebb-111">480 minutes (8 heures).</span><span class="sxs-lookup"><span data-stu-id="05ebb-111">480 minutes (8 hours).</span></span>|  
|<span data-ttu-id="05ebb-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="05ebb-112">**Occurrence**</span></span>|<span data-ttu-id="05ebb-113">Obligatoire, à moins qu'une valeur n'ait été spécifiée pour l'élément `NumberOfEvents`.</span><span class="sxs-lookup"><span data-stu-id="05ebb-113">Required unless a value has been specified for the `NumberOfEvents` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="05ebb-114">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="05ebb-114">Element Relationships</span></span>  
  
|<span data-ttu-id="05ebb-115">Relation</span><span class="sxs-lookup"><span data-stu-id="05ebb-115">Relationship</span></span>|<span data-ttu-id="05ebb-116">Éléments</span><span class="sxs-lookup"><span data-stu-id="05ebb-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="05ebb-117">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="05ebb-117">**Parent element**</span></span>|[<span data-ttu-id="05ebb-118">Élément TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="05ebb-118">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="05ebb-119">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="05ebb-119">**Child elements**</span></span>|<span data-ttu-id="05ebb-120">None</span><span class="sxs-lookup"><span data-stu-id="05ebb-120">None</span></span>|  
  
## <a name="example"></a><span data-ttu-id="05ebb-121">Exemple</span><span class="sxs-lookup"><span data-stu-id="05ebb-121">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="05ebb-122">Description</span><span class="sxs-lookup"><span data-stu-id="05ebb-122">Description</span></span>  
 <span data-ttu-id="05ebb-123">L'exemple de code suivant montre comment définir une durée de réglage maximale de 12 heures :</span><span class="sxs-lookup"><span data-stu-id="05ebb-123">The following code example shows how to set 12 hours as the maximum tuning time:</span></span>  
  
## <a name="code"></a><span data-ttu-id="05ebb-124">Code</span><span class="sxs-lookup"><span data-stu-id="05ebb-124">Code</span></span>  
  
```  
<DTAInput>  
  <Server>...</Server>  
  <Workload>...</Workload>  
  <TuningOptions>  
    <TuningTimeInMin>720</TuningTimeInMin>  
...code removed here...  
</DTAInput>  
```  
  
## <a name="see-also"></a><span data-ttu-id="05ebb-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="05ebb-125">See Also</span></span>  
 [<span data-ttu-id="05ebb-126">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="05ebb-126">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
