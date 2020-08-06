---
title: Relations d’attributs | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- member properties [Analysis Services], attribute relationships
- security [Analysis Services], properties
- PROPERTIES keyword
- storage [Analysis Services], attribute relationships
- natural hierarchies [Analysis Services]
- dimensions [Analysis Services], member properties
- queries [MDX], attribute relationships
- user-defined hierarchies [Analysis Services]
- attributes [Analysis Services], relationships
- member properties [Analysis Services]
- members [Analysis Services], attribute relationships
- storing data [Analysis Services], attribute relationships
- relationships [Analysis Services], attributes
ms.assetid: 2491422a-4cf5-4b23-b6ab-289222b22ce8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 122638a2728a8a85ee58661196797383da20eef8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702029"
---
# <a name="attribute-relationships"></a><span data-ttu-id="de457-102">Relations d’attributs</span><span class="sxs-lookup"><span data-stu-id="de457-102">Attribute Relationships</span></span>
  <span data-ttu-id="de457-103">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , les attributs d’une dimension sont toujours liés directement ou indirectement à l’attribut de clé.</span><span class="sxs-lookup"><span data-stu-id="de457-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], attributes within a dimension are always related either directly or indirectly to the key attribute.</span></span> <span data-ttu-id="de457-104">Quand vous définissez une dimension basée sur un schéma en étoile, c'est-à-dire quand tous les attributs de la dimension sont dérivés de la même table relationnelle, une relation d'attribut est automatiquement définie entre l'attribut clé et chaque attribut non-clé de la dimension.</span><span class="sxs-lookup"><span data-stu-id="de457-104">When you define a dimension based on a star schema, which is where all dimension attributes are derived from the same relational table, an attribute relationship is automatically defined between the key attribute and each non-key attribute of the dimension.</span></span> <span data-ttu-id="de457-105">Quand vous définissez une dimension basée sur un schéma en flocon, où les attributs de la dimension sont dérivés de plusieurs tables liées, une relation d'attribut est automatiquement définie comme suit :</span><span class="sxs-lookup"><span data-stu-id="de457-105">When you define a dimension based on a snowflake schema, which is where dimension attributes are derived from multiple related tables, an attribute relationship is automatically defined as follows:</span></span>  
  
-   <span data-ttu-id="de457-106">entre l'attribut clé et chaque attribut non-clé lié aux colonnes de la table de dimension principale ;</span><span class="sxs-lookup"><span data-stu-id="de457-106">Between the key attribute and each non-key attribute bound to columns in the main dimension table.</span></span>  
  
-   <span data-ttu-id="de457-107">entre l'attribut clé et l'attribut lié à la clé étrangère dans la table secondaire qui lie les tables de dimension sous-jacentes ;</span><span class="sxs-lookup"><span data-stu-id="de457-107">Between the key attribute and the attribute bound to the foreign key in the secondary table that links the underlying dimension tables.</span></span>  
  
-   <span data-ttu-id="de457-108">entre l'attribut lié à la clé étrangère de la table secondaire et chaque attribut non-clé lié aux colonnes de la table secondaire.</span><span class="sxs-lookup"><span data-stu-id="de457-108">Between the attribute bound to foreign key in the secondary table and each non-key attribute bound to columns from the secondary table.</span></span>  
  
 <span data-ttu-id="de457-109">Cependant, pour plusieurs raisons, vous pouvez souhaiter modifier ces relations d'attributs par défaut.</span><span class="sxs-lookup"><span data-stu-id="de457-109">However, there are a number of reasons why you might want to change these default attribute relationships.</span></span> <span data-ttu-id="de457-110">Par exemple, vous voulez définir une hiérarchie naturelle, un ordre de tri personnalisé ou une granularité de dimension basée sur un attribut non-clé.</span><span class="sxs-lookup"><span data-stu-id="de457-110">For example, you might want to define a natural hierarchy, a custom sort order, or dimension granularity based on a non-key attribute.</span></span> <span data-ttu-id="de457-111">Pour plus d’informations, consultez [référence des propriétés d’attribut de dimension](../multidimensional-models/dimension-attribute-properties-reference.md).</span><span class="sxs-lookup"><span data-stu-id="de457-111">For more information, see [Dimension Attribute Properties Reference](../multidimensional-models/dimension-attribute-properties-reference.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de457-112">Les relations d'attributs sont appelées propriétés de membre dans les expressions MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="de457-112">Attribute relationships are known in Multidimensional Expressions (MDX) as member properties.</span></span>  
  
## <a name="natural-hierarchy-relationships"></a><span data-ttu-id="de457-113">Relations de hiérarchie naturelle</span><span class="sxs-lookup"><span data-stu-id="de457-113">Natural Hierarchy Relationships</span></span>  
 <span data-ttu-id="de457-114">Une hiérarchie une hiérarchie naturelle quand chaque attribut inclus dans la hiérarchie définie par l'utilisateur possède une relation un-à-plusieurs avec l'attribut se trouvant immédiatement au-dessous de lui.</span><span class="sxs-lookup"><span data-stu-id="de457-114">A hierarchy is a natural hierarchy when each attribute included in the user-defined hierarchy has a one to many relationship with the attribute immediately below it.</span></span> <span data-ttu-id="de457-115">Imaginons par exemple une dimension Customer basée sur une table source relationnelle avec huit colonnes :</span><span class="sxs-lookup"><span data-stu-id="de457-115">For example, consider a Customer dimension based on a relational source table with eight columns:</span></span>  
  
-   <span data-ttu-id="de457-116">CustomerKey</span><span class="sxs-lookup"><span data-stu-id="de457-116">CustomerKey</span></span>  
  
-   <span data-ttu-id="de457-117">CustomerName</span><span class="sxs-lookup"><span data-stu-id="de457-117">CustomerName</span></span>  
  
-   <span data-ttu-id="de457-118">Age</span><span class="sxs-lookup"><span data-stu-id="de457-118">Age</span></span>  
  
-   <span data-ttu-id="de457-119">Sexe</span><span class="sxs-lookup"><span data-stu-id="de457-119">Gender</span></span>  
  
-   <span data-ttu-id="de457-120">E-mail</span><span class="sxs-lookup"><span data-stu-id="de457-120">Email</span></span>  
  
-   <span data-ttu-id="de457-121">City</span><span class="sxs-lookup"><span data-stu-id="de457-121">City</span></span>  
  
-   <span data-ttu-id="de457-122">Country</span><span class="sxs-lookup"><span data-stu-id="de457-122">Country</span></span>  
  
-   <span data-ttu-id="de457-123">Région</span><span class="sxs-lookup"><span data-stu-id="de457-123">Region</span></span>  
  
 <span data-ttu-id="de457-124">La dimension Analysis Services correspondante a sept attributs :</span><span class="sxs-lookup"><span data-stu-id="de457-124">The corresponding Analysis Services dimension has seven attributes:</span></span>  
  
-   <span data-ttu-id="de457-125">Customer (basée sur CustomerKey, avec CustomerName fournissant les noms des membres)</span><span class="sxs-lookup"><span data-stu-id="de457-125">Customer (based on CustomerKey, with CustomerName supplying member names)</span></span>  
  
-   <span data-ttu-id="de457-126">Age, Gender, Email, City, Region, Country</span><span class="sxs-lookup"><span data-stu-id="de457-126">Age, Gender, Email, City, Region, Country</span></span>  
  
 <span data-ttu-id="de457-127">Les relations représentant des hiérarchies naturelles sont appliquées en créant une relation d'attribut entre l'attribut d'un niveau et l'attribut du niveau qui se trouve au-dessous.</span><span class="sxs-lookup"><span data-stu-id="de457-127">Relationships representing natural hierarchies are enforced by creating an attribute relationship between the attribute for a level and the attribute for the level below it.</span></span> <span data-ttu-id="de457-128">Pour [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], ceci spécifie une relation naturelle et une agrégation potentielle.</span><span class="sxs-lookup"><span data-stu-id="de457-128">For [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], this specifies a natural relationship and potential aggregation.</span></span> <span data-ttu-id="de457-129">Dans la dimension Customer, une hiérarchie naturelle existe pour les attributs Country, Region, City et Customer.</span><span class="sxs-lookup"><span data-stu-id="de457-129">In the Customer dimension, a natural hierarchy exists for the Country, Region, City, and Customer attributes.</span></span> <span data-ttu-id="de457-130">La hiérarchie naturelle pour `{Country, Region, City, Customer}` est décrite en ajoutant les relations d'attributs suivantes :</span><span class="sxs-lookup"><span data-stu-id="de457-130">The natural hierarchy for `{Country, Region, City, Customer}` is described by adding the following attribute relationships:</span></span>  
  
-   <span data-ttu-id="de457-131">l'attribut Country en tant que relation d'attribut de l'attribut Region ;</span><span class="sxs-lookup"><span data-stu-id="de457-131">The Country attribute as an attribute relationship to the Region attribute.</span></span>  
  
-   <span data-ttu-id="de457-132">l'attribut Region en tant que relation d'attribut de l'attribut City ;</span><span class="sxs-lookup"><span data-stu-id="de457-132">The Region attribute as an attribute relationship to the City attribute.</span></span>  
  
-   <span data-ttu-id="de457-133">l'attribut City en tant que relation d'attribut de l'attribut Customer.</span><span class="sxs-lookup"><span data-stu-id="de457-133">The City attribute as an attribute relationship to the Customer attribute.</span></span>  
  
 <span data-ttu-id="de457-134">Pour parcourir les données du cube, vous pouvez également créer une hiérarchie définie par l’utilisateur qui ne représente pas une hiérarchie naturelle dans les données (appelée hiérarchie *ad hoc* ou de *création de rapports* ).</span><span class="sxs-lookup"><span data-stu-id="de457-134">For navigating data in the cube, you can also create a user-defined hierarchy that does not represent a natural hierarchy in the data (which is called an *ad hoc* or *reporting* hierarchy).</span></span> <span data-ttu-id="de457-135">Par exemple, vous pouvez créer une hiérarchie définie par l'utilisateur basée sur `{Age, Gender}`.</span><span class="sxs-lookup"><span data-stu-id="de457-135">For example, you could create a user-defined hierarchy based on `{Age, Gender}`.</span></span> <span data-ttu-id="de457-136">Les utilisateurs ne voient aucune différence quant à la façon dont les deux hiérarchies se comportent, bien que la hiérarchie naturelle bénéficie de structures d’agrégation et d’indexation, qui sont masquées par l’utilisateur, ce qui compte pour les relations naturelles dans les données sources.</span><span class="sxs-lookup"><span data-stu-id="de457-136">Users do not see any difference in how the two hierarchies behave, although the natural hierarchy benefits from aggregating and indexing structures - hidden from the user - that account for the natural relationships in the source data.</span></span>  
  
 <span data-ttu-id="de457-137">La propriété `SourceAttribute` d'un niveau détermine l'attribut utilisé pour décrire le niveau.</span><span class="sxs-lookup"><span data-stu-id="de457-137">The `SourceAttribute` property of a level determines which attribute is used to describe the level.</span></span> <span data-ttu-id="de457-138">La propriété `KeyColumns` de l'attribut spécifie la colonne de la vue de source de données qui fournit les membres.</span><span class="sxs-lookup"><span data-stu-id="de457-138">The `KeyColumns` property on the attribute specifies the column in the data source view that supplies the members.</span></span> <span data-ttu-id="de457-139">La propriété `NameColumn` de l'attribut peut spécifier une colonne de nom différente pour les membres.</span><span class="sxs-lookup"><span data-stu-id="de457-139">The `NameColumn` property on the attribute can specify a different name column for the members.</span></span>  
  
 <span data-ttu-id="de457-140">Pour définir un niveau dans une hiérarchie définie par l’utilisateur à l’aide de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , le **Concepteur de dimensions** vous permet de sélectionner un attribut de dimension, une colonne dans une table de dimension ou une colonne d’une table associée incluse dans la vue de source de données pour le cube.</span><span class="sxs-lookup"><span data-stu-id="de457-140">To define a level in a user-defined hierarchy using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], the **Dimension Designer** allows you to select a dimension attribute, a column in a dimension table, or a column from a related table included in the data source view for the cube.</span></span> <span data-ttu-id="de457-141">Pour plus d’informations sur la création de hiérarchies définies par l’utilisateur, consultez [créer des hiérarchies définies par l’utilisateur](../multidimensional-models/user-defined-hierarchies-create.md).</span><span class="sxs-lookup"><span data-stu-id="de457-141">For more information about creating user-defined hierarchies, see [Create User-Defined Hierarchies](../multidimensional-models/user-defined-hierarchies-create.md).</span></span>  
  
 <span data-ttu-id="de457-142">Dans Analysis Services, une hypothèse est généralement faite à propos du contenu des membres.</span><span class="sxs-lookup"><span data-stu-id="de457-142">In Analysis Services, an assumption is usually made about the content of members.</span></span> <span data-ttu-id="de457-143">Les membres feuilles n'ont pas de descendants et contiennent des données dérivées des sources de données sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="de457-143">Leaf members have no descendents and contain data derived from underlying data sources.</span></span> <span data-ttu-id="de457-144">Les membres non-feuilles ont des descendants et contiennent des données dérivées des agrégations effectuées sur les membres enfants.</span><span class="sxs-lookup"><span data-stu-id="de457-144">Nonleaf members have descendents and contain data derived from aggregations performed on child members.</span></span> <span data-ttu-id="de457-145">Dans les niveaux agrégés, les membres sont basés sur les agrégations des niveaux inférieurs.</span><span class="sxs-lookup"><span data-stu-id="de457-145">In aggregated levels, members are based on aggregations of subordinate levels.</span></span> <span data-ttu-id="de457-146">Par conséquent, quand la propriété `IsAggregatable` est définie à `False` sur un attribut source pour un niveau, aucun attribut pouvant faire l'objet d'une agrégation ne peut être ajouté en tant que niveau au dessus de cet attribut.</span><span class="sxs-lookup"><span data-stu-id="de457-146">Therefore, when the `IsAggregatable` property is set to `False` on a source attribute for a level, no aggregatable attributes should be added as levels above it.</span></span>  
  
## <a name="defining-an-attribute-relationship"></a><span data-ttu-id="de457-147">Définition d'une relation d'attribut</span><span class="sxs-lookup"><span data-stu-id="de457-147">Defining an Attribute Relationship</span></span>  
 <span data-ttu-id="de457-148">La principale contrainte lorsque vous créez une relation d'attribut consiste à veiller à ce que l'attribut auquel la relation d'attribut fait référence ne dispose que d'une seule valeur pour chaque membre de l'attribut auquel la relation d'attribut appartient.</span><span class="sxs-lookup"><span data-stu-id="de457-148">The main constraint when you create an attribute relationship is to make sure that the attribute referred to by the attribute relationship has no more than one value for any member in the attribute to which the attribute relationship belongs.</span></span> <span data-ttu-id="de457-149">Par exemple, si vous définissez une relation entre un attribut City (Ville) et un attribut State (État), chaque Ville ne peut être liée qu'à un seul État.</span><span class="sxs-lookup"><span data-stu-id="de457-149">For example, if you define a relationship between a City attribute and a State attribute, each city can only relate to a single state.</span></span>  
  
## <a name="attribute-relationship-queries"></a><span data-ttu-id="de457-150">Requêtes de relations d'attributs</span><span class="sxs-lookup"><span data-stu-id="de457-150">Attribute Relationship Queries</span></span>  
 <span data-ttu-id="de457-151">Vous pouvez utiliser des requêtes MDX pour extraire des données des relations d'attributs, sous forme de propriétés, avec le mot clé `PROPERTIES` de l'instruction MDX `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="de457-151">You can use MDX queries to retrieve data from attribute relationships, in the form of member properties, with the `PROPERTIES` keyword of the MDX `SELECT` statement.</span></span> <span data-ttu-id="de457-152">Pour plus d’informations sur l’utilisation de MDX pour récupérer des propriétés de membre, consultez [utilisation de propriétés de membre &#40;&#41;MDX ](../multidimensional-models/mdx/mdx-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="de457-152">For more information about how to use MDX to retrieve member properties, see [Using Member Properties &#40;MDX&#41;](../multidimensional-models/mdx/mdx-member-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de457-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="de457-153">See Also</span></span>  
 <span data-ttu-id="de457-154">[Attributs et hiérarchies d’attributs](attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="de457-154">[Attributes and Attribute Hierarchies](attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="de457-155">[Référence des propriétés d’attribut de dimension](../multidimensional-models/dimension-attribute-properties-reference.md) </span><span class="sxs-lookup"><span data-stu-id="de457-155">[Dimension Attribute Properties Reference](../multidimensional-models/dimension-attribute-properties-reference.md) </span></span>  
 <span data-ttu-id="de457-156">[Hiérarchies utilisateur](user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="de457-156">[User Hierarchies](user-hierarchies.md) </span></span>  
 [<span data-ttu-id="de457-157">Propriétés de la hiérarchie définie par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="de457-157">User Hierarchy Properties</span></span>](user-hierarchies-properties.md)  
  
  
