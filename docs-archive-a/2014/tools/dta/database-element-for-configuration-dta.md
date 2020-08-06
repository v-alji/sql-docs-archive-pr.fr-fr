---
title: Élément Database pour configuration (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database element
ms.assetid: e91ba243-6cc9-457a-8f5a-134f3c71ae69
author: stevestein
ms.author: sstein
ms.openlocfilehash: 69ce1a0ac9912907f6d22916dd6243621e0778db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695015"
---
# <a name="database-element-for-configuration-dta"></a><span data-ttu-id="03bab-102">Database, élément pour les configurations (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="03bab-102">Database Element for Configuration (DTA)</span></span>
  <span data-ttu-id="03bab-103">Spécifie la base de données dans laquelle vous souhaitez que l'Assistant Paramétrage du moteur de base de données évalue la configuration hypothétique (spécifiée par l'élément `Configuration`).</span><span class="sxs-lookup"><span data-stu-id="03bab-103">Specifies the database against which you want the Database Engine Tuning Advisor to evaluate the hypothetical configuration (specified by the `Configuration` element).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03bab-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="03bab-104">Syntax</span></span>  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="03bab-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="03bab-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="03bab-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="03bab-106">Characteristic</span></span>|<span data-ttu-id="03bab-107">Description</span><span class="sxs-lookup"><span data-stu-id="03bab-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="03bab-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="03bab-108">**Data type and length**</span></span>|<span data-ttu-id="03bab-109">Aucun.</span><span class="sxs-lookup"><span data-stu-id="03bab-109">None.</span></span>|  
|<span data-ttu-id="03bab-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="03bab-110">**Default value**</span></span>|<span data-ttu-id="03bab-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="03bab-111">None.</span></span>|  
|<span data-ttu-id="03bab-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="03bab-112">**Occurrence**</span></span>|<span data-ttu-id="03bab-113">Obligatoire une ou plusieurs fois par élément `Server`.</span><span class="sxs-lookup"><span data-stu-id="03bab-113">Required one or more times per `Server` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="03bab-114">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="03bab-114">Element Relationships</span></span>  
  
|<span data-ttu-id="03bab-115">Relation</span><span class="sxs-lookup"><span data-stu-id="03bab-115">Relationship</span></span>|<span data-ttu-id="03bab-116">Éléments</span><span class="sxs-lookup"><span data-stu-id="03bab-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="03bab-117">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="03bab-117">**Parent element**</span></span>|[<span data-ttu-id="03bab-118">Server, élément pour les configurations &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="03bab-118">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)|  
|<span data-ttu-id="03bab-119">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="03bab-119">**Child elements**</span></span>|[<span data-ttu-id="03bab-120">Name, élément pour les bases de données &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="03bab-120">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="03bab-121">Schema, élément pour les bases de données &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="03bab-121">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="03bab-122">Recommendation, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="03bab-122">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="03bab-123">Notes</span><span class="sxs-lookup"><span data-stu-id="03bab-123">Remarks</span></span>  
 <span data-ttu-id="03bab-124">Cet élément porte le nom **DatabaseTypecomplexType** dans le schéma XML de l’Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="03bab-124">This element is of the **DatabaseTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="03bab-125">Ne confondez pas cet élément `Database` avec celui dont le parent racine est l'élément `Server`, qui se trouve en haut du fichier d'entrée XML.</span><span class="sxs-lookup"><span data-stu-id="03bab-125">Do not confuse this `Database` element with the one whose root parent is the `Server` element, which occurs at the top of the XML input file.</span></span> <span data-ttu-id="03bab-126">Pour plus d’informations, consultez [Database, élément pour les serveurs &#40;Assistant Paramétrage de base de données&#41;](database-element-for-server-dta.md).</span><span class="sxs-lookup"><span data-stu-id="03bab-126">For more information, see [Database Element for Server &#40;DTA&#41;](database-element-for-server-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="03bab-127">Exemple</span><span class="sxs-lookup"><span data-stu-id="03bab-127">Example</span></span>  
 <span data-ttu-id="03bab-128">Pour obtenir un exemple d’utilisation de cet `Database` élément, consultez l' [exemple de fichier d’entrée XML avec une configuration spécifiée par l’utilisateur &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="03bab-128">For a usage example of this `Database` element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03bab-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="03bab-129">See Also</span></span>  
 [<span data-ttu-id="03bab-130">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="03bab-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
