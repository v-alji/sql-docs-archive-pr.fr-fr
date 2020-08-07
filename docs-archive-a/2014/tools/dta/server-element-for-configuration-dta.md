---
title: Élément Server pour configuration (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Server element
ms.assetid: da9ff870-9cfd-42fe-994b-7b9292681f7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 88182cdad2e7313f0910a106ee37d727d840bfed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612045"
---
# <a name="server-element-for-configuration-dta"></a><span data-ttu-id="97f60-102">Server, élément pour les configurations (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="97f60-102">Server Element for Configuration (DTA)</span></span>
  <span data-ttu-id="97f60-103">Contient les informations d'identification du serveur sur lequel vous souhaitez que l'Assistant Paramétrage du moteur de base de données évalue la configuration hypothétique (spécifiée par l'élément `Configuration`).</span><span class="sxs-lookup"><span data-stu-id="97f60-103">Contains the identifying information for the server where you want Database Engine Tuning Advisor to evaluate the hypothetical configuration (specified by the `Configuration` element).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97f60-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="97f60-104">Syntax</span></span>  
  
```  
  
<Configuration>  
    <Server>  
...code removed here...  
    </Server>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="97f60-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="97f60-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="97f60-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="97f60-106">Characteristic</span></span>|<span data-ttu-id="97f60-107">Description</span><span class="sxs-lookup"><span data-stu-id="97f60-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="97f60-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="97f60-108">**Data type and length**</span></span>|<span data-ttu-id="97f60-109">Aucun.</span><span class="sxs-lookup"><span data-stu-id="97f60-109">None.</span></span>|  
|<span data-ttu-id="97f60-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="97f60-110">**Default value**</span></span>|<span data-ttu-id="97f60-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="97f60-111">None.</span></span>|  
|<span data-ttu-id="97f60-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="97f60-112">**Occurrence**</span></span>|<span data-ttu-id="97f60-113">Obligatoire une fois par élément `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="97f60-113">Required once per `Configuration` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="97f60-114">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="97f60-114">Element Relationships</span></span>  
  
|<span data-ttu-id="97f60-115">Relation</span><span class="sxs-lookup"><span data-stu-id="97f60-115">Relationship</span></span>|<span data-ttu-id="97f60-116">Éléments</span><span class="sxs-lookup"><span data-stu-id="97f60-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="97f60-117">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="97f60-117">**Parent element**</span></span>|[<span data-ttu-id="97f60-118">Configuration, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="97f60-118">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)|  
|<span data-ttu-id="97f60-119">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="97f60-119">**Child elements**</span></span>|[<span data-ttu-id="97f60-120">Name, élément pour les serveurs &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="97f60-120">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)<br /><br /> [<span data-ttu-id="97f60-121">Database, élément pour les configurations &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="97f60-121">Database Element for Configuration &#40;DTA&#41;</span></span>](database-element-for-configuration-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="97f60-122">Notes</span><span class="sxs-lookup"><span data-stu-id="97f60-122">Remarks</span></span>  
 <span data-ttu-id="97f60-123">Vous ne pouvez spécifier qu’un seul `Server` élément pour l' `Configuration` élément.</span><span class="sxs-lookup"><span data-stu-id="97f60-123">You can specify only one `Server` element for the `Configuration` element.</span></span> <span data-ttu-id="97f60-124">Cet élément porte le nom **ServerTypecomplexType** dans le [schéma XML de l’Assistant Paramétrage du moteur de base de données](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="97f60-124">This element is of the **ServerTypecomplexType** name in the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span> <span data-ttu-id="97f60-125">Ne confondez pas cet élément `Server` avec l'élément enfant de l'élément `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="97f60-125">Do not confuse this `Server` element with the one that is the child of the `DTAInput` element.</span></span> <span data-ttu-id="97f60-126">Pour plus d’informations, consultez [Server, élément &#40;Assistant Paramétrage de base de données&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="97f60-126">For more information, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="97f60-127">Exemple</span><span class="sxs-lookup"><span data-stu-id="97f60-127">Example</span></span>  
 <span data-ttu-id="97f60-128">Pour obtenir un exemple d’utilisation, consultez l’[Exemple de fichier d’entrée XML avec une configuration spécifiée par l’utilisateur &#40;Assistant Paramétrage de base de données&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="97f60-128">For a usage example, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97f60-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="97f60-129">See Also</span></span>  
 [<span data-ttu-id="97f60-130">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="97f60-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
