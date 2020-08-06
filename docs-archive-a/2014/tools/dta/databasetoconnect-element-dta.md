---
title: Élément DatabaseToConnect, (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DatabaseToConnect element
ms.assetid: 65153a66-3aee-4429-99b7-0816ac23c285
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4c21b36319e4007264677d499b84964c7cb5ea7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695008"
---
# <a name="databasetoconnect-element-dta"></a><span data-ttu-id="bf0d1-102">DatabaseToConnect, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="bf0d1-102">DatabaseToConnect Element (DTA)</span></span>
  <span data-ttu-id="bf0d1-103">Spécifie la première base de données à laquelle l'Assistant Paramétrage du moteur de base de données se connecte lors du paramétrage d'une charge de travail.</span><span class="sxs-lookup"><span data-stu-id="bf0d1-103">Specifies the first database to which Database Engine Tuning Advisor connects when tuning a workload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf0d1-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="bf0d1-104">Syntax</span></span>  
  
```  
  
    <TuningOptions>  
...code removed here...  
      <DatabaseToConnect>...</DatabaseToConnect>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="bf0d1-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="bf0d1-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="bf0d1-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="bf0d1-106">Characteristic</span></span>|<span data-ttu-id="bf0d1-107">Description</span><span class="sxs-lookup"><span data-stu-id="bf0d1-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="bf0d1-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="bf0d1-108">**Data type and length**</span></span>|<span data-ttu-id="bf0d1-109">`string`, longueur illimitée.</span><span class="sxs-lookup"><span data-stu-id="bf0d1-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="bf0d1-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="bf0d1-110">**Default value**</span></span>|<span data-ttu-id="bf0d1-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="bf0d1-111">None.</span></span>|  
|<span data-ttu-id="bf0d1-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="bf0d1-112">**Occurrence**</span></span>|<span data-ttu-id="bf0d1-113">facultatif.</span><span class="sxs-lookup"><span data-stu-id="bf0d1-113">Optional.</span></span> <span data-ttu-id="bf0d1-114">Peut être utilisé une seule fois pour chaque élément `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="bf0d1-114">Can use once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="bf0d1-115">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="bf0d1-115">Element Relationships</span></span>  
  
|<span data-ttu-id="bf0d1-116">Relation</span><span class="sxs-lookup"><span data-stu-id="bf0d1-116">Relationship</span></span>|<span data-ttu-id="bf0d1-117">Éléments</span><span class="sxs-lookup"><span data-stu-id="bf0d1-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="bf0d1-118">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="bf0d1-118">**Parent element**</span></span>|[<span data-ttu-id="bf0d1-119">Élément TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="bf0d1-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="bf0d1-120">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="bf0d1-120">**Child elements**</span></span>|<span data-ttu-id="bf0d1-121">None</span><span class="sxs-lookup"><span data-stu-id="bf0d1-121">None</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf0d1-122">Notes</span><span class="sxs-lookup"><span data-stu-id="bf0d1-122">Remarks</span></span>  
 <span data-ttu-id="bf0d1-123">Utilisez `DatabaseToConnect` pour spécifier le nom de la première base de données à laquelle vous souhaitez que l'Assistant Paramétrage du moteur de base de données se connecte lorsqu'il démarre une session de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="bf0d1-123">Use `DatabaseToConnect` to specify the name of the first database to which you want Database Engine Tuning Advisor to connect when it starts the tuning session.</span></span> <span data-ttu-id="bf0d1-124">Vous ne pouvez spécifier qu'une seule base de données avec cet élément.</span><span class="sxs-lookup"><span data-stu-id="bf0d1-124">You can specify only one database with this element.</span></span> <span data-ttu-id="bf0d1-125">Si plusieurs noms de bases de données sont spécifiées, l'Assistant Paramétrage du moteur de base de données renvoie une erreur.</span><span class="sxs-lookup"><span data-stu-id="bf0d1-125">If multiple database names are specified, Database Engine Tuning Advisor returns an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf0d1-126">Exemple</span><span class="sxs-lookup"><span data-stu-id="bf0d1-126">Example</span></span>  
 <span data-ttu-id="bf0d1-127">Pour obtenir un exemple d’utilisation, consultez [Exemple de fichier d’entrée XML avec une charge de travail Inline &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md).</span><span class="sxs-lookup"><span data-stu-id="bf0d1-127">For a usage example, see the [XML Input File Sample with Inline Workload &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf0d1-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bf0d1-128">See Also</span></span>  
 [<span data-ttu-id="bf0d1-129">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="bf0d1-129">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
