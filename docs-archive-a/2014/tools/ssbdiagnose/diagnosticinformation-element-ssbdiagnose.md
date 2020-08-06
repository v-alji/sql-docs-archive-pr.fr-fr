---
title: Élément DiagnosticInformation (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- XML output file format [ssbdiagnose], diagnosticinformation element
- diagnosticinformation element
- ssbdiagnose
ms.assetid: 0cfda544-542c-4cf4-86d2-8031c91b10f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 92d76a065c24ddc1fc8d85989ed3202308571951
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602703"
---
# <a name="diagnosticinformation-element-ssbdiagnose"></a><span data-ttu-id="737c1-102">Élément DiagnosticInformation (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="737c1-102">DiagnosticInformation Element (ssbdiagnose)</span></span>
  <span data-ttu-id="737c1-103">L’élément **DiagnosticInformation** contient tous les éléments qui signalent les informations de diagnostic trouvées par l’utilitaire.</span><span class="sxs-lookup"><span data-stu-id="737c1-103">The **DiagnosticInformation** element contains all elements that report the diagnostic information found by the utility.</span></span> <span data-ttu-id="737c1-104">**DiagnosticInformation** est l’élément racine d’un fichier de sortie XML **ssbdiagnostic** .</span><span class="sxs-lookup"><span data-stu-id="737c1-104">**DiagnosticInformation** is the root element of a **ssbdiagnostic** XML output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="737c1-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="737c1-105">Syntax</span></span>  
  
```  
  
<DiagnosticInformation>   
    ...   
</DiagnosticInformation>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="737c1-106">Attributs des éléments</span><span class="sxs-lookup"><span data-stu-id="737c1-106">Element Attributes</span></span>  
  
|<span data-ttu-id="737c1-107">Attribut</span><span class="sxs-lookup"><span data-stu-id="737c1-107">Attribute</span></span>|<span data-ttu-id="737c1-108">Description</span><span class="sxs-lookup"><span data-stu-id="737c1-108">Description</span></span>|  
|---------------|-----------------|  
|`None`|<span data-ttu-id="737c1-109">N/A</span><span class="sxs-lookup"><span data-stu-id="737c1-109">N/A</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="737c1-110">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="737c1-110">Element Characteristics</span></span>  
  
|<span data-ttu-id="737c1-111">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="737c1-111">Characteristic</span></span>|<span data-ttu-id="737c1-112">Description</span><span class="sxs-lookup"><span data-stu-id="737c1-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="737c1-113">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="737c1-113">**Data type and length**</span></span>|<span data-ttu-id="737c1-114">Aucun.</span><span class="sxs-lookup"><span data-stu-id="737c1-114">None.</span></span>|  
|<span data-ttu-id="737c1-115">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="737c1-115">**Default value**</span></span>|<span data-ttu-id="737c1-116">Aucun.</span><span class="sxs-lookup"><span data-stu-id="737c1-116">None.</span></span>|  
|<span data-ttu-id="737c1-117">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="737c1-117">**Occurrence**</span></span>|<span data-ttu-id="737c1-118">Une fois par fichier de sortie XML **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="737c1-118">Once per **ssbdiagnose** XML output file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="737c1-119">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="737c1-119">Element Relationships</span></span>  
  
|<span data-ttu-id="737c1-120">Relation</span><span class="sxs-lookup"><span data-stu-id="737c1-120">Relationship</span></span>|<span data-ttu-id="737c1-121">Éléments</span><span class="sxs-lookup"><span data-stu-id="737c1-121">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="737c1-122">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="737c1-122">**Parent element**</span></span>|<span data-ttu-id="737c1-123">Aucun.</span><span class="sxs-lookup"><span data-stu-id="737c1-123">None.</span></span>|  
|<span data-ttu-id="737c1-124">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="737c1-124">**Child elements**</span></span>|[<span data-ttu-id="737c1-125">Élément Banner &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="737c1-125">Banner Element &#40;ssbdiagnose&#41;</span></span>](banner-element-ssbdiagnose.md)<br /><br /> [<span data-ttu-id="737c1-126">Élément Issue &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="737c1-126">Issue Element &#40;ssbdiagnose&#41;</span></span>](issue-element-ssbdiagnose.md)|  
  
## <a name="remarks"></a><span data-ttu-id="737c1-127">Notes</span><span class="sxs-lookup"><span data-stu-id="737c1-127">Remarks</span></span>  
 <span data-ttu-id="737c1-128">Pour plus d'informations sur les espaces de noms XML, consultez l'article [Namespaces in an XML Document](https://go.microsoft.com/fwlink/?LinkId=7341) dans la bibliothèque [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN.</span><span class="sxs-lookup"><span data-stu-id="737c1-128">For more information about XML namespaces, see [Namespaces in an XML Document](https://go.microsoft.com/fwlink/?LinkId=7341) in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="737c1-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="737c1-129">See Also</span></span>  
 [<span data-ttu-id="737c1-130">Utilitaire ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="737c1-130">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
