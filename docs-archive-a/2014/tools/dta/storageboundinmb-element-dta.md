---
title: Élément StorageBoundInMB, (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- StorageBoundInMB element
ms.assetid: a8374910-bf68-4edb-b464-53a3a705e7f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: ea49b0af981b8f8d96efb087033d8f1466364c76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704584"
---
# <a name="storageboundinmb-element-dta"></a><span data-ttu-id="bf7e9-102">StorageBoundInMB, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="bf7e9-102">StorageBoundInMB Element (DTA)</span></span>
  <span data-ttu-id="bf7e9-103">Spécifie l'espace maximal, en mégaoctets, pouvant être consommé par la recommandation de paramétrage de l'Assistant Paramétrage du moteur de base de données (jeu d'index et de partitions).</span><span class="sxs-lookup"><span data-stu-id="bf7e9-103">Specifies the maximum space in megabytes that can be consumed by the Database Engine Tuning Advisor tuning recommendation (index and partitioning set).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf7e9-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="bf7e9-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <StorageBoundInMB>...</ StorageBoundInMB >  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="bf7e9-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="bf7e9-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="bf7e9-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="bf7e9-106">Characteristic</span></span>|<span data-ttu-id="bf7e9-107">Description</span><span class="sxs-lookup"><span data-stu-id="bf7e9-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="bf7e9-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="bf7e9-108">**Data type and length**</span></span>|<span data-ttu-id="bf7e9-109">`unsignedInt`, longueur illimitée.</span><span class="sxs-lookup"><span data-stu-id="bf7e9-109">`unsignedInt`, unlimited length.</span></span>|  
|<span data-ttu-id="bf7e9-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="bf7e9-110">**Default value**</span></span>|<span data-ttu-id="bf7e9-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="bf7e9-111">None.</span></span>|  
|<span data-ttu-id="bf7e9-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="bf7e9-112">**Occurrence**</span></span>|<span data-ttu-id="bf7e9-113">facultatif.</span><span class="sxs-lookup"><span data-stu-id="bf7e9-113">Optional.</span></span> <span data-ttu-id="bf7e9-114">Ne peut être utilisé qu'une seule fois pour l'élément `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="bf7e9-114">Can only be used once for the `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="bf7e9-115">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="bf7e9-115">Element Relationships</span></span>  
  
|<span data-ttu-id="bf7e9-116">Relation</span><span class="sxs-lookup"><span data-stu-id="bf7e9-116">Relationship</span></span>|<span data-ttu-id="bf7e9-117">Éléments</span><span class="sxs-lookup"><span data-stu-id="bf7e9-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="bf7e9-118">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="bf7e9-118">**Parent element**</span></span>|[<span data-ttu-id="bf7e9-119">Élément TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="bf7e9-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="bf7e9-120">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="bf7e9-120">**Child elements**</span></span>|<span data-ttu-id="bf7e9-121">None</span><span class="sxs-lookup"><span data-stu-id="bf7e9-121">None</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf7e9-122">Notes</span><span class="sxs-lookup"><span data-stu-id="bf7e9-122">Remarks</span></span>  
 <span data-ttu-id="bf7e9-123">Lorsque plusieurs bases de données sont paramétrées, les recommandations pour toutes les bases de données sont prises en compte pour le calcul de l'espace.</span><span class="sxs-lookup"><span data-stu-id="bf7e9-123">When multiple databases are tuned, recommendations for all databases are considered for the space calculation.</span></span> <span data-ttu-id="bf7e9-124">Par défaut, l'Assistant Paramétrage du moteur de base de données utilise la plus petite taille des tailles de stockage suivantes :</span><span class="sxs-lookup"><span data-stu-id="bf7e9-124">By default, Database Engine Tuning Advisor assumes the smaller of the following storage sizes:</span></span>  
  
-   <span data-ttu-id="bf7e9-125">Trois fois la taille des données brutes, qui comprend la taille totale des segments et des index cluster sur les tables.</span><span class="sxs-lookup"><span data-stu-id="bf7e9-125">Three times the current raw data size, which includes the total size of heaps and clustered indexes on tables.</span></span>  
  
-   <span data-ttu-id="bf7e9-126">L'espace libre disponible sur tous les lecteurs de disques connectés, plus la taille des données brutes.</span><span class="sxs-lookup"><span data-stu-id="bf7e9-126">The free space on all attached disk drives plus the raw data size.</span></span>  
  
 <span data-ttu-id="bf7e9-127">La taille de stockage par défaut ne comprend pas les index non-cluster et les vues indexées.</span><span class="sxs-lookup"><span data-stu-id="bf7e9-127">The default storage size does not include nonclustered indexes and indexed views.</span></span>  
  
 <span data-ttu-id="bf7e9-128">Si la valeur spécifiée pour l'élément `StorageBoundInMB` dépasse celle de l'espace disque, l'Assistant Paramétrage du moteur de base de données renvoie une erreur mais continue le paramétrage.</span><span class="sxs-lookup"><span data-stu-id="bf7e9-128">If the value specified for the `StorageBoundInMB` element exceeds the actual disk space, Database Engine Tuning Advisor returns an error, but continues tuning.</span></span> <span data-ttu-id="bf7e9-129">Une fois le paramétrage terminé, vous pouvez ajouter de l'espace disque si vous décidez d'appliquer la recommandation.</span><span class="sxs-lookup"><span data-stu-id="bf7e9-129">After tuning is complete, you can add disk space if you decide to implement the recommendation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf7e9-130">Exemple</span><span class="sxs-lookup"><span data-stu-id="bf7e9-130">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="bf7e9-131">Description</span><span class="sxs-lookup"><span data-stu-id="bf7e9-131">Description</span></span>  
 <span data-ttu-id="bf7e9-132">L'exemple de code suivant montre comment définir une limite de 1500 mégaoctets comme espace disque maximal consommable par une recommandation de réglage :</span><span class="sxs-lookup"><span data-stu-id="bf7e9-132">The following code example shows how to set a limit of 1500 megabytes as the maximum disk space that a tuning recommendation can consume:</span></span>  
  
## <a name="code"></a><span data-ttu-id="bf7e9-133">Code</span><span class="sxs-lookup"><span data-stu-id="bf7e9-133">Code</span></span>  
  
```  
<DTAInput>  
  <Server>...</Server>  
  <Workload>...</Workload>  
  <TuningOptions>  
    <StorageBoundInMB>1500</StorageBoundInMB>  
...code removed here...  
</DTAInput>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf7e9-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bf7e9-134">See Also</span></span>  
 [<span data-ttu-id="bf7e9-135">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="bf7e9-135">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
