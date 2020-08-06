---
title: Create, élément (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Create element (DTA)
ms.assetid: 9d076c90-f933-45f4-b6d9-447793f6528b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 407f16c3898e56cd393e36c39ed799b83e0092ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695019"
---
# <a name="create-element-dta"></a><span data-ttu-id="35465-102">Create, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="35465-102">Create Element (DTA)</span></span>
  <span data-ttu-id="35465-103">Contient des informations sur les index, les statistiques ou les structures de segments d'une configuration spécifiée par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35465-103">Contains information about the indexes, statistics, or heap structures in a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35465-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="35465-104">Syntax</span></span>  
  
```  
  
<Recommendation>  
    <Create>  
    ...code removed here...  
    </Create>  
</Recommendation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="35465-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="35465-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="35465-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="35465-106">Characteristic</span></span>|<span data-ttu-id="35465-107">Description</span><span class="sxs-lookup"><span data-stu-id="35465-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="35465-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="35465-108">**Data type and length**</span></span>|<span data-ttu-id="35465-109">Aucun.</span><span class="sxs-lookup"><span data-stu-id="35465-109">None.</span></span>|  
|<span data-ttu-id="35465-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="35465-110">**Default value**</span></span>|<span data-ttu-id="35465-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="35465-111">None.</span></span>|  
|<span data-ttu-id="35465-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="35465-112">**Occurrence**</span></span>|<span data-ttu-id="35465-113">Obligatoire une fois pour chaque type de structure PDS (index, statistiques ou structures de segments).</span><span class="sxs-lookup"><span data-stu-id="35465-113">Required once for each physical design structure type (indexes, statistics, or heap structures).</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="35465-114">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="35465-114">Element Relationships</span></span>  
  
|<span data-ttu-id="35465-115">Relation</span><span class="sxs-lookup"><span data-stu-id="35465-115">Relationship</span></span>|<span data-ttu-id="35465-116">Éléments</span><span class="sxs-lookup"><span data-stu-id="35465-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="35465-117">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="35465-117">**Parent element**</span></span>|[<span data-ttu-id="35465-118">Recommendation, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="35465-118">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)|  
|<span data-ttu-id="35465-119">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="35465-119">**Child elements**</span></span>|[<span data-ttu-id="35465-120">Index, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="35465-120">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)<br /><br /> <span data-ttu-id="35465-121">`Statistics`, Élément (consultez [Assistant Paramétrage du moteur de base de données schéma XML](https://schemas.microsoft.com/sqlserver/) pour plus d’informations)</span><span class="sxs-lookup"><span data-stu-id="35465-121">`Statistics` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span><br /><br /> <span data-ttu-id="35465-122">`Heap`, Élément (consultez [Assistant Paramétrage du moteur de base de données schéma XML](https://schemas.microsoft.com/sqlserver/) pour plus d’informations)</span><span class="sxs-lookup"><span data-stu-id="35465-122">`Heap` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35465-123">Notes</span><span class="sxs-lookup"><span data-stu-id="35465-123">Remarks</span></span>  
 <span data-ttu-id="35465-124">Cet élément porte le nom **CreateTypecomplexType** dans le schéma XML de l’Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="35465-124">This element is of the **CreateTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="35465-125">Il est utilisé pour créer des index, des statistiques ou des structures de segments pour une configuration spécifiée par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35465-125">It is used to create indexes, statistics, and heap structures for a user-specified configuration.</span></span> <span data-ttu-id="35465-126">Ne confondez pas cet élément `Create` avec les autres types d'éléments qui peuvent être utilisés pour créer des vues (`CreateViewType`) ou des partitions (`CreatePType`).</span><span class="sxs-lookup"><span data-stu-id="35465-126">Do not confuse this `Create` element with the other types that can be used to create views (`CreateViewType`) or partitioning (`CreatePType`).</span></span> <span data-ttu-id="35465-127">Reportez-vous à la [Assistant Paramétrage du moteur de base de données schéma XML](https://schemas.microsoft.com/sqlserver/) pour plus d’informations sur ces autres `Create` types d’éléments.</span><span class="sxs-lookup"><span data-stu-id="35465-127">Refer to the [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information about these other `Create` element types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35465-128">Exemple</span><span class="sxs-lookup"><span data-stu-id="35465-128">Example</span></span>  
 <span data-ttu-id="35465-129">Pour obtenir un exemple d’utilisation de cet élément, consultez l’[Exemple de fichier d’entrée XML avec une configuration spécifiée par l’utilisateur &#40;Assistant Paramétrage de base de données&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="35465-129">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35465-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="35465-130">See Also</span></span>  
 [<span data-ttu-id="35465-131">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="35465-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
