---
title: Aperçu, vue | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.previewview.f1
helpviewer_keywords:
- Preview view [Reporting Services]
ms.assetid: 108255d1-5be8-47c1-80f3-1f2a055e4d02
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1ff7c59c3ac5143d4f4103edea1a5ee309046547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700698"
---
# <a name="preview-view"></a><span data-ttu-id="514b1-102">Vue Aperçu</span><span class="sxs-lookup"><span data-stu-id="514b1-102">Preview View</span></span>
  <span data-ttu-id="514b1-103">Utilisez la vue **Aperçu** pour afficher le rapport rendu.</span><span class="sxs-lookup"><span data-stu-id="514b1-103">Use **Preview** view to display the rendered report.</span></span> <span data-ttu-id="514b1-104">Lors de l'aperçu d'un rapport, le Générateur de rapports exécute le rapport localement et l'affiche dans la vue Aperçu.</span><span class="sxs-lookup"><span data-stu-id="514b1-104">When a report is previewed, Report Designer runs the report locally and displays it in the Preview view.</span></span> <span data-ttu-id="514b1-105">Dans le mode Aperçu, le rapport est traité dans sa totalité.</span><span class="sxs-lookup"><span data-stu-id="514b1-105">In preview mode, the report is processed in full.</span></span> <span data-ttu-id="514b1-106">Si le rapport contient une requête complexe ou une grande quantité de données, l'aperçu peut prendre plusieurs minutes à apparaître la première fois que vous l'affichez.</span><span class="sxs-lookup"><span data-stu-id="514b1-106">If the report has a complex query or has a large amount of data, preview might take several minutes to complete the first time you view it.</span></span> <span data-ttu-id="514b1-107">Pour les modifications ultérieures apportées exclusivement à la mise en forme du rapport, l'aperçu utilise les données mises en cache.</span><span class="sxs-lookup"><span data-stu-id="514b1-107">For subsequent changes that affect only the format of the report, preview uses cached data.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="514b1-108">Lorsque [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] est exécuté en tant que RemoteApp, les rapports ne peuvent pas être affichés dans la vue **Aperçu** de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="514b1-108">When [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] is run as a RemoteApp, reports cannot be displayed in **Preview** view in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="514b1-109">Les programmes RemoteApp sont des programmes auxquels les services de bureau à distance peuvent accéder à distance.</span><span class="sxs-lookup"><span data-stu-id="514b1-109">RemoteApp programs are programs that are accessed remotely through Remote Desktop Services.</span></span> <span data-ttu-id="514b1-110">Pour plus d'informations, consultez le [Guide pas à pas de RemoteApp Terminal Services](https://technet.microsoft.com/library/cc730673\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="514b1-110">For more information, see [TS RemoteApp Step-by-Step Guide](https://technet.microsoft.com/library/cc730673\(WS.10\).aspx).</span></span>  
  
## <a name="options"></a><span data-ttu-id="514b1-111">Options</span><span class="sxs-lookup"><span data-stu-id="514b1-111">Options</span></span>  
 <span data-ttu-id="514b1-112">Utilisez la barre d'outils pour gérer les fonctions d'aperçu.</span><span class="sxs-lookup"><span data-stu-id="514b1-112">Use the toolbar to manage preview functions.</span></span>  
  
 <span data-ttu-id="514b1-113">**Afficher ou masquer le plan du document**</span><span class="sxs-lookup"><span data-stu-id="514b1-113">**Show or Hide Document Map**</span></span>  
 <span data-ttu-id="514b1-114">Choisissez cette option pour afficher ou masquer le plan du document s'il existe.</span><span class="sxs-lookup"><span data-stu-id="514b1-114">Choose this option to show or hide the document map if one exists.</span></span>  
  
 <span data-ttu-id="514b1-115">**Afficher ou masquer la zone de paramètres**</span><span class="sxs-lookup"><span data-stu-id="514b1-115">**Show or Hide Parameter Area**</span></span>  
 <span data-ttu-id="514b1-116">Choisissez cette option pour afficher ou masquer les zones de paramètres des rapports contenant des paramètres.</span><span class="sxs-lookup"><span data-stu-id="514b1-116">Choose this option to show or hide the parameters boxes for reports with parameters.</span></span>  
  
 <span data-ttu-id="514b1-117">**Première page**</span><span class="sxs-lookup"><span data-stu-id="514b1-117">**First Page**</span></span>  
 <span data-ttu-id="514b1-118">Choisissez cette option pour atteindre la première page du rapport.</span><span class="sxs-lookup"><span data-stu-id="514b1-118">Choose this option to go to the first page of the report.</span></span>  
  
 <span data-ttu-id="514b1-119">**Page précédente**</span><span class="sxs-lookup"><span data-stu-id="514b1-119">**Previous Page**</span></span>  
 <span data-ttu-id="514b1-120">Choisissez cette option pour atteindre la page précédente du rapport.</span><span class="sxs-lookup"><span data-stu-id="514b1-120">Choose this option to go to the previous page of the report.</span></span>  
  
 <span data-ttu-id="514b1-121">**Page active**</span><span class="sxs-lookup"><span data-stu-id="514b1-121">**Current Page**</span></span>  
 <span data-ttu-id="514b1-122">Affiche la page active du rapport.</span><span class="sxs-lookup"><span data-stu-id="514b1-122">Displays the current page of the report.</span></span>  
  
 <span data-ttu-id="514b1-123">**Nombre total de pages**</span><span class="sxs-lookup"><span data-stu-id="514b1-123">**Total Pages**</span></span>  
 <span data-ttu-id="514b1-124">Affiche le nombre total de pages du rapport.</span><span class="sxs-lookup"><span data-stu-id="514b1-124">Displays the total number of pages in the report.</span></span>  
  
 <span data-ttu-id="514b1-125">**Page suivante**</span><span class="sxs-lookup"><span data-stu-id="514b1-125">**Next Page**</span></span>  
 <span data-ttu-id="514b1-126">Choisissez cette option pour atteindre la page suivante du rapport.</span><span class="sxs-lookup"><span data-stu-id="514b1-126">Choose this option to go to the next page of the report.</span></span>  
  
 <span data-ttu-id="514b1-127">**Dernière page**</span><span class="sxs-lookup"><span data-stu-id="514b1-127">**Last Page**</span></span>  
 <span data-ttu-id="514b1-128">Choisissez cette option pour atteindre la dernière page du rapport.</span><span class="sxs-lookup"><span data-stu-id="514b1-128">Choose this option to go to the last page of the report.</span></span>  
  
 <span data-ttu-id="514b1-129">**Revenir au rapport parent**</span><span class="sxs-lookup"><span data-stu-id="514b1-129">**Back to Parent Report**</span></span>  
 <span data-ttu-id="514b1-130">Choisissez cette option pour revenir au rapport parent.</span><span class="sxs-lookup"><span data-stu-id="514b1-130">Choose this option to go to the parent report.</span></span> <span data-ttu-id="514b1-131">Cette option sert à parcourir les rapports d'extraction.</span><span class="sxs-lookup"><span data-stu-id="514b1-131">This option is used to navigate drillthrough reports.</span></span>  
  
 <span data-ttu-id="514b1-132">**Arrêter le rendu**</span><span class="sxs-lookup"><span data-stu-id="514b1-132">**Stop Rendering**</span></span>  
 <span data-ttu-id="514b1-133">Choisissez cette option pour arrêter le processus de rendu.</span><span class="sxs-lookup"><span data-stu-id="514b1-133">Choose this option to stop the rendering process.</span></span>  
  
 <span data-ttu-id="514b1-134">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="514b1-134">**Refresh**</span></span>  
 <span data-ttu-id="514b1-135">Choisissez cette option pour actualiser le cache des données et exécutez de nouveau le rapport.</span><span class="sxs-lookup"><span data-stu-id="514b1-135">Choose this option to refresh the data cache and run the report again.</span></span>  
  
 <span data-ttu-id="514b1-136">**Imprimer**</span><span class="sxs-lookup"><span data-stu-id="514b1-136">**Print**</span></span>  
 <span data-ttu-id="514b1-137">Choisissez cette option pour imprimer le rapport.</span><span class="sxs-lookup"><span data-stu-id="514b1-137">Choose this option to print the report.</span></span>  
  
 <span data-ttu-id="514b1-138">**Page**</span><span class="sxs-lookup"><span data-stu-id="514b1-138">**Print Layout**</span></span>  
 <span data-ttu-id="514b1-139">Choisissez cette option pour basculer entre l'aperçu du rapport et l'affichage du rapport tel qu'il apparaîtra sur la page imprimée.</span><span class="sxs-lookup"><span data-stu-id="514b1-139">Choose this option to toggle between the preview report and the view of the report as it will appear on the printed page.</span></span>  
  
 <span data-ttu-id="514b1-140">**Mise en page**</span><span class="sxs-lookup"><span data-stu-id="514b1-140">**Page Setup**</span></span>  
 <span data-ttu-id="514b1-141">Choisissez cette option pour modifier aisément les propriétés de la page et de l'impression.</span><span class="sxs-lookup"><span data-stu-id="514b1-141">Choose this option to conveniently change page and print properties.</span></span> <span data-ttu-id="514b1-142">Utilisez l'option Page pour visualiser les modifications avant de procéder à l'impression.</span><span class="sxs-lookup"><span data-stu-id="514b1-142">Use Print Layout to view changes before printing.</span></span>  
  
 <span data-ttu-id="514b1-143">**Export**</span><span class="sxs-lookup"><span data-stu-id="514b1-143">**Export**</span></span>  
 <span data-ttu-id="514b1-144">Choisissez cette option pour exporter le rapport rendu dans un format spécifique.</span><span class="sxs-lookup"><span data-stu-id="514b1-144">Choose this option to export the rendered report in a specific format.</span></span>  
  
 <span data-ttu-id="514b1-145">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="514b1-145">**Zoom**</span></span>  
 <span data-ttu-id="514b1-146">Sélectionnez un facteur de zoom avant ou arrière pour l'affichage du rapport.</span><span class="sxs-lookup"><span data-stu-id="514b1-146">Select a zoom factor to zoom in or out on the report.</span></span>  
  
 <span data-ttu-id="514b1-147">**Texte recherché**</span><span class="sxs-lookup"><span data-stu-id="514b1-147">**Search Text**</span></span>  
 <span data-ttu-id="514b1-148">Tapez un fragment de texte à rechercher dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="514b1-148">Type text to search for a match within the report.</span></span> <span data-ttu-id="514b1-149">Vous ne pouvez pas utiliser d'opérateurs de recherche.</span><span class="sxs-lookup"><span data-stu-id="514b1-149">You cannot use search operators.</span></span> <span data-ttu-id="514b1-150">Cliquez sur **Rechercher** pour rechercher la première instance.</span><span class="sxs-lookup"><span data-stu-id="514b1-150">Click **Find** to search for the first instance.</span></span>  
  
 <span data-ttu-id="514b1-151">**Trouver**</span><span class="sxs-lookup"><span data-stu-id="514b1-151">**Find**</span></span>  
 <span data-ttu-id="514b1-152">Choisissez cette option pour commencer la recherche du texte dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="514b1-152">Choose this option to begin searching the report for the search text.</span></span>  
  
 <span data-ttu-id="514b1-153">**Suivant**</span><span class="sxs-lookup"><span data-stu-id="514b1-153">**Find Next**</span></span>  
 <span data-ttu-id="514b1-154">Choisissez cette option pour rechercher l'instance suivante du texte recherché.</span><span class="sxs-lookup"><span data-stu-id="514b1-154">Choose this option to search for the next instance of the search text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="514b1-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="514b1-155">See Also</span></span>  
 <span data-ttu-id="514b1-156">[Aperçu des rapports](../reports/previewing-reports.md) </span><span class="sxs-lookup"><span data-stu-id="514b1-156">[Previewing Reports](../reports/previewing-reports.md) </span></span>  
 [<span data-ttu-id="514b1-157">Aide sur le Concepteur de rapports via la touche F1</span><span class="sxs-lookup"><span data-stu-id="514b1-157">Report Designer F1 Help</span></span>](report-designer-f1-help.md)  
  
  
