---
title: Impossible de charger le fichier ou l’assembly &#39;Microsoft. AnalysisServices. SharePoint. Integration&#39; | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6e350b67-5e18-4b90-8fb7-a0109cbb27b7
author: minewiskan
ms.author: owend
ms.openlocfilehash: b7ba75bdbd8e25f98d11d822c22fa7881352ad88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612540"
---
# <a name="could-not-load-file-or-assembly-39microsoftanalysisservicessharepointintegration39"></a><span data-ttu-id="cb845-102">Impossible de charger le fichier ou l’assembly &#39;Microsoft. AnalysisServices. SharePoint. Integration&#39;</span><span class="sxs-lookup"><span data-stu-id="cb845-102">Could not load file or assembly &#39;Microsoft.AnalysisServices.SharePoint.Integration&#39;</span></span>
  <span data-ttu-id="cb845-103">Dans les environnements SharePoint 2010 qui disposent de PowerPivot pour SharePoint, cette erreur se produira si la solution au niveau de l'application pour PowerPivot n'a pas été déployée correctement.</span><span class="sxs-lookup"><span data-stu-id="cb845-103">In SharePoint 2010 environments that have PowerPivot for SharePoint, this error will occur if the application-level solution for PowerPivot did not deploy correctly.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cb845-104">Détails</span><span class="sxs-lookup"><span data-stu-id="cb845-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb845-105">S’applique à</span><span class="sxs-lookup"><span data-stu-id="cb845-105">Applies to</span></span>|<span data-ttu-id="cb845-106">PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="cb845-106">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="cb845-107">Version du produit</span><span class="sxs-lookup"><span data-stu-id="cb845-107">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="cb845-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb845-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="cb845-109">Cause</span><span class="sxs-lookup"><span data-stu-id="cb845-109">Cause</span></span>|<span data-ttu-id="cb845-110">La solution Powerpivotwebapp n'est pas déployée ou n'a pas été déployée correctement.</span><span class="sxs-lookup"><span data-stu-id="cb845-110">Powerpivotwebapp solution is not deployed or did not deploy correctly.</span></span>|  
|<span data-ttu-id="cb845-111">Texte du message</span><span class="sxs-lookup"><span data-stu-id="cb845-111">Message Text</span></span>|<span data-ttu-id="cb845-112">Impossible de charger le fichier ou l'assembly 'Microsoft.AnalysisServices.SharePoint.Integration'</span><span class="sxs-lookup"><span data-stu-id="cb845-112">Could not load file or assembly 'Microsoft.AnalysisServices.SharePoint.Integration'</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cb845-113">Explication</span><span class="sxs-lookup"><span data-stu-id="cb845-113">Explanation</span></span>  
 <span data-ttu-id="cb845-114">PowerPivot pour SharePoint utilise des packages de solution pour déployer ses fonctionnalités sur un serveur SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cb845-114">PowerPivot for SharePoint uses solution packages to deploy its features on a SharePoint server.</span></span> <span data-ttu-id="cb845-115">L'une des solutions n'est pas déployée correctement.</span><span class="sxs-lookup"><span data-stu-id="cb845-115">One of the solutions is not deployed correctly.</span></span> <span data-ttu-id="cb845-116">Par conséquent, cette erreur s'affiche chaque fois que vous essayez d'ouvrir la Galerie PowerPivot ou d'autres pages d'application PowerPivot sur un site SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cb845-116">As a result, this error appears whenever you try to open PowerPivot Gallery or other PowerPivot application pages on a SharePoint site.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cb845-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="cb845-117">User Action</span></span>  
 <span data-ttu-id="cb845-118">Déployez le package de solution.</span><span class="sxs-lookup"><span data-stu-id="cb845-118">Deploy the solution package.</span></span>  
  
1.  <span data-ttu-id="cb845-119">Dans l'Administration centrale, sous Paramètres système, cliquez sur **Gérer les solutions de la batterie**.</span><span class="sxs-lookup"><span data-stu-id="cb845-119">In Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="cb845-120">Cliquez sur **Powerpivotwebapp**.</span><span class="sxs-lookup"><span data-stu-id="cb845-120">Click **Powerpivotwebapp**.</span></span>  
  
3.  <span data-ttu-id="cb845-121">Cliquez sur **Déployer la solution**.</span><span class="sxs-lookup"><span data-stu-id="cb845-121">Click **Deploy Solution**.</span></span>  
  
4.  <span data-ttu-id="cb845-122">Choisissez l'application Web pour laquelle cette erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="cb845-122">Choose the web application for which this error is occurring.</span></span> <span data-ttu-id="cb845-123">S'il y a plusieurs applications Web, redéployez la solution pour chacune d'entre elles.</span><span class="sxs-lookup"><span data-stu-id="cb845-123">If there is more than one web application, redeploy the solution for all of hem.</span></span>  
  
5.  <span data-ttu-id="cb845-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb845-124">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb845-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cb845-125">See Also</span></span>  
 [<span data-ttu-id="cb845-126">Déployer des solutions PowerPivot sur SharePoint</span><span class="sxs-lookup"><span data-stu-id="cb845-126">Deploy PowerPivot Solutions to SharePoint</span></span>](deploy-power-pivot-solutions-to-sharepoint.md)  
  
  
