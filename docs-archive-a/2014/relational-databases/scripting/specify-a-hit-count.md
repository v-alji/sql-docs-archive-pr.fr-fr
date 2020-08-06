---
title: Spécifier un nombre d'accès
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vs.debug.breakpt.hitcount
helpviewer_keywords:
- Transact-SQL debugger, breakpoint hit count
ms.assetid: 24836939-94ed-4e57-aa85-5d6938d859e4
author: rothja
ms.author: jroth
ms.openlocfilehash: 34c75e990bce1ea5e64c0b45f7acbcaa52fc3c40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612222"
---
# <a name="specify-a-hit-count"></a><span data-ttu-id="2c6b2-102">Spécifier un nombre d'accès</span><span class="sxs-lookup"><span data-stu-id="2c6b2-102">Specify a Hit Count</span></span>
  <span data-ttu-id="2c6b2-103">Un nombre d'accès à un point d'arrêt est un compteur incrémenté par le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] chaque fois que le point d'arrêt est atteint.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-103">A breakpoint hit count is a counter that is incremented by the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger each time the breakpoint is reached.</span></span> <span data-ttu-id="2c6b2-104">Si le nombre d'accès spécifié est atteint et si les conditions de point d'arrêt spécifiées sont satisfaites, le débogueur effectue l'action spécifiée pour le point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-104">If the specified hit count is reached and any specified breakpoint condition is satisfied, the debugger performs the action specified for the breakpoint.</span></span>  
  
## <a name="hit-count-considerations"></a><span data-ttu-id="2c6b2-105">Considérations sur le nombre d'accès</span><span class="sxs-lookup"><span data-stu-id="2c6b2-105">Hit Count Considerations</span></span>  
 <span data-ttu-id="2c6b2-106">Par défaut, l'exécution s'arrête pour chaque accès à un point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-106">By default, execution breaks every time a breakpoint is hit.</span></span> <span data-ttu-id="2c6b2-107">Vous pouvez choisir entre les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="2c6b2-107">You can choose between the following options:</span></span>  
  
-   <span data-ttu-id="2c6b2-108">Toujours s'arrêter (valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="2c6b2-108">Break always (the default).</span></span>  
  
-   <span data-ttu-id="2c6b2-109">Arrêter lorsque le nombre d'accès est égal à une valeur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-109">Break when the hit count equals a specified value.</span></span>  
  
-   <span data-ttu-id="2c6b2-110">Arrêter lorsque le nombre d'accès est égal au multiple d'une valeur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-110">Break when the hit count equals a multiple of a specified value.</span></span>  
  
-   <span data-ttu-id="2c6b2-111">Arrêter lorsque le nombre d'accès est supérieur ou égal à une valeur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-111">Break when the hit count is greater than or equal to a specified value.</span></span>  
  
 <span data-ttu-id="2c6b2-112">Les nombres d'accès à un point d'arrêt sont incrémentés dans le cadre de l'étendue d'une session de débogage.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-112">Breakpoint hit counts are incremented within the scope of a debugging session.</span></span> <span data-ttu-id="2c6b2-113">Tous les nombres d'accès sont remis à zéro au démarrage de chaque session de débogage.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-113">All hit counts are set to zero at the start of each debugging session.</span></span>  
  
 <span data-ttu-id="2c6b2-114">Si vous souhaitez connaître le nombre d'accès à un point d'arrêt sans que l'exécution s'arrête, spécifiez un nombre d'accès avec une valeur très élevée afin que le point d'arrêt n'entraîne jamais l'arrêt.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-114">If you want to track how many times a breakpoint is hit without having the breakpoint break execution, specify a hit count with a very high value so the breakpoint never breaks.</span></span>  
  
 <span data-ttu-id="2c6b2-115">L'action par défaut pour un point d'arrêt consiste à arrêter l'exécution lorsque le nombre d'accès et la condition de point d'arrêt sont tous les deux satisfaits.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-115">The default action for a breakpoint is to break execution when both the hit count and breakpoint condition have been satisfied.</span></span> <span data-ttu-id="2c6b2-116">Pour plus d’informations sur la spécification d’autres actions, consultez [Spécifier une action de point d’arrêt](specify-a-breakpoint-action.md).</span><span class="sxs-lookup"><span data-stu-id="2c6b2-116">For information about specifying other actions, see [Specify a Breakpoint Action](specify-a-breakpoint-action.md).</span></span>  
  
#### <a name="to-specify-a-hit-count"></a><span data-ttu-id="2c6b2-117">Pour spécifier un nombre d'accès</span><span class="sxs-lookup"><span data-stu-id="2c6b2-117">To Specify a Hit Count</span></span>  
  
1.  <span data-ttu-id="2c6b2-118">Dans la fenêtre de l’éditeur, cliquez avec le bouton droit sur le glyphe du point d’arrêt, puis cliquez sur **Nombre d’accès** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-118">In the editor window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="2c6b2-119">-ou-</span><span class="sxs-lookup"><span data-stu-id="2c6b2-119">-or-</span></span>  
  
     <span data-ttu-id="2c6b2-120">Dans la fenêtre **Points d’arrêt** , cliquez avec le bouton droit sur le glyphe du point d’arrêt, puis cliquez sur **Nombre d’accès** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-120">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="2c6b2-121">Dans la boîte de dialogue **Nombre d’accès à un point d’arrêt** , sélectionnez le comportement que vous souhaitez dans la zone **Lorsque le point d’arrêt est atteint** .</span><span class="sxs-lookup"><span data-stu-id="2c6b2-121">In the **Breakpoint Hit Count** dialog box, select the behavior you want from the **When the breakpoint is hit** box.</span></span>  
  
     <span data-ttu-id="2c6b2-122">Si vous choisissez un paramètre autre que **Toujours s’arrêter**, une zone de texte apparaît à droite de la liste.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-122">If you choose any setting other than **Break Always**, a text box appears to the right of the list.</span></span> <span data-ttu-id="2c6b2-123">Entrez un entier dans cette zone de texte pour spécifier le nombre d'accès souhaité.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-123">Enter an integer in the text box to specify the hit count you want.</span></span>  
  
3.  <span data-ttu-id="2c6b2-124">Cliquez sur **OK** pour implémenter les modifications ou sur **Annuler** pour fermer sans appliquer les modifications.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-124">Click **OK** to implement the changes, or **Cancel** to exit without applying the changes.</span></span>  
  
#### <a name="to-view-or-reset-the-current-hit-count"></a><span data-ttu-id="2c6b2-125">Afficher ou réinitialiser le nombre d'accès actuel</span><span class="sxs-lookup"><span data-stu-id="2c6b2-125">To View or Reset the Current Hit Count</span></span>  
  
1.  <span data-ttu-id="2c6b2-126">Dans la fenêtre de l’éditeur, cliquez avec le bouton droit sur le glyphe du point d’arrêt, puis cliquez sur **Nombre d’accès** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-126">In the editor window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="2c6b2-127">-ou-</span><span class="sxs-lookup"><span data-stu-id="2c6b2-127">-or-</span></span>  
  
     <span data-ttu-id="2c6b2-128">Dans la fenêtre **Points d’arrêt** , cliquez avec le bouton droit sur le glyphe du point d’arrêt, puis cliquez sur **Nombre d’accès** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-128">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="2c6b2-129">Dans la boîte de dialogue **Nombre d’accès à un point d’arrêt** , le **Nombre d’accès actuel** est affiché juste au-dessus du bouton **Réinitialiser** .</span><span class="sxs-lookup"><span data-stu-id="2c6b2-129">In the **Breakpoint Hit Count** dialog box, the **Current hit count:** is displayed just above the **Reset** button.</span></span>  
  
3.  <span data-ttu-id="2c6b2-130">Cliquez sur **Réinitialiser** si vous souhaitez réinitialiser le nombre d’accès actuel à zéro.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-130">Click **Reset** if you want to set the current hit count to zero.</span></span>  
  
4.  <span data-ttu-id="2c6b2-131">Cliquez sur **OK** ou sur **Annuler** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2c6b2-131">Click **OK** or **Cancel** to exit the dialog.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c6b2-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c6b2-132">See Also</span></span>  
 [<span data-ttu-id="2c6b2-133">Spécifier une condition de point d’arrêt</span><span class="sxs-lookup"><span data-stu-id="2c6b2-133">Specify a Breakpoint Condition</span></span>](specify-a-breakpoint-condition.md)  
  
  
