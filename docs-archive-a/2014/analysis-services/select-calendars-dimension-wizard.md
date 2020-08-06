---
title: Sélectionner des calendriers (Assistant Dimension) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.serverSpecialCalendars.f1
ms.assetid: 6e28a020-2586-4b13-9333-b499fb1b33af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2048ee20dd91c942f01982d02f3265a6bad670dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610877"
---
# <a name="select-calendars-dimension-wizard"></a><span data-ttu-id="e338c-102">Sélectionner des calendriers (Assistant Dimension)</span><span class="sxs-lookup"><span data-stu-id="e338c-102">Select Calendars (Dimension Wizard)</span></span>
  <span data-ttu-id="e338c-103">La page **Sélectionner des calendriers** permet de créer des hiérarchies supplémentaires représentant les calendriers fiscaux, de rapports, de fabrication ou ISO (International Standards Organization) 8601 de la dimension de temps.</span><span class="sxs-lookup"><span data-stu-id="e338c-103">Use the **Select Calendars** page to create additional hierarchies representing fiscal, reporting, manufacturing, or International Standards Organization (ISO) 8601 calendars for the time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e338c-104">Cette page s’affiche uniquement si vous avez sélectionné **Dimension de temps du serveur** dans la page **Sélectionner le type de la dimension** ou **Construire la dimension sans utiliser de source de données** dans la page **Définition de dimension** et sélectionné **Dimension de temps** dans la page **Sélectionnez le type de la dimension** .</span><span class="sxs-lookup"><span data-stu-id="e338c-104">This page will appear only if you have selected **Server time dimension** on the **Select the Dimension Type** page, or if you selected **Build the dimension without using a data source** on the **Dimension Definition** page and selected **Time dimension** on the **Select the Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e338c-105">Options</span><span class="sxs-lookup"><span data-stu-id="e338c-105">Options</span></span>  
 <span data-ttu-id="e338c-106">**Calendrier fiscal**</span><span class="sxs-lookup"><span data-stu-id="e338c-106">**Fiscal calendar**</span></span>  
 <span data-ttu-id="e338c-107">Sélectionnez cette option pour créer une hiérarchie de temps en fonction d'un calendrier fiscal.</span><span class="sxs-lookup"><span data-stu-id="e338c-107">Select to create a time hierarchy based on a fiscal calendar.</span></span>  
  
 <span data-ttu-id="e338c-108">**Jour et mois de départ**</span><span class="sxs-lookup"><span data-stu-id="e338c-108">**Start day and month**</span></span>  
 <span data-ttu-id="e338c-109">Sélectionnez le jour et le mois de début du calendrier fiscal.</span><span class="sxs-lookup"><span data-stu-id="e338c-109">Select the day and month on which the fiscal calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e338c-110">Cette option est disponible uniquement quand **Calendrier fiscal** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e338c-110">This option is available only when **Fiscal calendar** is selected.</span></span>  
  
 <span data-ttu-id="e338c-111">**Convention de nom de calendrier fiscal**</span><span class="sxs-lookup"><span data-stu-id="e338c-111">**Fiscal calendar naming convention**</span></span>  
 <span data-ttu-id="e338c-112">Sélectionnez la convention de nom utilisée par le calendrier fiscal.</span><span class="sxs-lookup"><span data-stu-id="e338c-112">Select the naming convention used by the fiscal calendar.</span></span> <span data-ttu-id="e338c-113">Sélectionnez **Nom de l’année civile** ou **Nom de l’année civile + 1**.</span><span class="sxs-lookup"><span data-stu-id="e338c-113">Select either **Calendar year name** or **Calendar year name +1**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e338c-114">Cette option est disponible uniquement quand **Calendrier fiscal** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e338c-114">This option is available only when **Fiscal calendar** is selected.</span></span>  
  
 <span data-ttu-id="e338c-115">**Calendrier de rapports (ou du marketing)**</span><span class="sxs-lookup"><span data-stu-id="e338c-115">**Reporting (or marketing) calendar**</span></span>  
 <span data-ttu-id="e338c-116">Sélectionnez cette option pour créer une hiérarchie de temps en fonction d'un calendrier de rapports.</span><span class="sxs-lookup"><span data-stu-id="e338c-116">Select to create a time hierarchy based on a reporting calendar.</span></span>  
  
 <span data-ttu-id="e338c-117">**Semaine et mois de départ**</span><span class="sxs-lookup"><span data-stu-id="e338c-117">**Start week and month**</span></span>  
 <span data-ttu-id="e338c-118">Sélectionnez la semaine et le mois de début du calendrier de rapports.</span><span class="sxs-lookup"><span data-stu-id="e338c-118">Select the week and month on which the reporting calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e338c-119">Cette option est disponible uniquement quand **Calendrier rapports (ou marketing)** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e338c-119">This option is available when **Reporting (or marketing) calendar** is selected.</span></span>  
  
 <span data-ttu-id="e338c-120">**Modèle semaine du mois**</span><span class="sxs-lookup"><span data-stu-id="e338c-120">**Week by month pattern**</span></span>  
 <span data-ttu-id="e338c-121">Sélectionnez le modèle de semaine du mois utilisé par le calendrier des rapports.</span><span class="sxs-lookup"><span data-stu-id="e338c-121">Select the week by month pattern used by the reporting calendar.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e338c-122">Cette option est disponible uniquement quand **Calendrier rapports (ou marketing)** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e338c-122">This option is available when **Reporting (or marketing) calendar** is selected.</span></span>  
  
 <span data-ttu-id="e338c-123">Le tableau suivant répertorie les options disponibles pour le modèle de semaine du mois.</span><span class="sxs-lookup"><span data-stu-id="e338c-123">The following table lists the options available for the week by month pattern.</span></span>  
  
|<span data-ttu-id="e338c-124">Valeur</span><span class="sxs-lookup"><span data-stu-id="e338c-124">Value</span></span>|<span data-ttu-id="e338c-125">Description</span><span class="sxs-lookup"><span data-stu-id="e338c-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e338c-126">**Semaine 445**</span><span class="sxs-lookup"><span data-stu-id="e338c-126">**Week 445**</span></span>|<span data-ttu-id="e338c-127">Le premier mois du trimestre compte 4 semaines, le deuxième mois en compte 4, et le troisième mois en compte 5.</span><span class="sxs-lookup"><span data-stu-id="e338c-127">The first month in the quarter has 4 weeks, the second month in the quarter has 4 weeks, and the third month in the quarter has 5 weeks.</span></span>|  
|<span data-ttu-id="e338c-128">**Semaine 454**</span><span class="sxs-lookup"><span data-stu-id="e338c-128">**Week 454**</span></span>|<span data-ttu-id="e338c-129">Le premier mois du trimestre compte 4 semaines, le deuxième mois en compte 5, et le troisième mois en compte 4.</span><span class="sxs-lookup"><span data-stu-id="e338c-129">The first month in the quarter has 4 weeks, the second month in the quarter has 5 weeks, and the third month in the quarter has 4 weeks.</span></span>|  
|<span data-ttu-id="e338c-130">**Semaine 544**</span><span class="sxs-lookup"><span data-stu-id="e338c-130">**Week 544**</span></span>|<span data-ttu-id="e338c-131">Le premier mois du trimestre a 5 semaines, le deuxième mois du trimestre a 4 semaines et le troisième mois du trimestre a 4 semaines.</span><span class="sxs-lookup"><span data-stu-id="e338c-131">The first month in the quarter has 5 weeks, the second month in the quarter has 4 weeks, and the third month in the quarter has 4 weeks.</span></span>|  
  
 <span data-ttu-id="e338c-132">**Calendrier de fabrication**</span><span class="sxs-lookup"><span data-stu-id="e338c-132">**Manufacturing calendar**</span></span>  
 <span data-ttu-id="e338c-133">Sélectionnez cette option pour créer une hiérarchie de temps en fonction d'un calendrier de fabrication.</span><span class="sxs-lookup"><span data-stu-id="e338c-133">Select to create a time hierarchy based on a manufacturing calendar.</span></span>  
  
 <span data-ttu-id="e338c-134">**Semaine et mois de départ**</span><span class="sxs-lookup"><span data-stu-id="e338c-134">**Start week and month**</span></span>  
 <span data-ttu-id="e338c-135">Sélectionnez la semaine et le mois de début du calendrier de fabrication.</span><span class="sxs-lookup"><span data-stu-id="e338c-135">Select the week and month on which the manufacturing calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e338c-136">Cette option est disponible uniquement quand **Calendrier de fabrication** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e338c-136">This option is available when **Manufacturing calendar** is selected.</span></span>  
  
 <span data-ttu-id="e338c-137">**Trimestre avec des périodes supplémentaires**</span><span class="sxs-lookup"><span data-stu-id="e338c-137">**Quarter with extra periods**</span></span>  
 <span data-ttu-id="e338c-138">Sélectionnez ou tapez le trimestre qui doit contenir les périodes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="e338c-138">Select or type the quarter that will contain the extra periods.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e338c-139">Cette option est disponible uniquement quand **Calendrier de fabrication** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e338c-139">This option is available when **Manufacturing calendar** is selected.</span></span>  
  
 <span data-ttu-id="e338c-140">**Calendrier ISO 8601**</span><span class="sxs-lookup"><span data-stu-id="e338c-140">**ISO 8601 calendar**</span></span>  
 <span data-ttu-id="e338c-141">Sélectionnez cette option pour créer une hiérarchie en fonction du calendrier ISO 8601.</span><span class="sxs-lookup"><span data-stu-id="e338c-141">Select to create a hierarchy based on the ISO 8601 calendar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e338c-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e338c-142">See Also</span></span>  
 <span data-ttu-id="e338c-143">[Aide (F1) de l’Assistant Dimension](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="e338c-143">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="e338c-144">[Dimensions &#40;Analysis Services-données multidimensionnelles&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e338c-144">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="e338c-145">Dimensions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="e338c-145">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
