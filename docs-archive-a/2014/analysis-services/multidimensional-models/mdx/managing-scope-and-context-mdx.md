---
title: Gestion de la portée et du contexte (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [MDX], context
- scope [MDX]
- CALCULATE statement
- This function [MDX]
- SCOPE statement
- scripts [MDX], scope
ms.assetid: 631e7c20-8be9-4c35-8609-76516aef19d1
author: minewiskan
ms.author: owend
ms.openlocfilehash: f7cf1e6cea8df00b632e114a5a8756373738ca6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604191"
---
# <a name="managing-scope-and-context-mdx"></a><span data-ttu-id="43929-102">Gestion de la portée et du contexte (MDX)</span><span class="sxs-lookup"><span data-stu-id="43929-102">Managing Scope and Context (MDX)</span></span>
  <span data-ttu-id="43929-103">Dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , un script MDX (Multidimensional Expressions) peut s’appliquer à l’intégralité du cube ou à des portions spécifiques du cube, à des points spécifiques de l’exécution du script.</span><span class="sxs-lookup"><span data-stu-id="43929-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], a Multidimensional Expressions (MDX) script can apply to the entire cube, or to specific portions of the cube, at specific points within the execution of the script.</span></span> <span data-ttu-id="43929-104">Le script MDX peut opter pour approche par couche des calculs au sein d'un cube à l'aide de tests de calcul.</span><span class="sxs-lookup"><span data-stu-id="43929-104">The MDX script can take a layered approach to calculations within a cube through the use of calculation passes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43929-105">Pour plus d’informations sur la manière dont les tests de calcul peuvent affecter les calculs, consultez [Présentation des concepts d’ordre de passage et d’ordre de résolution &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span><span class="sxs-lookup"><span data-stu-id="43929-105">For more information on how calculation passes can affect calculations, see [Understanding Pass Order and Solve Order &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span></span>  
  
 <span data-ttu-id="43929-106">Pour contrôler le test de calcul, la portée et le contexte au sein d'un script MDX, vous devez utiliser en particulier l'instruction CACULATE, la fonction `This` et l'instruction SCOPE.</span><span class="sxs-lookup"><span data-stu-id="43929-106">To control the calculation pass, scope, and context within an MDX script, you specifically use the CACULATE statement, the `This` function, and the SCOPE statement.</span></span>  
  
## <a name="using-the-calculate-statement"></a><span data-ttu-id="43929-107">Utilisation de l'instruction CALCULATE</span><span class="sxs-lookup"><span data-stu-id="43929-107">Using the CALCULATE Statement</span></span>  
 <span data-ttu-id="43929-108">L'instruction CALCULATE remplit chaque cellule du cube avec des données agrégées.</span><span class="sxs-lookup"><span data-stu-id="43929-108">The CALCULATE statement populates each cell in the cube with aggregated data.</span></span> <span data-ttu-id="43929-109">Par exemple, une instruction CALCULATE unique se situe au début du script MDX par défaut.</span><span class="sxs-lookup"><span data-stu-id="43929-109">For example, the default MDX script has a single CALCULATE statement at the beginning of the script.</span></span>  
  
 <span data-ttu-id="43929-110">Pour plus d’informations sur la syntaxe de l’instruction CALCULATE, consultez [Instruction CALCULATE &#40;MDX&#41;](/sql/mdx/mdx-scripting-calculate).</span><span class="sxs-lookup"><span data-stu-id="43929-110">For more information on the syntax of the CALCULATE statement, see [CALCULATE Statement &#40;MDX&#41;](/sql/mdx/mdx-scripting-calculate).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43929-111">Si le script contient une instruction SCOPE comprenant une instruction CALCULATE, la syntaxe MDX évalue cette dernière au sein du contexte du sous-cube défini par l'instruction SCOPE, et non sur l'intégralité du cube.</span><span class="sxs-lookup"><span data-stu-id="43929-111">If the script contains a SCOPE statement that contains a CALCULATE statement, MDX evaluates the CALCULATE statement within the context of the subcube defined by the SCOPE statement, not against the whole cube.</span></span>  
  
## <a name="using-the-this-function"></a><span data-ttu-id="43929-112">Utilisation de la fonction This</span><span class="sxs-lookup"><span data-stu-id="43929-112">Using the This Function</span></span>  
 <span data-ttu-id="43929-113">La fonction `This` permet de récupérer le sous-cube actuel au sein d'un script MDX.</span><span class="sxs-lookup"><span data-stu-id="43929-113">The `This` function lets you retrieve the current subcube within an MDX script.</span></span> <span data-ttu-id="43929-114">Vous pouvez utiliser la fonction `This` pour affecter rapidement une expression MDX comme valeur aux cellules du sous-cube actuel.</span><span class="sxs-lookup"><span data-stu-id="43929-114">You can use the `This` function to quickly set the value of cells within the current subcube to an MDX expression.</span></span> <span data-ttu-id="43929-115">La plupart du temps, la fonction `This` est utilisée conjointement avec l'instruction SCOPE pour modifier le contenu d'un sous-cube particulier pendant un test de calcul spécifique.</span><span class="sxs-lookup"><span data-stu-id="43929-115">You often use the `This` function in conjunction with the SCOPE statement to change the contents of a specific subcube during a specific calculation pass.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43929-116">Si le script contient une instruction SCOPE comprenant une fonction `This`, la syntaxe MDX évalue la fonction `This` au sein du contexte du sous-cube défini par l'instruction SCOPE, et non sur l'intégralité du cube.</span><span class="sxs-lookup"><span data-stu-id="43929-116">If the script contains a SCOPE statement that contains a `This` function, MDX evaluates the `This` function within the context of the subcube defined by the SCOPE statement, not against the whole cube.</span></span>  
  
### <a name="this-function-example"></a><span data-ttu-id="43929-117">Exemple de fonction This</span><span class="sxs-lookup"><span data-stu-id="43929-117">This Function Example</span></span>  
 <span data-ttu-id="43929-118">L'exemple de commande de script MDX suivant utilise la fonction `This` pour augmenter de 10 % la valeur de la mesure Amount, dans le groupe de mesures Finance de l'exemple de cube [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)], pour les enfants du membre Redmond de la dimension Customer :</span><span class="sxs-lookup"><span data-stu-id="43929-118">The following MDX script command example uses the `This` function to increase the value of the Amount measure, in the Finance measure group of the [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] sample cube, to 10% higher for the children of the Redmond member in the Customer dimension:</span></span>  
  
```  
/* This SCOPE statement defines the current subcube */  
SCOPE([Customer].&[Redmond].MEMBERS,   
    [Measures].[Amount], *);  
        /* This expression sets the value of the Amount measure */  
        THIS = [Measures].[Amount] * 1.1;  
END SCOPE;  
```  
  
 <span data-ttu-id="43929-119">Pour plus d’informations sur la syntaxe de la `This` fonction, consultez [cet &#40;&#41;MDX ](/sql/mdx/this-mdx).</span><span class="sxs-lookup"><span data-stu-id="43929-119">For more information on the syntax of the `This` function, see [This &#40;MDX&#41;](/sql/mdx/this-mdx).</span></span>  
  
## <a name="using-the-scope-statement"></a><span data-ttu-id="43929-120">Utilisation de l'instruction SCOPE</span><span class="sxs-lookup"><span data-stu-id="43929-120">Using the SCOPE Statement</span></span>  
 <span data-ttu-id="43929-121">L'instruction SCOPE définit le sous-cube actuel qui contient (et spécifie la portée) d'autres expressions et instructions MDX au sein d'un script MDX.</span><span class="sxs-lookup"><span data-stu-id="43929-121">The SCOPE statement defines the current subcube that contains, and specifies the scope of, other MDX expressions and statements within an MDX script.</span></span> <span data-ttu-id="43929-122">MDX évalue ces autres expressions et instructions MDX, notamment la fonction `This` et l'instruction CALCULATE, dans le contexte du sous-cube.</span><span class="sxs-lookup"><span data-stu-id="43929-122">MDX evaluates this other MDX expressions and statements, including the `This` function and the CALCULATE statement, within the context of the subcube.</span></span>  
  
 <span data-ttu-id="43929-123">Une instruction SCOPE est dynamique, mais pas itérative de nature.</span><span class="sxs-lookup"><span data-stu-id="43929-123">A SCOPE statement is dynamic, but not iterative in nature.</span></span> <span data-ttu-id="43929-124">Les instructions contenues dans une instruction SCOPE s'exécutent à une seule reprise, mais le sous-cube proprement dit peut être déterminé de manière dynamique.</span><span class="sxs-lookup"><span data-stu-id="43929-124">The statements contained within a SCOPE statement run once, but the subcube itself can be dynamically determined.</span></span> <span data-ttu-id="43929-125">Vous pouvez, par exemple, posséder un cube appelé SampleCube</span><span class="sxs-lookup"><span data-stu-id="43929-125">For example, you have a cube named SampleCube.</span></span> <span data-ttu-id="43929-126">et appliquer à ce dernier l'instruction SCOPE suivante pour définir un sous-cube définissant le contexte en tant que ALLMEMBERS dans la dimension Measures :</span><span class="sxs-lookup"><span data-stu-id="43929-126">Against the SampleCube cube, you apply the following SCOPE statement to define a subcube the defines the context as the ALLMEMBERS within the Measures dimension:</span></span>  
  
 `SCOPE([Measures].ALLMEMBERS);`  
  
 `THIS = [Measures].ALLMEMBERS.COUNT;`  
  
 `END SCOPE;`  
  
 <span data-ttu-id="43929-127">Les instructions et expressions contenues dans cette instruction SCOPE s'exécutent à une seule reprise.</span><span class="sxs-lookup"><span data-stu-id="43929-127">The statements and expressions within this SCOPE statement run once.</span></span>  
  
 <span data-ttu-id="43929-128">À présent, un utilisateur de l'entreprise exécute la requête suivante contenant une mesure, appelée ExistingMeasure, sur le cube SampleCube :</span><span class="sxs-lookup"><span data-stu-id="43929-128">Now, a business user runs the following MDX query that contains one measure, named ExistingMeasure, against the SampleCube cube:</span></span>  
  
 `WITH MEMBER [Measures].[NewMeasure] AS '1'`  
  
 `SELECT`  
  
 `[Measures].ALLMEMBERS ON COLUMNS,`  
  
 `[Customer].DEFAULTMEMBER ON ROWS`  
  
 `FROM`  
  
 `[SampleCube]`  
  
 <span data-ttu-id="43929-129">Le jeu de cellules retourné par la requête ressemble au résultat affiché dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="43929-129">The cellset returned from the query resembles the output shown in the following table.</span></span>  
  
||<span data-ttu-id="43929-130">[ExistingMeasure]</span><span class="sxs-lookup"><span data-stu-id="43929-130">[ExistingMeasure]</span></span>|<span data-ttu-id="43929-131">[NewMeasure]</span><span class="sxs-lookup"><span data-stu-id="43929-131">[NewMeasure]</span></span>|  
|-|-------------------------|--------------------|  
|<span data-ttu-id="43929-132">[Customer].[All]</span><span class="sxs-lookup"><span data-stu-id="43929-132">[Customer].[All]</span></span>|<span data-ttu-id="43929-133">2</span><span class="sxs-lookup"><span data-stu-id="43929-133">2</span></span>|<span data-ttu-id="43929-134">2</span><span class="sxs-lookup"><span data-stu-id="43929-134">2</span></span>|  
  
 <span data-ttu-id="43929-135">Si vous observez le jeu de cellules retourné, vous pouvez constater que la valeur ExistingMeasure, comprise dans l'instruction SCOPE du script MDX, est mise à jour dynamiquement après la définition de la mesure NewMeasure.</span><span class="sxs-lookup"><span data-stu-id="43929-135">Looking at the returned cellset, notice how the ExistingMeasure value, included in the SCOPE statement within the MDX script, is dynamically updated after the measure NewMeasure was defined.</span></span>  
  
 <span data-ttu-id="43929-136">Une instruction SCOPE peut être imbriquée dans une autre instruction SCOPE.</span><span class="sxs-lookup"><span data-stu-id="43929-136">A SCOPE statement can be nested within another SCOPE statement.</span></span> <span data-ttu-id="43929-137">Cependant, comme l'instruction SCOPE n'est pas itérative, l'objectif principal de l'imbrication d'instructions SCOPE consiste à sous-diviser davantage un sous-cube en vue d'un traitement spécial.</span><span class="sxs-lookup"><span data-stu-id="43929-137">However, as the SCOPE statement is not iterative, the primary purpose for nesting SCOPE statements is to further subdivide a subcube for special treatment.</span></span>  
  
### <a name="scope-statement-example"></a><span data-ttu-id="43929-138">Exemple d'instruction SCOPE</span><span class="sxs-lookup"><span data-stu-id="43929-138">SCOPE Statement Example</span></span>  
 <span data-ttu-id="43929-139">L'exemple de script MDX suivant utilise l'instruction SCOPE pour augmenter de 10 % la valeur de la mesure Amount, dans le groupe de mesures Finance de l'exemple de cube [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] , pour les enfants du membre Redmond de la dimension Customer.</span><span class="sxs-lookup"><span data-stu-id="43929-139">The following MDX script example uses a SCOPE statement to sets the value of the Amount measure, in the Finance measure group of the [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] sample cube, to 10% higher for the children of the Redmond member in the Customer dimension.</span></span> <span data-ttu-id="43929-140">Cependant, une autre instruction SCOPE modifie le sous-cube pour inclure la mesure Amount des enfants de l'année civile 2002.</span><span class="sxs-lookup"><span data-stu-id="43929-140">However, another SCOPE statement changes the subcube to include the Amount measure for the children of the 2002 calendar year.</span></span> <span data-ttu-id="43929-141">Pour terminer, la mesure Amount n'est agrégée que pour ce sous-cube, en laissant inchangées les valeurs agrégées de la mesure Amount pour les autres années civiles.</span><span class="sxs-lookup"><span data-stu-id="43929-141">Finally, the Amount measure is then aggregated only for that subcube, leaving the aggregated values for the Amount measure in other calendar years unchanged.</span></span>  
  
```  
/* Calculate the entire cube first. */  
CALCULATE;  
/* This SCOPE statement defines the current subcube */  
SCOPE([Customer].&[Redmond].MEMBERS,   
    [Measures].[Amount], *);  
        /* This expression sets the value of the Amount measure */  
        THIS = [Measures].[Amount] * 1.1;  
END SCOPE;  
```  
  
 <span data-ttu-id="43929-142">Pour plus d’informations sur la syntaxe de l’instruction SCOPE, consultez [Instruction SCOPE &#40;MDX&#41;](/sql/mdx/mdx-scripting-scope).</span><span class="sxs-lookup"><span data-stu-id="43929-142">For more information on the syntax of the SCOPE statement, see [SCOPE Statement &#40;MDX&#41;](/sql/mdx/mdx-scripting-scope).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43929-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43929-143">See Also</span></span>  
 <span data-ttu-id="43929-144">[Référence du langage MDX &#40;&#41;MDX](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="43929-144">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 <span data-ttu-id="43929-145">[Script MDX de base &#40;&#41;MDX](the-basic-mdx-script-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="43929-145">[The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md) </span></span>  
 [<span data-ttu-id="43929-146">Principes de base des requêtes MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="43929-146">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
