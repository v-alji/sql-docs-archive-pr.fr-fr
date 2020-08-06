---
title: Ajouter une expression (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a60ee091-b4ed-41e1-9b6a-032c316cd03f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 16f414bfad47ae92681de50eb576a6ac2cb3f5fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696415"
---
# <a name="add-an-expression-report-builder-and-ssrs"></a><span data-ttu-id="955cd-102">Ajouter une expression (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="955cd-102">Add an Expression (Report Builder and SSRS)</span></span>
  <span data-ttu-id="955cd-103">Les expressions sont utilisées dans l'ensemble d'un rapport pour définir des propriétés d'éléments de rapport, des filtres, des groupes, un ordre de tri, des chaînes de connexion et des valeurs de paramètres.</span><span class="sxs-lookup"><span data-stu-id="955cd-103">Expressions are used throughout a report for defining report item properties, filters, groups, sort order, connection strings, and parameter values.</span></span> <span data-ttu-id="955cd-104">Les expressions commencent par un signe égal (=) et sont écrites en langage [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="955cd-104">Expressions begin with an equal sign (=) and are written in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span> <span data-ttu-id="955cd-105">Elles sont évaluées au moment de l'exécution par le processeur de rapports, qui associe le résultat d'évaluation aux éléments de disposition du rapport.</span><span class="sxs-lookup"><span data-stu-id="955cd-105">They are evaluated at run time by the report processor, which combines the evaluation result with report layout elements.</span></span>  
  
 <span data-ttu-id="955cd-106">Les expressions peuvent être simples ou complexes.</span><span class="sxs-lookup"><span data-stu-id="955cd-106">Expressions can be simple or complex.</span></span> <span data-ttu-id="955cd-107">Une expression simple fait référence à un élément unique dans une collection intégrée.</span><span class="sxs-lookup"><span data-stu-id="955cd-107">Simple expression refer to a single item in a built-in collection.</span></span> <span data-ttu-id="955cd-108">Les expressions complexes peuvent contenir des constantes, opérateurs, éléments de collecte globaux et appels de fonction.</span><span class="sxs-lookup"><span data-stu-id="955cd-108">Complex expressions can contain constants, operators, global collection items, and function calls.</span></span> <span data-ttu-id="955cd-109">Pour plus d’informations, consultez [Expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="955cd-109">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-expression-to-a-text-box"></a><span data-ttu-id="955cd-110">Pour ajouter une expression à une zone de texte</span><span class="sxs-lookup"><span data-stu-id="955cd-110">To add an expression to a text box</span></span>  
  
-   <span data-ttu-id="955cd-111">En mode **Conception** , cliquez sur la zone de texte sur l'aire de conception à laquelle ajouter une expression.</span><span class="sxs-lookup"><span data-stu-id="955cd-111">In **Design** view, click the text box on the design surface to which you want to add an expression.</span></span>  
  
    -   <span data-ttu-id="955cd-112">Pour une expression simple, tapez le texte affiché de l'expression dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="955cd-112">For a simple expression, type the display text for the expression in the text box.</span></span> <span data-ttu-id="955cd-113">Par exemple, pour le champ de dataset Sales, tapez `[Sales]`.</span><span class="sxs-lookup"><span data-stu-id="955cd-113">For example, for the dataset field Sales, type `[Sales]`.</span></span>  
  
    -   <span data-ttu-id="955cd-114">Pour une expression complexe, cliquez avec le bouton droit sur la zone de texte, puis sélectionnez **Expression**.</span><span class="sxs-lookup"><span data-stu-id="955cd-114">For a complex expression, right-click the text box, and select **Expression**.</span></span> <span data-ttu-id="955cd-115">La boîte de dialogue **Expression** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="955cd-115">The **Expression** dialog box opens.</span></span> <span data-ttu-id="955cd-116">Tapez ou créez interactivement votre expression après le signe égal (=) dans le volet d'expression, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="955cd-116">Type or interactively create your expression after the '=' in the expression pane, and then click OK.</span></span>  
  
         <span data-ttu-id="955cd-117">L'expression apparaît sur l'aire de conception sous la forme `<<Expr>>`.</span><span class="sxs-lookup"><span data-stu-id="955cd-117">The expression appears on the design surface as `<<Expr>>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="955cd-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="955cd-118">See Also</span></span>  
 <span data-ttu-id="955cd-119">[Mise en forme du texte et des espaces réservés &#40;Générateur de rapports et SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="955cd-119">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="955cd-120">[Zones de texte &#40;Générateur de rapport et SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="955cd-120">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="955cd-121">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="955cd-121">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="955cd-122">[Exemples d’équations de filtre &#40;Générateur de rapports et SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="955cd-122">[Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="955cd-123">[Exemples d’expressions de groupe &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="955cd-123">[Group Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="955cd-124">[Boîte de dialogue Expression &#40;Générateur de rapports&#41;](../expression-dialog-box-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="955cd-124">[Expression Dialog Box &#40;Report Builder&#41;](../expression-dialog-box-report-builder.md) </span></span>  
 <span data-ttu-id="955cd-125">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="955cd-125">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="955cd-126">Ajouter du code à un rapport &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="955cd-126">Add Code to a Report &#40;SSRS&#41;</span></span>](add-code-to-a-report-ssrs.md)  
  
  
