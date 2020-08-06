---
title: Élément Database pour le serveur (DTA) | Microsoft Docs
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
ms.assetid: 5cd9a87a-af4b-45f3-8c18-f7fd7e7d3064
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9a48d255898eff6bd780f8edf2c8d2da7229b0ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695012"
---
# <a name="database-element-for-server-dta"></a><span data-ttu-id="02b73-102">Élément Database pour les serveurs (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="02b73-102">Database Element for Server (DTA)</span></span>
  <span data-ttu-id="02b73-103">Spécifie la base de données que vous souhaitez paramétrer sur un serveur spécifique.</span><span class="sxs-lookup"><span data-stu-id="02b73-103">Specifies the database you want to tune on a specific server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02b73-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="02b73-104">Syntax</span></span>  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="02b73-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="02b73-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="02b73-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="02b73-106">Characteristic</span></span>|<span data-ttu-id="02b73-107">Description</span><span class="sxs-lookup"><span data-stu-id="02b73-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="02b73-108">Type de données et longueur</span><span class="sxs-lookup"><span data-stu-id="02b73-108">Data type and length</span></span>|<span data-ttu-id="02b73-109">Aucun.</span><span class="sxs-lookup"><span data-stu-id="02b73-109">None.</span></span>|  
|<span data-ttu-id="02b73-110">Valeur par défaut</span><span class="sxs-lookup"><span data-stu-id="02b73-110">Default value</span></span>|<span data-ttu-id="02b73-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="02b73-111">None.</span></span>|  
|<span data-ttu-id="02b73-112">Occurrence</span><span class="sxs-lookup"><span data-stu-id="02b73-112">Occurrence</span></span>|<span data-ttu-id="02b73-113">Obligatoire une ou plusieurs fois par élément `Server`.</span><span class="sxs-lookup"><span data-stu-id="02b73-113">Required one or more times per `Server` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="02b73-114">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="02b73-114">Element Relationships</span></span>  
  
|<span data-ttu-id="02b73-115">Relation</span><span class="sxs-lookup"><span data-stu-id="02b73-115">Relationship</span></span>|<span data-ttu-id="02b73-116">Éléments</span><span class="sxs-lookup"><span data-stu-id="02b73-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="02b73-117">Élément parent</span><span class="sxs-lookup"><span data-stu-id="02b73-117">Parent element</span></span>|[<span data-ttu-id="02b73-118">Server, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="02b73-118">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)|  
|<span data-ttu-id="02b73-119">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="02b73-119">Child elements</span></span>|[<span data-ttu-id="02b73-120">Name, élément pour les bases de données &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="02b73-120">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="02b73-121">Schema, élément pour les bases de données &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="02b73-121">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="02b73-122">Notes</span><span class="sxs-lookup"><span data-stu-id="02b73-122">Remarks</span></span>  
 <span data-ttu-id="02b73-123">Cet élément porte le nom **DatabaseDetailsTypecomplexType** dans le schéma XML de l’Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="02b73-123">This element is of the **DatabaseDetailsTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="02b73-124">Ne confondez pas cet élément `Database` avec celui dont le parent racine est l'élément `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="02b73-124">Do not confuse this `Database` element with the one whose root parent is the `Configuration` element.</span></span> <span data-ttu-id="02b73-125">Pour plus d’informations, consultez [Database, élément pour les configurations &#40;Assistant Paramétrage de base de données&#41;](database-element-for-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="02b73-125">For more information, see [Database Element for Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="02b73-126">Exemple</span><span class="sxs-lookup"><span data-stu-id="02b73-126">Example</span></span>  
 <span data-ttu-id="02b73-127">Pour obtenir un exemple d’utilisation de l' `Database` élément, consultez [Server, élément &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="02b73-127">For a usage example of the `Database` element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02b73-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="02b73-128">See Also</span></span>  
 [<span data-ttu-id="02b73-129">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="02b73-129">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
