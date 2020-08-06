---
title: Élément table pour Schema (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Table element [DTA]
ms.assetid: a59e8319-05d1-47f3-af39-7d970ab8e7dc
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd444b1da99b22e0259dc1f50818c1763b7052ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704576"
---
# <a name="table-element-for-schema-dta"></a><span data-ttu-id="83e25-102">Table, élément pour les schémas (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="83e25-102">Table Element for Schema (DTA)</span></span>
  <span data-ttu-id="83e25-103">Spécifie la table pour le paramétrage.</span><span class="sxs-lookup"><span data-stu-id="83e25-103">Specifies the table for tuning.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83e25-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="83e25-104">Syntax</span></span>  
  
```  
  
<Schema>  
...code removed here...  
    <Table>...</Table>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="83e25-105">Attributs des éléments</span><span class="sxs-lookup"><span data-stu-id="83e25-105">Element Attributes</span></span>  
  
|<span data-ttu-id="83e25-106">Attribut</span><span class="sxs-lookup"><span data-stu-id="83e25-106">Attribute</span></span>|<span data-ttu-id="83e25-107">Description</span><span class="sxs-lookup"><span data-stu-id="83e25-107">Description</span></span>|  
|---------------|-----------------|  
|`NumberOfRows`|<span data-ttu-id="83e25-108">facultatif.</span><span class="sxs-lookup"><span data-stu-id="83e25-108">Optional.</span></span> <span data-ttu-id="83e25-109">Entier qui vous permet de simuler des tables de différentes tailles.</span><span class="sxs-lookup"><span data-stu-id="83e25-109">Integer that allows you to simulate tables of different sizes.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="83e25-110">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="83e25-110">Element Characteristics</span></span>  
  
|<span data-ttu-id="83e25-111">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="83e25-111">Characteristic</span></span>|<span data-ttu-id="83e25-112">Description</span><span class="sxs-lookup"><span data-stu-id="83e25-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="83e25-113">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="83e25-113">**Data type and length**</span></span>|<span data-ttu-id="83e25-114">**string**, entre 1 et 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="83e25-114">**string**, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="83e25-115">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="83e25-115">**Default value**</span></span>|<span data-ttu-id="83e25-116">Aucun.</span><span class="sxs-lookup"><span data-stu-id="83e25-116">None.</span></span>|  
|<span data-ttu-id="83e25-117">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="83e25-117">**Occurrence**</span></span>|<span data-ttu-id="83e25-118">facultatif.</span><span class="sxs-lookup"><span data-stu-id="83e25-118">Optional.</span></span> <span data-ttu-id="83e25-119">Répertoriez autant de tables que nécessaire pour votre charge de travail.</span><span class="sxs-lookup"><span data-stu-id="83e25-119">List as many tables as appropriate for your workload.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="83e25-120">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="83e25-120">Element Relationships</span></span>  
  
|<span data-ttu-id="83e25-121">Relation</span><span class="sxs-lookup"><span data-stu-id="83e25-121">Relationship</span></span>|<span data-ttu-id="83e25-122">Éléments</span><span class="sxs-lookup"><span data-stu-id="83e25-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="83e25-123">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="83e25-123">**Parent element**</span></span>|[<span data-ttu-id="83e25-124">Schema, élément pour les bases de données &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="83e25-124">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
|<span data-ttu-id="83e25-125">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="83e25-125">**Child elements**</span></span>|[<span data-ttu-id="83e25-126">Name, élément pour les tables &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="83e25-126">Name Element for Table &#40;DTA&#41;</span></span>](name-element-for-table-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="83e25-127">Notes</span><span class="sxs-lookup"><span data-stu-id="83e25-127">Remarks</span></span>  
 <span data-ttu-id="83e25-128">Si vous ne spécifiez pas d'élément `Table`, l'Assistant Paramétrage du moteur de base de données suppose que toutes les tables sur la base de données spécifiée peuvent être paramétrées.</span><span class="sxs-lookup"><span data-stu-id="83e25-128">If you do not specify a `Table` element, Database Engine Tuning Advisor will assume all tables on the specified database can be tuned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83e25-129">Exemple</span><span class="sxs-lookup"><span data-stu-id="83e25-129">Example</span></span>  
 <span data-ttu-id="83e25-130">Pour obtenir un exemple d’utilisation, consultez [Server, élément &#40;Assistant Paramétrage de base de données&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="83e25-130">For a usage example, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e25-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="83e25-131">See Also</span></span>  
 [<span data-ttu-id="83e25-132">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="83e25-132">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
