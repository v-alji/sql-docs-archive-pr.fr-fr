---
title: Notions de base des scripts MDX (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], scripts
- calculations [Analysis Services], scripts
- MDX [Analysis Services], scripts
- scripts [MDX]
- cubes [Analysis Services], calculations
- Multidimensional Expressions [Analysis Services], scripts
ms.assetid: fdecb3ce-7c87-4bab-8000-532ba7a29f96
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2f7638339d8fc366ee384d453f6df683f3bd41f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612566"
---
# <a name="mdx-scripting-fundamentals-analysis-services"></a><span data-ttu-id="c25cb-102">Principes de base des scripts MDX (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="c25cb-102">MDX Scripting Fundamentals (Analysis Services)</span></span>
  <span data-ttu-id="c25cb-103">Dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , un script MDX (Multidimensional Expressions) est constitué d’une ou plusieurs expressions ou instructions MDX qui remplissent un cube avec des calculs.</span><span class="sxs-lookup"><span data-stu-id="c25cb-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], a Multidimensional Expressions (MDX) script is made up of one or more MDX expressions or statements that populate a cube with calculations.</span></span>  
  
 <span data-ttu-id="c25cb-104">Un script MDX définit le processus de calcul pour un cube.</span><span class="sxs-lookup"><span data-stu-id="c25cb-104">An MDX script defines the calculation process for a cube.</span></span> <span data-ttu-id="c25cb-105">Il est également considéré comme un élément du cube proprement dit.</span><span class="sxs-lookup"><span data-stu-id="c25cb-105">An MDX script is also considered part of the cube itself.</span></span> <span data-ttu-id="c25cb-106">Par conséquent, la modification d'un script MDX associé à un cube entraîne immédiatement la modification de son processus de calcul.</span><span class="sxs-lookup"><span data-stu-id="c25cb-106">Therefore, changing an MDX script associated with a cube immediately changes the calculation process for the cube.</span></span>  
  
 <span data-ttu-id="c25cb-107">Pour créer des scripts MDX, vous pouvez utiliser le Concepteur de cube disponible dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c25cb-107">To create MDX scripts, you can use Cube Designer in the [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="c25cb-108">Pour plus d’informations, consultez [Définir des attributions et d’autres commandes de script](../define-assignments-and-other-script-commands.md) et [Introduction aux scripts MDX dans Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892).</span><span class="sxs-lookup"><span data-stu-id="c25cb-108">For more information, see [Define Assignments and Other Script Commands](../define-assignments-and-other-script-commands.md) and [Introduction to MDX Scripting in Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892).</span></span>  
  
 <span data-ttu-id="c25cb-109">Pour résoudre les problèmes de performance liés aux calculs et aux requêtes MDX, consultez la section relative à l’optimisation de MDX du [Guide des performances de SQL Server Analysis Services](https://go.microsoft.com/fwlink/p/?LinkId=399050).</span><span class="sxs-lookup"><span data-stu-id="c25cb-109">For performance issues related to MDX queries and calculations, see the MDX optimization section in the [SQL Server Analysis Services Performance Guide](https://go.microsoft.com/fwlink/p/?LinkId=399050).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c25cb-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c25cb-110">In This Section</span></span>  
  
|<span data-ttu-id="c25cb-111">Rubrique</span><span class="sxs-lookup"><span data-stu-id="c25cb-111">Topic</span></span>|<span data-ttu-id="c25cb-112">Description</span><span class="sxs-lookup"><span data-stu-id="c25cb-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c25cb-113">Script MDX de base &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c25cb-113">The Basic MDX Script &#40;MDX&#41;</span></span>](the-basic-mdx-script-mdx.md)|<span data-ttu-id="c25cb-114">Décrit en détail le script MDX de base, notamment le script MDX par défaut fourni dans chaque cube, ainsi que le mode de fonctionnement général des scripts MDX au sein d’un cube dans [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c25cb-114">Details the basic MDX script, including the default MDX script provided in each cube, and how MDX scripts generally function within a cube in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="c25cb-115">Gestion de la portée et du contexte &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c25cb-115">Managing Scope and Context &#40;MDX&#41;</span></span>](managing-scope-and-context-mdx.md)|<span data-ttu-id="c25cb-116">Décrit l’utilisation de l’instruction [CALCULATE](/sql/mdx/mdx-scripting-calculate) , de l’instruction [SCOPE](/sql/mdx/mdx-scripting-scope) et de la fonction [This](/sql/mdx/this-mdx) pour gérer le contexte et la portée au sein d’un script MDX.</span><span class="sxs-lookup"><span data-stu-id="c25cb-116">Describes how to use the [CALCULATE](/sql/mdx/mdx-scripting-calculate) statement, the [SCOPE](/sql/mdx/mdx-scripting-scope) statement, and the [This](/sql/mdx/this-mdx) function to manage context and scope within an MDX script.</span></span>|  
|[<span data-ttu-id="c25cb-117">Utilisation de variables et de paramètres &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c25cb-117">Using Variables and Parameters &#40;MDX&#41;</span></span>](using-variables-and-parameters-mdx.md)|<span data-ttu-id="c25cb-118">Décrit l'utilisation de variables et de paramètres dans un script MDX.</span><span class="sxs-lookup"><span data-stu-id="c25cb-118">Describes how to use variables and parameters in an MDX script.</span></span>|  
|[<span data-ttu-id="c25cb-119">Gestion des erreurs &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c25cb-119">Error Handling &#40;MDX&#41;</span></span>](error-handling-mdx.md)|<span data-ttu-id="c25cb-120">Explique la gestion des erreurs au sein d'un script MDX.</span><span class="sxs-lookup"><span data-stu-id="c25cb-120">Explains error handling within an MDX script.</span></span>|  
|[<span data-ttu-id="c25cb-121">Prise en charge de MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c25cb-121">Supported MDX &#40;MDX&#41;</span></span>](supported-mdx-mdx.md)|<span data-ttu-id="c25cb-122">Fournit la liste des opérateurs, instructions et fonctions MDX pris en charge dans un script MDX.</span><span class="sxs-lookup"><span data-stu-id="c25cb-122">Provides a list of supported MDX operators, statements, and functions within an MDX script.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c25cb-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c25cb-123">See Also</span></span>  
 [<span data-ttu-id="c25cb-124">Guide de référence du langage MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c25cb-124">MDX Language Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-language-reference-mdx)  
  
  
