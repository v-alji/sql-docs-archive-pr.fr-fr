---
title: Configurer le niveau (tous) pour les hiérarchies d’attribut | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- All members
- IsAggregatable property
- topmost levels [Analysis Services]
- (All) levels
- AttributeAllMemberName property
- levels [Analysis Services]
- members [Analysis Services], All
- AllMemberName property
ms.assetid: 0cb35e6f-b10f-483d-b893-78f6ca3979fd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9874a8c8a6861bc7d9e44271b089e8af3a4c0ae2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698694"
---
# <a name="configure-the-all-level-for-attribute-hierarchies"></a><span data-ttu-id="42a1f-102">Configurer le niveau (Tous) des hiérarchies d'attributs</span><span class="sxs-lookup"><span data-stu-id="42a1f-102">Configure the (All) Level for Attribute Hierarchies</span></span>
  <span data-ttu-id="42a1f-103">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , le niveau (tous) est un niveau facultatif, généré par le système.</span><span class="sxs-lookup"><span data-stu-id="42a1f-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the (All) level is an optional, system-generated level.</span></span> <span data-ttu-id="42a1f-104">Il contient un seul membre dont la valeur est l'agrégation des valeurs de tous les membres du niveau situé juste en dessous.</span><span class="sxs-lookup"><span data-stu-id="42a1f-104">It contains only one member whose value is the aggregation of the values of all members in the immediately subordinate level.</span></span> <span data-ttu-id="42a1f-105">Ce membre est appelé membre Tous.</span><span class="sxs-lookup"><span data-stu-id="42a1f-105">This member is called the All member.</span></span> <span data-ttu-id="42a1f-106">Ce membre est créé par le système et il ne figure pas dans la table de dimension.</span><span class="sxs-lookup"><span data-stu-id="42a1f-106">It is a system-generated member that is not contained in the dimension table.</span></span> <span data-ttu-id="42a1f-107">Étant donné que le membre du niveau (Tous) se trouve au sommet d'une hiérarchie, sa valeur est l'agrégation consolidée des valeurs de tous les membres de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="42a1f-107">Because the member in the (All) level is at the top of the hierarchy, the member's value is the consolidated aggregation of the values of all members in the hierarchy.</span></span> <span data-ttu-id="42a1f-108">Le membre Tous sert souvent de membre par défaut d'une hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="42a1f-108">The All member often serves as the default member of a hierarchy.</span></span>  
  
 <span data-ttu-id="42a1f-109">La présence d'un niveau (Tous) dans une hiérarchie d'attributs dépend de la valeur de la propriété `IsAggregatable` de l'attribut, et la présence d'un niveau (Tous) dans une hiérarchie définie par l'utilisateur dépend de la propriété `IsAggregatable` de l'attribut au niveau le plus élevé de la hiérarchie définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="42a1f-109">The presence of an (All) level in an attribute hierarchy depends on the `IsAggregatable` property setting for the attribute and the presence of an (All) level in a user-defined hierarchy depends on the `IsAggregatable` property of the attribute at the top-most level of user-defined hierarchy.</span></span> <span data-ttu-id="42a1f-110">Si la propriété `IsAggregatable` a la valeur `True`, il existera un niveau (Tous).</span><span class="sxs-lookup"><span data-stu-id="42a1f-110">If the `IsAggregatable` property is set to `True`, an (All) level will exist.</span></span> <span data-ttu-id="42a1f-111">Au contraire, une hiérarchie n'a pas de niveau (Tous) si sa propriété `IsAggregatable` a la valeur `False`.</span><span class="sxs-lookup"><span data-stu-id="42a1f-111">A hierarchy has no (All) level if the `IsAggregatable` property is set to `False`.</span></span>  
  
## <a name="establishing-the-topmost-level"></a><span data-ttu-id="42a1f-112">Établissement du niveau le plus élevé</span><span class="sxs-lookup"><span data-stu-id="42a1f-112">Establishing the Topmost Level</span></span>  
 <span data-ttu-id="42a1f-113">Si la propriété `IsAggregatable` de l'attribut source d'un niveau d'une hiérarchie a la valeur `False`, aucun niveau agrégeable ne peut apparaître dans la hiérarchie au-dessus de ce niveau.</span><span class="sxs-lookup"><span data-stu-id="42a1f-113">If the `IsAggregatable` property is set to `False` on the source attribute of a level in a hierarchy, then no aggregatable level can appear in the hierarchy above that level.</span></span> <span data-ttu-id="42a1f-114">Un niveau non agrégeable doit être le niveau le plus élevé d'une hiérarchie, ou la propriété `IsAggregatable` des attributs sources des niveaux qui sont au-dessus de lui doit aussi avoir la valeur `False`.</span><span class="sxs-lookup"><span data-stu-id="42a1f-114">A non-aggregatable level must be the topmost level of any hierarchy or the `IsAggregatable` property of the source attributes for any levels above it must also be set to `False`.</span></span>  
  
## <a name="all-member-and-all-level"></a><span data-ttu-id="42a1f-115">Membre Tous et niveau (Tous)</span><span class="sxs-lookup"><span data-stu-id="42a1f-115">All Member and (All) Level</span></span>  
 <span data-ttu-id="42a1f-116">Le membre unique du niveau (Tous) est appelé membre Tous.</span><span class="sxs-lookup"><span data-stu-id="42a1f-116">The single member of the (All) level is called the All member.</span></span> <span data-ttu-id="42a1f-117">La `AttributeAllMemberName` propriété d’une dimension spécifie le nom du membre tous pour les attributs d’une dimension.</span><span class="sxs-lookup"><span data-stu-id="42a1f-117">The `AttributeAllMemberName`property on a dimension specifies the name of the All member for attributes in a dimension.</span></span> <span data-ttu-id="42a1f-118">La propriété `AllMemberName` d'une hiérarchie spécifie le nom du membre Tous de cette hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="42a1f-118">The `AllMemberName` property on a hierarchy specifies the name of the All member for the hierarchy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a1f-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="42a1f-119">See Also</span></span>  
 [<span data-ttu-id="42a1f-120">Définir un membre par défaut</span><span class="sxs-lookup"><span data-stu-id="42a1f-120">Define a Default Member</span></span>](attribute-properties-define-a-default-member.md)  
  
  
