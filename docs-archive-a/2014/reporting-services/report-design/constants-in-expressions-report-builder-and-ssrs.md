---
title: Constantes dans les expressions (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b8ae650b-0f46-4848-b62b-15f8a40751b8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d95005a04482cb03d3bb3860aea695c7e7969255
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603895"
---
# <a name="constants-in-expressions-report-builder-and-ssrs"></a><span data-ttu-id="5da20-102">Constantes dans les expressions (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="5da20-102">Constants in Expressions (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5da20-103">Une constante se compose de texte littéral ou de texte prédéfini.</span><span class="sxs-lookup"><span data-stu-id="5da20-103">A constant consists of literal text or predefined text.</span></span> <span data-ttu-id="5da20-104">Le processeur de rapports a accès aux constantes prédéfinies afin que, lorsque vous les incluez dans une expression, les valeurs qu'elles représentent soient substituées dans l'expression avant son évaluation.</span><span class="sxs-lookup"><span data-stu-id="5da20-104">The report processor has access to predefined constants so that when you include them in an expression, the values they represent are substituted in the expression before it is evaluated.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="literal-text"></a><span data-ttu-id="5da20-105">Texte littéral</span><span class="sxs-lookup"><span data-stu-id="5da20-105">Literal Text</span></span>  
 <span data-ttu-id="5da20-106">Dans une expression, le texte littéral est le texte qui figure entre guillemets doubles.</span><span class="sxs-lookup"><span data-stu-id="5da20-106">In an expression, literal text is text that is in double quotation marks.</span></span> <span data-ttu-id="5da20-107">Vous pouvez également taper le texte directement dans une zone de texte sans guillemets doubles s'il ne fait pas partie d'une expression.</span><span class="sxs-lookup"><span data-stu-id="5da20-107">You can also type text directly into a text box without double quotation marks if it is not part of an expression.</span></span> <span data-ttu-id="5da20-108">Si la valeur de la zone de texte ne commence pas par un signe égal (=), le texte est traité comme texte littéral.</span><span class="sxs-lookup"><span data-stu-id="5da20-108">If the text box value does not begin with an equal sign (=), the text is treated as literal text.</span></span> <span data-ttu-id="5da20-109">Le tableau suivant répertorie plusieurs exemples de texte littéral dans une expression.</span><span class="sxs-lookup"><span data-stu-id="5da20-109">The following table shows several examples of literal text in an expression.</span></span>  
  
|<span data-ttu-id="5da20-110">Constant</span><span class="sxs-lookup"><span data-stu-id="5da20-110">Constant</span></span>|<span data-ttu-id="5da20-111">Texte affiché</span><span class="sxs-lookup"><span data-stu-id="5da20-111">Display text</span></span>|<span data-ttu-id="5da20-112">Texte de l'expression</span><span class="sxs-lookup"><span data-stu-id="5da20-112">Expression text</span></span>|  
|--------------|------------------|---------------------|  
|<span data-ttu-id="5da20-113">Report run at:</span><span class="sxs-lookup"><span data-stu-id="5da20-113">Report run at:</span></span>|<\<Expr>>|`="Report run at: " & Globals!ExecutionTime`|  
|<span data-ttu-id="5da20-114">Adventure Works Cycles</span><span class="sxs-lookup"><span data-stu-id="5da20-114">Adventure Works Cycles</span></span>|<span data-ttu-id="5da20-115">Adventure Works Cycles</span><span class="sxs-lookup"><span data-stu-id="5da20-115">Adventure Works Cycles</span></span>|<span data-ttu-id="5da20-116">Adventure Works Cycles</span><span class="sxs-lookup"><span data-stu-id="5da20-116">Adventure Works Cycles</span></span>|  
|<span data-ttu-id="5da20-117">[Texte affiché entre crochets]</span><span class="sxs-lookup"><span data-stu-id="5da20-117">[Bracketed display text]</span></span>|<span data-ttu-id="5da20-118">\\[Texte affiché entre crochets\\]</span><span class="sxs-lookup"><span data-stu-id="5da20-118">\\[Bracketed display text\\]</span></span>|<span data-ttu-id="5da20-119">[Texte affiché entre crochets]</span><span class="sxs-lookup"><span data-stu-id="5da20-119">[Bracketed display text]</span></span>|  
  
## <a name="rdl-constants"></a><span data-ttu-id="5da20-120">Constantes RDL</span><span class="sxs-lookup"><span data-stu-id="5da20-120">RDL Constants</span></span>  
 <span data-ttu-id="5da20-121">Vous pouvez utiliser des constantes définies en RDL (Report Definition Language) dans une expression.</span><span class="sxs-lookup"><span data-stu-id="5da20-121">You can use constants defined in Report Definition Language (RDL) in an expression.</span></span> <span data-ttu-id="5da20-122">Dans la boîte de dialogue **Expression** , les constantes apparaissent lorsque vous créez une expression pour une propriété de rapport qui accepte uniquement certaines valeurs valides, également appelées types énumérés.</span><span class="sxs-lookup"><span data-stu-id="5da20-122">In the **Expression** dialog box, constants appear when you create an expression for a report property that only accepts certain valid values, also known as enumerated types.</span></span> <span data-ttu-id="5da20-123">Le tableau suivant contient deux exemples.</span><span class="sxs-lookup"><span data-stu-id="5da20-123">The following table shows two examples.</span></span>  
  
|<span data-ttu-id="5da20-124">Propriété</span><span class="sxs-lookup"><span data-stu-id="5da20-124">Property</span></span>|<span data-ttu-id="5da20-125">Description</span><span class="sxs-lookup"><span data-stu-id="5da20-125">Description</span></span>|<span data-ttu-id="5da20-126">Valeurs</span><span class="sxs-lookup"><span data-stu-id="5da20-126">Values</span></span>|  
|--------------|-----------------|------------|  
|<span data-ttu-id="5da20-127">TextAlign</span><span class="sxs-lookup"><span data-stu-id="5da20-127">TextAlign</span></span>|<span data-ttu-id="5da20-128">Valeurs valides pour aligner le texte dans une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="5da20-128">Valid values for aligning text in a text box.</span></span>|<span data-ttu-id="5da20-129">Général, Gauche, Centre, Droit</span><span class="sxs-lookup"><span data-stu-id="5da20-129">General, Left, Center, Right</span></span>|  
|<span data-ttu-id="5da20-130">BorderStyle</span><span class="sxs-lookup"><span data-stu-id="5da20-130">BorderStyle</span></span>|<span data-ttu-id="5da20-131">Valeurs valides pour une ligne ajoutée à un rapport.</span><span class="sxs-lookup"><span data-stu-id="5da20-131">Valid values for a line added to a report.</span></span>|<span data-ttu-id="5da20-132">Par défaut, Aucune, Pointillés, Tirets, Unie, Double, Tiret-point, Tiret-point-point</span><span class="sxs-lookup"><span data-stu-id="5da20-132">Default, None, Dotted, Dashed, Solid, Double, DashDot, DashDotdot</span></span>|  
  
## <a name="visual-basic-constants"></a><span data-ttu-id="5da20-133">Constantes Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5da20-133">Visual Basic Constants</span></span>  
 <span data-ttu-id="5da20-134">Vous pouvez utiliser des constantes définies dans la bibliothèque d'exécutables [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] dans une expression.</span><span class="sxs-lookup"><span data-stu-id="5da20-134">You can use constants defined in the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] run-time library in an expression.</span></span> <span data-ttu-id="5da20-135">Par exemple, vous pouvez utiliser la constante `DateInterval.Day`.</span><span class="sxs-lookup"><span data-stu-id="5da20-135">For example, you can use the constant `DateInterval.Day`.</span></span> <span data-ttu-id="5da20-136">Pour la date du 10 janvier 2008, l'expression suivante retourne le nombre 10 :</span><span class="sxs-lookup"><span data-stu-id="5da20-136">The following expression for the date January 10, 2008 returns the number 10:</span></span>  
  
 `=DatePart("d",Globals!ExecutionTime)`  
  
## <a name="clr-constants"></a><span data-ttu-id="5da20-137">Constantes CLR</span><span class="sxs-lookup"><span data-stu-id="5da20-137">CLR Constants</span></span>  
 <span data-ttu-id="5da20-138">Vous pouvez utiliser des constantes définies dans les classes CLR (Common Language Runtime) [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] dans une expression.</span><span class="sxs-lookup"><span data-stu-id="5da20-138">You can use constants defined in [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] common language run-time (CLR) classes in an expression.</span></span> <span data-ttu-id="5da20-139">Le tableau suivant contient un exemple de couleur définie par le système.</span><span class="sxs-lookup"><span data-stu-id="5da20-139">The following table shows an example of a system-defined color.</span></span>  
  
|<span data-ttu-id="5da20-140">Constant</span><span class="sxs-lookup"><span data-stu-id="5da20-140">Constant</span></span>|<span data-ttu-id="5da20-141">Description</span><span class="sxs-lookup"><span data-stu-id="5da20-141">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="5da20-142">MistyRose</span><span class="sxs-lookup"><span data-stu-id="5da20-142">MistyRose</span></span>|<span data-ttu-id="5da20-143">Lorsque vous créez une expression pour une propriété de rapport basée sur la couleur d'arrière-plan, vous pouvez spécifier une couleur par nom.</span><span class="sxs-lookup"><span data-stu-id="5da20-143">When you create an expression for a report property that is based on background color, you can specify a color by name.</span></span> <span data-ttu-id="5da20-144">Les noms valides sont répertoriés dans la boîte de dialogue **Expression** .</span><span class="sxs-lookup"><span data-stu-id="5da20-144">Valid names are listed in the **Expression** dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5da20-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5da20-145">See Also</span></span>  
 <span data-ttu-id="5da20-146">[Boîte de dialogue expression](../expression-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="5da20-146">[Expression Dialog Box](../expression-dialog-box.md) </span></span>  
 <span data-ttu-id="5da20-147">[Expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5da20-147">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5da20-148">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5da20-148">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5da20-149">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5da20-149">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5da20-150">Boîte de dialogue Expression &#40;Générateur de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="5da20-150">Expression Dialog Box &#40;Report Builder&#41;</span></span>](../expression-dialog-box-report-builder.md)  
  
  
