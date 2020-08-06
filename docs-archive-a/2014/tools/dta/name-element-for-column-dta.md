---
title: Élément Name pour la colonne (DTA) | Microsoft Docs
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
ms.assetid: f93b61de-01fe-4237-ada4-f1e481550564
author: stevestein
ms.author: sstein
ms.openlocfilehash: fad3d9a86a7c5db6b6a7503dc90b5a1540e3618b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694991"
---
# <a name="name-element-for-column-dta"></a><span data-ttu-id="1793b-102">Name, élément pour les colonnes (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="1793b-102">Name Element for Column (DTA)</span></span>
  <span data-ttu-id="1793b-103">Spécifie le nom d'une colonne d'index dans une configuration spécifiée par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1793b-103">Specifies the name for an index column in a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1793b-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1793b-104">Syntax</span></span>  
  
```  
  
<Index>  
    <Column>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="1793b-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="1793b-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="1793b-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="1793b-106">Characteristic</span></span>|<span data-ttu-id="1793b-107">Description</span><span class="sxs-lookup"><span data-stu-id="1793b-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="1793b-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="1793b-108">**Data type and length**</span></span>|<span data-ttu-id="1793b-109">`string`, longueur illimitée.</span><span class="sxs-lookup"><span data-stu-id="1793b-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="1793b-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="1793b-110">**Default value**</span></span>|<span data-ttu-id="1793b-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="1793b-111">None.</span></span>|  
|<span data-ttu-id="1793b-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="1793b-112">**Occurrence**</span></span>|<span data-ttu-id="1793b-113">Obligatoire une fois pour chaque `Column` élément.</span><span class="sxs-lookup"><span data-stu-id="1793b-113">Required once for each `Column` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="1793b-114">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="1793b-114">Element Relationships</span></span>  
  
|<span data-ttu-id="1793b-115">Relation</span><span class="sxs-lookup"><span data-stu-id="1793b-115">Relationship</span></span>|<span data-ttu-id="1793b-116">Éléments</span><span class="sxs-lookup"><span data-stu-id="1793b-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="1793b-117">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="1793b-117">**Parent element**</span></span>|[<span data-ttu-id="1793b-118">Column, élément pour les index &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="1793b-118">Column Element for Index &#40;DTA&#41;</span></span>](column-element-for-index-dta.md)|  
|<span data-ttu-id="1793b-119">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="1793b-119">**Child elements**</span></span>|<span data-ttu-id="1793b-120">Aucun.</span><span class="sxs-lookup"><span data-stu-id="1793b-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1793b-121">Exemple</span><span class="sxs-lookup"><span data-stu-id="1793b-121">Example</span></span>  
 <span data-ttu-id="1793b-122">Pour obtenir un exemple d’utilisation de cet élément, consultez l’[Exemple de fichier d’entrée XML avec une configuration spécifiée par l’utilisateur &#40;Assistant Paramétrage de base de données&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="1793b-122">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1793b-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1793b-123">See Also</span></span>  
 [<span data-ttu-id="1793b-124">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="1793b-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
