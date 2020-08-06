---
title: Définir des périodes (Assistant Dimension) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.timefrequency.f1
ms.assetid: 6bda6b7e-d306-4e68-9acb-84de8f44d1b4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 88b69eaa265b7a98f7d32063b602897d02016fa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613684"
---
# <a name="define-time-periods-dimension-wizard"></a><span data-ttu-id="0dfe1-102">Définir des périodes (Assistant Dimension)</span><span class="sxs-lookup"><span data-stu-id="0dfe1-102">Define Time Periods (Dimension Wizard)</span></span>
  <span data-ttu-id="0dfe1-103">Utilisez la page **Définir des périodes** pour définir les informations d'année civile et les fréquences de temps à inclure dans la dimension de temps ou la dimension de temps du serveur.</span><span class="sxs-lookup"><span data-stu-id="0dfe1-103">Use the **Define Time Periods** page to define the calendar year information and time frequencies to include in the time dimension or server time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0dfe1-104"> Cette page s'affiche uniquement si vous avez sélectionné **Dimension de temps du serveur** dans la page **Sélectionner le type de la dimension** , ou **Construire la dimension sans utiliser de source de données** dans la page **Sélectionner la méthode de construction** et sélectionné **Dimension de temps** dans la page **Sélectionner le type de la dimension** .</span><span class="sxs-lookup"><span data-stu-id="0dfe1-104">This page will appear only if you have selected **Server time dimension** on the **Select the Dimension Type** page, or if you selected **Build the dimension without using a data source** on the **Select Build Method** page and selected **Time dimension** on the **Select the Dimension Type** page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0dfe1-105">Cette page permet de définir l'année civile d'une dimension de temps.</span><span class="sxs-lookup"><span data-stu-id="0dfe1-105">This page is for defining the calendar year of a time dimension.</span></span> <span data-ttu-id="0dfe1-106">Pour définir l’année fiscale, de fabrication, de rapports ou ISO (International Standards Organization) 8601 de la dimension de temps, utilisez la page **Sélectionner des calendriers** .</span><span class="sxs-lookup"><span data-stu-id="0dfe1-106">To define a fiscal, manufacturing, reporting, or International Standards Organization (ISO) 8601 year for the time dimension, use the **Select Calendars** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0dfe1-107">Options</span><span class="sxs-lookup"><span data-stu-id="0dfe1-107">Options</span></span>  
 <span data-ttu-id="0dfe1-108">**Premier jour du calendrier**</span><span class="sxs-lookup"><span data-stu-id="0dfe1-108">**First calendar day**</span></span>  
 <span data-ttu-id="0dfe1-109">Tapez ou sélectionnez le premier jour de l'année en cours.</span><span class="sxs-lookup"><span data-stu-id="0dfe1-109">Type or select the day that begins the current year.</span></span>  
  
 <span data-ttu-id="0dfe1-110">**Dernier jour du calendrier**</span><span class="sxs-lookup"><span data-stu-id="0dfe1-110">**Last calendar day**</span></span>  
 <span data-ttu-id="0dfe1-111">Tapez ou sélectionnez le dernier jour de l'année en cours.</span><span class="sxs-lookup"><span data-stu-id="0dfe1-111">Type or select the day that ends the current year.</span></span>  
  
 <span data-ttu-id="0dfe1-112">**Premier jour de la semaine**</span><span class="sxs-lookup"><span data-stu-id="0dfe1-112">**First day of the week**</span></span>  
 <span data-ttu-id="0dfe1-113">Sélectionnez le premier jour d'une semaine.</span><span class="sxs-lookup"><span data-stu-id="0dfe1-113">Select the day that begins a week.</span></span>  
  
 <span data-ttu-id="0dfe1-114">**Périodes**</span><span class="sxs-lookup"><span data-stu-id="0dfe1-114">**Time periods**</span></span>  
 <span data-ttu-id="0dfe1-115">Sélectionnez les périodes de l'année civile de la dimension de temps.</span><span class="sxs-lookup"><span data-stu-id="0dfe1-115">Select the time periods for the calendar year of the time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0dfe1-116">La période `Date` est requise.</span><span class="sxs-lookup"><span data-stu-id="0dfe1-116">The `Date` time period is required.</span></span>  
  
 <span data-ttu-id="0dfe1-117">**Langue pour les noms des membres de temps**</span><span class="sxs-lookup"><span data-stu-id="0dfe1-117">**Language for time member names**</span></span>  
 <span data-ttu-id="0dfe1-118">Sélectionnez la langue des membres de la dimension de temps.</span><span class="sxs-lookup"><span data-stu-id="0dfe1-118">Select the language for the members in the time dimension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dfe1-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0dfe1-119">See Also</span></span>  
 <span data-ttu-id="0dfe1-120">[Aide (F1) de l’Assistant Dimension](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="0dfe1-120">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="0dfe1-121">[Dimensions &#40;Analysis Services-données multidimensionnelles&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0dfe1-121">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="0dfe1-122">[Dimensions dans les modèles multidimensionnels](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="0dfe1-122">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="0dfe1-123">Sélectionnez calendriers &#40;Assistant Dimension&#41;</span><span class="sxs-lookup"><span data-stu-id="0dfe1-123">Select Calendars &#40;Dimension Wizard&#41;</span></span>](select-calendars-dimension-wizard.md)  
  
  
