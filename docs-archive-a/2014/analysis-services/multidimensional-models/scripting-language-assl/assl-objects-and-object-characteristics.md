---
title: Objets ASSL et caractéristiques de l’objet | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- reference exceptions [Analysis Services Scripting Language]
- ASSL, objects
- inheritance [Analysis Services Scripting Language]
- localized names [Analysis Services Scripting Language]
- objects [Analysis Services Scripting Language]
- names [Analysis Services Scripting Language]
- Analysis Services Scripting Language, objects
- expansion [Analysis Services Scripting Language]
ms.assetid: 6e5c28b5-c0bc-4ccd-82e5-e174bbb71386
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76d57bb421a7f486983476a6549a5121ce88ee9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611978"
---
# <a name="assl-objects-and-object-characteristics"></a><span data-ttu-id="80b38-102">Objets ASSL et caractéristiques des objets</span><span class="sxs-lookup"><span data-stu-id="80b38-102">ASSL Objects and Object Characteristics</span></span>
  <span data-ttu-id="80b38-103">Dans le langage ASSL (Analysis Services Scripting Language), les objets suivent des recommandations spécifiques en ce qui concerne les groupes d'objets, l'héritage, l'affectation de noms, l'expansion et le traitement.</span><span class="sxs-lookup"><span data-stu-id="80b38-103">Objects in Analysis Services Scripting Language (ASSL) follow specific guidelines in regards to object groups, inheritance, naming, expansion, and processing.</span></span>  
  
## <a name="object-groups"></a><span data-ttu-id="80b38-104">Groupes d'objets</span><span class="sxs-lookup"><span data-stu-id="80b38-104">Object Groups</span></span>  
 <span data-ttu-id="80b38-105">Tous les [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] objets ont une représentation XML.</span><span class="sxs-lookup"><span data-stu-id="80b38-105">All [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] objects have an XML representation.</span></span> <span data-ttu-id="80b38-106">Les objets se répartissent en deux groupes :</span><span class="sxs-lookup"><span data-stu-id="80b38-106">The objects are divided into two groups:</span></span>  
  
 <span data-ttu-id="80b38-107">**Objets principaux**</span><span class="sxs-lookup"><span data-stu-id="80b38-107">**Major objects**</span></span>  
 <span data-ttu-id="80b38-108">Les objets principaux peuvent être créés, modifiés et supprimés de manière indépendante.</span><span class="sxs-lookup"><span data-stu-id="80b38-108">Major objects can be independently created, altered, and deleted.</span></span> <span data-ttu-id="80b38-109">Les objets principaux sont représentés par les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="80b38-109">Major objects include:</span></span>  
  
-   <span data-ttu-id="80b38-110">Serveurs</span><span class="sxs-lookup"><span data-stu-id="80b38-110">Servers</span></span>  
  
-   <span data-ttu-id="80b38-111">Bases de données</span><span class="sxs-lookup"><span data-stu-id="80b38-111">Databases</span></span>  
  
-   <span data-ttu-id="80b38-112">Dimensions</span><span class="sxs-lookup"><span data-stu-id="80b38-112">Dimensions</span></span>  
  
-   <span data-ttu-id="80b38-113">Cubes</span><span class="sxs-lookup"><span data-stu-id="80b38-113">Cubes</span></span>  
  
-   <span data-ttu-id="80b38-114">les groupes de mesures ;</span><span class="sxs-lookup"><span data-stu-id="80b38-114">Measure groups</span></span>  
  
-   <span data-ttu-id="80b38-115">Partitions</span><span class="sxs-lookup"><span data-stu-id="80b38-115">Partitions</span></span>  
  
-   <span data-ttu-id="80b38-116">Perspectives</span><span class="sxs-lookup"><span data-stu-id="80b38-116">Perspectives</span></span>  
  
-   <span data-ttu-id="80b38-117">Modèles d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="80b38-117">Mining models</span></span>  
  
-   <span data-ttu-id="80b38-118">Rôles</span><span class="sxs-lookup"><span data-stu-id="80b38-118">Roles</span></span>  
  
-   <span data-ttu-id="80b38-119">Commandes associées à un serveur ou à une base de données</span><span class="sxs-lookup"><span data-stu-id="80b38-119">Commands associated with a server or database</span></span>  
  
-   <span data-ttu-id="80b38-120">Sources de données</span><span class="sxs-lookup"><span data-stu-id="80b38-120">Data sources</span></span>  
  
 <span data-ttu-id="80b38-121">Les objets principaux s'appuient sur les propriétés suivantes pour suivre leur historique et leur état :</span><span class="sxs-lookup"><span data-stu-id="80b38-121">Major objects have the following properties to track their history and status.</span></span>  
  
-   `CreatedTimestamp`  
  
-   `LastSchemaUpdate`  
  
-   <span data-ttu-id="80b38-122">`LastProcessed` (le cas échéant)</span><span class="sxs-lookup"><span data-stu-id="80b38-122">`LastProcessed` (where appropriate)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80b38-123">La classification d'un objet comme objet principal a un effet sur la façon dont une instance de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] traite cet objet et sur la façon dont il est traité dans le langage de définition d'objet.</span><span class="sxs-lookup"><span data-stu-id="80b38-123">The classification of an object as a major object affects how an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] treats that object and how that object is handled in the object definition language.</span></span> <span data-ttu-id="80b38-124">Toutefois, cette classification ne garantit pas que les outils de gestion et de développement [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] permettront de créer, modifier ou supprimer ces objets de manière indépendante.</span><span class="sxs-lookup"><span data-stu-id="80b38-124">However, this classification does not guarantee that [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] management and development tools will allow the independent creation, modification, or deletion of these objects.</span></span>  
  
 <span data-ttu-id="80b38-125">**Objets secondaires**</span><span class="sxs-lookup"><span data-stu-id="80b38-125">**Minor objects**</span></span>  
 <span data-ttu-id="80b38-126">Les objets secondaires ne peuvent être créés, modifiés ou supprimés que dans la cadre de la création, de la modification ou de la suppression de l'objet principal parent.</span><span class="sxs-lookup"><span data-stu-id="80b38-126">Minor objects can only be created, altered, or deleted as part of creating, altering, or deleting the parent major object.</span></span> <span data-ttu-id="80b38-127">Les objets secondaires sont représentés par les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="80b38-127">Minor objects include:</span></span>  
  
-   <span data-ttu-id="80b38-128">Hiérarchies et niveaux</span><span class="sxs-lookup"><span data-stu-id="80b38-128">Hierarchies and levels</span></span>  
  
-   <span data-ttu-id="80b38-129">Attributs</span><span class="sxs-lookup"><span data-stu-id="80b38-129">Attributes</span></span>  
  
-   <span data-ttu-id="80b38-130">Mesures</span><span class="sxs-lookup"><span data-stu-id="80b38-130">Measures</span></span>  
  
-   <span data-ttu-id="80b38-131">Colonnes de modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="80b38-131">Mining model columns</span></span>  
  
-   <span data-ttu-id="80b38-132">Commandes associées à un cube</span><span class="sxs-lookup"><span data-stu-id="80b38-132">Commands associated with a cube</span></span>  
  
-   <span data-ttu-id="80b38-133">Agrégations</span><span class="sxs-lookup"><span data-stu-id="80b38-133">Aggregations</span></span>  
  
## <a name="object-expansion"></a><span data-ttu-id="80b38-134">Expansion d'objet</span><span class="sxs-lookup"><span data-stu-id="80b38-134">Object Expansion</span></span>  
 <span data-ttu-id="80b38-135">La restriction `ObjectExpansion` peut être utilisée pour contrôler le degré d'expansion des éléments XML ASSL retournés par le serveur.</span><span class="sxs-lookup"><span data-stu-id="80b38-135">The `ObjectExpansion` restriction can be used to control the degree of expansion of ASSL XML returned by the server.</span></span> <span data-ttu-id="80b38-136">Cette restriction propose les options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="80b38-136">This restriction has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="80b38-137">Valeur d'énumération</span><span class="sxs-lookup"><span data-stu-id="80b38-137">Enumeration value</span></span>|<span data-ttu-id="80b38-138">Autorisé pour\<Alter></span><span class="sxs-lookup"><span data-stu-id="80b38-138">Allowed for \<Alter></span></span>|<span data-ttu-id="80b38-139">Description</span><span class="sxs-lookup"><span data-stu-id="80b38-139">Description</span></span>|  
|-----------------------|---------------------------|-----------------|  
|<span data-ttu-id="80b38-140">*ReferenceOnly*</span><span class="sxs-lookup"><span data-stu-id="80b38-140">*ReferenceOnly*</span></span>|<span data-ttu-id="80b38-141">Non</span><span class="sxs-lookup"><span data-stu-id="80b38-141">no</span></span>|<span data-ttu-id="80b38-142">Retourne uniquement le nom, l'ID et l'horodateur pour l'objet demandé et tous les objets principaux qu'il contient de manière récursive.</span><span class="sxs-lookup"><span data-stu-id="80b38-142">Returns only the name, ID, and timestamp for the requested object and for all contained major objects recursively.</span></span>|  
|<span data-ttu-id="80b38-143">*ObjectProperties*</span><span class="sxs-lookup"><span data-stu-id="80b38-143">*ObjectProperties*</span></span>|<span data-ttu-id="80b38-144">oui</span><span class="sxs-lookup"><span data-stu-id="80b38-144">yes</span></span>|<span data-ttu-id="80b38-145">Développe l'objet demandé et les objets secondaires qu'il contient, mais ne retourne pas les objets principaux qu'il contient.</span><span class="sxs-lookup"><span data-stu-id="80b38-145">Expands the requested object and minor contained objects, but does not return major contained objects.</span></span>|  
|<span data-ttu-id="80b38-146">*ExpandObject*</span><span class="sxs-lookup"><span data-stu-id="80b38-146">*ExpandObject*</span></span>|<span data-ttu-id="80b38-147">Non</span><span class="sxs-lookup"><span data-stu-id="80b38-147">no</span></span>|<span data-ttu-id="80b38-148">Identique à *ObjectProperties*, mais retourne également le nom, l'ID et l'horodateur pour les objets principaux contenus.</span><span class="sxs-lookup"><span data-stu-id="80b38-148">Same as *ObjectProperties*, but also returns the name, ID, and timestamp for contained major objects.</span></span>|  
|<span data-ttu-id="80b38-149">*ExpandFull*</span><span class="sxs-lookup"><span data-stu-id="80b38-149">*ExpandFull*</span></span>|<span data-ttu-id="80b38-150">oui</span><span class="sxs-lookup"><span data-stu-id="80b38-150">yes</span></span>|<span data-ttu-id="80b38-151">Développe entièrement l'objet demandé et touts les objets qu'il contient de manière récursive.</span><span class="sxs-lookup"><span data-stu-id="80b38-151">Fully expands the requested object and all contained objects recursively.</span></span>|  
  
 <span data-ttu-id="80b38-152">Cette section de référence ASSL décrit la représentation *ExpandFull* .</span><span class="sxs-lookup"><span data-stu-id="80b38-152">This ASSL reference section describes the *ExpandFull* representation.</span></span> <span data-ttu-id="80b38-153">Tous les autres niveaux `ObjectExpansion` sont dérivés de ce niveau.</span><span class="sxs-lookup"><span data-stu-id="80b38-153">All other `ObjectExpansion` levels are derived from this level.</span></span>  
  
## <a name="object-processing"></a><span data-ttu-id="80b38-154">Traitement des objets</span><span class="sxs-lookup"><span data-stu-id="80b38-154">Object Processing</span></span>  
 <span data-ttu-id="80b38-155">ASSL inclut des éléments ou des propriétés en lecture seule (par exemple, `LastProcessed`) qui peuvent être lus à partir de l'instance [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], mais qui sont omis lorsque des scripts de commande sont soumis à l'instance.</span><span class="sxs-lookup"><span data-stu-id="80b38-155">ASSL includes read-only elements or properties (for example, `LastProcessed`) that can be read from the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance, but which are omitted when command scripts are submitted to the instance.</span></span> [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="80b38-156">ignore les valeurs modifiées pour les éléments en lecture seule sans émettre d'avertissement ni d'erreur.</span><span class="sxs-lookup"><span data-stu-id="80b38-156">ignores modified values for read-only elements without warning or error.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="80b38-157">ignore également les propriétés non appropriées ou non pertinentes sans déclencher d'erreurs de validation.</span><span class="sxs-lookup"><span data-stu-id="80b38-157">also ignores inappropriate or irrelevant properties without raising validation errors.</span></span> <span data-ttu-id="80b38-158">Par exemple, l'élément X ne doit être présent que lorsque l'élément Y a une valeur particulière.</span><span class="sxs-lookup"><span data-stu-id="80b38-158">For example, the X element should only be present when the Y element has a particular value.</span></span> <span data-ttu-id="80b38-159">L'instance [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] ignore l'élément X au lieu de le valider par rapport à la valeur de l'élément Y.</span><span class="sxs-lookup"><span data-stu-id="80b38-159">The [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance ignores the X element instead of validating that element against the value of the Y element.</span></span>  
  
  
