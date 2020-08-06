---
title: Élément Schema pour la base de données (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Schema element
ms.assetid: d932e59c-953f-4ab4-934d-b6baf344835c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7653177878f3a832abd2d1ca266bc5feb17b9a29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601862"
---
# <a name="schema-element-for-database-dta"></a><span data-ttu-id="e86c6-102">Schema, élément pour les bases de données (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="e86c6-102">Schema Element for Database (DTA)</span></span>
  <span data-ttu-id="e86c6-103">Spécifie le schéma de la base de données que vous souhaitez paramétrer.</span><span class="sxs-lookup"><span data-stu-id="e86c6-103">Specifies the schema of the database that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e86c6-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e86c6-104">Syntax</span></span>  
  
```  
  
<Database>  
...code removed here...  
    <Schema>...</Schema>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="e86c6-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="e86c6-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="e86c6-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="e86c6-106">Characteristic</span></span>|<span data-ttu-id="e86c6-107">Description</span><span class="sxs-lookup"><span data-stu-id="e86c6-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="e86c6-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="e86c6-108">**Data type and length**</span></span>|<span data-ttu-id="e86c6-109">Aucun.</span><span class="sxs-lookup"><span data-stu-id="e86c6-109">None.</span></span>|  
|<span data-ttu-id="e86c6-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="e86c6-110">**Default value**</span></span>|<span data-ttu-id="e86c6-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="e86c6-111">None.</span></span>|  
|<span data-ttu-id="e86c6-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="e86c6-112">**Occurrence**</span></span>|<span data-ttu-id="e86c6-113">Obligatoire une fois pour l'élément **Database** spécifié sous l'élément **Server** .</span><span class="sxs-lookup"><span data-stu-id="e86c6-113">Required once for the **Database** element that is specified under the **Server** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="e86c6-114">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="e86c6-114">Element Relationships</span></span>  
  
|<span data-ttu-id="e86c6-115">Relation</span><span class="sxs-lookup"><span data-stu-id="e86c6-115">Relationship</span></span>|<span data-ttu-id="e86c6-116">Éléments</span><span class="sxs-lookup"><span data-stu-id="e86c6-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="e86c6-117">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="e86c6-117">**Parent element**</span></span>|[<span data-ttu-id="e86c6-118">Database, élément pour les serveurs &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="e86c6-118">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
|<span data-ttu-id="e86c6-119">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="e86c6-119">**Child elements**</span></span>|[<span data-ttu-id="e86c6-120">Name, élément pour les schémas &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="e86c6-120">Name Element for Schema &#40;DTA&#41;</span></span>](name-element-for-schema-dta.md)<br /><br /> [<span data-ttu-id="e86c6-121">Table, élément pour les schémas &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="e86c6-121">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="e86c6-122">Exemple</span><span class="sxs-lookup"><span data-stu-id="e86c6-122">Example</span></span>  
 <span data-ttu-id="e86c6-123">Pour obtenir un exemple d’utilisation de cet élément, consultez [Server, élément &#40;Assistant Paramétrage de base de données&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="e86c6-123">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e86c6-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e86c6-124">See Also</span></span>  
 [<span data-ttu-id="e86c6-125">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="e86c6-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
