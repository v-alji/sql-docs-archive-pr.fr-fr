---
title: Activer, désactiver et supprimer des points d'arrêt
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 357b5874-273f-43a9-8e30-83872bdea5dc
author: rothja
ms.author: jroth
ms.openlocfilehash: 17e83c6488b9d9026fb78e5fb8f50e22533fa61e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613979"
---
# <a name="enable-disable-and-delete-breakpoints"></a><span data-ttu-id="ce762-102">Activer, désactiver et supprimer des points d'arrêt</span><span class="sxs-lookup"><span data-stu-id="ce762-102">Enable, Disable, and Delete Breakpoints</span></span>
  <span data-ttu-id="ce762-103">Pour afficher et gérer tous les points d'arrêt ouverts, vous pouvez utiliser la fenêtre **Points d'arrêt** .</span><span class="sxs-lookup"><span data-stu-id="ce762-103">To view and manage all the open breakpoints, you can use the **Breakpoints** window.</span></span> <span data-ttu-id="ce762-104">Utilisez la fenêtre pour afficher les informations sur les points d'arrêt et entreprendre des actions, telles que la suppression, la désactivation ou l'activation des points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="ce762-104">Use the window to view breakpoint information and to take actions such as deleting, disabling, or enabling breakpoints.</span></span>  
  
## <a name="the-breakpoints-window"></a><span data-ttu-id="ce762-105">Fenêtre Points d'arrêt</span><span class="sxs-lookup"><span data-stu-id="ce762-105">The Breakpoints Window</span></span>  
 <span data-ttu-id="ce762-106">La fenêtre **Points d'arrêt** répertorie des informations telles que la ligne de code sur laquelle se trouve le point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="ce762-106">The **Breakpoints** window lists information such as which line of code the breakpoint is located on.</span></span> <span data-ttu-id="ce762-107">Dans la fenêtre **Points d'arrêt** , vous pouvez aussi supprimer, désactiver et activer des points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="ce762-107">In the **Breakpoints** window, you can also delete, disable, and enable breakpoints.</span></span> <span data-ttu-id="ce762-108">Pour plus d'informations sur la fenêtre **Points d'arrêt** , consultez [Points d'arrêt Window](transact-sql-debugger-breakpoints-window.md).</span><span class="sxs-lookup"><span data-stu-id="ce762-108">For more information about the **Breakpoints** window, see [Breakpoints Window](transact-sql-debugger-breakpoints-window.md)</span></span>  
  
 <span data-ttu-id="ce762-109">La désactivation d'un point d'arrêt l'empêche de suspendre l'exécution. Toutefois, la définition reste en place au cas où vous souhaiteriez activer le point d'arrêt ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="ce762-109">Disabling a breakpoint prevents it from pausing execution, but leaves the definition in place in case you want to enable the breakpoint later.</span></span> <span data-ttu-id="ce762-110">La suppression d'un point d'arrêt le supprime définitivement.</span><span class="sxs-lookup"><span data-stu-id="ce762-110">Deleting a breakpoint removes it permanently.</span></span> <span data-ttu-id="ce762-111">Vous devez activer/désactiver un nouveau point d'arrêt pour suspendre l'exécution de l'instruction.</span><span class="sxs-lookup"><span data-stu-id="ce762-111">You must toggle a new breakpoint to pause execution on the statement.</span></span>  
  
## <a name="to-open-the-breakpoints-window"></a><span data-ttu-id="ce762-112">Pour ouvrir la fenêtre Points d'arrêt</span><span class="sxs-lookup"><span data-stu-id="ce762-112">To Open the Breakpoints Window</span></span>  
 <span data-ttu-id="ce762-113">**To open the Breakpoints window**</span><span class="sxs-lookup"><span data-stu-id="ce762-113">**To open the Breakpoints window**</span></span>  
  
 <span data-ttu-id="ce762-114">Vous pouvez ouvrir la fenêtre **Points d'arrêt** de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce762-114">You can open the **Breakpoints** window in one of the following ways:</span></span>  
  
-   <span data-ttu-id="ce762-115">Dans le menu **Déboguer** , cliquez sur **Fenêtres**, puis sur **Points d'arrêt**.</span><span class="sxs-lookup"><span data-stu-id="ce762-115">On the **Debug** menu, click **Windows**, and then click **Breakpoints**.</span></span>  
  
-   <span data-ttu-id="ce762-116">Dans la barre d'outils **Déboguer** , cliquez sur le bouton **Points d'arrêt** .</span><span class="sxs-lookup"><span data-stu-id="ce762-116">On the **Debug** toolbar, click the **Breakpoints** button.</span></span>  
  
-   <span data-ttu-id="ce762-117">Appuyez sur CTRL+ALT+B.</span><span class="sxs-lookup"><span data-stu-id="ce762-117">Press CTRL+ALT+B.</span></span>  
  
## <a name="to-disable-a-single-breakpoint"></a><span data-ttu-id="ce762-118">Pour désactiver un point d'arrêt</span><span class="sxs-lookup"><span data-stu-id="ce762-118">To Disable a Single Breakpoint</span></span>  
 <span data-ttu-id="ce762-119">**To disable a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="ce762-119">**To disable a single breakpoint**</span></span>  
  
 <span data-ttu-id="ce762-120">Vous pouvez désactiver un point d'arrêt de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce762-120">You can disable a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="ce762-121">Dans la fenêtre de l’éditeur de requête, cliquez avec le bouton droit sur le point d’arrêt, puis cliquez sur **Désactiver le point d’arrêt**.</span><span class="sxs-lookup"><span data-stu-id="ce762-121">In the Query Editor window, right-click the breakpoint, and then click **Disable Breakpoint**.</span></span>  
  
-   <span data-ttu-id="ce762-122">Dans la fenêtre Points d'arrêt, désactivez la case à cocher à gauche du point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="ce762-122">In the Breakpoints window, clear the check box to the left of the breakpoint.</span></span>  
  
## <a name="to-disable-all-breakpoints"></a><span data-ttu-id="ce762-123">Pour désactiver tous les points d'arrêt</span><span class="sxs-lookup"><span data-stu-id="ce762-123">To Disable All Breakpoints</span></span>  
 <span data-ttu-id="ce762-124">**To disable all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="ce762-124">**To disable all breakpoints**</span></span>  
  
 <span data-ttu-id="ce762-125">Vous pouvez désactiver tous les points d'arrêt de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce762-125">You can disable all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="ce762-126">Dans le menu **Déboguer** , cliquez sur **Désactiver tous les points d'arrêt**.</span><span class="sxs-lookup"><span data-stu-id="ce762-126">On the **Debug** menu, click **Disable All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="ce762-127">Dans la barre d'outils de la fenêtre **Points d'arrêt** , cliquez sur le bouton **Désactiver tous les points d'arrêt** .</span><span class="sxs-lookup"><span data-stu-id="ce762-127">On the toolbar of the **Breakpoints** window, click the **Disable All Breakpoints** button.</span></span>  
  
## <a name="to-enable-a-single-breakpoint"></a><span data-ttu-id="ce762-128">Pour activer un point d'arrêt</span><span class="sxs-lookup"><span data-stu-id="ce762-128">To Enable a Single Breakpoint</span></span>  
 <span data-ttu-id="ce762-129">**To enable a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="ce762-129">**To enable a single breakpoint**</span></span>  
  
 <span data-ttu-id="ce762-130">Vous pouvez activer un point d'arrêt de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce762-130">You can enable a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="ce762-131">Dans la fenêtre de l’éditeur de requête, cliquez avec le bouton droit sur le point d’arrêt, puis cliquez sur **Activer le point d’arrêt**.</span><span class="sxs-lookup"><span data-stu-id="ce762-131">In the Query Editor window, right-click the breakpoint, and then click **Enable Breakpoint**.</span></span>  
  
-   <span data-ttu-id="ce762-132">Dans la fenêtre Points d'arrêt, activez la case à cocher à gauche du point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="ce762-132">In the Breakpoints window, click the box to the left of the breakpoint.</span></span>  
  
## <a name="to-enable-all-breakpoints"></a><span data-ttu-id="ce762-133">Pour activer tous les points d'arrêt</span><span class="sxs-lookup"><span data-stu-id="ce762-133">To Enable All Breakpoints</span></span>  
 <span data-ttu-id="ce762-134">**To enable all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="ce762-134">**To enable all breakpoints**</span></span>  
  
 <span data-ttu-id="ce762-135">Vous pouvez activer tous les points d'arrêt de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce762-135">You can enable all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="ce762-136">Dans le menu **Déboguer** , cliquez sur **Activer tous les points d'arrêt**.</span><span class="sxs-lookup"><span data-stu-id="ce762-136">On the **Debug** menu, click **Enable All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="ce762-137">Dans la barre d'outils de la fenêtre **Points d'arrêt** , cliquez sur le bouton **Activer tous les points d'arrêt** .</span><span class="sxs-lookup"><span data-stu-id="ce762-137">On the toolbar of the **Breakpoints** window, click the **Enable All Breakpoints** button.</span></span>  
  
## <a name="to-delete-a-single-breakpoint"></a><span data-ttu-id="ce762-138">Pour supprimer un point d'arrêt</span><span class="sxs-lookup"><span data-stu-id="ce762-138">To Delete a Single Breakpoint</span></span>  
 <span data-ttu-id="ce762-139">**To delete a single breakpoint**</span><span class="sxs-lookup"><span data-stu-id="ce762-139">**To delete a single breakpoint**</span></span>  
  
 <span data-ttu-id="ce762-140">Vous pouvez supprimer un point d'arrêt de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce762-140">You can delete a single breakpoint in one of the following ways:</span></span>  
  
-   <span data-ttu-id="ce762-141">Dans la fenêtre de l’éditeur de requête, cliquez avec le bouton droit sur le point d’arrêt, puis cliquez sur **Supprimer le point d’arrêt**.</span><span class="sxs-lookup"><span data-stu-id="ce762-141">In the Query Editor window, right-click the breakpoint, and then click **Delete Breakpoint**.</span></span>  
  
-   <span data-ttu-id="ce762-142">Dans la fenêtre Points d’arrêt, cliquez avec le bouton droit sur le point d’arrêt, puis cliquez sur **Supprimer** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="ce762-142">In the Breakpoints window, right-click the breakpoint, and then click **Delete** on the shortcut menu.</span></span>  
  
-   <span data-ttu-id="ce762-143">Dans la fenêtre Points d'arrêt, sélectionnez le point d'arrêt, puis appuyez sur Suppr.</span><span class="sxs-lookup"><span data-stu-id="ce762-143">In the Breakpoints window, select the breakpoint, and then press DELETE.</span></span>  
  
## <a name="to-delete-all-breakpoints"></a><span data-ttu-id="ce762-144">Pour supprimer tous les points d'arrêt</span><span class="sxs-lookup"><span data-stu-id="ce762-144">To Delete All Breakpoints</span></span>  
 <span data-ttu-id="ce762-145">**To delete all breakpoints**</span><span class="sxs-lookup"><span data-stu-id="ce762-145">**To delete all breakpoints**</span></span>  
  
 <span data-ttu-id="ce762-146">Vous pouvez supprimer tous les points d'arrêt de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce762-146">You can delete all breakpoints in one of the following ways:</span></span>  
  
-   <span data-ttu-id="ce762-147">Dans le menu **Déboguer** , cliquez sur **Supprimer tous les points d'arrêt**.</span><span class="sxs-lookup"><span data-stu-id="ce762-147">On the **Debug** menu, cllick **Delete All Breakpoints**.</span></span>  
  
-   <span data-ttu-id="ce762-148">Dans la barre d'outils de la fenêtre **Points d'arrêt** , cliquez sur le bouton **Supprimer tous les points d'arrêt** .</span><span class="sxs-lookup"><span data-stu-id="ce762-148">On the toolbar of the **Breakpoints** window, click the **Delete All Breakpoints** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce762-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ce762-149">See Also</span></span>  
 [<span data-ttu-id="ce762-150">Basculer un point d’arrêt</span><span class="sxs-lookup"><span data-stu-id="ce762-150">Toggle a Breakpoint</span></span>](../spatial/point.md)  
  
  
