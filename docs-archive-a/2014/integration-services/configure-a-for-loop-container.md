---
title: Configurer un conteneur de boucles for | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], For Loop
- For Loop containers
ms.assetid: b9cd7ea7-b198-4a35-8b16-6acf09611ca5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9cb33ea5b7f3f59baad3c94f6bc845c281613ec9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601619"
---
# <a name="configure-a-for-loop-container"></a><span data-ttu-id="07380-102">Configurer un conteneur de boucles For</span><span class="sxs-lookup"><span data-stu-id="07380-102">Configure a For Loop Container</span></span>
  <span data-ttu-id="07380-103">Cette procédure décrit comment configurer un conteneur de boucles For à l’aide de la boîte de dialogue **Éditeur de boucle For** .</span><span class="sxs-lookup"><span data-stu-id="07380-103">This procedure describes how to configure a For Loop container by using the **For Loop Editor** dialog box.</span></span>  
  
### <a name="to-configure-the-for-loop-container"></a><span data-ttu-id="07380-104">Pour configurer le conteneur de boucles For</span><span class="sxs-lookup"><span data-stu-id="07380-104">To configure the For Loop container</span></span>  
  
1.  <span data-ttu-id="07380-105">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], double-cliquez sur le conteneur de boucles For pour ouvrir l’ **Éditeur de boucle For**.</span><span class="sxs-lookup"><span data-stu-id="07380-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], double-click the For Loop container to open the **For Loop Editor**.</span></span>  
  
2.  <span data-ttu-id="07380-106">Si vous le souhaitez, modifiez le nom et la description du conteneur de boucles For.</span><span class="sxs-lookup"><span data-stu-id="07380-106">Optionally, modify the name and description of the For Loop container.</span></span>  
  
3.  <span data-ttu-id="07380-107">Si vous le souhaitez, tapez une expression d’initialisation dans la zone de texte **InitExpression** .</span><span class="sxs-lookup"><span data-stu-id="07380-107">Optionally, type an initialization expression in the **InitExpression** text box.</span></span>  
  
4.  <span data-ttu-id="07380-108">Tapez une expression d’évaluation dans la zone de texte **EvalExpression** .</span><span class="sxs-lookup"><span data-stu-id="07380-108">Type an evaluation expression in the **EvalExpression** text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="07380-109">L'expression doit prendre une valeur de type Boolean.</span><span class="sxs-lookup"><span data-stu-id="07380-109">The expression must evaluate to a Boolean.</span></span> <span data-ttu-id="07380-110">Lorsque l'expression correspond à `false`, la boucle cesse de s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="07380-110">When the expression evaluates to `false`, the loop stops running.</span></span>  
  
5.  <span data-ttu-id="07380-111">Si vous le souhaitez, tapez une expression d’assignation dans la zone de texte **AssignExpression** .</span><span class="sxs-lookup"><span data-stu-id="07380-111">Optionally, type an assignment expression in the **AssignExpression** text box.</span></span>  
  
6.  <span data-ttu-id="07380-112">Si vous le souhaitez, cliquez sur **Expressions** et, dans la page **Expressions** , créez des expressions de propriété pour les propriétés du conteneur de boucles For.</span><span class="sxs-lookup"><span data-stu-id="07380-112">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions for the properties of the For Loop container.</span></span> <span data-ttu-id="07380-113">Pour plus d’informations, consultez [Ajouter ou modifier une Expression de propriété](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="07380-113">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="07380-114">Cliquez sur **OK** pour fermer la boîte de dialogue **Éditeur de boucle For**.</span><span class="sxs-lookup"><span data-stu-id="07380-114">Click **OK** to close the **For Loop Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07380-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07380-115">See Also</span></span>  
 <span data-ttu-id="07380-116">[Conteneur de boucles for](control-flow/for-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="07380-116">[For Loop Container](control-flow/for-loop-container.md) </span></span>  
 <span data-ttu-id="07380-117">[Integration Services &#40;des expressions de&#41; SSIS](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="07380-117">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 [<span data-ttu-id="07380-118">Expressions de propriété dans des packages</span><span class="sxs-lookup"><span data-stu-id="07380-118">Use Property Expressions in Packages</span></span>](expressions/use-property-expressions-in-packages.md)  
  
  
