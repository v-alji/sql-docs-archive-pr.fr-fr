---
title: Définir le comportement semi-additif | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- semiadditive
- Business Intelligence enhancements [Analysis Services], semiadditive behavior
- measures [Analysis Services], semiadditive
ms.assetid: b25726bc-728b-4601-ad87-9015c39dc615
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9c2028c350046fdcc9f98bcd0f0612d6a91ccabb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605832"
---
# <a name="define-semiadditive-behavior"></a><span data-ttu-id="6930f-102">Définir le comportement semi-additif</span><span class="sxs-lookup"><span data-stu-id="6930f-102">Define Semiadditive Behavior</span></span>
  <span data-ttu-id="6930f-103">Les mesures semi-additives, qui n'agrègent pas uniformément toutes les dimensions, sont très fréquentes dans les scénarios d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="6930f-103">Semiadditive measures, which do not uniformly aggregate across all dimensions, are very common in many business scenarios.</span></span> <span data-ttu-id="6930f-104">Chaque cube qui se base sur l'instantané de soldes dans le temps pose ce problème.</span><span class="sxs-lookup"><span data-stu-id="6930f-104">Every cube that is based on snapshots of balances over time exhibits this problem.</span></span> <span data-ttu-id="6930f-105">Ces instantanés s'utilisent dans des applications traitant de titres de placement, de soldes de compte, de budgétisation, de ressources humaines, de polices et de déclarations d'assurance, et de nombreux autres domaines d'activité.</span><span class="sxs-lookup"><span data-stu-id="6930f-105">You can find these snapshots in applications dealing with securities, account balances, budgeting, human resources, insurance policies and claims, and many other business domains.</span></span>  
  
 <span data-ttu-id="6930f-106">Ajoutez le comportement semi-additif à un cube pour définir une méthode d'agrégation de mesures ou de membres individuels de l'attribut de type de compte.</span><span class="sxs-lookup"><span data-stu-id="6930f-106">Add semiadditive behavior to a cube to define an aggregation method for individual measures or members of the account type attribute.</span></span> <span data-ttu-id="6930f-107">Si le cube contient une dimension de comptes, vous pouvez automatiquement définir le comportement semi-additif sur la base du type de compte.</span><span class="sxs-lookup"><span data-stu-id="6930f-107">If the cube contains an account dimension, you can automatically set semiadditive behavior based on the account type.</span></span>  
  
 <span data-ttu-id="6930f-108">Pour ajouter un comportement semi-additif, ouvrez un cube dans le Concepteur de cube et choisissez **Ajouter Business Intelligence** dans le menu Cube.</span><span class="sxs-lookup"><span data-stu-id="6930f-108">To add semiadditive behavior, open a cube in Cube Designer and choose **Add Business Intelligence** from the Cube menu.</span></span> <span data-ttu-id="6930f-109">Dans l’Assistant Business Intelligence, sélectionnez l’option **Définir le comportement semi-additif** dans la page **Choisir des améliorations** .</span><span class="sxs-lookup"><span data-stu-id="6930f-109">In the Business Intelligence Wizard, select the **Define semiadditive behavior** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="6930f-110">L'Assistant vous guide ensuite tout au long des étapes d'identification des mesures ayant un comportement semi-additif.</span><span class="sxs-lookup"><span data-stu-id="6930f-110">This wizard then guides you through the steps of identifying which measures have semiadditive behavior.</span></span>  
  
 <span data-ttu-id="6930f-111">Excepté pour LastChild qui est disponible dans l'édition Standard, les comportements semi-additifs sont uniquement disponibles dans les éditions Business Intelligence ou Entreprise.</span><span class="sxs-lookup"><span data-stu-id="6930f-111">With the exception of LastChild which is available in the standard edition, semi-additive behaviors are only available in the business intelligence or enterprise editions.</span></span>  
  
## <a name="define-semiadditive-behavior"></a><span data-ttu-id="6930f-112">Définir le comportement semi-additif</span><span class="sxs-lookup"><span data-stu-id="6930f-112">Define Semiadditive Behavior</span></span>  
 <span data-ttu-id="6930f-113">Dans la page **Définir le comportement semi-additif** de l’Assistant, choisissez comment définir le comportement semi-additif en sélectionnant l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="6930f-113">On the **Define Semiadditive Behavior** page of the wizard, you select how to define semiadditivity by selecting one of the following options:</span></span>  
  
 <span data-ttu-id="6930f-114">**Désactiver le comportement semi-additif**</span><span class="sxs-lookup"><span data-stu-id="6930f-114">**Turn off semiadditive behavior**</span></span>  
 <span data-ttu-id="6930f-115">Supprime le comportement semi-additif d'un cube dans lequel le comportement semi-additif était auparavant défini.</span><span class="sxs-lookup"><span data-stu-id="6930f-115">Removes semiadditive behavior from a cube in which semiadditive behavior was previously defined.</span></span> <span data-ttu-id="6930f-116">Cette sélection affecte de nouveau la valeur `SUM` à une mesure si cette dernière a l'un des types de fonction d'agrégation suivants :</span><span class="sxs-lookup"><span data-stu-id="6930f-116">This selection resets a measure to `SUM` if it is set to any of the following aggregation function types:</span></span>  
  
-   <span data-ttu-id="6930f-117">By Account</span><span class="sxs-lookup"><span data-stu-id="6930f-117">By Account</span></span>  
  
-   <span data-ttu-id="6930f-118">Average of Children</span><span class="sxs-lookup"><span data-stu-id="6930f-118">Average of Children</span></span>  
  
-   <span data-ttu-id="6930f-119">First Child</span><span class="sxs-lookup"><span data-stu-id="6930f-119">First Child</span></span>  
  
-   <span data-ttu-id="6930f-120">Last Child</span><span class="sxs-lookup"><span data-stu-id="6930f-120">Last Child</span></span>  
  
-   <span data-ttu-id="6930f-121">Last Nonempty Child</span><span class="sxs-lookup"><span data-stu-id="6930f-121">Last Nonempty Child</span></span>  
  
-   <span data-ttu-id="6930f-122">First Nonempty Child</span><span class="sxs-lookup"><span data-stu-id="6930f-122">First Nonempty Child</span></span>  
  
-   <span data-ttu-id="6930f-123">None</span><span class="sxs-lookup"><span data-stu-id="6930f-123">None</span></span>  
  
 <span data-ttu-id="6930f-124">Cette option ne change pas les mesures avec une fonction d’agrégation normale : `Sum` , `Min` ,, `Max` `Count` ou `Distinct``Count` .</span><span class="sxs-lookup"><span data-stu-id="6930f-124">This option does not change measures with a regular aggregation function: `Sum`, `Min`, `Max`, `Count`, or `Distinct``Count`.</span></span>  
  
 <span data-ttu-id="6930f-125">**L’Assistant a détecté une dimension de compte « compte », qui contient des membres semi-additifs. Le serveur agrégera les membres de cette dimension en fonction du comportement semi-additif spécifié pour chaque type de compte.**</span><span class="sxs-lookup"><span data-stu-id="6930f-125">**The wizard has detected the 'Account" account dimension, which contains semiadditive members. The server will aggregate members of this dimension according to the semiadditive behavior specified for each account type.**</span></span>  
 <span data-ttu-id="6930f-126">Provoque la définition de toutes les mesures d'un groupe de mesures dimensionné par une dimension de type Compte dans la fonction d'agrégation par le système, et le serveur agrège les membres de la dimension en fonction du comportement semi-additif spécifié pour chaque type de compte.</span><span class="sxs-lookup"><span data-stu-id="6930f-126">Causes the system to set all measures from a measure group dimensioned by an Account type dimension to the By Account aggregation function and the server will aggregate members of the dimension according to the semiadditive behavior specified for each account type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6930f-127">Cette option est sélectionnée par défaut si l'Assistant détecte une dimension de type Compte.</span><span class="sxs-lookup"><span data-stu-id="6930f-127">This option is selected by default if the wizard detects an Account type dimension.</span></span>  
  
 <span data-ttu-id="6930f-128">**Définir le comportement semi-additif pour les mesures individuelles**</span><span class="sxs-lookup"><span data-stu-id="6930f-128">**Define semiadditive behavior for individual measures**</span></span>  
 <span data-ttu-id="6930f-129">Sélectionne le comportement semi-additif de chaque mesure individuellement.</span><span class="sxs-lookup"><span data-stu-id="6930f-129">Selects the semiadditive behavior of each measure individually.</span></span> <span data-ttu-id="6930f-130">La valeur par défaut est `SUM` (totalement additif).</span><span class="sxs-lookup"><span data-stu-id="6930f-130">The default setting is `SUM` (fully additive).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6930f-131">Cette option est sélectionnée par défaut si l'Assistant ne détecte pas une dimension de type Compte.</span><span class="sxs-lookup"><span data-stu-id="6930f-131">This option is selected by default if the wizard does not detect an Account type dimension.</span></span>  
  
 <span data-ttu-id="6930f-132">Pour chaque mesure, vous pouvez sélectionner l'un des types de fonctionnalités semi-additives décrits dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="6930f-132">For each measure, you can select from the types of semiadditive functionality described in the following table.</span></span>  
  
|<span data-ttu-id="6930f-133">Fonction semi-additive</span><span class="sxs-lookup"><span data-stu-id="6930f-133">Semiadditive function</span></span>|<span data-ttu-id="6930f-134">Description</span><span class="sxs-lookup"><span data-stu-id="6930f-134">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="6930f-135">Average of Children</span><span class="sxs-lookup"><span data-stu-id="6930f-135">Average of Children</span></span>|<span data-ttu-id="6930f-136">L'agrégation d'un membre est la moyenne de ses enfants.</span><span class="sxs-lookup"><span data-stu-id="6930f-136">The aggregation of a member is the average of its children.</span></span>|  
|<span data-ttu-id="6930f-137">ByAccount</span><span class="sxs-lookup"><span data-stu-id="6930f-137">ByAccount</span></span>|<span data-ttu-id="6930f-138">Le système lit le comportement semi-additif spécifié pour le type de compte.</span><span class="sxs-lookup"><span data-stu-id="6930f-138">The system reads the semiadditive behavior specified for the account type.</span></span>|  
|<span data-ttu-id="6930f-139">Count</span><span class="sxs-lookup"><span data-stu-id="6930f-139">Count</span></span>|<span data-ttu-id="6930f-140">L'agrégation est un nombre de membres.</span><span class="sxs-lookup"><span data-stu-id="6930f-140">The aggregation is a count of members.</span></span>|  
|<span data-ttu-id="6930f-141">Distinct Count</span><span class="sxs-lookup"><span data-stu-id="6930f-141">Distinct Count</span></span>|<span data-ttu-id="6930f-142">L'agrégation est un nombre de membres uniques.</span><span class="sxs-lookup"><span data-stu-id="6930f-142">The aggregation is a count of unique members.</span></span>|  
|<span data-ttu-id="6930f-143">First Child</span><span class="sxs-lookup"><span data-stu-id="6930f-143">First Child</span></span>|<span data-ttu-id="6930f-144">La valeur de membre est évaluée comme la valeur de son premier enfant avec la dimension de temps.</span><span class="sxs-lookup"><span data-stu-id="6930f-144">The member value is evaluated as the value of its first child along the time dimension.</span></span>|  
|<span data-ttu-id="6930f-145">FirstNonEmpty</span><span class="sxs-lookup"><span data-stu-id="6930f-145">FirstNonEmpty</span></span>|<span data-ttu-id="6930f-146">La valeur de membre est évaluée comme la valeur de son premier enfant avec la dimension de temps qui contient les données.</span><span class="sxs-lookup"><span data-stu-id="6930f-146">The member value is evaluated as the value of its first child along the time dimension that contains data.</span></span>|  
|<span data-ttu-id="6930f-147">LastChild</span><span class="sxs-lookup"><span data-stu-id="6930f-147">LastChild</span></span>|<span data-ttu-id="6930f-148">La valeur de membre est évaluée comme la valeur de son dernier enfant avec la dimension de temps.</span><span class="sxs-lookup"><span data-stu-id="6930f-148">The member value is evaluated as the value of its last child along the time dimension.</span></span>|  
|<span data-ttu-id="6930f-149">LastNonEmpty</span><span class="sxs-lookup"><span data-stu-id="6930f-149">LastNonEmpty</span></span>|<span data-ttu-id="6930f-150">La valeur de membre est évaluée comme la valeur de son dernier enfant avec la dimension de temps qui contient les données.</span><span class="sxs-lookup"><span data-stu-id="6930f-150">The member value is evaluated as the value of its last child along the time dimension that contains data.</span></span>|  
|<span data-ttu-id="6930f-151">Max</span><span class="sxs-lookup"><span data-stu-id="6930f-151">Max</span></span>|<span data-ttu-id="6930f-152">La fonction d'agrégation maximale standard est appliquée.</span><span class="sxs-lookup"><span data-stu-id="6930f-152">The standard maximum aggregation function is applied.</span></span>|  
|<span data-ttu-id="6930f-153">Min</span><span class="sxs-lookup"><span data-stu-id="6930f-153">Min</span></span>|<span data-ttu-id="6930f-154">La fonction d'agrégation minimale standard est appliquée.</span><span class="sxs-lookup"><span data-stu-id="6930f-154">The standard minimum aggregation function is applied.</span></span>|  
|<span data-ttu-id="6930f-155">None</span><span class="sxs-lookup"><span data-stu-id="6930f-155">None</span></span>|<span data-ttu-id="6930f-156">Aucune agrégation n'est appliquée.</span><span class="sxs-lookup"><span data-stu-id="6930f-156">No aggregation is applied.</span></span>|  
|<span data-ttu-id="6930f-157">SUM</span><span class="sxs-lookup"><span data-stu-id="6930f-157">Sum</span></span>|<span data-ttu-id="6930f-158">La fonction d'addition standard est appliquée.</span><span class="sxs-lookup"><span data-stu-id="6930f-158">The standard summation function is applied.</span></span>|  
  
 <span data-ttu-id="6930f-159">Tout comportement semi-additif existant est écrasé lorsque vous terminez l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="6930f-159">Any existing semiadditive behavior is overwritten when you complete the wizard.</span></span>  
  
  
