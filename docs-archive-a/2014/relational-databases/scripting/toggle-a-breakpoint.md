---
title: Basculer un point d'arrêt
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c477ab89-a1cd-4f2c-aa7c-40525041100f
author: rothja
ms.author: jroth
ms.openlocfilehash: 72e26e9b1d04bc2eced6bcb6d93d3c86a016d308
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612752"
---
# <a name="toggle-a-breakpoint"></a><span data-ttu-id="ad46c-102">Basculer un point d'arrêt</span><span class="sxs-lookup"><span data-stu-id="ad46c-102">Toggle a Breakpoint</span></span>
  <span data-ttu-id="ad46c-103">Le fait de définir un point d'arrêt sur une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] s'appelle le basculement d'un point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="ad46c-103">The act of setting a breakpoint on a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is called toggling a breakpoint.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="ad46c-104">Points d’arrêt</span><span class="sxs-lookup"><span data-stu-id="ad46c-104">Breakpoints</span></span>  
 <span data-ttu-id="ad46c-105">Une fois le point d'arrêt défini, il est représenté par une icône dans la barre grise à gauche de l'instruction.</span><span class="sxs-lookup"><span data-stu-id="ad46c-105">Once the breakpoint has been set, it is represented by an icon in the grey bar to the left of the statement.</span></span> <span data-ttu-id="ad46c-106">Cette icône s'appelle un glyphe de point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="ad46c-106">The icon is called a breakpoint glyph.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="ad46c-107">Les points d’arrêt sont appliqués à une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] complète.</span><span class="sxs-lookup"><span data-stu-id="ad46c-107">breakpoints are applied to a complete [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="ad46c-108">Lorsqu'un point d'arrêt est activé, le débogueur met en surbrillance l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] associée.</span><span class="sxs-lookup"><span data-stu-id="ad46c-108">When a breakpoint is toggled on, the debugger highlights the associated [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
 <span data-ttu-id="ad46c-109">S'il existe plusieurs instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] sur une ligne, vous pouvez basculer un point d'arrêt pour chaque instruction.</span><span class="sxs-lookup"><span data-stu-id="ad46c-109">If there are multiple [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on a line, you can toggle a breakpoint for each statement.</span></span> <span data-ttu-id="ad46c-110">Cliquer dans la barre grise à gauche de la fenêtre bascule un point d'arrêt sur la première instruction de la ligne.</span><span class="sxs-lookup"><span data-stu-id="ad46c-110">Clicking in the grey bar on the left of the window toggles a breakpoint on the first statement on the line.</span></span> <span data-ttu-id="ad46c-111">Vous pouvez basculer un point d’arrêt dans une instruction suivante en mettant en surbrillance une partie de l’instruction ou en plaçant le curseur dans l’instruction, puis en appuyant sur F9 ou en cliquant sur **Basculer le point d’arrêt** dans le menu **Déboguer** .</span><span class="sxs-lookup"><span data-stu-id="ad46c-111">You can toggle a breakpoint in a subsequent statement by highlighting any part of the statement, or moving the cursor into the statement, and then either pressing F9 or clicking **Toggle Breakpoint** on the **Debug** menu.</span></span> <span data-ttu-id="ad46c-112">Si plusieurs points d'arrêt se trouvent sur une ligne, un seul glyphe de point d'arrêt se trouve dans la barre grise à gauche.</span><span class="sxs-lookup"><span data-stu-id="ad46c-112">If you have multiple breakpoints on a line, there is only one breakpoint glyph in the grey bar on the left.</span></span>  
  
 <span data-ttu-id="ad46c-113">Une fois qu'un point d'arrêt a été basculé, vous pouvez effectuer plusieurs actions sur celui-ci, par exemple modifier ses propriétés ou les désactiver temporairement.</span><span class="sxs-lookup"><span data-stu-id="ad46c-113">After a breakpoint has been toggled, you can perform various actions on the breakpoint, such as editing its properties or temporarily disabling it.</span></span> <span data-ttu-id="ad46c-114">Pour plus d’informations, consultez [Points d’arrêt Transact-SQL](transact-sql-breakpoints.md).</span><span class="sxs-lookup"><span data-stu-id="ad46c-114">For more information, see [Transact-SQL Breakpoints](transact-sql-breakpoints.md).</span></span>  
  
## <a name="toggle-a-breakpoint"></a><span data-ttu-id="ad46c-115">Basculer un point d'arrêt</span><span class="sxs-lookup"><span data-stu-id="ad46c-115">Toggle a Breakpoint</span></span>  
 <span data-ttu-id="ad46c-116">**Pour basculer un point d'arrêt sur une instruction Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ad46c-116">**To toggle a breakpoint on a Transact-SQL statement**</span></span>  
  
1.  <span data-ttu-id="ad46c-117">Cliquez sur la barre grise à gauche de l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad46c-117">Click the gray bar to the left side of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
2.  <span data-ttu-id="ad46c-118">Vous pouvez également mettre en surbrillance une partie quelconque de l'instruction ou placer le curseur sur l'instruction, puis effectuer l'une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="ad46c-118">Alternatively, either highlight any part of the statement or move the cursor to the statement, and then perform either action:</span></span>  
  
    -   <span data-ttu-id="ad46c-119">Appuyez sur F9.</span><span class="sxs-lookup"><span data-stu-id="ad46c-119">Press F9.</span></span>  
  
    -   <span data-ttu-id="ad46c-120">Dans le menu **Déboguer** , cliquez sur **Basculer le point d’arrêt**.</span><span class="sxs-lookup"><span data-stu-id="ad46c-120">On the **Debug** menu, click **Toggle Breakpoint**.</span></span>  
  
  
