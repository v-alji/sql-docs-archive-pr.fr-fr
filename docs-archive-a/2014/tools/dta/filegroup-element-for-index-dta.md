---
title: Élément FileGroup pour index (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Filegroup element [DTA]
ms.assetid: 7078d2fb-fa77-44fc-beb3-c095088fcb85
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ed8ea723d6c0798b93e16411ee47d6e956c6c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704580"
---
# <a name="filegroup-element-for-index-dta"></a><span data-ttu-id="f63f0-102">Filegroup, élément pour les index (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="f63f0-102">Filegroup Element for Index (DTA)</span></span>
  <span data-ttu-id="f63f0-103">Spécifie le groupe de fichiers sur lequel l'index doit être créé pour une configuration spécifiée par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f63f0-103">Specifies the filegroup on which the index is to be created for a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f63f0-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f63f0-104">Syntax</span></span>  
  
```  
  
<Index>  
  <Name>...</Name>  
  <Column>  
    <Name>...</Name>  
  <Filegroup>...</Filegroup>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="f63f0-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="f63f0-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="f63f0-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="f63f0-106">Characteristic</span></span>|<span data-ttu-id="f63f0-107">Description</span><span class="sxs-lookup"><span data-stu-id="f63f0-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="f63f0-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="f63f0-108">**Data type and length**</span></span>|<span data-ttu-id="f63f0-109">`string`, longueur illimitée.</span><span class="sxs-lookup"><span data-stu-id="f63f0-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="f63f0-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="f63f0-110">**Default value**</span></span>|<span data-ttu-id="f63f0-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="f63f0-111">None.</span></span>|  
|<span data-ttu-id="f63f0-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="f63f0-112">**Occurrence**</span></span>|<span data-ttu-id="f63f0-113">facultatif.</span><span class="sxs-lookup"><span data-stu-id="f63f0-113">Optional.</span></span> <span data-ttu-id="f63f0-114">Peut être utilisé une seule fois pour chaque élément `Index`.</span><span class="sxs-lookup"><span data-stu-id="f63f0-114">Can use once for each `Index` element.</span></span> <span data-ttu-id="f63f0-115">Cet élément ne peut pas être utilisé si les éléments `PartitionScheme` et `PartitionColumn` sont spécifiés pour l'élément `Index`.</span><span class="sxs-lookup"><span data-stu-id="f63f0-115">This element cannot be used if the `PartitionScheme` and `PartitionColumn` elements are specified for the `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="f63f0-116">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="f63f0-116">Element Relationships</span></span>  
  
|<span data-ttu-id="f63f0-117">Relation</span><span class="sxs-lookup"><span data-stu-id="f63f0-117">Relationship</span></span>|<span data-ttu-id="f63f0-118">Éléments</span><span class="sxs-lookup"><span data-stu-id="f63f0-118">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="f63f0-119">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="f63f0-119">**Parent element**</span></span>|[<span data-ttu-id="f63f0-120">Index, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f63f0-120">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="f63f0-121">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="f63f0-121">**Child elements**</span></span>|<span data-ttu-id="f63f0-122">Aucun.</span><span class="sxs-lookup"><span data-stu-id="f63f0-122">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f63f0-123">Exemple</span><span class="sxs-lookup"><span data-stu-id="f63f0-123">Example</span></span>  
 <span data-ttu-id="f63f0-124">Pour obtenir un exemple d’utilisation de cet élément, consultez l’[Exemple de fichier d’entrée XML avec une configuration spécifiée par l’utilisateur &#40;Assistant Paramétrage de base de données&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="f63f0-124">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f63f0-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f63f0-125">See Also</span></span>  
 [<span data-ttu-id="f63f0-126">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f63f0-126">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
