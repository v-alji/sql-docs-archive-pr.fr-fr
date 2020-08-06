---
title: Définir des relations d’attributs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Analysis Services], relationships
- relationships [Analysis Services], attributes
ms.assetid: 9184d344-e96d-4025-ad6f-3f75129746df
author: minewiskan
ms.author: owend
ms.openlocfilehash: a694c68a55de2533c4ce7791d3be865008b6321f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601154"
---
# <a name="define-attribute-relationships"></a><span data-ttu-id="e426c-102">Définir des relations d'attributs</span><span class="sxs-lookup"><span data-stu-id="e426c-102">Define Attribute Relationships</span></span>
  <span data-ttu-id="e426c-103">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , les attributs constituent le bloc de construction fondamental d’une dimension.</span><span class="sxs-lookup"><span data-stu-id="e426c-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], attributes are the fundamental building block of a dimension.</span></span> <span data-ttu-id="e426c-104">Une dimension contient un ensemble d'attributs organisés en fonction des relations d'attributs.</span><span class="sxs-lookup"><span data-stu-id="e426c-104">A dimension contains a set of attributes that are organized based on attribute relationships.</span></span>  
  
 <span data-ttu-id="e426c-105">Pour chaque table incluse dans une dimension, il existe une relation d'attribut qui lie l'attribut de clé de la table à d'autres attributs de cette table.</span><span class="sxs-lookup"><span data-stu-id="e426c-105">For each table included in a dimension, there is an attribute relationship that relates the table's key attribute to other attributes from that table.</span></span> <span data-ttu-id="e426c-106">Vous créez cette relation lors de la création de la dimension.</span><span class="sxs-lookup"><span data-stu-id="e426c-106">You create this relationship when you create the dimension.</span></span>  
  
 <span data-ttu-id="e426c-107">Une relation d'attribut offre les avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="e426c-107">An attribute relationship provides the following advantages:</span></span>  
  
-   <span data-ttu-id="e426c-108">Réduit la quantité de mémoire nécessaire au traitement de dimension.</span><span class="sxs-lookup"><span data-stu-id="e426c-108">Reduces the amount of memory needed for dimension processing.</span></span> <span data-ttu-id="e426c-109">Cela accélère le traitement des dimensions, des partitions et des requêtes.</span><span class="sxs-lookup"><span data-stu-id="e426c-109">This speeds up dimension, partition, and query processing.</span></span>  
  
-   <span data-ttu-id="e426c-110">Augmente les performances des requêtes car l'accès au stockage est plus rapide et les plans d'exécution sont mieux optimisés.</span><span class="sxs-lookup"><span data-stu-id="e426c-110">Increases query performance because storage access is faster and execution plans are better optimized.</span></span>  
  
-   <span data-ttu-id="e426c-111">Permet la sélection d'agrégats plus efficaces par les algorithmes de conception d'agrégation, à condition que les hiérarchies définies par l'utilisateur aient été définies avec les chemins d'accès de relation.</span><span class="sxs-lookup"><span data-stu-id="e426c-111">Results in the selection of more effective aggregates by the aggregation design algorithms, provided that user-defined hierarchies have been defined along the relationship paths.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e426c-112">Pour plus d’informations sur l’importance et les implications de la définition et de la configuration des relations d’attributs, consultez la section « amélioration des performances des requêtes » dans le [Guide des performances SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="e426c-112">For more information about the importance and implications of defining and configuring attribute relationships, see the section, "Enhancing query performance," in the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="attribute-relationship-considerations"></a><span data-ttu-id="e426c-113">Considérations sur les relations d'attributs</span><span class="sxs-lookup"><span data-stu-id="e426c-113">Attribute Relationship Considerations</span></span>  
 <span data-ttu-id="e426c-114">Lorsque les données sous-jacentes le prennent en charge, il est également conseillé de définir des relations d'attributs uniques entre les attributs.</span><span class="sxs-lookup"><span data-stu-id="e426c-114">When the underlying data supports it, you should also define unique attribute relationships between attributes.</span></span> <span data-ttu-id="e426c-115">Pour définir des relations d’attributs uniques, utilisez l’onglet **Relations d’attributs** du Concepteur de dimensions.</span><span class="sxs-lookup"><span data-stu-id="e426c-115">To define unique attribute relationships, use the **Attribute Relationships** tab of Dimension Designer.</span></span>  
  
 <span data-ttu-id="e426c-116">Tout attribut qui a une relation sortante doit avoir une clé unique relative à son attribut associé.</span><span class="sxs-lookup"><span data-stu-id="e426c-116">Any attribute that has an outgoing relationship must have a unique key relative to its related attribute.</span></span> <span data-ttu-id="e426c-117">En d'autres termes, un membre dans un attribut source ne doit identifier qu'un seul membre dans un attribut associé.</span><span class="sxs-lookup"><span data-stu-id="e426c-117">In other words, a member in a source attribute must identify one and only one member in a related attribute.</span></span> <span data-ttu-id="e426c-118">Considérons par exemple la relation Ville ->Département.</span><span class="sxs-lookup"><span data-stu-id="e426c-118">For example, consider the relationship, City -> State.</span></span> <span data-ttu-id="e426c-119">Dans cette relation, l'attribut source est Ville et l'attribut associé est Département.</span><span class="sxs-lookup"><span data-stu-id="e426c-119">In this relationship, the source attribute is City and the related attribute is State.</span></span> <span data-ttu-id="e426c-120">L’attribut source est le côté « plusieurs » et le côté associé est le côté « un » de la relation plusieurs-à-un.</span><span class="sxs-lookup"><span data-stu-id="e426c-120">The source attribute is the "many" side and the related side is the "one" side of the many-to-one relationship.</span></span> <span data-ttu-id="e426c-121">La clé pour l'attribut source serait Ville + Département.</span><span class="sxs-lookup"><span data-stu-id="e426c-121">The key for the source attribute would be City + State.</span></span> <span data-ttu-id="e426c-122">Pour plus d’informations, consultez [Créer, modifier ou supprimer une relation d’attribut](attribute-relationships-create-modify-or-delete-relationship.md).</span><span class="sxs-lookup"><span data-stu-id="e426c-122">For more information, see [Create, Modify, or Delete an Attribute Relationship](attribute-relationships-create-modify-or-delete-relationship.md).</span></span>  
  
 <span data-ttu-id="e426c-123">Pour plus d’informations sur les propriétés d’une relation d’attribut, consultez [Configurer des propriétés de relations d’attributs](attribute-relationships-configure-attribute-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e426c-123">For more information about properties of an attribute relationship, see [Configure Attribute Relationship Properties](attribute-relationships-configure-attribute-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e426c-124">La définition incorrecte de relations d'attributs peut produire des résultats de requête non valides.</span><span class="sxs-lookup"><span data-stu-id="e426c-124">Defining attribute relationships incorrectly can cause invalid query results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e426c-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e426c-125">See Also</span></span>  
 [<span data-ttu-id="e426c-126">Relations d’attributs</span><span class="sxs-lookup"><span data-stu-id="e426c-126">Attribute Relationships</span></span>](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md)  
  
  
