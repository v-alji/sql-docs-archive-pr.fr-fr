---
title: Création de jeux nommés dans l’étendue de session (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- CREATE SET statement
- session-scoped named sets [MDX]
ms.assetid: b751e1e4-6d4c-4d36-a28d-ffdaaee0f1c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: d35bd61dcc59eca8bcb920ed99f2e791631047c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703332"
---
# <a name="creating-session-scoped-named-sets-mdx"></a><span data-ttu-id="cbf84-102">Création de jeux nommés dans l'étendue de session (MDX)</span><span class="sxs-lookup"><span data-stu-id="cbf84-102">Creating Session-Scoped Named Sets (MDX)</span></span>
  <span data-ttu-id="cbf84-103">Pour créer un jeu nommé disponible dans l’ensemble d’une session MDX (Multidimensional Expressions), utilisez l’instruction [CREATE SET](/sql/mdx/mdx-data-definition-create-set) .</span><span class="sxs-lookup"><span data-stu-id="cbf84-103">To create a named set that is available throughout a Multidimensional Expressions (MDX) session, you use the [CREATE SET](/sql/mdx/mdx-data-definition-create-set) statement.</span></span> <span data-ttu-id="cbf84-104">Un jeu nommé créé à l'aide de l'instruction CREATE SET n'est supprimé qu'après la fermeture de la session MDX.</span><span class="sxs-lookup"><span data-stu-id="cbf84-104">A named set that is created by using the CREATE SET statement will not be removed until after the MDX session closes.</span></span>  
  
 <span data-ttu-id="cbf84-105">Comme décrit dans cette rubrique, la syntaxe du mot clé WITH est explicite et simple d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="cbf84-105">As discussed in this topic, the syntax of the WITH keyword is straightforward and easy to use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cbf84-106">Pour plus d’informations sur les jeux nommés, consultez [Création de jeux nommés à l’aide d’expressions MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="cbf84-106">For more information about named sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
## <a name="create-set-syntax"></a><span data-ttu-id="cbf84-107">Syntaxe de CREATE SET</span><span class="sxs-lookup"><span data-stu-id="cbf84-107">CREATE SET Syntax</span></span>  
 <span data-ttu-id="cbf84-108">Utilisez la syntaxe suivante pour l'instruction CREATE SET :</span><span class="sxs-lookup"><span data-stu-id="cbf84-108">Use the following syntax for the CREATE SET statement:</span></span>  
  
```  
CREATE SESSION SET [CURRENTCUBE. | <cube name>.]<Set Identifier> AS <Set Expression>  
```  
  
 <span data-ttu-id="cbf84-109">Dans la syntaxe de l'instruction CREATE SET, le paramètre `cube name` contient le nom du cube qui comprend les membres du jeu nommé.</span><span class="sxs-lookup"><span data-stu-id="cbf84-109">In the CREATE SET syntax, the `cube name` parameter contains the name of the cube that contains the members for the named set.</span></span> <span data-ttu-id="cbf84-110">Si le paramètre `cube name` n'est pas spécifié, le cube actuel est utilisé comme cube contenant le membre du jeu nommé.</span><span class="sxs-lookup"><span data-stu-id="cbf84-110">If the `cube name` parameter is not specified, the current cube will be used as the cube that contains the member for the named set.</span></span> <span data-ttu-id="cbf84-111">En outre, le paramètre `Set_Identifier` contient l'alias du jeu nommé et le paramètre `Set_Expression` contient l'expression d'ensemble à laquelle l'alias du jeu nommé fait référence.</span><span class="sxs-lookup"><span data-stu-id="cbf84-111">Also, the `Set_Identifier` parameter contains the alias for the named set, and the `Set_Expression` parameter contains the set expression to which the named set alias will refer.</span></span>  
  
## <a name="create-set-example"></a><span data-ttu-id="cbf84-112">Exemple avec CREATE SET</span><span class="sxs-lookup"><span data-stu-id="cbf84-112">CREATE SET Example</span></span>  
 <span data-ttu-id="cbf84-113">L'exemple suivant utilise l'instruction CREATE SET pour créer le jeu nommé `SetCities_2_3` en se basant sur le cube Store.</span><span class="sxs-lookup"><span data-stu-id="cbf84-113">The following example uses the CREATE SET statement to create the `SetCities_2_3` named set based on the Store cube.</span></span> <span data-ttu-id="cbf84-114">Les membres du jeu nommé `SetCities_2_3` sont les magasins situés dans City 2 et City 3.</span><span class="sxs-lookup"><span data-stu-id="cbf84-114">The members of the `SetCities_2_3` named set are the stores within City 2 and City 3.</span></span>  
  
```  
create Session set [Store].[SetCities_2_3] as  
{[Data Stores].[ByLocation].[State].&[CA].&[City 02],  
[Data Stores].[ByLocation].[State].&[NH].&[City 03]}  
```  
  
 <span data-ttu-id="cbf84-115">Si vous utilisez l'instruction CREATE SET pour définir le jeu nommé `SetCities_2_3` , ce dernier reste disponible pendant toute la durée de la session MDX active.</span><span class="sxs-lookup"><span data-stu-id="cbf84-115">By using the CREATE SET statement to define the `SetCities_2_3` named set, this named set remains available for the length of the current MDX session.</span></span> <span data-ttu-id="cbf84-116">L'exemple suivant est celui d'une requête valide qui retourne les membres City 2 et City 3 ; par ailleurs, celle-ci peut être exécutée à tout moment après la création du jeu nommé `SetCities_2_3` et avant la fermeture de la session.</span><span class="sxs-lookup"><span data-stu-id="cbf84-116">The following example is a valid query that would return City 2 and City 3 members, and that could be run anytime after you create the `SetCities_2_3` named set and before the session closes.</span></span>  
  
```  
select SetCities_2_3 on 0 from [Store]  
```  
  
## <a name="see-also"></a><span data-ttu-id="cbf84-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cbf84-117">See Also</span></span>  
 [<span data-ttu-id="cbf84-118">Création de jeux nommés d’étendue de requête &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="cbf84-118">Creating Query-Scoped Named Sets &#40;MDX&#41;</span></span>](mdx-named-sets-creating-query-scoped-named-sets.md)  
  
  
