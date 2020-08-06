---
title: Élément TestServer (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TestServer element
ms.assetid: caa3547a-2cd5-47ad-ace2-a36752835cfe
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8d1f1fadf76a43caca262652254e8a778602183c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704579"
---
# <a name="testserver-element-dta"></a><span data-ttu-id="0f391-102">TestServer, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="0f391-102">TestServer Element (DTA)</span></span>
  <span data-ttu-id="0f391-103">Spécifie le serveur de test à utiliser lors du paramétrage d'un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="0f391-103">Specifies the test server to use when tuning a production server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f391-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0f391-104">Syntax</span></span>  
  
```  
  
<TuningOptions>  
  <TestServer>...</TestServer>  
   ...code removed here...  
</TuningOptions>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="0f391-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="0f391-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="0f391-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="0f391-106">Characteristic</span></span>|<span data-ttu-id="0f391-107">Description</span><span class="sxs-lookup"><span data-stu-id="0f391-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0f391-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="0f391-108">**Data type and length**</span></span>|<span data-ttu-id="0f391-109">**string**, longueur illimitée.</span><span class="sxs-lookup"><span data-stu-id="0f391-109">**string**, unlimited length.</span></span>|  
|<span data-ttu-id="0f391-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="0f391-110">**Default value**</span></span>|<span data-ttu-id="0f391-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="0f391-111">None.</span></span>|  
|<span data-ttu-id="0f391-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="0f391-112">**Occurrence**</span></span>|<span data-ttu-id="0f391-113">facultatif.</span><span class="sxs-lookup"><span data-stu-id="0f391-113">Optional.</span></span> <span data-ttu-id="0f391-114">Peut être utilisé une seule fois pour chaque élément `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="0f391-114">Can use once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="0f391-115">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="0f391-115">Element Relationships</span></span>  
  
|<span data-ttu-id="0f391-116">Relation</span><span class="sxs-lookup"><span data-stu-id="0f391-116">Relationship</span></span>|<span data-ttu-id="0f391-117">Éléments</span><span class="sxs-lookup"><span data-stu-id="0f391-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="0f391-118">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="0f391-118">**Parent element**</span></span>|[<span data-ttu-id="0f391-119">Élément TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="0f391-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="0f391-120">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="0f391-120">**Child elements**</span></span>|<span data-ttu-id="0f391-121">Aucun.</span><span class="sxs-lookup"><span data-stu-id="0f391-121">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0f391-122">Exemple</span><span class="sxs-lookup"><span data-stu-id="0f391-122">Example</span></span>  
 <span data-ttu-id="0f391-123">Pour obtenir un exemple d’utilisation de cet élément, consultez [Réduire la charge de paramétrage du serveur de production](../../relational-databases/performance/reduce-the-production-server-tuning-load.md).</span><span class="sxs-lookup"><span data-stu-id="0f391-123">For a usage example of this element, see [Reduce the Production Server Tuning Load](../../relational-databases/performance/reduce-the-production-server-tuning-load.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f391-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f391-124">See Also</span></span>  
 [<span data-ttu-id="0f391-125">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="0f391-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
