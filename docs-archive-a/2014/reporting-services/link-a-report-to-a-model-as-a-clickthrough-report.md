---
title: Lier un rapport à un modèle en tant que rapport généré interactif | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- customizing clickthrough reports
- clickthrough reports, customizing
- clickthrough reports, templates
ms.assetid: 3af42de3-67ef-41c2-bc8a-7045baec6f63
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cb84f8036dbe5a1694628144f0b948452261ca75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601951"
---
# <a name="link-a-report-to-a-model-as-a-clickthrough-report"></a><span data-ttu-id="8fcfe-102">Lier un rapport à un modèle en tant que rapport généré interactif</span><span class="sxs-lookup"><span data-stu-id="8fcfe-102">Link a Report to a Model as a Clickthrough Report</span></span>
  <span data-ttu-id="8fcfe-103">Plutôt que d'utiliser les modèles de rapports générés interactifs à l'aide de clics, vous pouvez créer un rapport de Générateur de rapports et le lier à une entité spécifique dans le modèle de rapport.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-103">Instead of using the default clickthrough report templates, you can create a Report Builder report and then link it to a specific entity in the report model.</span></span> <span data-ttu-id="8fcfe-104">Lorsque la personne qui affiche le rapport clique sur des données interactives dans le rapport principal, ce rapport s'affiche sous forme de rapport consultable à l'aide de clics.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-104">When the person viewing the report clicks the interactive data in the main report, this report is displayed as a clickthrough report.</span></span> <span data-ttu-id="8fcfe-105">Pour lier un rapport à une entité, utilisez le Gestionnaire de rapports [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8fcfe-105">To link a report to an entity, use [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8fcfe-106">L'entité principale, ou de base, qui est utilisée dans le rapport doit être celle à laquelle le rapport est lié.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-106">The primary, or base, entity that is used in the report must to be the same entity to which the report is linked.</span></span>  
  
### <a name="to-start-report-manager-from-a-browser"></a><span data-ttu-id="8fcfe-107">Pour démarrer le Gestionnaire de rapports à partir du navigateur</span><span class="sxs-lookup"><span data-stu-id="8fcfe-107">To start Report Manager from a browser</span></span>  
  
1.  <span data-ttu-id="8fcfe-108">Ouvrez [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer 6.0 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-108">Open [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer 6.0 or later.</span></span>  
  
2.  <span data-ttu-id="8fcfe-109">Dans la barre d'adresses du navigateur Web, tapez l'URL du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-109">In the address bar of the Web browser, type the Report Manager URL.</span></span> <span data-ttu-id="8fcfe-110">Par défaut, l’URL est http:// \<*ComputerName*> /reports.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-110">By default, the URL is http://\<*ComputerName*>/reports.</span></span>  
  
### <a name="to-create-a-customized-clickthrough-report"></a><span data-ttu-id="8fcfe-111">Pour créer un rapport consultable à l'aide de clics</span><span class="sxs-lookup"><span data-stu-id="8fcfe-111">To create a customized clickthrough report</span></span>  
  
1.  <span data-ttu-id="8fcfe-112">Accédez au modèle de rapport auquel vous souhaitez ajouter le rapport généré interactif personnalisé.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-112">Navigate to the report model to which you want to add the customized clickthrough report.</span></span>  
  
2.  <span data-ttu-id="8fcfe-113">Double-cliquez sur le modèle de rapport.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-113">Double-click the report model.</span></span>  
  
3.  <span data-ttu-id="8fcfe-114">Cliquez sur **Rapports générés interactifs**.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-114">Click **Clickthrough**.</span></span>  
  
4.  <span data-ttu-id="8fcfe-115">Sélectionnez l'entité à laquelle vous souhaitez attacher le rapport généré interactif personnalisé.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-115">Select the entity to which you want to attach the customized clickthrough report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8fcfe-116">Cette entité doit être la même que l'entité de base du rapport généré interactif personnalisé.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-116">This entity must be the same as the base entity of the customized clickthrough report.</span></span>  
  
5.  <span data-ttu-id="8fcfe-117">Pour afficher le rapport personnalisé après avoir cliqué sur une seule instance de l'entité sélectionnée, cliquez sur le bouton **Parcourir** du rapport à une seule instance.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-117">To display the customized report when a single instance of the selected entity is clicked, click the Single instance report **Browse** button.</span></span>  
  
     <span data-ttu-id="8fcfe-118">-ou-</span><span class="sxs-lookup"><span data-stu-id="8fcfe-118">-or-</span></span>  
  
     <span data-ttu-id="8fcfe-119">Pour afficher le rapport personnalisé après avoir cliqué sur plusieurs instances de l'entité sélectionnée, cliquez sur le bouton **Parcourir** du rapport à plusieurs instances.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-119">To display the customized report when a multiple instance of the selected entity is clicked, click the Multiple instance report **Browse** button.</span></span>  
  
6.  <span data-ttu-id="8fcfe-120">Sélectionnez le rapport, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-120">Select the report and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="8fcfe-121">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="8fcfe-121">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fcfe-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8fcfe-122">See Also</span></span>  
 [<span data-ttu-id="8fcfe-123">Rapports générés interactifs &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8fcfe-123">Clickthrough Reports &#40;SSRS&#41;</span></span>](reports/clickthrough-reports-ssrs.md)  
  
  
