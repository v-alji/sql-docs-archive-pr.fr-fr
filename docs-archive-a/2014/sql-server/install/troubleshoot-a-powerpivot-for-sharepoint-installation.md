---
title: Résoudre les problèmes d’une installation PowerPivot pour SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 97bc2ce7-af04-4372-ad79-c96b8c3417ab
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3adc27132d976288c14ac702baae0b842e8aef0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604899"
---
# <a name="troubleshoot-a-powerpivot-for-sharepoint-installation"></a><span data-ttu-id="e8312-102">Dépanner une installation PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="e8312-102">Troubleshoot a PowerPivot for SharePoint Installation</span></span>
  <span data-ttu-id="e8312-103">Si vous obtenez des erreurs au lieu des pages et fonctionnalités attendues, procédez comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e8312-103">If you get errors instead of the pages and features you expect, do the following.</span></span>  
  
-   <span data-ttu-id="e8312-104">Lisez les notes de publication pour SharePoint et [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] pour prendre connaissance des solutions de contournement pour les problèmes d'installation connus.</span><span class="sxs-lookup"><span data-stu-id="e8312-104">Review release notes for both SharePoint and [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to get workarounds for known installation problems.</span></span> <span data-ttu-id="e8312-105">Les notes de publication sont fournies avec le support d'installation ou sur le site Microsoft à partir duquel vous avez téléchargé le logiciel.</span><span class="sxs-lookup"><span data-stu-id="e8312-105">Release notes are provided with the installation media or on the Microsoft site from which you downloaded the software.</span></span>  
  
    -   <span data-ttu-id="e8312-106">[Notes de publication de SQL Server 2014](https://technet.microsoft.com/library/dn169381\(v=sql.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="e8312-106">[SQL Server 2014 Release Notes](https://technet.microsoft.com/library/dn169381\(v=sql.15\).aspx).</span></span>  
  
-   <span data-ttu-id="e8312-107">Consultez la rubrique wiki Technet, [Dépannage des installations de PowerPivot (et autres compléments)](https://social.technet.microsoft.com/wiki/contents/articles/13737.troubleshooting-installations-of-powerpivot-and-other-add-ins.aspx).</span><span class="sxs-lookup"><span data-stu-id="e8312-107">See the Technet wiki topic, [Troubleshooting Installations of PowerPivot (and other add-ins)](https://social.technet.microsoft.com/wiki/contents/articles/13737.troubleshooting-installations-of-powerpivot-and-other-add-ins.aspx).</span></span>  
  
## <a name="issues"></a><span data-ttu-id="e8312-108">Problèmes</span><span class="sxs-lookup"><span data-stu-id="e8312-108">Issues</span></span>  
  
### <a name="powerpivot-gallery-thumbnail-images-show-as-a-red-x"></a><span data-ttu-id="e8312-109">Les images miniatures de la Galerie PowerPivot s'affichent sous la forme d'une croix (X) rouge</span><span class="sxs-lookup"><span data-stu-id="e8312-109">PowerPivot Gallery Thumbnail images show as a red X</span></span>  
 <span data-ttu-id="e8312-110">L'une des causes possibles est que la **Fonctionnalité d'intégration PowerPivot pour les collections de sites** n'est pas active.</span><span class="sxs-lookup"><span data-stu-id="e8312-110">One Possible cause is the **PowerPivot features Integration for Site Collections** is not active.</span></span> <span data-ttu-id="e8312-111">Renseignez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e8312-111">Complete the following:</span></span>  
  
1.  <span data-ttu-id="e8312-112">Dans la bibliothèque Galerie PowerPivot, cliquez sur **paramètres du site** à partir de l’icône engrenage ![paramètres SharePoint](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "Paramètres SharePoint") ou de la liste d' **hébergement** .</span><span class="sxs-lookup"><span data-stu-id="e8312-112">In the PowerPivot Gallery library, click **Site Settings** from either the gear icon ![SharePoint Settings](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "SharePoint Settings") or the **Home** list.</span></span>  
  
2.  <span data-ttu-id="e8312-113">Dans la section **Administration de la collection de sites** , cliquez sur **Fonctionnalités de la collection de sites**.</span><span class="sxs-lookup"><span data-stu-id="e8312-113">In the **Site Collection Administration** section, click **Site Collection Features**.</span></span>  
  
3.  <span data-ttu-id="e8312-114">Cliquez sur **Fonctionnalités de la collection de sites**.</span><span class="sxs-lookup"><span data-stu-id="e8312-114">Click **Site Collection Features**.</span></span>  
  
4.  <span data-ttu-id="e8312-115">Vérifiez que **Fonctionnalité d'intégration PowerPivot pour les collections de sites** est **Activée**.</span><span class="sxs-lookup"><span data-stu-id="e8312-115">Verify **PowerPivot features Integration for Site Collections** is **Active**.</span></span>  
  
 <span data-ttu-id="e8312-116">Pour obtenir d’autres causes de ce problème, consultez [Galerie PowerPivot affiche des X rouges pour les icônes](https://support.microsoft.com/kb/2361559) ( https://support.microsoft.com/kb/2361559) .</span><span class="sxs-lookup"><span data-stu-id="e8312-116">For additional causes of this issue, see [PowerPivot Gallery shows Red X's for Icons](https://support.microsoft.com/kb/2361559) (https://support.microsoft.com/kb/2361559).</span></span>  
  
  
