---
title: Élément Name pour la base de données (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Name element
ms.assetid: e871c4fa-3b57-46cf-b4f8-e3be86f92dc4
author: stevestein
ms.author: sstein
ms.openlocfilehash: c692e31b9175bf05dcfb0504ea79e98cbb82f36b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694979"
---
# <a name="name-element-for-database-dta"></a><span data-ttu-id="105a1-102">Name, élément pour les bases de données (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="105a1-102">Name Element for Database (DTA)</span></span>
  <span data-ttu-id="105a1-103">Spécifie le nom de la base de données que vous souhaitez paramétrer.</span><span class="sxs-lookup"><span data-stu-id="105a1-103">Specifies the name of a database that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="105a1-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="105a1-104">Syntax</span></span>  
  
```  
  
<Server>  
    <Database>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="105a1-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="105a1-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="105a1-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="105a1-106">Characteristic</span></span>|<span data-ttu-id="105a1-107">Description</span><span class="sxs-lookup"><span data-stu-id="105a1-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="105a1-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="105a1-108">**Data type and length**</span></span>|<span data-ttu-id="105a1-109">`string`, longueur illimitée.</span><span class="sxs-lookup"><span data-stu-id="105a1-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="105a1-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="105a1-110">**Default value**</span></span>|<span data-ttu-id="105a1-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="105a1-111">None.</span></span>|  
|<span data-ttu-id="105a1-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="105a1-112">**Occurrence**</span></span>|<span data-ttu-id="105a1-113">Obligatoire une fois par élément `Database`.</span><span class="sxs-lookup"><span data-stu-id="105a1-113">Required once per `Database` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="105a1-114">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="105a1-114">Element Relationships</span></span>  
  
|<span data-ttu-id="105a1-115">Relation</span><span class="sxs-lookup"><span data-stu-id="105a1-115">Relationship</span></span>|<span data-ttu-id="105a1-116">Éléments</span><span class="sxs-lookup"><span data-stu-id="105a1-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="105a1-117">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="105a1-117">**Parent element**</span></span>|[<span data-ttu-id="105a1-118">Database, élément pour les serveurs &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="105a1-118">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
|<span data-ttu-id="105a1-119">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="105a1-119">**Child elements**</span></span>|<span data-ttu-id="105a1-120">Aucun.</span><span class="sxs-lookup"><span data-stu-id="105a1-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="105a1-121">Exemple</span><span class="sxs-lookup"><span data-stu-id="105a1-121">Example</span></span>  
 <span data-ttu-id="105a1-122">Pour obtenir un exemple d’utilisation de cet élément, consultez [Server, élément &#40;Assistant Paramétrage de base de données&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="105a1-122">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="105a1-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="105a1-123">See Also</span></span>  
 [<span data-ttu-id="105a1-124">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="105a1-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
