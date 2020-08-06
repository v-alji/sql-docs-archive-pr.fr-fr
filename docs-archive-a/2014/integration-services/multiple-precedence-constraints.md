---
title: Contraintes de précédence multiples | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- multiple precedence constraints
- precedence executables [Integration Services]
- precedence constraints [Integration Services], multiple
- constrained executables [Integration Services]
ms.assetid: 71c53ead-3d19-4bc1-aafd-e5b32595b420
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16fefbbf886818989131710876564fc9e147a56a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605546"
---
# <a name="multiple-precedence-constraints"></a><span data-ttu-id="ddc3b-102">Contraintes de précédence multiples</span><span class="sxs-lookup"><span data-stu-id="ddc3b-102">Multiple Precedence Constraints</span></span>
  <span data-ttu-id="ddc3b-103">Une contrainte de précédence connecte deux exécutables : deux tâches, deux conteneurs, ou un de chaque.</span><span class="sxs-lookup"><span data-stu-id="ddc3b-103">A precedence constraint connects two executables: two tasks, two containers, or one of each.</span></span> <span data-ttu-id="ddc3b-104">Ils sont connus sous le nom d'exécutable de précédence et d'exécutable contraint.</span><span class="sxs-lookup"><span data-stu-id="ddc3b-104">They are known as the precedence executable and the constrained executable.</span></span> <span data-ttu-id="ddc3b-105">Un exécutable contraint peut comprendre plusieurs contraintes de précédence.</span><span class="sxs-lookup"><span data-stu-id="ddc3b-105">A constrained executable can have multiple precedence constraints.</span></span> <span data-ttu-id="ddc3b-106">Pour plus d’informations, consultez [Contraintes de précédence](control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="ddc3b-106">For more information, see [Precedence Constraints](control-flow/precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="ddc3b-107">Assembler des scénarios de contraintes complexes par regroupement de contraintes permet d'implémenter un flux de contrôle complexe dans les packages.</span><span class="sxs-lookup"><span data-stu-id="ddc3b-107">Assembling complex constraint scenarios by grouping constraints enables you to implement complex control flow in packages.</span></span> <span data-ttu-id="ddc3b-108">Par exemple, dans l'illustration qui suit, la tâche D est liée à la tâche A par une contrainte `Success`, la tâche D est liée à la tâche B par une contrainte `Failure` et la tâche D est liée à la tâche C par une contrainte `Success`.</span><span class="sxs-lookup"><span data-stu-id="ddc3b-108">For example, in the following illustration, Task D is linked to Task A by a `Success` constraint, Task D is linked to Task B by a `Failure` constraint, and Task D is linked to Task C by a `Success` constraint.</span></span> <span data-ttu-id="ddc3b-109">Les contraintes de précédence entre la tâche D et la tâche A, entre la tâche D et la tâche B, et entre la tâche D et la tâche C participent à une relation *et* logique.</span><span class="sxs-lookup"><span data-stu-id="ddc3b-109">The precedence constraints between Task D and Task A, between Task D and Task B, and between Task D and Task C participate in a logical *and* relationship.</span></span> <span data-ttu-id="ddc3b-110">Par conséquent, pour que la tâche D s'exécute, la tâche A doit s'exécuter avec succès, la tâche B doit échouer et la tâche C doit s'exécuter avec succès.</span><span class="sxs-lookup"><span data-stu-id="ddc3b-110">Therefore, for Task D to run, Task A must run successfully, Task B must fail, and Task C must run successfully.</span></span>  
  
 <span data-ttu-id="ddc3b-111">![Tâches liées par des contraintes de précédence](media/precedenceconstraints.gif "Tâches liées par des contraintes de précédence")</span><span class="sxs-lookup"><span data-stu-id="ddc3b-111">![Tasks linked by precedence constraints](media/precedenceconstraints.gif "Tasks linked by precedence constraints")</span></span>  
  
## <a name="logicaland-property"></a><span data-ttu-id="ddc3b-112">Propriété LogicalAnd</span><span class="sxs-lookup"><span data-stu-id="ddc3b-112">LogicalAnd Property</span></span>  
 <span data-ttu-id="ddc3b-113">Si une tâche ou un conteneur comporte plusieurs contraintes, la propriété `LogicalAnd` indique si une contrainte de précédence est évaluée seule ou de concert avec les autres contraintes.</span><span class="sxs-lookup"><span data-stu-id="ddc3b-113">If a task or a container has multiple constraints, the `LogicalAnd` property specifies whether a precedence constraint is evaluated singly or in concert with other constraints.</span></span>  
  
 <span data-ttu-id="ddc3b-114">Vous pouvez définir la `LogicalAnd` propriété à l’aide de l **'éditeur de contrainte de précédence** dans le [!INCLUDE[ssIS](../includes/ssis-md.md)] concepteur ou dans le fenêtre Propriétés qui [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] fournit.</span><span class="sxs-lookup"><span data-stu-id="ddc3b-114">You can set the `LogicalAnd` property using the **Precedence Constraint Editor** in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, or in the Properties window that [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] provides.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ddc3b-115">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ddc3b-115">Related Tasks</span></span>  
 [<span data-ttu-id="ddc3b-116">Définir les propriétés d'une contrainte de précédence</span><span class="sxs-lookup"><span data-stu-id="ddc3b-116">Set the Properties of a Precedence Constraint</span></span>](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md)  
  
  
