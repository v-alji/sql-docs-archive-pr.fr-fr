---
title: Élément EventString (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- EventString element
ms.assetid: f76c37b4-2f6e-4274-8ee2-87e89d98e8a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 981cd0be06fd0972426fcb2fa67b0c4143cf9178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705787"
---
# <a name="eventstring-element-dta"></a><span data-ttu-id="5a7bd-102">EventString, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="5a7bd-102">EventString Element (DTA)</span></span>
  <span data-ttu-id="5a7bd-103">Spécifie une charge de travail de script [!INCLUDE[tsql](../../includes/tsql-md.md)] directement dans le fichier d'entrée XML.</span><span class="sxs-lookup"><span data-stu-id="5a7bd-103">Specifies a [!INCLUDE[tsql](../../includes/tsql-md.md)] script workload directly in the XML input file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a7bd-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5a7bd-104">Syntax</span></span>  
  
```  
  
<Workload>  
    <EventString Weight="...">  
    ...code removed here...  
    </EventString>  
</Workload>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="5a7bd-105">Attributs des éléments</span><span class="sxs-lookup"><span data-stu-id="5a7bd-105">Element Attributes</span></span>  
  
|<span data-ttu-id="5a7bd-106">Attribut</span><span class="sxs-lookup"><span data-stu-id="5a7bd-106">Attribute</span></span>|<span data-ttu-id="5a7bd-107">Description</span><span class="sxs-lookup"><span data-stu-id="5a7bd-107">Description</span></span>|  
|---------------|-----------------|  
|`Weight`|<span data-ttu-id="5a7bd-108">facultatif.</span><span class="sxs-lookup"><span data-stu-id="5a7bd-108">Optional.</span></span> <span data-ttu-id="5a7bd-109">Spécifie le facteur de pondération de la requête (facteur d'importance) pour l'événement spécifié.</span><span class="sxs-lookup"><span data-stu-id="5a7bd-109">Specifies the query weight factor (a factor of importance) for the specified event.</span></span> <span data-ttu-id="5a7bd-110">Utilisez un type de données `float` pour spécifier la pondération.</span><span class="sxs-lookup"><span data-stu-id="5a7bd-110">Use a `float` data type to specify the weight.</span></span> <span data-ttu-id="5a7bd-111">Par exemple, `Weight`="100.01".</span><span class="sxs-lookup"><span data-stu-id="5a7bd-111">For example, `Weight`="100.01".</span></span> <span data-ttu-id="5a7bd-112">La valeur minimale que vous pouvez spécifier pour `Weight` est « 0 ».</span><span class="sxs-lookup"><span data-stu-id="5a7bd-112">The minimum value you can specify for `Weight` is "0".</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="5a7bd-113">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="5a7bd-113">Element Characteristics</span></span>  
  
|<span data-ttu-id="5a7bd-114">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="5a7bd-114">Characteristic</span></span>|<span data-ttu-id="5a7bd-115">Description</span><span class="sxs-lookup"><span data-stu-id="5a7bd-115">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="5a7bd-116">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="5a7bd-116">**Data type and length**</span></span>|<span data-ttu-id="5a7bd-117">`string`, la longueur est illimitée.</span><span class="sxs-lookup"><span data-stu-id="5a7bd-117">`string`, length is unlimited.</span></span>|  
|<span data-ttu-id="5a7bd-118">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="5a7bd-118">**Default value**</span></span>|<span data-ttu-id="5a7bd-119">Aucun.</span><span class="sxs-lookup"><span data-stu-id="5a7bd-119">None.</span></span>|  
|<span data-ttu-id="5a7bd-120">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="5a7bd-120">**Occurrence**</span></span>|<span data-ttu-id="5a7bd-121">Obligatoire une fois si aucun autre type de charge de travail n'est spécifié.</span><span class="sxs-lookup"><span data-stu-id="5a7bd-121">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="5a7bd-122">Vous devez spécifier un élément enfant `EventString`, `File` ou `Database` pour le parent `Workload`, mais un seul type peut être utilisé.</span><span class="sxs-lookup"><span data-stu-id="5a7bd-122">You must specify an `EventString`, a `File`, or a `Database` child element for the `Workload` parent, but only one type can be used.</span></span> <span data-ttu-id="5a7bd-123">Par exemple, si vous spécifiez une charge de travail avec l'élément `EventString`, vous ne pouvez pas spécifier une charge de travail avec l'élément `File` dans le même fichier d'entrée XML.</span><span class="sxs-lookup"><span data-stu-id="5a7bd-123">For example, if you specify a workload with the `EventString` element, then you cannot also specify a workload with the `File` element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="5a7bd-124">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="5a7bd-124">Element Relationships</span></span>  
  
|<span data-ttu-id="5a7bd-125">Relation</span><span class="sxs-lookup"><span data-stu-id="5a7bd-125">Relationship</span></span>|<span data-ttu-id="5a7bd-126">Éléments</span><span class="sxs-lookup"><span data-stu-id="5a7bd-126">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="5a7bd-127">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="5a7bd-127">**Parent element**</span></span>|[<span data-ttu-id="5a7bd-128">Workload, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="5a7bd-128">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="5a7bd-129">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="5a7bd-129">**Child elements**</span></span>|<span data-ttu-id="5a7bd-130">Aucun.</span><span class="sxs-lookup"><span data-stu-id="5a7bd-130">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5a7bd-131">Exemple</span><span class="sxs-lookup"><span data-stu-id="5a7bd-131">Example</span></span>  
 <span data-ttu-id="5a7bd-132">Pour obtenir un exemple d’utilisation de cet élément, consultez [Exemple de fichier d’entrée XML avec une charge de travail Inline &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md).</span><span class="sxs-lookup"><span data-stu-id="5a7bd-132">For a usage example of this element, see the [XML Input File Sample with Inline Workload &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md) .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a7bd-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5a7bd-133">See Also</span></span>  
 [<span data-ttu-id="5a7bd-134">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="5a7bd-134">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
