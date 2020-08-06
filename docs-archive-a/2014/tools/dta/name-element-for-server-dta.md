---
title: Élément Name pour le serveur (DTA) | Microsoft Docs
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
ms.assetid: 4c94754d-6d62-4357-8ce7-f107ebf90c71
author: stevestein
ms.author: sstein
ms.openlocfilehash: 202258c3c87f8a35d1ee30b19880f5e9423fa394
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612056"
---
# <a name="name-element-for-server-dta"></a><span data-ttu-id="32c1b-102">Name, élément pour les serveurs (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="32c1b-102">Name Element for Server (DTA)</span></span>
  <span data-ttu-id="32c1b-103">Contient le nom du serveur sur lequel résident les bases de données que vous souhaitez paramétrer.</span><span class="sxs-lookup"><span data-stu-id="32c1b-103">Contains the name of the server where the databases you want to tune reside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32c1b-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="32c1b-104">Syntax</span></span>  
  
```  
  
...code removed here...  
<Server>  
    <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="32c1b-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="32c1b-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="32c1b-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="32c1b-106">Characteristic</span></span>|<span data-ttu-id="32c1b-107">Description</span><span class="sxs-lookup"><span data-stu-id="32c1b-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="32c1b-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="32c1b-108">**Data type and length**</span></span>|<span data-ttu-id="32c1b-109">`string`, entre 1 et 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="32c1b-109">`string`, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="32c1b-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="32c1b-110">**Default value**</span></span>|<span data-ttu-id="32c1b-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="32c1b-111">None.</span></span>|  
|<span data-ttu-id="32c1b-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="32c1b-112">**Occurrence**</span></span>|<span data-ttu-id="32c1b-113">Obligatoire une fois par élément **Server** .</span><span class="sxs-lookup"><span data-stu-id="32c1b-113">Required once per **Server** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="32c1b-114">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="32c1b-114">Element Relationships</span></span>  
  
|<span data-ttu-id="32c1b-115">Relation</span><span class="sxs-lookup"><span data-stu-id="32c1b-115">Relationship</span></span>|<span data-ttu-id="32c1b-116">Éléments</span><span class="sxs-lookup"><span data-stu-id="32c1b-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="32c1b-117">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="32c1b-117">**Parent element**</span></span>|[<span data-ttu-id="32c1b-118">Server, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="32c1b-118">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)|  
|<span data-ttu-id="32c1b-119">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="32c1b-119">**Child elements**</span></span>|<span data-ttu-id="32c1b-120">Aucun.</span><span class="sxs-lookup"><span data-stu-id="32c1b-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="32c1b-121">Exemple</span><span class="sxs-lookup"><span data-stu-id="32c1b-121">Example</span></span>  
 <span data-ttu-id="32c1b-122">Pour voir un exemple d’utilisation de l’élément **Name** , consultez [Server, élément &#40;Assistant Paramétrage de base de données&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="32c1b-122">For an example of how this **Name** element is used, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32c1b-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32c1b-123">See Also</span></span>  
 [<span data-ttu-id="32c1b-124">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="32c1b-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
