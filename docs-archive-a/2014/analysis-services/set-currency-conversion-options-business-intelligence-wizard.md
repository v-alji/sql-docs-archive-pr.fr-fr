---
title: Définir les options de conversion monétaire (Assistant Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.calculationsettings.f1
ms.assetid: a49d4e1f-bdda-4a83-ab4f-ce8c500e1d6d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61877deb0bc422d65f977e3fc9de3e678f7d8477
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705515"
---
# <a name="set-currency-conversion-options-business-intelligence-wizard"></a><span data-ttu-id="570b9-102">Définir les options de conversion monétaire (Assistant Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="570b9-102">Set Currency Conversion Options (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="570b9-103">La page **Définir les options de conversion monétaire** permet de définir les calculs relatifs à la conversion monétaire pour un groupe de mesures contenant des taux de change.</span><span class="sxs-lookup"><span data-stu-id="570b9-103">Use the **Set Currency Conversion** page to define currency conversion calculations for a measure group that contains exchange rates.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="570b9-104">Cette page ne s’affiche pas si l’Assistant Business Intelligence a été démarré à partir du Concepteur de dimensions ou en cliquant avec le bouton droit sur une dimension dans l’Explorateur de solutions dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="570b9-104">This page does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="570b9-105">Options</span><span class="sxs-lookup"><span data-stu-id="570b9-105">Options</span></span>  
 <span data-ttu-id="570b9-106">**Sélectionnez le groupe de mesures qui contient le taux de change**</span><span class="sxs-lookup"><span data-stu-id="570b9-106">**Select the measure group that contains exchange rates**</span></span>  
 <span data-ttu-id="570b9-107">Groupe de mesures contenant les taux de change que les calculs de conversion monétaire utilisent comme point de référence.</span><span class="sxs-lookup"><span data-stu-id="570b9-107">Select the measure group that contains the exchange rates that the currency conversion calculations should reference.</span></span>  
  
 <span data-ttu-id="570b9-108">**Spécifiez la devise pivot**</span><span class="sxs-lookup"><span data-stu-id="570b9-108">**Specify the pivot currency**</span></span>  
 <span data-ttu-id="570b9-109">Membre servant de devise pivot pour le groupe de mesures.</span><span class="sxs-lookup"><span data-stu-id="570b9-109">Select the member that serves as the pivot currency for the measure group.</span></span>  
  
 <span data-ttu-id="570b9-110">**Comment avez-vous entré vos taux de change (autrement dit, sélectionnez une devise d'exemple)**</span><span class="sxs-lookup"><span data-stu-id="570b9-110">**Select how you entered your exchange rates (select a sample currency)**</span></span>  
 <span data-ttu-id="570b9-111">Permet de sélectionner un membre représentant une devise exemple tirée de la dimension monétaire afin de changer le texte relatif à la parité de X unités de la devise pivot pour 1 unité de devise d'exemple, ainsi que la parité de X unités de la devise d'exemple pour 1 unité de la devise pivot, afin de mieux afficher le sens des taux de change.</span><span class="sxs-lookup"><span data-stu-id="570b9-111">Select a member representing a sample currency from the currency dimension to change the text for the X pivot currency per 1 sample currency and X sample currency per 1 pivot currency options to better display the exchange rate direction.</span></span>  
  
 <span data-ttu-id="570b9-112">**Devise pivot X par 1 devise d'exemple**</span><span class="sxs-lookup"><span data-stu-id="570b9-112">**X pivot currency per 1 sample currency**</span></span>  
 <span data-ttu-id="570b9-113">Permet d'indiquer que les taux de change dans le groupe de mesures des taux représentent un multiplicateur de la devise pivot spécifiée.</span><span class="sxs-lookup"><span data-stu-id="570b9-113">Select to indicate that the exchange rates in the rate measure group represent a multiplier for the specified pivot currency.</span></span>  
  
 <span data-ttu-id="570b9-114">**Devise d'exemple X par 1 devise pivot**</span><span class="sxs-lookup"><span data-stu-id="570b9-114">**X sample currency per 1 pivot currency**</span></span>  
 <span data-ttu-id="570b9-115">Permet d'indiquer que les taux de change dans le groupe de mesures des taux représentent un multiplicateur de la devise d'exemple spécifiée.</span><span class="sxs-lookup"><span data-stu-id="570b9-115">Select to indicate that the exchange rates in the rate measure group represent a multiplier for the specified sample currency.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="570b9-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="570b9-116">See Also</span></span>  
 <span data-ttu-id="570b9-117">[Aide (F1) de l’Assistant Business Intelligence](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="570b9-117">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="570b9-118">[Concepteur de cube &#40;Analysis Services-données multidimensionnelles&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="570b9-118">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="570b9-119">Concepteur de dimensions &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="570b9-119">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
