---
title: Recommendation, élément (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Recommendation element
ms.assetid: 679ea535-865a-4633-a4d3-5b3090515158
author: stevestein
ms.author: sstein
ms.openlocfilehash: b4eb54a106d67f0217a2604b2d08754d0d2c0765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601863"
---
# <a name="recommendation-element-dta"></a><span data-ttu-id="d8808-102">Recommendation, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="d8808-102">Recommendation Element (DTA)</span></span>
  <span data-ttu-id="d8808-103">Contient des informations sur les index hypothétiques qui font partie d'une configuration spécifiée par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d8808-103">Contains information about the hypothetical indexes that are part of a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8808-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d8808-104">Syntax</span></span>  
  
```  
  
<Configuration>  
    ...code removed here...  
    <Table>  
      <Name>...</Name>  
      <Recommendation>  
      ...code removed here...  
      </Recommendation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="d8808-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="d8808-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="d8808-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="d8808-106">Characteristic</span></span>|<span data-ttu-id="d8808-107">Description</span><span class="sxs-lookup"><span data-stu-id="d8808-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d8808-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="d8808-108">**Data type and length**</span></span>|<span data-ttu-id="d8808-109">Aucun.</span><span class="sxs-lookup"><span data-stu-id="d8808-109">None.</span></span>|  
|<span data-ttu-id="d8808-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="d8808-110">**Default value**</span></span>|<span data-ttu-id="d8808-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="d8808-111">None.</span></span>|  
|<span data-ttu-id="d8808-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="d8808-112">**Occurrence**</span></span>|<span data-ttu-id="d8808-113">facultatif.</span><span class="sxs-lookup"><span data-stu-id="d8808-113">Optional.</span></span> <span data-ttu-id="d8808-114">Peut être utilisé une seule fois pour chaque élément `Table`.</span><span class="sxs-lookup"><span data-stu-id="d8808-114">Can use once for each `Table` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="d8808-115">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="d8808-115">Element Relationships</span></span>  
  
|<span data-ttu-id="d8808-116">Relation</span><span class="sxs-lookup"><span data-stu-id="d8808-116">Relationship</span></span>|<span data-ttu-id="d8808-117">Éléments</span><span class="sxs-lookup"><span data-stu-id="d8808-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="d8808-118">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="d8808-118">**Parent element**</span></span>|[<span data-ttu-id="d8808-119">Table, élément pour les schémas &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="d8808-119">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
|<span data-ttu-id="d8808-120">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="d8808-120">**Child elements**</span></span>|[<span data-ttu-id="d8808-121">Create, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="d8808-121">Create Element &#40;DTA&#41;</span></span>](create-element-dta.md)<br /><br /> <span data-ttu-id="d8808-122">Élément `Drop`.</span><span class="sxs-lookup"><span data-stu-id="d8808-122">`Drop` element.</span></span> <span data-ttu-id="d8808-123">Pour plus d'informations, consultez l'article [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="d8808-123">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8808-124">Notes</span><span class="sxs-lookup"><span data-stu-id="d8808-124">Remarks</span></span>  
 <span data-ttu-id="d8808-125">Cet élément porte le nom **RecommendationTypecomplexType** dans le schéma XML de l’Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="d8808-125">This element is of the **RecommendationTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="d8808-126">Il est utilisé pour spécifier des index dans une configuration hypothétique.</span><span class="sxs-lookup"><span data-stu-id="d8808-126">It is used to specify indexes for a hypothetical configuration.</span></span> <span data-ttu-id="d8808-127">Ne confondez pas cet élément `Recommendation` avec les autres types d'éléments qui peuvent être utilisés pour spécifier le partitionnement (`RecommendationPType`) ou les vues (`RecommendationViewType`).</span><span class="sxs-lookup"><span data-stu-id="d8808-127">Do not confuse this `Recommendation` element with the other types that can be used to specify partitioning (`RecommendationPType`) or views (`RecommendationViewType`).</span></span> <span data-ttu-id="d8808-128">Pour plus d’informations sur ces autres `Recommendation` types d’éléments, consultez la [Assistant Paramétrage du moteur de base de données schéma XML](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="d8808-128">For information about these other `Recommendation` element types, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8808-129">Exemple</span><span class="sxs-lookup"><span data-stu-id="d8808-129">Example</span></span>  
 <span data-ttu-id="d8808-130">Pour obtenir un exemple d’utilisation de cet élément, consultez l’[Exemple de fichier d’entrée XML avec une configuration spécifiée par l’utilisateur &#40;Assistant Paramétrage de base de données&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="d8808-130">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8808-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8808-131">See Also</span></span>  
 [<span data-ttu-id="d8808-132">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="d8808-132">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
