---
title: Spécifier une condition de point d'arrêt
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint conditions
ms.assetid: b43d8a2b-99a3-4fb7-8848-99c042ea7ef7
author: rothja
ms.author: jroth
ms.openlocfilehash: 659b6ca1149eb8f0412efbe2adbaf4c1ffce59d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702672"
---
# <a name="specify-a-breakpoint-condition"></a><span data-ttu-id="b12f5-102">Spécifier une condition de point d'arrêt</span><span class="sxs-lookup"><span data-stu-id="b12f5-102">Specify a Breakpoint Condition</span></span>
  <span data-ttu-id="b12f5-103">Une condition de point d'arrêt est une expression [!INCLUDE[tsql](../../includes/tsql-md.md)] évaluée par le débogueur lorsque le point d'arrêt est atteint.</span><span class="sxs-lookup"><span data-stu-id="b12f5-103">A breakpoint condition is a [!INCLUDE[tsql](../../includes/tsql-md.md)] expression that is evaluated by the debugger when the breakpoint is reached.</span></span> <span data-ttu-id="b12f5-104">Si la condition est satisfaite et si le nombre d'accès spécifié est atteint, le débogueur arrête ou effectue l'action spécifiée pour le point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="b12f5-104">If the condition is satisfied and any specified hit count reached, the debugger either breaks or performs the action specified for the breakpoint.</span></span>  
  
## <a name="specifying-conditions"></a><span data-ttu-id="b12f5-105">Spécification des conditions</span><span class="sxs-lookup"><span data-stu-id="b12f5-105">Specifying Conditions</span></span>  
 <span data-ttu-id="b12f5-106">L'expression spécifiée doit être une expression Transact-SQL valide qui correspond à une valeur booléenne.</span><span class="sxs-lookup"><span data-stu-id="b12f5-106">The expression specified must be a valid Transact-SQL expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="b12f5-107">Pour plus d’informations, consultez [Expressions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/expressions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b12f5-107">For more information, see [Expressions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/expressions-transact-sql).</span></span>  
  
 <span data-ttu-id="b12f5-108">Si vous spécifiez une condition de point d'arrêt avec une syntaxe incorrecte, un message d'avertissement apparaît immédiatement.</span><span class="sxs-lookup"><span data-stu-id="b12f5-108">If you specify a breakpoint condition with invalid syntax, a warning message appears immediately.</span></span> <span data-ttu-id="b12f5-109">Si vous spécifiez une condition avec une syntaxe correcte mais une sémantique incorrecte, un message d'avertissement s'affiche lorsque le point d'arrêt est atteint pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="b12f5-109">If you specify a condition with valid syntax but invalid semantics, a warning message is displayed the first time the breakpoint is hit.</span></span> <span data-ttu-id="b12f5-110">Dans les deux cas, le débogueur arrête l'exécution lorsque le point d'arrêt non valide est atteint.</span><span class="sxs-lookup"><span data-stu-id="b12f5-110">In either case, the debugger breaks execution when the invalid breakpoint is hit.</span></span>  
  
#### <a name="to-specify-a-condition"></a><span data-ttu-id="b12f5-111">Pour spécifier une condition</span><span class="sxs-lookup"><span data-stu-id="b12f5-111">To Specify a Condition</span></span>  
  
1.  <span data-ttu-id="b12f5-112">Dans la fenêtre de l’éditeur, cliquez avec le bouton droit sur le glyphe du point d’arrêt, puis cliquez sur **Condition** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="b12f5-112">In the editor window, right-click the breakpoint glyph, and then click **Condition** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="b12f5-113">-ou-</span><span class="sxs-lookup"><span data-stu-id="b12f5-113">-or-</span></span>  
  
     <span data-ttu-id="b12f5-114">Dans la fenêtre **Points d’arrêt** , cliquez avec le bouton droit sur le glyphe du point d’arrêt, puis cliquez sur **Condition** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="b12f5-114">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Condition** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="b12f5-115">Dans la boîte de dialogue **Condition de point d’arrêt** , entrez une expression booléenne valide dans la zone **Condition** .</span><span class="sxs-lookup"><span data-stu-id="b12f5-115">In the **Breakpoint Condition** dialog box, enter a valid Boolean expression in the **Condition** box.</span></span>  
  
3.  <span data-ttu-id="b12f5-116">Choisissez **est vrai** si vous souhaitez arrêter lorsque l’expression correspond à `true` , ou choisissez **a changé** si vous souhaitez arrêter lorsque la valeur de l’expression a changé.</span><span class="sxs-lookup"><span data-stu-id="b12f5-116">Choose **Is true** if you want to break when the expression evaluates to `true`, or choose **Has changed** if you want to break when the value of the expression has changed.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b12f5-117">Le débogueur n'évalue l'expression booléenne que lorsque le point d'arrêt est atteint pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="b12f5-117">The debugger does not evaluate the Boolean expression until the first time the breakpoint is reached.</span></span> <span data-ttu-id="b12f5-118">Si vous choisissez **a changé**, le débogueur ne considère pas la première évaluation comme une modification, donc il ne s’y arrête pas.</span><span class="sxs-lookup"><span data-stu-id="b12f5-118">If you choose **Has changed**, the debugger does not consider the first evaluation to be a change, so the debugger will not break on the first evaluation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b12f5-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b12f5-119">See Also</span></span>  
 <span data-ttu-id="b12f5-120">[Spécifier un nombre d’accès](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="b12f5-120">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 [<span data-ttu-id="b12f5-121">Spécifier une action de point d’arrêt</span><span class="sxs-lookup"><span data-stu-id="b12f5-121">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)  
