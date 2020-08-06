---
title: Créer des hiérarchies définies par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- user-defined hierarchies [Analysis Services]
ms.assetid: 16715b85-0630-4a8e-99b0-c0d213cade26
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17e870a2b20125132342db1845689b7c2481d623
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700325"
---
# <a name="create-user-defined-hierarchies"></a><span data-ttu-id="2bc60-102">Créer des hiérarchies définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="2bc60-102">Create User-Defined Hierarchies</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="2bc60-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]vous permet de créer des hiérarchies définies par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2bc60-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] lets you create user-defined hierarchies.</span></span> <span data-ttu-id="2bc60-104">Une hiérarchie est une collection de niveaux basés sur des attributs.</span><span class="sxs-lookup"><span data-stu-id="2bc60-104">A hierarchy is a collection of levels based on attributes.</span></span> <span data-ttu-id="2bc60-105">Par exemple, une hiérarchie de temps peut contenir les niveaux Année, Trimestre, Mois, Semaine et Jour.</span><span class="sxs-lookup"><span data-stu-id="2bc60-105">For example, a time hierarchy might contain the Year, Quarter, Month, Week, and Day levels.</span></span> <span data-ttu-id="2bc60-106">Dans certaines hiérarchies, chaque attribut de membre est lié de manière unique à l'attribut de membre du niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="2bc60-106">In some hierarchies, each member attribute uniquely implies the member attribute above it.</span></span> <span data-ttu-id="2bc60-107">Ce type de hiérarchie est parfois appelé hiérarchie naturelle.</span><span class="sxs-lookup"><span data-stu-id="2bc60-107">This is sometimes referred to as a natural hierarchy.</span></span> <span data-ttu-id="2bc60-108">Les utilisateurs finaux peuvent utiliser une hiérarchie pour explorer les données d'un cube.</span><span class="sxs-lookup"><span data-stu-id="2bc60-108">A hierarchy can be used by end users to browse cube data.</span></span> <span data-ttu-id="2bc60-109">Définissez des hiérarchies à l'aide du volet Hiérarchies du Concepteur de dimensions dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bc60-109">Define hierarchies by using the Hierarchies pane of Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="2bc60-110">Lors de la création d’une hiérarchie définie par l’utilisateur, la hiérarchie peut devenir *déséquilibrée*.</span><span class="sxs-lookup"><span data-stu-id="2bc60-110">When you create a user-defined hierarchy, the hierarchy might become *ragged*.</span></span> <span data-ttu-id="2bc60-111">Une hiérarchie déséquilibrée est une hiérarchie dans laquelle le membre parent logique d’au moins un membre ne figure pas dans le niveau immédiatement supérieur à ce membre.</span><span class="sxs-lookup"><span data-stu-id="2bc60-111">A ragged hierarchy is where the logical parent member of at least one member is not in the level immediately above the member.</span></span> <span data-ttu-id="2bc60-112">Si une hiérarchie est déséquilibrée, il existe des paramètres permettant de contrôler si les membres manquants sont visibles et de les afficher.</span><span class="sxs-lookup"><span data-stu-id="2bc60-112">If you have a ragged hierarchy, there are settings that control whether the missing members are visible and how to display the missing members.</span></span> <span data-ttu-id="2bc60-113">Pour plus d’informations sur les hiérarchies, consultez [Hiérarchies déséquilibrées](user-defined-hierarchies-ragged-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="2bc60-113">For more information, see [Ragged Hierarchies](user-defined-hierarchies-ragged-hierarchies.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bc60-114">Pour plus d’informations sur les problèmes de performances liés à la conception et à la configuration des hiérarchies définies par l’utilisateur, consultez le [Guide des performances SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="2bc60-114">For more information about performance issues related to the design and configuration of user-defined hierarchies, see the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc60-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2bc60-115">See Also</span></span>  
 <span data-ttu-id="2bc60-116">[Propriétés de la hiérarchie utilisateur](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md) </span><span class="sxs-lookup"><span data-stu-id="2bc60-116">[User Hierarchy Properties](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md) </span></span>  
 <span data-ttu-id="2bc60-117">[Propriétés de niveau &#91;ées sur&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md) </span><span class="sxs-lookup"><span data-stu-id="2bc60-117">[Level Properties &#91;Paved Over&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md) </span></span>  
 [<span data-ttu-id="2bc60-118">Hiérarchie parent-enfant</span><span class="sxs-lookup"><span data-stu-id="2bc60-118">Parent-Child Hierarchy</span></span>](parent-child-dimension.md)  
  
  
