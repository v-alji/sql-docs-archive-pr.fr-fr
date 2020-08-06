---
title: Élément Name pour Schema (DTA) | Microsoft Docs
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
ms.assetid: 014e4854-fed2-454b-8557-5f7c5bb6b17a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 678a6d58b35b25be2aed6d91fcae7ceb2640bdcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703599"
---
# <a name="name-element-for-schema-dta"></a><span data-ttu-id="8b2ef-102">Name, élément pour les schémas (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="8b2ef-102">Name Element for Schema (DTA)</span></span>
  <span data-ttu-id="8b2ef-103">Contient le nom du schéma.</span><span class="sxs-lookup"><span data-stu-id="8b2ef-103">Contains name of the schema.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b2ef-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="8b2ef-104">Syntax</span></span>  
  
```  
  
<Database>  
...code removed here  
    <Schema>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="8b2ef-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="8b2ef-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="8b2ef-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="8b2ef-106">Characteristic</span></span>|<span data-ttu-id="8b2ef-107">Description</span><span class="sxs-lookup"><span data-stu-id="8b2ef-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="8b2ef-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="8b2ef-108">**Data type and length**</span></span>|<span data-ttu-id="8b2ef-109">`string`, entre 1 et 255 caractères</span><span class="sxs-lookup"><span data-stu-id="8b2ef-109">`string`, between 1 and 255 characters</span></span>|  
|<span data-ttu-id="8b2ef-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="8b2ef-110">**Default value**</span></span>|<span data-ttu-id="8b2ef-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="8b2ef-111">None.</span></span>|  
|<span data-ttu-id="8b2ef-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="8b2ef-112">**Occurrence**</span></span>|<span data-ttu-id="8b2ef-113">Obligatoire une fois par élément **Schema** .</span><span class="sxs-lookup"><span data-stu-id="8b2ef-113">Required once per **Schema** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="8b2ef-114">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="8b2ef-114">Element Relationships</span></span>  
  
|<span data-ttu-id="8b2ef-115">Relation</span><span class="sxs-lookup"><span data-stu-id="8b2ef-115">Relationship</span></span>|<span data-ttu-id="8b2ef-116">Éléments</span><span class="sxs-lookup"><span data-stu-id="8b2ef-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="8b2ef-117">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="8b2ef-117">**Parent element**</span></span>|[<span data-ttu-id="8b2ef-118">Schema, élément pour les bases de données &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="8b2ef-118">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
|<span data-ttu-id="8b2ef-119">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="8b2ef-119">**Child elements**</span></span>|<span data-ttu-id="8b2ef-120">Aucun.</span><span class="sxs-lookup"><span data-stu-id="8b2ef-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8b2ef-121">Exemple</span><span class="sxs-lookup"><span data-stu-id="8b2ef-121">Example</span></span>  
 <span data-ttu-id="8b2ef-122">Pour obtenir un exemple d’utilisation de cet élément, consultez [Server, élément &#40;Assistant Paramétrage de base de données&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="8b2ef-122">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b2ef-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8b2ef-123">See Also</span></span>  
 [<span data-ttu-id="8b2ef-124">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="8b2ef-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
