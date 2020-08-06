---
title: Élément Database pour la charge de travail (DTA) | Microsoft Docs
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
ms.assetid: 112fca2a-37e5-4162-b2e7-b56eb8ab0c6f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2774bc7ed981c84c966a394c95347208cbc6d656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695016"
---
# <a name="database-element-for-workload-dta"></a><span data-ttu-id="56791-102">Database, élément pour les charges de travail (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="56791-102">Database Element for Workload (DTA)</span></span>
  <span data-ttu-id="56791-103">Spécifie la base de données où se trouve la table de trace de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="56791-103">Specifies the database where the workload trace table is located.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56791-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="56791-104">Syntax</span></span>  
  
```  
  
<Workload>  
  <Database>  
   ...code removed here...  
  </Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="56791-105">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="56791-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="56791-106">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="56791-106">Characteristic</span></span>|<span data-ttu-id="56791-107">Description</span><span class="sxs-lookup"><span data-stu-id="56791-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="56791-108">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="56791-108">**Data type and length**</span></span>|<span data-ttu-id="56791-109">Aucun.</span><span class="sxs-lookup"><span data-stu-id="56791-109">None.</span></span>|  
|<span data-ttu-id="56791-110">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="56791-110">**Default value**</span></span>|<span data-ttu-id="56791-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="56791-111">None.</span></span>|  
|<span data-ttu-id="56791-112">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="56791-112">**Occurrence**</span></span>|<span data-ttu-id="56791-113">Obligatoire une fois si aucun autre type de charge de travail n'est spécifié.</span><span class="sxs-lookup"><span data-stu-id="56791-113">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="56791-114">Vous devez spécifier un élément enfant `EventString`, `File` ou `Database` pour le parent `Workload`, mais un seul type peut être utilisé.</span><span class="sxs-lookup"><span data-stu-id="56791-114">You must specify an `EventString`, a `File`, or a `Database` child element for the `Workload` parent, but only one type can be used.</span></span> <span data-ttu-id="56791-115">Par exemple, si vous spécifiez une charge de travail avec l' `Database` élément, vous ne pouvez pas spécifier une charge de travail avec l' `File` élément dans le même fichier d’entrée XML.</span><span class="sxs-lookup"><span data-stu-id="56791-115">For example, if you specify a workload with the `Database` element, you cannot also specify a workload with the `File` element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="56791-116">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="56791-116">Element Relationships</span></span>  
  
|<span data-ttu-id="56791-117">Relation</span><span class="sxs-lookup"><span data-stu-id="56791-117">Relationship</span></span>|<span data-ttu-id="56791-118">Éléments</span><span class="sxs-lookup"><span data-stu-id="56791-118">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="56791-119">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="56791-119">**Parent element**</span></span>|[<span data-ttu-id="56791-120">Workload, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="56791-120">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="56791-121">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="56791-121">**Child elements**</span></span>|[<span data-ttu-id="56791-122">Name, élément pour les bases de données &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="56791-122">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="56791-123">Schema, élément pour les bases de données &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="56791-123">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="56791-124">Notes</span><span class="sxs-lookup"><span data-stu-id="56791-124">Remarks</span></span>  
 <span data-ttu-id="56791-125">Cet élément porte le nom **DatabaseDetailsTypecomplexType** dans le schéma XML de l’Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="56791-125">This element is of the **DatabaseDetailsTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="56791-126">Ne confondez pas cet élément `Database` avec celui dont le parent racine est l'élément `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="56791-126">Do not confuse this `Database` element with the one whose root parent is the `Configuration` element.</span></span> <span data-ttu-id="56791-127">(Consultez [Database, élément pour les configurations &#40;Assistant Paramétrage de base de données&#41;](database-element-for-configuration-dta.md).)</span><span class="sxs-lookup"><span data-stu-id="56791-127">(See [Database Element for Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md).)</span></span>  
  
## <a name="example"></a><span data-ttu-id="56791-128">Exemple</span><span class="sxs-lookup"><span data-stu-id="56791-128">Example</span></span>  
 <span data-ttu-id="56791-129">Pour obtenir un exemple d’utilisation de cet `Database` élément, consultez l’exemple de code dans [élément de charge de travail &#40;DTA&#41;](workload-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="56791-129">For a usage example of this `Database` element, see the code example in [Workload Element &#40;DTA&#41;](workload-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56791-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="56791-130">See Also</span></span>  
 [<span data-ttu-id="56791-131">Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="56791-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
