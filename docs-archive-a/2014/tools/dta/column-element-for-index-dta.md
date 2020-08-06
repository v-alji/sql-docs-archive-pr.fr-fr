---
title: Élément Column pour index (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Column element
ms.assetid: ba9fac20-26bd-4333-940e-842c15241b46
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67853dc7d1193d3a0f80e56023846bc55a20bdaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695043"
---
# <a name="column-element-for-index-dta"></a><span data-ttu-id="3e116-102">Column, élément pour les index (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="3e116-102">Column Element for Index (DTA)</span></span>
  <span data-ttu-id="3e116-103">Spécifie les colonnes sur lesquelles l'index est créé pour une configuration spécifiée par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3e116-103">Specifies the columns on which the index is created for a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e116-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3e116-104">Syntax</span></span>  
  
```  
  
<Create>  
  <Index>  
    <Name>...</Name>  
    <Column [Type | SortOrder]>  
     ...code removed here...  
     </Column>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="3e116-105">Attributs des éléments</span><span class="sxs-lookup"><span data-stu-id="3e116-105">Element Attributes</span></span>  
  
|<span data-ttu-id="3e116-106">Attribut de colonne</span><span class="sxs-lookup"><span data-stu-id="3e116-106">Column Attribute</span></span>|<span data-ttu-id="3e116-107">Description</span><span class="sxs-lookup"><span data-stu-id="3e116-107">Description</span></span>|  
|----------------------|-----------------|  
|`Type`|<span data-ttu-id="3e116-108">facultatif.</span><span class="sxs-lookup"><span data-stu-id="3e116-108">Optional.</span></span> <span data-ttu-id="3e116-109">Spécifie le type de colonne d'index.</span><span class="sxs-lookup"><span data-stu-id="3e116-109">Specifies the index column type.</span></span> <span data-ttu-id="3e116-110">Utilisez un type de données **string** pour spécifier cet attribut avec l'une des valeurs autorisées suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e116-110">Use a **string** data type to specify this attribute with one of the following allowed values:</span></span><br /><br /> <span data-ttu-id="3e116-111">`KeyColumn`:</span><span class="sxs-lookup"><span data-stu-id="3e116-111">`KeyColumn`:</span></span><br />                  <span data-ttu-id="3e116-112">Spécifie que la colonne est référencée par une clé d'index.</span><span class="sxs-lookup"><span data-stu-id="3e116-112">Specifies that the column is referenced by an index key.</span></span> <span data-ttu-id="3e116-113">Utilisez la syntaxe suivante pour définir cet attribut :</span><span class="sxs-lookup"><span data-stu-id="3e116-113">Use the following syntax to set this attribute:</span></span><br />`<Column Type="KeyColumn">`<br /><span data-ttu-id="3e116-114">Pour plus d’informations sur les colonnes clés, consultez [Description des index cluster et non-cluster](../../relational-databases/indexes/clustered-and-nonclustered-indexes-described.md).</span><span class="sxs-lookup"><span data-stu-id="3e116-114">For more information about key columns, see [Clustered and Nonclustered Indexes Described](../../relational-databases/indexes/clustered-and-nonclustered-indexes-described.md).</span></span><br /><br /> <span data-ttu-id="3e116-115">`IncludedColumn`: Spécifie que la colonne est une colonne incluse (au lieu d’une colonne clé).</span><span class="sxs-lookup"><span data-stu-id="3e116-115">`IncludedColumn`: Specifies that the column is an included column (instead of a key column).</span></span> <span data-ttu-id="3e116-116">Utilisez la syntaxe suivante pour définir cet attribut :</span><span class="sxs-lookup"><span data-stu-id="3e116-116">Use the following syntax to set this attribute:</span></span><br />`<Column Type="IncludedColumn">`<br /><span data-ttu-id="3e116-117">Pour plus d’informations sur les colonnes incluses, consultez [Créer des index avec colonnes incluses](../../relational-databases/indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="3e116-117">For more information about included columns, see [Create Indexes with Included Columns](../../relational-databases/indexes/create-indexes-with-included-columns.md).</span></span>|  
|`SortOrder`|<span data-ttu-id="3e116-118">facultatif.</span><span class="sxs-lookup"><span data-stu-id="3e116-118">Optional.</span></span> <span data-ttu-id="3e116-119">Spécifie l'ordre de tri de la colonne.</span><span class="sxs-lookup"><span data-stu-id="3e116-119">Specifies the sorting order of the column.</span></span> <span data-ttu-id="3e116-120">Utilisez un type de données **string** pour spécifier un ordre de tri **"Ascending"** ou **"Descending"** comme suit :</span><span class="sxs-lookup"><span data-stu-id="3e116-120">Use a **string** data type to specify either an **"Ascending"** or **"Descending"** sorting order as follows:</span></span><br /><br /> `<Column SortOrder="Ascending">`|  
  
## <a name="element-characteristics"></a><span data-ttu-id="3e116-121">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="3e116-121">Element Characteristics</span></span>  
  
|<span data-ttu-id="3e116-122">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="3e116-122">Characteristic</span></span>|<span data-ttu-id="3e116-123">Description</span><span class="sxs-lookup"><span data-stu-id="3e116-123">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="3e116-124">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="3e116-124">**Data type and length**</span></span>|<span data-ttu-id="3e116-125">Aucun.</span><span class="sxs-lookup"><span data-stu-id="3e116-125">None.</span></span>|  
|<span data-ttu-id="3e116-126">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="3e116-126">**Default value**</span></span>|<span data-ttu-id="3e116-127">Aucun.</span><span class="sxs-lookup"><span data-stu-id="3e116-127">None.</span></span>|  
|<span data-ttu-id="3e116-128">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="3e116-128">**Occurrence**</span></span>|<span data-ttu-id="3e116-129">Peut spécifié jusqu'à 1 024 colonnes pour l'élément `Index`.</span><span class="sxs-lookup"><span data-stu-id="3e116-129">Can specify up to 1024 columns for the `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="3e116-130">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="3e116-130">Element Relationships</span></span>  
  
|<span data-ttu-id="3e116-131">Relation</span><span class="sxs-lookup"><span data-stu-id="3e116-131">Relationship</span></span>|<span data-ttu-id="3e116-132">Éléments</span><span class="sxs-lookup"><span data-stu-id="3e116-132">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="3e116-133">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="3e116-133">**Parent element**</span></span>|[<span data-ttu-id="3e116-134">Index, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3e116-134">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="3e116-135">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="3e116-135">**Child elements**</span></span>|[<span data-ttu-id="3e116-136">Name, élément pour les colonnes &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3e116-136">Name Element for Column &#40;DTA&#41;</span></span>](name-element-for-column-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="3e116-137">Exemple</span><span class="sxs-lookup"><span data-stu-id="3e116-137">Example</span></span>  
 <span data-ttu-id="3e116-138">Pour obtenir un exemple d’utilisation de cet élément, consultez l’[Exemple de fichier d’entrée XML avec une configuration spécifiée par l’utilisateur &#40;Assistant Paramétrage de base de données&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="3e116-138">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e116-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e116-139">See Also</span></span>  
 [<span data-ttu-id="3e116-140">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="3e116-140">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
