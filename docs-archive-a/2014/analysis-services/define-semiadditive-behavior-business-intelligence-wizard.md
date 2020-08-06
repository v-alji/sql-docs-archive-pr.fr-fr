---
title: Définir le comportement semi-additif (Assistant Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.semiadditivememberdetection.f1
ms.assetid: e57080ba-ce96-40f8-bca7-6701d1725b3c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5a3c46de038a7e45dcb39805e324260676a03228
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696312"
---
# <a name="define-semiadditive-behavior-business-intelligence-wizard"></a><span data-ttu-id="64620-102">Définir le comportement semi-additif (Assistant Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="64620-102">Define Semiadditive Behavior (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="64620-103">Utilisez la page **Définir le comportement semi-additif** pour activer ou désactiver le comportement semi-additif sur les mesures.</span><span class="sxs-lookup"><span data-stu-id="64620-103">Use the **Define Semiadditive Behavior** page to enable or disable semi-additive behavior on measures.</span></span> <span data-ttu-id="64620-104">Celui-ci détermine comment les mesures sont contenues dans un cube sont agrégées sur une dimension de temps.</span><span class="sxs-lookup"><span data-stu-id="64620-104">Semi-additive behavior determines how measures that are contained by a cube are aggregated over a time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="64620-105">Excepté pour LastChild qui est disponible dans l'édition Standard, les comportements semi-additifs sont uniquement disponibles dans les éditions Business Intelligence ou Entreprise.</span><span class="sxs-lookup"><span data-stu-id="64620-105">With the exception of LastChild which is available in the standard edition, semi-additive behaviors are only available in the business intelligence or enterprise editions.</span></span> <span data-ttu-id="64620-106">En outre, étant donné que le comportement semi-additif n’est défini que sur les mesures et non les dimensions, vous ne trouverez pas cette page dans l’Assistant Business Intelligence s’il a été démarré à partir du Concepteur de dimensions ou en cliquant avec le bouton droit sur une dimension dans l’Explorateur de solutions dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64620-106">Furthermore, because semiadditive behavior is defined only on measures and not dimensions, you will not find this page in the Business Intelligence Wizard if it was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="64620-107">Options</span><span class="sxs-lookup"><span data-stu-id="64620-107">Options</span></span>  
 <span data-ttu-id="64620-108">**Désactiver le comportement semi-additif**</span><span class="sxs-lookup"><span data-stu-id="64620-108">**Turn off semiadditive behavior**</span></span>  
 <span data-ttu-id="64620-109">Désactive le comportement semi-additif dans toutes les mesures contenues dans le cube.</span><span class="sxs-lookup"><span data-stu-id="64620-109">Disables semi-additive behavior in all measures contained by the cube.</span></span>  
  
 <span data-ttu-id="64620-110">**L’Assistant a détecté la \<dimension name> dimension Account, qui contient des membres semi-additifs. Le serveur agrégera les membres de cette dimension en fonction du comportement semi-additif spécifié pour chaque type de compte.**</span><span class="sxs-lookup"><span data-stu-id="64620-110">**The wizard has detected the \<dimension name> account dimension, which contains semiadditive members. The server will aggregate members of this dimension according to the semiadditive behavior specified for each account type.**</span></span>  
 <span data-ttu-id="64620-111">Active le comportement semi-additif pour les dimensions de compte qui contiennent des membres semi-additifs.</span><span class="sxs-lookup"><span data-stu-id="64620-111">Enables semi-additive behavior for account dimensions that contain semi-additive members.</span></span> <span data-ttu-id="64620-112">Cette option configure la fonction d'agrégation de toutes les mesures dans des groupes qui font référence à la dimension de compte `ByAccount`.</span><span class="sxs-lookup"><span data-stu-id="64620-112">Selecting this option sets the aggregation function of all measures in measure groups that reference the account dimension to `ByAccount`.</span></span>  
  
 <span data-ttu-id="64620-113">Pour plus d’informations sur les dimensions de compte, consultez [Créer un compte Finance de la dimension de type parent-enfant](multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md).</span><span class="sxs-lookup"><span data-stu-id="64620-113">For more information about account dimensions, see [Create a Finance Account of parent-child type Dimension](multidimensional-models/database-dimensions-finance-account-of-parent-child-type.md).</span></span>  
  
 <span data-ttu-id="64620-114">**Définir le comportement semi-additif pour les membres individuels**</span><span class="sxs-lookup"><span data-stu-id="64620-114">**Define semiadditive behavior for individual members**</span></span>  
 <span data-ttu-id="64620-115">Active le comportement semi-additif et spécifie la fonction d'agrégation semi-additive pour des mesures données.</span><span class="sxs-lookup"><span data-stu-id="64620-115">Enables semi-additive behavior and specifies the semi-additive aggregation function for specific measures.</span></span> <span data-ttu-id="64620-116">Cette fonction s'applique à toutes les dimensions référencées par le groupe de mesures qui contiennent la mesure.</span><span class="sxs-lookup"><span data-stu-id="64620-116">The aggregation function applies to all dimensions that are referenced by the measure group that contains the measure.</span></span>  
  
 <span data-ttu-id="64620-117">**Mesures**</span><span class="sxs-lookup"><span data-stu-id="64620-117">**Measures**</span></span>  
 <span data-ttu-id="64620-118">Affiche le nom d'une mesure contenue dans le cube.</span><span class="sxs-lookup"><span data-stu-id="64620-118">Displays the name of a measure contained by the cube.</span></span>  
  
 <span data-ttu-id="64620-119">**Fonction semi-additive**</span><span class="sxs-lookup"><span data-stu-id="64620-119">**Semiadditive Function**</span></span>  
 <span data-ttu-id="64620-120">Sélectionnez le type d'agrégation de la mesure sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="64620-120">Select the aggregation function for the selected measure.</span></span> <span data-ttu-id="64620-121">Le tableau suivant répertorie les fonctions d'agrégation disponibles.</span><span class="sxs-lookup"><span data-stu-id="64620-121">The following table lists the aggregation functions that are available.</span></span>  
  
|<span data-ttu-id="64620-122">Valeur</span><span class="sxs-lookup"><span data-stu-id="64620-122">Value</span></span>|<span data-ttu-id="64620-123">Description</span><span class="sxs-lookup"><span data-stu-id="64620-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="64620-124">**AverageOfChildren**</span><span class="sxs-lookup"><span data-stu-id="64620-124">**AverageOfChildren**</span></span>|<span data-ttu-id="64620-125">Agrégation réalisée en retournant la moyenne des enfants de la mesure.</span><span class="sxs-lookup"><span data-stu-id="64620-125">Aggregated by returning the average of the measure's children.</span></span>|  
|`ByAccount`|<span data-ttu-id="64620-126">Agrégation réalisée par la fonction d'agrégation associée au type de compte spécifié d'un attribut dans une dimension de compte.</span><span class="sxs-lookup"><span data-stu-id="64620-126">Aggregated by the aggregation function associated with the specified account type of an attribute in an account dimension.</span></span>|  
|`Count`|<span data-ttu-id="64620-127">Agrégation réalisée en utilisant la fonction `Count`.</span><span class="sxs-lookup"><span data-stu-id="64620-127">Aggregated using the `Count` function.</span></span>|  
|`DistinctCount`|<span data-ttu-id="64620-128">Agrégation réalisée en utilisant la fonction `DistinctCount`.</span><span class="sxs-lookup"><span data-stu-id="64620-128">Aggregated using the `DistinctCount` function.</span></span>|  
|<span data-ttu-id="64620-129">**FirstChild**</span><span class="sxs-lookup"><span data-stu-id="64620-129">**FirstChild**</span></span>|<span data-ttu-id="64620-130">Agrégation réalisée par retour du premier membre enfant de la mesure sur une dimension de temps.</span><span class="sxs-lookup"><span data-stu-id="64620-130">Aggregated by returning the measure's first child member over a time dimension.</span></span>|  
|<span data-ttu-id="64620-131">**FirstNonEmpty**</span><span class="sxs-lookup"><span data-stu-id="64620-131">**FirstNonEmpty**</span></span>|<span data-ttu-id="64620-132">Agrégation réalisée par retour du premier membre non vide de la mesure sur une dimension de temps.</span><span class="sxs-lookup"><span data-stu-id="64620-132">Aggregated by returning the measure's first nonempty member over a time dimension.</span></span>|  
|<span data-ttu-id="64620-133">**LastChild**</span><span class="sxs-lookup"><span data-stu-id="64620-133">**LastChild**</span></span>|<span data-ttu-id="64620-134">Agrégation réalisée par retour du dernier membre enfant de la mesure sur une dimension de temps.</span><span class="sxs-lookup"><span data-stu-id="64620-134">Aggregated by returning the measure's last child member over a time dimension.</span></span>|  
|<span data-ttu-id="64620-135">**LastNonEmpty**</span><span class="sxs-lookup"><span data-stu-id="64620-135">**LastNonEmpty**</span></span>|<span data-ttu-id="64620-136">Agrégation réalisée par retour du dernier membre non vide de la mesure sur une dimension de temps.</span><span class="sxs-lookup"><span data-stu-id="64620-136">Aggregated by returning the measure's last nonempty member over a time dimension.</span></span>|  
|`Max`|<span data-ttu-id="64620-137">Agrégation réalisée en utilisant la fonction `Max`.</span><span class="sxs-lookup"><span data-stu-id="64620-137">Aggregated using the `Max` function.</span></span>|  
|`Min`|<span data-ttu-id="64620-138">Agrégation réalisée en utilisant la fonction `Min`.</span><span class="sxs-lookup"><span data-stu-id="64620-138">Aggregated using the `Min` function.</span></span>|  
|<span data-ttu-id="64620-139">**Aucun**</span><span class="sxs-lookup"><span data-stu-id="64620-139">**None**</span></span>|<span data-ttu-id="64620-140">L'agrégation n'est pas effectuée.</span><span class="sxs-lookup"><span data-stu-id="64620-140">No aggregation performed.</span></span>|  
|`Sum`|<span data-ttu-id="64620-141">Agrégation réalisée en utilisant la fonction `Sum`.</span><span class="sxs-lookup"><span data-stu-id="64620-141">Aggregated using the `Sum` function.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="64620-142">Les sélections effectuées pour cette option s’appliquent uniquement si l’option **Définir le comportement semi-additif pour les membres individuels** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="64620-142">Selections made for this option apply only if **Define semiadditive behavior for individual members** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64620-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="64620-143">See Also</span></span>  
 <span data-ttu-id="64620-144">[Aide (F1) de l’Assistant Business Intelligence](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="64620-144">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="64620-145">[Concepteur de cube &#40;Analysis Services-données multidimensionnelles&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="64620-145">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="64620-146">Concepteur de dimensions &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="64620-146">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
