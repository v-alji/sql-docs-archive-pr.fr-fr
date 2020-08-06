---
title: Élément Name pour index (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Name element
ms.assetid: 2300e9cf-f0a8-49e6-b1f5-45ffe03ccb5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: a878923a3d483fae5ad6b55421a2b286f15ceb29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707983"
---
# <a name="name-element-for-index-dta"></a><span data-ttu-id="0fa9a-102">Name, élément pour les index (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="0fa9a-102">Name Element for Index (DTA)</span></span>
  <span data-ttu-id="0fa9a-103">Spécifie le nom d'un index dans la configuration spécifiée par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0fa9a-103">Specifies a name for an index in the user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fa9a-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0fa9a-104">Syntax</span></span>  
  
```  
  
<Create>  
    <Index>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="0fa9a-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="0fa9a-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="0fa9a-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="0fa9a-106">Characteristic</span></span>|<span data-ttu-id="0fa9a-107">Description</span><span class="sxs-lookup"><span data-stu-id="0fa9a-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0fa9a-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-108">**Data type and length**</span></span>|<span data-ttu-id="0fa9a-109">`string`, longueur illimitée.</span><span class="sxs-lookup"><span data-stu-id="0fa9a-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="0fa9a-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-110">**Default value**</span></span>|<span data-ttu-id="0fa9a-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="0fa9a-111">None.</span></span>|  
|<span data-ttu-id="0fa9a-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-112">**Occurrence**</span></span>|<span data-ttu-id="0fa9a-113">Obligatoire une fois pour chaque `Index` élément.</span><span class="sxs-lookup"><span data-stu-id="0fa9a-113">Required once for each `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="0fa9a-114">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="0fa9a-114">Element Relationships</span></span>  
  
|<span data-ttu-id="0fa9a-115">Relation</span><span class="sxs-lookup"><span data-stu-id="0fa9a-115">Relationship</span></span>|<span data-ttu-id="0fa9a-116">Éléments</span><span class="sxs-lookup"><span data-stu-id="0fa9a-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="0fa9a-117">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-117">**Parent element**</span></span>|[<span data-ttu-id="0fa9a-118">Index, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="0fa9a-118">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="0fa9a-119">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="0fa9a-119">**Child elements**</span></span>|<span data-ttu-id="0fa9a-120">Aucun.</span><span class="sxs-lookup"><span data-stu-id="0fa9a-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0fa9a-121">Exemple</span><span class="sxs-lookup"><span data-stu-id="0fa9a-121">Example</span></span>  
 <span data-ttu-id="0fa9a-122">Pour obtenir un exemple d’utilisation de cet élément, consultez l’[Exemple de fichier d’entrée XML avec une configuration spécifiée par l’utilisateur &#40;Assistant Paramétrage de base de données&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="0fa9a-122">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fa9a-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0fa9a-123">See Also</span></span>  
 [<span data-ttu-id="0fa9a-124">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="0fa9a-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
