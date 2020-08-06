---
title: Sélectionner les membres (Assistant Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.memberconversion.f1
ms.assetid: 1a147461-d594-41e7-a41d-09d2d003e1e0
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd5f184e0d9670725609531b6d0a101f8e7f8647
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603077"
---
# <a name="select-members-business-intelligence-wizard"></a><span data-ttu-id="9cd6c-102">Sélectionner les membres (Assistant Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="9cd6c-102">Select Members (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="9cd6c-103">Utilisez la page **Sélectionner les membres** pour déterminer à quels membres l'Assistant Business Intelligence doit appliquer la fonction de conversion monétaire spécifiée à la page **Définir les options de conversion monétaire** .</span><span class="sxs-lookup"><span data-stu-id="9cd6c-103">Use the **Select Members** page to determine to which members the Business Intelligence Wizard should apply the currency conversion functionality specified on the **Set Currency Conversion Options** page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9cd6c-104">Cette page ne s’affiche pas si l’Assistant Business Intelligence a été démarré à partir du Concepteur de dimensions ou en cliquant avec le bouton droit sur une dimension dans l’Explorateur de solutions dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cd6c-104">This page does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="9cd6c-105">Options</span><span class="sxs-lookup"><span data-stu-id="9cd6c-105">Options</span></span>  
 <span data-ttu-id="9cd6c-106">**Dimension de mesures**</span><span class="sxs-lookup"><span data-stu-id="9cd6c-106">**Measures dimension**</span></span>  
 <span data-ttu-id="9cd6c-107">Sélectionnez cette option afin d'appliquer la fonctionnalité de conversion monétaire à une ou plusieurs mesures du cube.</span><span class="sxs-lookup"><span data-stu-id="9cd6c-107">Select to apply the currency conversion functionality to one or more measures in the cube.</span></span>  
  
 <span data-ttu-id="9cd6c-108">Une fois cette option sélectionnée, la grille affiche les options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="9cd6c-108">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="9cd6c-109">Option</span><span class="sxs-lookup"><span data-stu-id="9cd6c-109">Option</span></span>|<span data-ttu-id="9cd6c-110">Description</span><span class="sxs-lookup"><span data-stu-id="9cd6c-110">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="9cd6c-111">**Types de mesure intégrés**</span><span class="sxs-lookup"><span data-stu-id="9cd6c-111">**Built-in Measure Types**</span></span>|<span data-ttu-id="9cd6c-112">Sélectionnez cette option afin d'inclure la fonctionnalité de conversion monétaire pour la mesure spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9cd6c-112">Select to include currency conversion functionality for the specified measure.</span></span>|  
|<span data-ttu-id="9cd6c-113">**Mesures**</span><span class="sxs-lookup"><span data-stu-id="9cd6c-113">**Measures**</span></span>|<span data-ttu-id="9cd6c-114">Sélectionnez la mesure dans le groupe de mesures de taux qui contient le taux de change à utiliser lors de la conversion de la mesure sélectionnée à la section **Types de mesures intégrés** .</span><span class="sxs-lookup"><span data-stu-id="9cd6c-114">Select the measure from the rate measure group that contains the exchange rate to use when the measure selected in **Built-in Measure Types** is converted.</span></span>|  
  
 <span data-ttu-id="9cd6c-115">**Hiérarchie de comptes**</span><span class="sxs-lookup"><span data-stu-id="9cd6c-115">**Account hierarchy**</span></span>  
 <span data-ttu-id="9cd6c-116">Sélectionnez cette option afin d'appliquer la fonctionnalité de conversion monétaire à un ou plusieurs membres dans la hiérarchie de comptes de la dimension incluse dans le cube.</span><span class="sxs-lookup"><span data-stu-id="9cd6c-116">Select to apply the currency conversion functionality to one or more members in the account hierarchy of the account dimension included in the cube.</span></span> <span data-ttu-id="9cd6c-117">La hiérarchie de compte est la hiérarchie dans la dimension de compte dont la `Type` propriété est définie sur *Account*.</span><span class="sxs-lookup"><span data-stu-id="9cd6c-117">The account hierarchy is the hierarchy within the account dimension whose `Type` property is set to *Account*.</span></span>  
  
 <span data-ttu-id="9cd6c-118">Une fois cette option sélectionnée, la grille affiche les options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="9cd6c-118">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="9cd6c-119">Option</span><span class="sxs-lookup"><span data-stu-id="9cd6c-119">Option</span></span>|<span data-ttu-id="9cd6c-120">Description</span><span class="sxs-lookup"><span data-stu-id="9cd6c-120">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="9cd6c-121">**Membre du compte**</span><span class="sxs-lookup"><span data-stu-id="9cd6c-121">**Account Member**</span></span>|<span data-ttu-id="9cd6c-122">Sélectionnez cette option afin d'inclure la fonctionnalité de conversion monétaire pour le membre spécifié de la hiérarchie de comptes.</span><span class="sxs-lookup"><span data-stu-id="9cd6c-122">Select to include currency conversion functionality for the specified member of the account hierarchy.</span></span>|  
|<span data-ttu-id="9cd6c-123">**Mesures**</span><span class="sxs-lookup"><span data-stu-id="9cd6c-123">**Measures**</span></span>|<span data-ttu-id="9cd6c-124">Sélectionnez la mesure dans le groupe de mesures Taux qui contient le taux de change à utiliser lors de la conversion des mesures relatives au membre choisi dans **Membre du compte** .</span><span class="sxs-lookup"><span data-stu-id="9cd6c-124">Select the measure from the rate measure group that contains the exchange rate to use when the measures for the member selected in **Account Member** are converted.</span></span>|  
  
 <span data-ttu-id="9cd6c-125">**Hiérarchie de comptes basée sur le type**</span><span class="sxs-lookup"><span data-stu-id="9cd6c-125">**Account hierarchy based on type**</span></span>  
 <span data-ttu-id="9cd6c-126">Sélectionnez afin d'appliquer la fonctionnalité de conversion monétaire à tous les membres d'attributs dans la hiérarchie de comptes dont la propriété `Type` est définie sur le type de compte indiqué.</span><span class="sxs-lookup"><span data-stu-id="9cd6c-126">Select to apply the currency conversion functionality to all members of attributes in the account hierarchy whose `Type` property is set to a specified account type.</span></span>  
  
 <span data-ttu-id="9cd6c-127">Une fois cette option sélectionnée, la grille affiche les options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="9cd6c-127">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="9cd6c-128">Option</span><span class="sxs-lookup"><span data-stu-id="9cd6c-128">Option</span></span>|<span data-ttu-id="9cd6c-129">Description</span><span class="sxs-lookup"><span data-stu-id="9cd6c-129">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="9cd6c-130">**Type de compte**</span><span class="sxs-lookup"><span data-stu-id="9cd6c-130">**Account Type**</span></span>|<span data-ttu-id="9cd6c-131">Sélectionnez cette option afin d'inclure la fonctionnalité de conversion monétaire pour le type de compte spécifié.</span><span class="sxs-lookup"><span data-stu-id="9cd6c-131">Select to include currency conversion functionality for the specified account type.</span></span>|  
|<span data-ttu-id="9cd6c-132">**Mesures**</span><span class="sxs-lookup"><span data-stu-id="9cd6c-132">**Measures**</span></span>|<span data-ttu-id="9cd6c-133">Sélectionnez la mesure dans le groupe de mesures Taux qui contient le taux de change à utiliser lors de la conversion des mesures relatives aux membres d'attributs dont le type de compte correspond à celui indiqué dans **Type de compte** .</span><span class="sxs-lookup"><span data-stu-id="9cd6c-133">Select the measure from the rate measure group that contains the exchange rate to use when measures for the members of attributes using the account type selected in **Account Type** are converted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9cd6c-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9cd6c-134">See Also</span></span>  
 <span data-ttu-id="9cd6c-135">[Aide (F1) de l’Assistant Business Intelligence](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="9cd6c-135">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="9cd6c-136">[Concepteur de cube &#40;Analysis Services-données multidimensionnelles&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="9cd6c-136">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="9cd6c-137">Concepteur de dimensions &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="9cd6c-137">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
