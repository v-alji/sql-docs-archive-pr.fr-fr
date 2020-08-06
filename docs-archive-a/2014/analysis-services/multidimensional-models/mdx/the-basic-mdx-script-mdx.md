---
title: Script MDX de base (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- default MDX scripts
- statements [MDX]
- expressions [MDX], scripts
- scripts [MDX], about scripts
ms.assetid: 83d9afda-7d34-42b5-8f28-20172a905f23
author: minewiskan
ms.author: owend
ms.openlocfilehash: de0d2fea002beda0eca480bd27140bdd202fcb83
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705579"
---
# <a name="the-basic-mdx-script-mdx"></a><span data-ttu-id="6fd2c-102">Script MDX de base (MDX)</span><span class="sxs-lookup"><span data-stu-id="6fd2c-102">The Basic MDX Script (MDX)</span></span>
  <span data-ttu-id="6fd2c-103">Un script MDX (Multidimensional Expressions) définit le processus de calcul d’un cube dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6fd2c-103">A Multidimensional Expressions (MDX) script defines the calculation process for a cube in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="6fd2c-104">Il existe deux types de scripts MDX :</span><span class="sxs-lookup"><span data-stu-id="6fd2c-104">There are two types of MDX scripts:</span></span>  
  
 <span data-ttu-id="6fd2c-105">**Script MDX par défaut**</span><span class="sxs-lookup"><span data-stu-id="6fd2c-105">**The default MDX script**</span></span>  
 <span data-ttu-id="6fd2c-106">Au moment de la création d’un cube, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] crée un script MDX par défaut pour celui-ci.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-106">At the time that you create a cube, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] creates a default MDX script for that cube.</span></span> <span data-ttu-id="6fd2c-107">Ce script définit un test de calcul pour l'intégralité du cube.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-107">This script defines a calculation pass for the whole cube.</span></span>  
  
 <span data-ttu-id="6fd2c-108">**Script MDX défini par l'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="6fd2c-108">**User-defined MDX script**</span></span>  
 <span data-ttu-id="6fd2c-109">Lorsque vous avez créé un cube, vous pouvez ajouter des scripts MDX définis par l'utilisateur qui étendent les possibilités de calcul du cube.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-109">After you have created a cube, you can add user-defined MDX scripts that extend the calculation capabilities of the cube.</span></span>  
  
## <a name="the-default-mdx-script"></a><span data-ttu-id="6fd2c-110">Script MDX par défaut</span><span class="sxs-lookup"><span data-stu-id="6fd2c-110">The Default MDX Script</span></span>  
 <span data-ttu-id="6fd2c-111">Le script MDX par défaut créé par [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] au moment de la définition d’un cube contient une instruction CALCULATE unique.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-111">The default MDX script that [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] creates when you define a cube contains a single CALCULATE statement.</span></span> <span data-ttu-id="6fd2c-112">Cette dernière se situe au début du script MDX par défaut et indique que l'intégralité du cube doit être calculée pendant le premier test de calcul.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-112">This single CALCULATE statement is at the beginning of the default MDX script, and indicates that the entire cube should be calculated during the first calculation pass.</span></span>  
  
 <span data-ttu-id="6fd2c-113">Le script MDX par défaut contient également les commandes de script qui créent des jeux nommés, des assignations et des membres calculés dans le Concepteur de cube :</span><span class="sxs-lookup"><span data-stu-id="6fd2c-113">The default MDX script also contains the script commands that create named sets, assignments, and calculated members created in Cube Designer:</span></span>  
  
-   [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="6fd2c-114">ajoute directement les commandes de script au script MDX par défaut.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-114">directly adds script commands to the default MDX script.</span></span>  
  
-   <span data-ttu-id="6fd2c-115">Pour chaque jeu nommé défini dans le cube, il existe une instruction CREATE SET correspondante dans le script MDX par défaut.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-115">For each named set in the cube, a corresponding CREATE SET statement exists in the default MDX script.</span></span>  
  
-   <span data-ttu-id="6fd2c-116">Pour chaque membre calculé défini dans le cube, il existe une instruction CREATE MEMBER correspondante dans le script MDX par défaut.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-116">For each calculated member defined in the cube, a corresponding CREATE MEMBER statement exists in the default MDX script.</span></span>  
  
 <span data-ttu-id="6fd2c-117">Vous pouvez contrôler l’ordre des commandes de script, des jeux nommés et des membres calculés dans le script MDX par défaut à l’aide de l’onglet **Calculs** du Concepteur de cube.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-117">You can control the order of script commands, named sets, and calculated members in the default MDX script by using the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="6fd2c-118">Pour plus d’informations sur la définition des calculs stockés dans le script MDX par défaut, consultez [Calculs dans les modèles multidimensionnels](../calculations-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="6fd2c-118">For more information on defining calculations stored in the default MDX script, see [Calculations in Multidimensional Models](../calculations-in-multidimensional-models.md).</span></span>  
  
 <span data-ttu-id="6fd2c-119">Si aucun script MDX n'est associé à un cube, ce dernier utilise le script MDX par défaut.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-119">If there is no MDX script associated with a cube, the cube assumes the default MDX script.</span></span> <span data-ttu-id="6fd2c-120">Un cube doit être au moins associé à un script MDX, car il se base sur celui-ci pour déterminer le comportement de calcul.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-120">A cube needs to be associated with at least one MDX script because a cube relies on the MDX script to determine calculation behavior.</span></span> <span data-ttu-id="6fd2c-121">En d'autres termes, un cube qui n'est associé à aucun script MDX ou associé à un script MDX vide ne peut pas calculer de cellules.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-121">In other words, a cube that was not associated with an MDX script or was associated with an empty MDX script could not and would not be able to calculate any cells.</span></span> <span data-ttu-id="6fd2c-122">Si vous créez des cubes par programmation, à l'aide de commandes ASSL (Analysis Services Scripting Language) ou de l'objet AMO (Analysis Management Object), il est recommandé de créer un script MDX par défaut contenant une instruction CALCULATE unique pour le cube.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-122">If you programmatically create cubes, either by using Analysis Services Scripting Language (ASSL) commands or by using Analysis Management Objects (AMO), it is recommended that you create a default MDX script containing a single CALCULATE statement for the cube.</span></span>  
  
## <a name="mdx-script-content"></a><span data-ttu-id="6fd2c-123">Contenu du script MDX</span><span class="sxs-lookup"><span data-stu-id="6fd2c-123">MDX Script Content</span></span>  
 <span data-ttu-id="6fd2c-124">Un script MDX peut contenir les instructions et expressions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6fd2c-124">An MDX script can contain the following statements and expressions:</span></span>  
  
 <span data-ttu-id="6fd2c-125">Toutes les instructions de script MDX</span><span class="sxs-lookup"><span data-stu-id="6fd2c-125">All MDX scripting statements</span></span>  
 <span data-ttu-id="6fd2c-126">Dans les scripts MDX, les instructions de script MDX contrôlent le contexte et la portée des calculs et gèrent le comportement des autres instructions dans le script MDX.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-126">In MDX scripts, MDX scripting statements control the context and scope of calculations, and manage the behavior of other statements in the MDX script.</span></span> <span data-ttu-id="6fd2c-127">Cette catégorie comprend les instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6fd2c-127">This category includes the following statements:</span></span>  
  
-   [<span data-ttu-id="6fd2c-128">DONT</span><span class="sxs-lookup"><span data-stu-id="6fd2c-128">CALCULATE</span></span>](/sql/mdx/mdx-scripting-calculate)  
  
-   [<span data-ttu-id="6fd2c-129">ANTIGEL</span><span class="sxs-lookup"><span data-stu-id="6fd2c-129">FREEZE</span></span>](/sql/mdx/mdx-scripting-freeze)  
  
-   [<span data-ttu-id="6fd2c-130">ÉTENDUE</span><span class="sxs-lookup"><span data-stu-id="6fd2c-130">SCOPE</span></span>](/sql/mdx/mdx-scripting-scope)  
  
 <span data-ttu-id="6fd2c-131">Pour plus d’informations sur les instructions de script MDX, consultez [Instructions de script MDX &#40;MDX&#41;](/sql/mdx/mdx-scripting-statements-mdx).</span><span class="sxs-lookup"><span data-stu-id="6fd2c-131">For more information on MDX scripting statements, see [MDX Scripting Statements &#40;MDX&#41;](/sql/mdx/mdx-scripting-statements-mdx).</span></span>  
  
 [<span data-ttu-id="6fd2c-132">CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="6fd2c-132">CREATE MEMBER</span></span>](/sql/mdx/mdx-data-definition-create-member)  
 <span data-ttu-id="6fd2c-133">L'instruction CREATE MEMBER crée des membres calculés.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-133">The CREATE MEMBER statement creates calculated members.</span></span> <span data-ttu-id="6fd2c-134">Pour plus d’informations sur la création de membres calculés, consultez [Création de membres calculés dans MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="6fd2c-134">For more information about how to create calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
 [<span data-ttu-id="6fd2c-135">CREATE SET</span><span class="sxs-lookup"><span data-stu-id="6fd2c-135">CREATE SET</span></span>](/sql/mdx/mdx-data-definition-create-set)  
 <span data-ttu-id="6fd2c-136">L'instruction CREATE SET crée des jeux nommés.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-136">The CREATE SET statement creates named sets.</span></span> <span data-ttu-id="6fd2c-137">Pour plus d’informations sur la création de jeux nommés, consultez [Création de jeux nommés à l’aide d’expressions MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="6fd2c-137">For more information about how to create names sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
 <span data-ttu-id="6fd2c-138">Instructions conditionnelles</span><span class="sxs-lookup"><span data-stu-id="6fd2c-138">Conditional statements</span></span>  
 <span data-ttu-id="6fd2c-139">Les instructions conditionnelles ajoutent une logique conditionnelle aux scripts MDX.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-139">Conditional statements add conditional logic to MDX scripts.</span></span> <span data-ttu-id="6fd2c-140">Cette catégorie comprend les instructions [CASE](/sql/mdx/case-statement-mdx) et [IF](/sql/mdx/mdx-scripting-if) .</span><span class="sxs-lookup"><span data-stu-id="6fd2c-140">This category includes the [CASE](/sql/mdx/case-statement-mdx) and [IF](/sql/mdx/mdx-scripting-if) statements.</span></span>  
  
 <span data-ttu-id="6fd2c-141">Expressions d'assignation</span><span class="sxs-lookup"><span data-stu-id="6fd2c-141">Assignment expressions</span></span>  
 <span data-ttu-id="6fd2c-142">Une expression d'assignation affecte une expression, telle qu'une valeur, à un sous-cube contraint.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-142">An assignment expression assigns an expression, such as a value, to a constrained subcube.</span></span> <span data-ttu-id="6fd2c-143">Une expression de sous-cube contraint est une collection d'expressions de jeux contraints qui définit les « côtés » d'un sous-cube au sein d'un script MDX.</span><span class="sxs-lookup"><span data-stu-id="6fd2c-143">A constrained subcube expression is a collection of constrained set expressions that define the "edges" of a subcube within an MDX script.</span></span> <span data-ttu-id="6fd2c-144">Les codes suivants représentent la syntaxe d'une expression de sous-cube contraint :</span><span class="sxs-lookup"><span data-stu-id="6fd2c-144">The following codes shows the syntax for a constrained subcube expression:</span></span>  
  
```  
<Constrained subcube> ::= (   
    ( <Constrained set> [<Crossjoin operator> <Constrained set>...] |  
    <ROOT function> |  
    <TREE function> |  
    LEAVES() |  
    * ) [, <Constrained subcube>...]  
<Constrained set> ::=   
    <Natural hierarchy>.MEMBERS |   
    <Natural hierarchy>.LEVEL(<numeric expression>).MEMBERS |   
    { <Natural hierarchy member> } |   
    DESCENDANTS( <Natural hierarchy member>, <Level expression>, ( SELF | AFTER | SELF_AND_AFTER ) ) |   
    DESCENDANTS( <Natural hierarchy member>, , LEAVES )  
<Natural hierarchy> ::= <Hierarchy identifier>  
<Natural hierarchy member> ::= <Natural hierarchy>.<identifier>[.<identifier>...]  
```  
  
## <a name="see-also"></a><span data-ttu-id="6fd2c-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6fd2c-145">See Also</span></span>  
 <span data-ttu-id="6fd2c-146">[Référence du langage MDX &#40;&#41;MDX](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="6fd2c-146">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="6fd2c-147">Principes de base des scripts MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6fd2c-147">MDX Scripting Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-scripting-fundamentals-analysis-services.md)  
  
  
