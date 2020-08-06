---
title: Élément Name pour la table (DTA) | Microsoft Docs
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
ms.assetid: 422a755f-ee52-4863-b1aa-f4ef1b8fd0bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8fa8481cf8990fb63995abcb6300cd9a352c859a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612053"
---
# <a name="name-element-for-table-dta"></a><span data-ttu-id="679da-102">Name, élément pour les tables (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="679da-102">Name Element for Table (DTA)</span></span>
  <span data-ttu-id="679da-103">Spécifie un nom de table pour le paramétrage.</span><span class="sxs-lookup"><span data-stu-id="679da-103">Specifies a table name for tuning.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="679da-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="679da-104">Syntax</span></span>  
  
```  
  
<Schema>  
    <Table>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="679da-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="679da-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="679da-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="679da-106">Characteristic</span></span>|<span data-ttu-id="679da-107">Description</span><span class="sxs-lookup"><span data-stu-id="679da-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="679da-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="679da-108">**Data type and length**</span></span>|<span data-ttu-id="679da-109">`string`, entre 1 et 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="679da-109">`string`, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="679da-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="679da-110">**Default value**</span></span>|<span data-ttu-id="679da-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="679da-111">None.</span></span>|  
|<span data-ttu-id="679da-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="679da-112">**Occurrence**</span></span>|<span data-ttu-id="679da-113">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="679da-113">Required.</span></span> <span data-ttu-id="679da-114">Une fois par élément `Table`.</span><span class="sxs-lookup"><span data-stu-id="679da-114">Once for each `Table` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="679da-115">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="679da-115">Element Relationships</span></span>  
  
|<span data-ttu-id="679da-116">Relation</span><span class="sxs-lookup"><span data-stu-id="679da-116">Relationship</span></span>|<span data-ttu-id="679da-117">Éléments</span><span class="sxs-lookup"><span data-stu-id="679da-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="679da-118">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="679da-118">**Parent element**</span></span>|[<span data-ttu-id="679da-119">Table, élément pour les schémas &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="679da-119">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
|<span data-ttu-id="679da-120">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="679da-120">**Child elements**</span></span>|<span data-ttu-id="679da-121">Aucun.</span><span class="sxs-lookup"><span data-stu-id="679da-121">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="679da-122">Exemple</span><span class="sxs-lookup"><span data-stu-id="679da-122">Example</span></span>  
 <span data-ttu-id="679da-123">Pour obtenir un exemple d’utilisation, consultez [Server, élément &#40;Assistant Paramétrage de base de données&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="679da-123">For a usage example, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="679da-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="679da-124">See Also</span></span>  
 [<span data-ttu-id="679da-125">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="679da-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
