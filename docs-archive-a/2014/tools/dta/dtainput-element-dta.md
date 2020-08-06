---
title: Élément DTAInput (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DTAInput element
ms.assetid: 40c19abf-ded5-43de-be96-5b43b1b81b03
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7d2ff380a4ae1595e50aae472efc5fb4ac72efe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696356"
---
# <a name="dtainput-element-dta"></a><span data-ttu-id="00b26-102">DTAInput, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="00b26-102">DTAInput Element (DTA)</span></span>
  <span data-ttu-id="00b26-103">Contient la définition de l'entrée XML pour l'Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="00b26-103">Contains the definition of XML input for Database Engine Tuning Advisor.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00b26-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="00b26-104">Syntax</span></span>  
  
```  
  
<DTAXML>  
    <DTAInput>  
    ...code removed here...  
    </DTAInput>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="00b26-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="00b26-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="00b26-106">Caractéristiques</span><span class="sxs-lookup"><span data-stu-id="00b26-106">Characteristics</span></span>|<span data-ttu-id="00b26-107">Description</span><span class="sxs-lookup"><span data-stu-id="00b26-107">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="00b26-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="00b26-108">**Data type and length**</span></span>|<span data-ttu-id="00b26-109">Aucun.</span><span class="sxs-lookup"><span data-stu-id="00b26-109">None.</span></span>|  
|<span data-ttu-id="00b26-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="00b26-110">**Default value**</span></span>|<span data-ttu-id="00b26-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="00b26-111">None.</span></span>|  
|<span data-ttu-id="00b26-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="00b26-112">**Occurrence**</span></span>|<span data-ttu-id="00b26-113">Obligatoire une fois par élément **DTAXML** .</span><span class="sxs-lookup"><span data-stu-id="00b26-113">Optional once per **DTAXML** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="00b26-114">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="00b26-114">Element Relationships</span></span>  
  
|<span data-ttu-id="00b26-115">Relation</span><span class="sxs-lookup"><span data-stu-id="00b26-115">Relationship</span></span>|<span data-ttu-id="00b26-116">Éléments</span><span class="sxs-lookup"><span data-stu-id="00b26-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="00b26-117">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="00b26-117">**Parent element**</span></span>|[<span data-ttu-id="00b26-118">DTAXML, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="00b26-118">DTAXML Element &#40;DTA&#41;</span></span>](dtaxml-element-dta.md)|  
|<span data-ttu-id="00b26-119">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="00b26-119">**Child elements**</span></span>|[<span data-ttu-id="00b26-120">Server, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="00b26-120">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)<br /><br /> [<span data-ttu-id="00b26-121">Workload, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="00b26-121">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)<br /><br /> [<span data-ttu-id="00b26-122">Élément TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="00b26-122">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)<br /><br /> [<span data-ttu-id="00b26-123">Configuration, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="00b26-123">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="00b26-124">Notes</span><span class="sxs-lookup"><span data-stu-id="00b26-124">Remarks</span></span>  
 <span data-ttu-id="00b26-125">Cet élément est la racine de la hiérarchie de schéma d'entrée de l'Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="00b26-125">This element is the root of the Database Engine Tuning Advisor input schema hierarchy.</span></span> <span data-ttu-id="00b26-126">Les entrées de l'Assistant Paramétrage du moteur de base de données peuvent être des arguments qui spécifient les bases de données à paramétrer, des charges de travail, des options de paramétrage ou une configuration spécifiée par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="00b26-126">Input to Database Engine Tuning Advisor can be arguments that specify the servers whose databases you want to tune, workloads, tuning options, or a user-specified configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00b26-127">Exemple</span><span class="sxs-lookup"><span data-stu-id="00b26-127">Example</span></span>  
 <span data-ttu-id="00b26-128">Pour obtenir un exemple d’utilisation de l’élément **DTAInput**, consultez [Exemple de fichier d’entrée XML simple &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="00b26-128">For a usage example of the **DTAInput** element, see [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b26-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="00b26-129">See Also</span></span>  
 [<span data-ttu-id="00b26-130">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="00b26-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
