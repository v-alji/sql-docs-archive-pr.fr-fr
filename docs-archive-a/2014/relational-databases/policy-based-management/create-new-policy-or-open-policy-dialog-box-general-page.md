---
title: Créer une stratégie ou Ouvrir une stratégie, boîte de dialogue (page Général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.newgroup.f1
- sql12.swb.dmf.policy.f1
- sql12.swb.dmf.policy.filter.f1
ms.assetid: c00bebd0-d04b-4c64-840e-8b7a2c603436
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4b67cb8faf18001b841824b806e7befc0683d457
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603468"
---
# <a name="create-new-policy-or-open-policy-dialog-box-general-page"></a><span data-ttu-id="e103b-102">Boîte de dialogue Créer une nouvelle stratégie ou Ouvrir une stratégie, page Général</span><span class="sxs-lookup"><span data-stu-id="e103b-102">Create New Policy or Open Policy Dialog Box, General Page</span></span>
  <span data-ttu-id="e103b-103">Utilisez cette boîte de dialogue pour créer une stratégie de la Gestion basée sur des stratégies ou pour modifier une stratégie existante.</span><span class="sxs-lookup"><span data-stu-id="e103b-103">Use this dialog box to create a new Policy-Based Management policy or modify an existing policy.</span></span> <span data-ttu-id="e103b-104">Utilisez les zones **Par rapport aux cibles** et **Restriction sur le serveur** comme filtre pour limiter les stratégies à un sous-ensemble de toutes les cibles possibles.</span><span class="sxs-lookup"><span data-stu-id="e103b-104">Use the **Against targets** and **Server restriction** areas as a filter to limit policies to a subset of all possible targets.</span></span> <span data-ttu-id="e103b-105">Pour être utilisées comme filtres cibles, des conditions doivent être définies sur une facette physique, ne doivent pas contenir de fonctions et ne doivent pas contenir l'opérateur LIKE.</span><span class="sxs-lookup"><span data-stu-id="e103b-105">For conditions to be used as target filters, they must be defined on a physical facet, must not contain functions, and must not contain the LIKE operator.</span></span> <span data-ttu-id="e103b-106">Lorsque le système calcule le jeu d'objets pour une stratégie, les objets système sont exclus par défaut.</span><span class="sxs-lookup"><span data-stu-id="e103b-106">When the system computes the object set for a policy, by default the system objects are excluded.</span></span>  <span data-ttu-id="e103b-107">Par exemple, si le jeu d'objets de la stratégie fait référence à toutes les tables, la stratégie ne s'applique pas aux tables système.</span><span class="sxs-lookup"><span data-stu-id="e103b-107">For example, if the object set of the policy refers to all tables, the policy will not apply to system tables.</span></span> <span data-ttu-id="e103b-108">Si les utilisateurs souhaitent évaluer une stratégie sur les objets système, ils peuvent les ajouter explicitement au jeu d'objets.</span><span class="sxs-lookup"><span data-stu-id="e103b-108">If users want to evaluate a policy against system objects, they can explicitly add system objects to the object set.</span></span> <span data-ttu-id="e103b-109">Toutefois, bien que toutes les stratégies soient prises en charge pour le mode d'évaluation **vérifier la planification** , pour des raisons de performances, toutes les stratégies comportant des jeux d'objets arbitraires ne sont pas prises en charge pour le mode d'évaluation **vérifier la planification** .</span><span class="sxs-lookup"><span data-stu-id="e103b-109">However, though all policies are supported for **check on schedule** evaluation mode, for performance reason, not all policies with arbitrary object sets are supported for **check on change** evaluation mode.</span></span> <span data-ttu-id="e103b-110">Pour plus d’informations, consultez [https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx](https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx)</span><span class="sxs-lookup"><span data-stu-id="e103b-110">For more information, see [https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx](https://blogs.msdn.com/b/sqlpbm/archive/2009/04/13/policy-evaluation-modes.aspx)</span></span>  
  
## <a name="options"></a><span data-ttu-id="e103b-111">Options</span><span class="sxs-lookup"><span data-stu-id="e103b-111">Options</span></span>  
 <span data-ttu-id="e103b-112">**Nom**</span><span class="sxs-lookup"><span data-stu-id="e103b-112">**Name**</span></span>  
 <span data-ttu-id="e103b-113">Pour une nouvelle stratégie, tapez le nom de la nouvelle stratégie.</span><span class="sxs-lookup"><span data-stu-id="e103b-113">For a new policy, type the new policy name.</span></span> <span data-ttu-id="e103b-114">Pour une stratégie existante, le nom est affiché.</span><span class="sxs-lookup"><span data-stu-id="e103b-114">For an existing policy, the name is displayed.</span></span>  
  
 <span data-ttu-id="e103b-115">**Activé**</span><span class="sxs-lookup"><span data-stu-id="e103b-115">**Enabled**</span></span>  
 <span data-ttu-id="e103b-116">Cochez la case **Activé** pour activer la stratégie.</span><span class="sxs-lookup"><span data-stu-id="e103b-116">Select the **Enabled** check box to enable the policy.</span></span> <span data-ttu-id="e103b-117">Désactivez la case à cocher **Activé** pour désactiver la stratégie.</span><span class="sxs-lookup"><span data-stu-id="e103b-117">Clear the **Enabled** check box to disable the policy.</span></span> <span data-ttu-id="e103b-118">La case à cocher **Activée** s'applique à l'automation de stratégie.</span><span class="sxs-lookup"><span data-stu-id="e103b-118">The **Enabled** box applies to policy automation.</span></span> <span data-ttu-id="e103b-119">Elle crée ou supprime le système d'automation pour la stratégie.</span><span class="sxs-lookup"><span data-stu-id="e103b-119">It creates or removes the automation system for the policy.</span></span> <span data-ttu-id="e103b-120">L'automation utilise les mécanismes suivants :</span><span class="sxs-lookup"><span data-stu-id="e103b-120">Automation uses the following mechanisms:</span></span>  
  
 <span data-ttu-id="e103b-121">**Sur modification - Empêcher**</span><span class="sxs-lookup"><span data-stu-id="e103b-121">**On change: prevent**</span></span>  
 <span data-ttu-id="e103b-122">Un déclencheur de base de données applique la conformité.</span><span class="sxs-lookup"><span data-stu-id="e103b-122">A database trigger enforces compliance.</span></span>  
  
 <span data-ttu-id="e103b-123">**Sur modification - Journal uniquement**</span><span class="sxs-lookup"><span data-stu-id="e103b-123">**On change: log only**</span></span>  
 <span data-ttu-id="e103b-124">Un événement des services de notification vérifie la conformité.</span><span class="sxs-lookup"><span data-stu-id="e103b-124">A notification services event checks for compliance.</span></span>  
  
 <span data-ttu-id="e103b-125">**Selon planification**</span><span class="sxs-lookup"><span data-stu-id="e103b-125">**On schedule**</span></span>  
 <span data-ttu-id="e103b-126">Un travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est créé pour vérifier la conformité selon une planification.</span><span class="sxs-lookup"><span data-stu-id="e103b-126">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job is created to check for compliance on a schedule.</span></span>  
  
 <span data-ttu-id="e103b-127">Les stratégies exécutées avec le mode d'évaluation **À la demande** n'utilisent pas cette case à cocher.</span><span class="sxs-lookup"><span data-stu-id="e103b-127">Policies that are run using **On demand** evaluation mode do not use this check box.</span></span>  
  
 <span data-ttu-id="e103b-128">**Vérifier la condition**</span><span class="sxs-lookup"><span data-stu-id="e103b-128">**Check condition**</span></span>  
 <span data-ttu-id="e103b-129">Sélectionnez la condition de la Gestion basée sur des stratégies utilisée par cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="e103b-129">Select the Policy-Based Management condition that this policy uses.</span></span> <span data-ttu-id="e103b-130">Toutes les conditions sur le serveur pour la facette de la Gestion basée sur des stratégies associée sont répertoriées.</span><span class="sxs-lookup"><span data-stu-id="e103b-130">All conditions on the server for the associated Policy-Based Management facet are listed.</span></span> <span data-ttu-id="e103b-131">Cliquez sur **Nouvelle condition** pour créer une condition.</span><span class="sxs-lookup"><span data-stu-id="e103b-131">Click **New condition** to create a new condition.</span></span> <span data-ttu-id="e103b-132">Cliquez sur le bouton **…** pour modifier la condition.</span><span class="sxs-lookup"><span data-stu-id="e103b-132">Click the ellipsis (**...**) button to modify the condition.</span></span>  
  
 <span data-ttu-id="e103b-133">**Par rapport aux cibles**</span><span class="sxs-lookup"><span data-stu-id="e103b-133">**Against targets**</span></span>  
 <span data-ttu-id="e103b-134">Sélectionnez les types de cibles disponibles pour cette facette afin d'achever une expression de filtre.</span><span class="sxs-lookup"><span data-stu-id="e103b-134">Select the target types that are available for this facet to complete a filter expression.</span></span>  
  
 <span data-ttu-id="e103b-135">**Mode d'évaluation**</span><span class="sxs-lookup"><span data-stu-id="e103b-135">**Evaluation Mode**</span></span>  
 <span data-ttu-id="e103b-136">Sélectionnez le mode d'évaluation à utiliser pour la stratégie.</span><span class="sxs-lookup"><span data-stu-id="e103b-136">Select the evaluation mode for the policy.</span></span> <span data-ttu-id="e103b-137">Certaines stratégies peuvent être vérifiées mais pas appliquées.</span><span class="sxs-lookup"><span data-stu-id="e103b-137">Some policies can be checked but not enforced.</span></span> <span data-ttu-id="e103b-138">Les modes d'évaluation sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="e103b-138">The evaluation modes are as follows:</span></span>  
  
 <span data-ttu-id="e103b-139">**À la demande**</span><span class="sxs-lookup"><span data-stu-id="e103b-139">**On demand**</span></span>  
 <span data-ttu-id="e103b-140">La stratégie n’est exécutée que lorsque vous l’exécutez depuis la boîte de dialogue **Évaluer** .</span><span class="sxs-lookup"><span data-stu-id="e103b-140">Policy will only be run when you run it from the **Evaluate** dialog box.</span></span>  
  
 <span data-ttu-id="e103b-141">**Selon planification**</span><span class="sxs-lookup"><span data-stu-id="e103b-141">**On schedule**</span></span>  
 <span data-ttu-id="e103b-142">Évalue périodiquement la stratégie, enregistre une entrée de journal pour les stratégies non conformes et crée un rapport.</span><span class="sxs-lookup"><span data-stu-id="e103b-142">Periodically evaluates the policy, records a log entry for policies that have out-of-compliance, and creates a report.</span></span> <span data-ttu-id="e103b-143">Active la zone **Planification** .</span><span class="sxs-lookup"><span data-stu-id="e103b-143">Enables the **Schedule** box.</span></span>  
  
 <span data-ttu-id="e103b-144">**Sur modification - Journal uniquement**</span><span class="sxs-lookup"><span data-stu-id="e103b-144">**On change: log only**</span></span>  
 <span data-ttu-id="e103b-145">Lorsque des modifications sont essayées, cette option n'empêche pas les modifications hors de-conformité, mais elle enregistre les violations de stratégie.</span><span class="sxs-lookup"><span data-stu-id="e103b-145">When changes are tried, this option does not prevent out-of-compliance changes, but logs policy violations.</span></span>  
  
 <span data-ttu-id="e103b-146">**Sur modification - Empêcher**</span><span class="sxs-lookup"><span data-stu-id="e103b-146">**On change: prevent**</span></span>  
 <span data-ttu-id="e103b-147">Lorsque des modifications sont essayées, cette option empêche toute modification qui enfreindrait la stratégie.</span><span class="sxs-lookup"><span data-stu-id="e103b-147">When changes are tried, this option prevents changes that would violate the policy.</span></span>  
  
 <span data-ttu-id="e103b-148">**Planification**</span><span class="sxs-lookup"><span data-stu-id="e103b-148">**Schedule**</span></span>  
 <span data-ttu-id="e103b-149">Cette option apparaît lorsque le mode d’évaluation **Selon la planification** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e103b-149">This option appears when **On schedule** evaluation mode is selected.</span></span> <span data-ttu-id="e103b-150">Tapez le nom de la planification, cliquez sur **Choisir** pour sélectionner une planification dans la liste ou sur **Nouveau** pour créer une planification.</span><span class="sxs-lookup"><span data-stu-id="e103b-150">Type the name of the schedule, click **Pick** to select a schedule from a list, or click **New** to create a new schedule.</span></span> <span data-ttu-id="e103b-151">Pour activer la zone de planification, l'option **Selon la planification** doit être sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e103b-151">To enable the schedule area, **On schedule** must be selected.</span></span>  
  
 <span data-ttu-id="e103b-152">**Restriction sur le serveur**</span><span class="sxs-lookup"><span data-stu-id="e103b-152">**Server restriction**</span></span>  
 <span data-ttu-id="e103b-153">Sélectionnez les types de serveurs appropriés pour cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="e103b-153">Select the types of servers that are appropriate for this policy.</span></span> <span data-ttu-id="e103b-154">Vous pouvez choisir **Aucun** ou sélectionner une condition qui filtre les serveurs possibles.</span><span class="sxs-lookup"><span data-stu-id="e103b-154">Options are **None** or select a condition that filters the possible servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e103b-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e103b-155">See Also</span></span>  
 [<span data-ttu-id="e103b-156">Administrer des serveurs à l'aide de la Gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="e103b-156">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
