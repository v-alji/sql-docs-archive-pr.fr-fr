---
title: Sources de données d’objets existants (Assistant source de données) (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourcewizard.specifyobject.f1
ms.assetid: e6ef6dea-9db8-45c4-8959-f9febd7caf7b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 621c938f4902c95dee1e2fcccb0f292597a565f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702113"
---
# <a name="data-sources-from-existing-objects-data-source-wizard-analysis-services"></a><span data-ttu-id="d1b93-102">Sources de données d'objets existants (Assistant Source de données) (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="d1b93-102">Data sources from existing objects (Data Source Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="d1b93-103">Utilisez la page **Sources de données d'objets existants** pour spécifier une source de données ou un projet existant sur laquelle (ou lequel) baser la nouvelle source de données.</span><span class="sxs-lookup"><span data-stu-id="d1b93-103">Use the **Data sources from existing objects** page to specify an existing data source or project on which to base the new data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d1b93-104">Options</span><span class="sxs-lookup"><span data-stu-id="d1b93-104">Options</span></span>  
 <span data-ttu-id="d1b93-105">**Créer une source de données basée sur une source de données existante dans votre solution**</span><span class="sxs-lookup"><span data-stu-id="d1b93-105">**Create a data source based on an existing data source in your solution**</span></span>  
 <span data-ttu-id="d1b93-106">Choisissez de baser la nouvelle source de données sur une source de données existant dans la solution.</span><span class="sxs-lookup"><span data-stu-id="d1b93-106">Select to base the new data source on an existing data source in the solution.</span></span> <span data-ttu-id="d1b93-107">Lors de la construction, de l'actualisation ou du déploiement d'un projet qui utilise une nouvelle source de données, celle-ci adopte les paramètres de la source de données que vous spécifiez lorsque vous sélectionnez cette option.</span><span class="sxs-lookup"><span data-stu-id="d1b93-107">When a project that uses the new data source is built, refreshed, or deployed, the new data source acquires the settings from the data source you specify when you select this option.</span></span>  
  
 <span data-ttu-id="d1b93-108">**Source de données**</span><span class="sxs-lookup"><span data-stu-id="d1b93-108">**Data source**</span></span>  
 <span data-ttu-id="d1b93-109">Dans la liste des sources de données regroupées par projet, sélectionnez une source de données sur laquelle vous voulez baser la nouvelle source de données.</span><span class="sxs-lookup"><span data-stu-id="d1b93-109">Select a data source on which you want to base the new data source from the list of data sources, which is grouped by project.</span></span>  
  
 <span data-ttu-id="d1b93-110">**Créer une source de données basée sur un projet Analysis Services**</span><span class="sxs-lookup"><span data-stu-id="d1b93-110">**Create a data source based on an Analysis Services project**</span></span>  
 <span data-ttu-id="d1b93-111">Sélectionnez cette option pour créer une nouvelle source de données qui référence un autre [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projet dans la solution actuelle.</span><span class="sxs-lookup"><span data-stu-id="d1b93-111">Select to create a new data source that references another [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project in the current solution.</span></span> <span data-ttu-id="d1b93-112">La nouvelle source de données adopte les paramètres des propriétés `TargetServer` et `TargetDatabase` du projet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d1b93-112">The new data source acquires settings from the `TargetServer` and `TargetDatabase` properties of the selected project.</span></span> <span data-ttu-id="d1b93-113">Lors de la construction, de l'actualisation ou du déploiement d'un projet qui utilise une nouvelle source de données, celle-ci adopte les paramètres de la source de données que vous spécifiez lorsque vous sélectionnez cette option.</span><span class="sxs-lookup"><span data-stu-id="d1b93-113">When a project that uses the new data source is built, refreshed, or deployed, the new data source acquires settings from the data source you specify when you select this option.</span></span>  
  
 <span data-ttu-id="d1b93-114">**Projet**</span><span class="sxs-lookup"><span data-stu-id="d1b93-114">**Project**</span></span>  
 <span data-ttu-id="d1b93-115">Sélectionnez le projet que vous voulez référencer dans la nouvelle source de données.</span><span class="sxs-lookup"><span data-stu-id="d1b93-115">Select the project that you want to reference in the new data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1b93-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d1b93-116">See Also</span></span>  
 <span data-ttu-id="d1b93-117">[Aide (F1) de l’Assistant source de données &#40;Analysis Services&#41;](data-source-wizard-f1-help-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="d1b93-117">[Data Source Wizard F1 Help &#40;Analysis Services&#41;](data-source-wizard-f1-help-analysis-services.md) </span></span>  
 <span data-ttu-id="d1b93-118">[Sources de données dans les modèles multidimensionnels](multidimensional-models/data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="d1b93-118">[Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="d1b93-119">Sources de données prises en charge &#40;SSAS multidimensionnel&#41;</span><span class="sxs-lookup"><span data-stu-id="d1b93-119">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/supported-data-sources-ssas-multidimensional.md)  
  
  
