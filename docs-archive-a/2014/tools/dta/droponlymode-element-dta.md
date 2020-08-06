---
title: Élément DropOnlyMode, (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DropOnlyMode element
ms.assetid: 80960676-7581-4074-889b-80ee665963dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: b274dc394a933308cf2161cc271d09b8391900c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695004"
---
# <a name="droponlymode-element-dta"></a><span data-ttu-id="a855e-102">DropOnlyMode, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="a855e-102">DropOnlyMode Element (DTA)</span></span>
  <span data-ttu-id="a855e-103">Spécifie que l'Assistant Paramétrage du moteur de base de données doit supprimer uniquement les index, les vues indexées ou les partitions existantes pendant la session de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="a855e-103">Specifies that Database Engine Tuning Advisor should only consider dropping existing indexes, indexed views, or partitions during the tuning session.</span></span> <span data-ttu-id="a855e-104">Aucune nouvelle structure PDS n'est pas prise en compte lorsque cette option de paramétrage est spécifiée.</span><span class="sxs-lookup"><span data-stu-id="a855e-104">No new physical design structures are considered when this tuning option is specified.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a855e-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a855e-105">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <DropOnlyMode>...</DropOnlyMode>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="a855e-106">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="a855e-106">Element Characteristics</span></span>  
  
|<span data-ttu-id="a855e-107">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="a855e-107">Characteristic</span></span>|<span data-ttu-id="a855e-108">Description</span><span class="sxs-lookup"><span data-stu-id="a855e-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="a855e-109">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="a855e-109">**Data type and length**</span></span>|<span data-ttu-id="a855e-110">Aucun.</span><span class="sxs-lookup"><span data-stu-id="a855e-110">None.</span></span>|  
|<span data-ttu-id="a855e-111">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="a855e-111">**Default value**</span></span>|<span data-ttu-id="a855e-112">Aucun.</span><span class="sxs-lookup"><span data-stu-id="a855e-112">None.</span></span>|  
|<span data-ttu-id="a855e-113">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="a855e-113">**Occurrence**</span></span>|<span data-ttu-id="a855e-114">facultatif.</span><span class="sxs-lookup"><span data-stu-id="a855e-114">Optional.</span></span> <span data-ttu-id="a855e-115">Ne peut être utilisé qu'une seule fois pour chaque élément `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="a855e-115">Can use only once for each `TuningOptions` element.</span></span> <span data-ttu-id="a855e-116">Ne peut pas être utilisé si les éléments suivants sont spécifiés dans l'élément `TuningOptions` :</span><span class="sxs-lookup"><span data-stu-id="a855e-116">Cannot be used if the following elements are specified in the `TuningOptions` element:</span></span><br /><br /> [<span data-ttu-id="a855e-117">FeatureSet, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="a855e-117">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)<br /><br /> [<span data-ttu-id="a855e-118">Partitioning, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="a855e-118">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)<br /><br /> <span data-ttu-id="a855e-119">[L’élément KeepExisting &#40;Assistant Paramétrage de base de données&#41;](keepexisting-element-dta.md) est défini sur **ALL**</span><span class="sxs-lookup"><span data-stu-id="a855e-119">[KeepExisting Element &#40;DTA&#41;](keepexisting-element-dta.md) is set to **ALL**</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="a855e-120">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="a855e-120">Element Relationships</span></span>  
  
|<span data-ttu-id="a855e-121">Relation</span><span class="sxs-lookup"><span data-stu-id="a855e-121">Relationship</span></span>|<span data-ttu-id="a855e-122">Éléments</span><span class="sxs-lookup"><span data-stu-id="a855e-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="a855e-123">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="a855e-123">**Parent element**</span></span>|[<span data-ttu-id="a855e-124">Élément TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="a855e-124">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="a855e-125">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="a855e-125">**Child elements**</span></span>|<span data-ttu-id="a855e-126">Aucun.</span><span class="sxs-lookup"><span data-stu-id="a855e-126">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a855e-127">Exemple</span><span class="sxs-lookup"><span data-stu-id="a855e-127">Example</span></span>  
 <span data-ttu-id="a855e-128">L'exemple suivant illustre la section `TuningOptions` d'un fichier d'entrée XML de l'Assistant Paramétrage du moteur de base de données dans lequel l'élément `DropOnlyMode` est spécifié.</span><span class="sxs-lookup"><span data-stu-id="a855e-128">The following example shows the `TuningOptions` section of a Database Engine Tuning Advisor XML input file where the `DropOnlyMode` is specified.</span></span> <span data-ttu-id="a855e-129">Dans cet exemple, la durée de paramétrage est limitée à 24 heures (1440 minutes) et tous les index cluster et non cluster existants sont pris en compte en vue de leur suppression :</span><span class="sxs-lookup"><span data-stu-id="a855e-129">In this example the tuning time is limited to 24 hours (1440 minutes) and all existing clustered and nonclustered indexes will be considered for dropping:</span></span>  
  
```xml  
<TuningOptions  
  <TuningTimeInMin>1440</Name>  
  <KeepExisting>ALIGNED</KeepExisting>  
  <DropOnlyMode />  
</TuningOptions>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a855e-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a855e-130">See Also</span></span>  
 [<span data-ttu-id="a855e-131">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="a855e-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
