---
title: Élément DTAXML (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DTAXML element
ms.assetid: 3d9942ed-8a27-40db-a7c9-808984d914a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9f428cf996bb819ece74c13226fcd5116a19142b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703635"
---
# <a name="dtaxml-element-dta"></a><span data-ttu-id="0bd98-102">DTAXML, élément (Assistant Paramétrage de base de données)</span><span class="sxs-lookup"><span data-stu-id="0bd98-102">DTAXML Element (DTA)</span></span>
  <span data-ttu-id="0bd98-103">Élément racine d'un fichier d'entrée ou de sortie de l'Assistant Paramétrage du moteur de base de données, **DTAXML** contient tous les éléments qui décrivent les entrées et les sorties de paramétrage générées par l'Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="0bd98-103">The root element of a Database Engine Tuning Advisor XML input or output file, **DTAXML** contains all elements that describe tuning input and the tuning output that Database Engine Tuning Advisor generates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bd98-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0bd98-104">Syntax</span></span>  
  
```  
  
<DTAXML   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
    xmlns="https://schemas.microsoft.com/sqlserver/2004/07/dta">  
    ...code removed here...  
</DTAXML>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="0bd98-105">Attributs des éléments</span><span class="sxs-lookup"><span data-stu-id="0bd98-105">Element Attributes</span></span>  
  
|<span data-ttu-id="0bd98-106">Attribut</span><span class="sxs-lookup"><span data-stu-id="0bd98-106">Attribute</span></span>|<span data-ttu-id="0bd98-107">Description</span><span class="sxs-lookup"><span data-stu-id="0bd98-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns:xsi`|<span data-ttu-id="0bd98-108">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="0bd98-108">Required.</span></span> <span data-ttu-id="0bd98-109">Identifie l'espace de noms de l'instance du schéma XML.</span><span class="sxs-lookup"><span data-stu-id="0bd98-109">Identifies the XML Schema Instance namespace.</span></span> <span data-ttu-id="0bd98-110">Les attributs de cet espace de noms servent à référencer le schéma qui est utilisé pour valider le fichier XML de l'Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="0bd98-110">Attributes from this namespace are used to reference the schema that is used to validate the Database Engine Tuning Advisor XML file.</span></span><br /><br /> <span data-ttu-id="0bd98-111">Valeur requise : [http://www.w3.org/2001/XMLSchema-instance](http://www.w3.org/2001/XMLSchema-instance)</span><span class="sxs-lookup"><span data-stu-id="0bd98-111">Required value: [http://www.w3.org/2001/XMLSchema-instance](http://www.w3.org/2001/XMLSchema-instance)</span></span>|  
|`xmlns`|<span data-ttu-id="0bd98-112">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="0bd98-112">Required.</span></span> <span data-ttu-id="0bd98-113">Identifie l'espace de noms de l'Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="0bd98-113">Identifies the Database Engine Tuning Advisor namespace.</span></span><br /><br /> <span data-ttu-id="0bd98-114">Si vous modifiez le fichier XML de l'Assistant Paramétrage du moteur de base de données à l'aide de l'éditeur XML dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], cette valeur est utilisée par l'aide obtenue par la touche F1 et l'aide dynamique pour rechercher les rubriques de référence dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0bd98-114">If you edit the Database Engine Tuning Advisor XML file using the XML editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], this value is used by F1 Help and Dynamic Help to locate possible reference topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span><br /><br /> <span data-ttu-id="0bd98-115">Valeur obligatoire :</span><span class="sxs-lookup"><span data-stu-id="0bd98-115">Required value:</span></span><br /><br /> <span data-ttu-id="0bd98-116">[Database Engine Tuning Advisor XML Schema](https://go.microsoft.com/fwlink/?LinkId=43100) Namespace</span><span class="sxs-lookup"><span data-stu-id="0bd98-116">[Database Engine Tuning Advisor XML Schema](https://go.microsoft.com/fwlink/?LinkId=43100) Namespace</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="0bd98-117">Caractéristiques de l'élément</span><span class="sxs-lookup"><span data-stu-id="0bd98-117">Element Characteristics</span></span>  
  
|<span data-ttu-id="0bd98-118">Caractéristique</span><span class="sxs-lookup"><span data-stu-id="0bd98-118">Characteristic</span></span>|<span data-ttu-id="0bd98-119">Description</span><span class="sxs-lookup"><span data-stu-id="0bd98-119">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0bd98-120">**Type de données et longueur**</span><span class="sxs-lookup"><span data-stu-id="0bd98-120">**Data type and length**</span></span>|<span data-ttu-id="0bd98-121">Aucun.</span><span class="sxs-lookup"><span data-stu-id="0bd98-121">None.</span></span>|  
|<span data-ttu-id="0bd98-122">**Valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="0bd98-122">**Default value**</span></span>|<span data-ttu-id="0bd98-123">Aucun.</span><span class="sxs-lookup"><span data-stu-id="0bd98-123">None.</span></span>|  
|<span data-ttu-id="0bd98-124">**Occurrence**</span><span class="sxs-lookup"><span data-stu-id="0bd98-124">**Occurrence**</span></span>|<span data-ttu-id="0bd98-125">Obligatoire une fois par fichier XML de l'Assistant Paramétrage du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="0bd98-125">Required once per DTA XML file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="0bd98-126">Relations entre les éléments</span><span class="sxs-lookup"><span data-stu-id="0bd98-126">Element Relationships</span></span>  
  
|<span data-ttu-id="0bd98-127">Relation</span><span class="sxs-lookup"><span data-stu-id="0bd98-127">Relationship</span></span>|<span data-ttu-id="0bd98-128">Éléments</span><span class="sxs-lookup"><span data-stu-id="0bd98-128">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="0bd98-129">**Élément parent**</span><span class="sxs-lookup"><span data-stu-id="0bd98-129">**Parent element**</span></span>|<span data-ttu-id="0bd98-130">None</span><span class="sxs-lookup"><span data-stu-id="0bd98-130">None</span></span>|  
|<span data-ttu-id="0bd98-131">**Éléments enfants**</span><span class="sxs-lookup"><span data-stu-id="0bd98-131">**Child elements**</span></span>|[<span data-ttu-id="0bd98-132">DTAInput, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="0bd98-132">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)<br /><br /> <span data-ttu-id="0bd98-133">`DTAOutput`, Élément (consultez [Assistant Paramétrage du moteur de base de données schéma XML](https://schemas.microsoft.com/sqlserver/) pour plus d’informations)</span><span class="sxs-lookup"><span data-stu-id="0bd98-133">`DTAOutput` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bd98-134">Notes</span><span class="sxs-lookup"><span data-stu-id="0bd98-134">Remarks</span></span>  
 <span data-ttu-id="0bd98-135">Pour plus d'informations sur les espaces de noms XML, consultez l'article [Namespaces in an XML Document](https://go.microsoft.com/fwlink/?LinkId=7341) dans la bibliothèque [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN.</span><span class="sxs-lookup"><span data-stu-id="0bd98-135">For more information about XML namespaces, see [Namespaces in an XML Document](https://go.microsoft.com/fwlink/?LinkId=7341) in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bd98-136">Exemple</span><span class="sxs-lookup"><span data-stu-id="0bd98-136">Example</span></span>  
 <span data-ttu-id="0bd98-137">Pour obtenir des exemples d’éléments **DTAXML** caractéristiques, consultez [Exemples de fichiers d’entrée XML &#40;DTA&#41;](xml-input-file-samples-dta.md).</span><span class="sxs-lookup"><span data-stu-id="0bd98-137">For examples of typical **DTAXML** elements, see [XML Input File Samples &#40;DTA&#41;](xml-input-file-samples-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bd98-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0bd98-138">See Also</span></span>  
 <span data-ttu-id="0bd98-139">[Référence des fichiers d’entrée XML &#40;Assistant Paramétrage du moteur de base de données&#41;](xml-input-file-reference-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="0bd98-139">[XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="0bd98-140">Démarrer et utiliser l’Assistant Paramétrage du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="0bd98-140">Start and Use the Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md)  
  
  
