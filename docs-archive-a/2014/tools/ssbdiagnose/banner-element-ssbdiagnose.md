---
title: Élément Banner (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- banner element
- XML output file format [ssbdiagnose], banner element
- ssbdiagnose
ms.assetid: cc6cd49a-acf0-4cfb-8c6a-554692b89de2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13238ac4ef1745dea4fbf3392484ac6137c09df1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710084"
---
# <a name="banner-element-ssbdiagnose"></a><span data-ttu-id="f5baf-102">Élément Banner (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="f5baf-102">Banner Element (ssbdiagnose)</span></span>
  <span data-ttu-id="f5baf-103">Identifie quel utilitaire a généré le fichier de sortie XML **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="f5baf-103">Identifies which utility generated the **ssbdiagnose** output XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5baf-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f5baf-104">Syntax</span></span>  
  
```  
  
<Banner  
    title="..."   
    product="..."   
    version="..." />  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="f5baf-105">Attributs des éléments</span><span class="sxs-lookup"><span data-stu-id="f5baf-105">Element Attributes</span></span>  
  
|<span data-ttu-id="f5baf-106">Attribut</span><span class="sxs-lookup"><span data-stu-id="f5baf-106">Attribute</span></span>|<span data-ttu-id="f5baf-107">Description</span><span class="sxs-lookup"><span data-stu-id="f5baf-107">Description</span></span>|  
|---------------|-----------------|  
|`title`|<span data-ttu-id="f5baf-108">Identifie l’utilitaire qui a généré le fichier de sortie XML **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="f5baf-108">Identifies the utility that generated the **ssbdiagnose** XML output file.</span></span>|  
|`product`|<span data-ttu-id="f5baf-109">Identifie le produit qui a généré le fichier de sortie XML **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="f5baf-109">Identifies the product that generated the **ssbdiagnose** XML output file.</span></span>|  
|`version`|<span data-ttu-id="f5baf-110">Identifie quelle version de l'utilitaire a généré le fichier de sortie XML.</span><span class="sxs-lookup"><span data-stu-id="f5baf-110">Identifies which version of the utility generated the XML output file.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="f5baf-111">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="f5baf-111">Element Characteristics</span></span>  
  
|<span data-ttu-id="f5baf-112">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="f5baf-112">Characteristic</span></span>|<span data-ttu-id="f5baf-113">Description</span><span class="sxs-lookup"><span data-stu-id="f5baf-113">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="f5baf-114">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="f5baf-114">**Data type and length**</span></span>|<span data-ttu-id="f5baf-115">Aucun.</span><span class="sxs-lookup"><span data-stu-id="f5baf-115">None.</span></span>|  
|<span data-ttu-id="f5baf-116">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="f5baf-116">**Default value**</span></span>|<span data-ttu-id="f5baf-117">Aucun.</span><span class="sxs-lookup"><span data-stu-id="f5baf-117">None.</span></span>|  
|<span data-ttu-id="f5baf-118">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="f5baf-118">**Occurrence**</span></span>|<span data-ttu-id="f5baf-119">Se produit une fois par fichier de sortie XML **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="f5baf-119">Occurs once per **ssbdiagnose** output XML file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="f5baf-120">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="f5baf-120">Element Relationships</span></span>  
  
|<span data-ttu-id="f5baf-121">Relation</span><span class="sxs-lookup"><span data-stu-id="f5baf-121">Relationship</span></span>|<span data-ttu-id="f5baf-122">Éléments</span><span class="sxs-lookup"><span data-stu-id="f5baf-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="f5baf-123">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="f5baf-123">**Parent element**</span></span>|[<span data-ttu-id="f5baf-124">Élément DiagnosticInformation &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="f5baf-124">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)|  
|<span data-ttu-id="f5baf-125">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="f5baf-125">**Child elements**</span></span>|<span data-ttu-id="f5baf-126">Aucun.</span><span class="sxs-lookup"><span data-stu-id="f5baf-126">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f5baf-127">Exemple</span><span class="sxs-lookup"><span data-stu-id="f5baf-127">Example</span></span>  
 <span data-ttu-id="f5baf-128">Exemple d'élément Banner.</span><span class="sxs-lookup"><span data-stu-id="f5baf-128">This is an example of a banner element.</span></span>  
  
```  
<Banner title="Service Broker Diagnostics Utility" product="Microsoft SQL Server" version="10.0.1073.0" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5baf-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5baf-129">See Also</span></span>  
 [<span data-ttu-id="f5baf-130">Utilitaire ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="f5baf-130">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
