---
title: Créer une stratégie de gestion basée sur des stratégies | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, creating policies
ms.assetid: b28bf963-89f9-4941-b6c1-6004fec347f1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e76b4dce17e00bae5e8ca4fcf071868c0641c786
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610624"
---
# <a name="create-a-policy-based-management-policy"></a><span data-ttu-id="41df2-102">Créer une stratégie de gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="41df2-102">Create a Policy-Based Management Policy</span></span>
  <span data-ttu-id="41df2-103">Cette rubrique explique comment créer une stratégie de gestion basée sur des stratégies dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41df2-103">This topic describes how to create a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="41df2-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="41df2-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="41df2-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="41df2-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="41df2-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="41df2-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="41df2-107">**Pour créer une stratégie à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="41df2-107">**To create a policy, using:**</span></span>  
  
     [<span data-ttu-id="41df2-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="41df2-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="41df2-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="41df2-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="41df2-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="41df2-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="41df2-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="41df2-111">Permissions</span></span>  
 <span data-ttu-id="41df2-112">Nécessite l'appartenance au rôle PolicyAdministratorRole dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="41df2-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="41df2-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="41df2-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-policy"></a><span data-ttu-id="41df2-114">Pour créer une stratégie</span><span class="sxs-lookup"><span data-stu-id="41df2-114">To create a policy</span></span>  
  
1.  <span data-ttu-id="41df2-115">Dans l’ **Explorateur d’objets**, cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez créer une nouvelle stratégie de gestion basées sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="41df2-115">In **Object Explorer**, click the plus sign to expand the server where you want to create a new a Policy-Based Management policy.</span></span>  
  
2.  <span data-ttu-id="41df2-116">Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="41df2-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="41df2-117">Cliquez sur le signe plus (+) pour développer **Gestion de la stratégie**.</span><span class="sxs-lookup"><span data-stu-id="41df2-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="41df2-118">Cliquez avec le bouton droit sur le dossier **Stratégies** et sélectionnez **Nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="41df2-118">Right-click the **Policies** folder and select **New Policy**.</span></span>  
  
5.  <span data-ttu-id="41df2-119">Dans la boîte de dialogue **Créer une nouvelle stratégie** , dans la zone **Nom** , tapez le nom de la nouvelle stratégie.</span><span class="sxs-lookup"><span data-stu-id="41df2-119">In the **Create New Policy** dialog box, in the **Name** box, type the name of the new policy.</span></span>  
  
6.  <span data-ttu-id="41df2-120">Si vous souhaitez que la stratégie soit activée dès sa création, activez la case à cocher **Activé** .</span><span class="sxs-lookup"><span data-stu-id="41df2-120">If you want the policy to be enabled as soon as it is created, select the **Enabled** check box.</span></span> <span data-ttu-id="41df2-121">Si le mode d'évaluation est **À la demande**, la case à cocher **Activé** n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="41df2-121">If the evaluation mode is **On demand**, the **Enabled** check box is not available.</span></span>  
  
7.  <span data-ttu-id="41df2-122">Dans la liste **Vérifier la condition** , sélectionnez l'une des conditions existantes ou sélectionnez **Nouvelle condition**.</span><span class="sxs-lookup"><span data-stu-id="41df2-122">In the **Check condition** list, select one of the existing conditions, or select **New Condition**.</span></span> <span data-ttu-id="41df2-123">Pour modifier une condition, sélectionnez-la, puis cliquez sur le bouton de sélection ( **...** ). Pour plus d’informations, consultez [Créer une condition de gestion basée sur des stratégies.](create-a-new-policy-based-management-condition.md) ou [Afficher ou modifier les propriétés d’une condition de gestion basée sur des stratégies](view-or-modify-the-properties-of-a-policy-based-management-condition.md).</span><span class="sxs-lookup"><span data-stu-id="41df2-123">To edit a condition, select the condition and then click the ellipsis (**...**). For more information, see [Create a New Policy-Based Management Condition](create-a-new-policy-based-management-condition.md) or [View or Modify the Properties of a Policy-Based Management Condition](view-or-modify-the-properties-of-a-policy-based-management-condition.md).</span></span>  
  
8.  <span data-ttu-id="41df2-124">Dans la zone **Par rapport aux cibles** , sélectionnez un ou plusieurs types de cibles pour cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="41df2-124">In the **Against targets** box, select one or more target types for this policy.</span></span> <span data-ttu-id="41df2-125">Certaines conditions et facettes peuvent être appliquées uniquement à certains types de cibles.</span><span class="sxs-lookup"><span data-stu-id="41df2-125">Some conditions and facets can only be applied to certain types of targets.</span></span> <span data-ttu-id="41df2-126">Les jeux de cibles disponibles apparaissent dans la zone associée.</span><span class="sxs-lookup"><span data-stu-id="41df2-126">The available target sets appear in the associated box.</span></span> <span data-ttu-id="41df2-127">Développez **Toutes les** pour sélectionner une condition de filtrage pour certains types des cibles.</span><span class="sxs-lookup"><span data-stu-id="41df2-127">Expand **Every** to select a filtering condition for some types of the targets.</span></span> <span data-ttu-id="41df2-128">Si aucune cible n'apparaît dans cette zone, la portée de la condition de vérification est le niveau serveur.</span><span class="sxs-lookup"><span data-stu-id="41df2-128">If no targets appear in this box, the check condition is scoped at the server level.</span></span>  
  
9. <span data-ttu-id="41df2-129">Dans la zone **Mode d'évaluation** , sélectionnez le comportement de cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="41df2-129">In the **Evaluation Mode** box, select how this policy will behave.</span></span> <span data-ttu-id="41df2-130">Différentes conditions peuvent avoir différents modes d'évaluation valides.</span><span class="sxs-lookup"><span data-stu-id="41df2-130">Different conditions can have different valid evaluation modes.</span></span> <span data-ttu-id="41df2-131">Pour plus d’informations sur les modes d’évaluation valides, consultez [Administrer des serveurs à l’aide de la gestion basée sur des stratégies](administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="41df2-131">For more information about which evaluation modes are valid, see [Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md).</span></span>  
  
10. <span data-ttu-id="41df2-132">Si la stratégie doit être évaluée selon une planification, définissez le mode d'évaluation sur la valeur **Selon la planification**, puis cliquez sur **Choisir** pour sélectionner une planification, ou cliquez sur **Nouvelle** pour créer une planification.</span><span class="sxs-lookup"><span data-stu-id="41df2-132">If the policy will be evaluated on a schedule, set the evaluation mode to **On schedule**, and then click **Pick** to select a schedule, or click **New** to create a new schedule.</span></span>  
  
11. <span data-ttu-id="41df2-133">Pour limiter la stratégie au sous-ensemble des types cibles, dans la zone **Restriction sur le serveur** , sélectionnez une condition de limitation ou créez-en une.</span><span class="sxs-lookup"><span data-stu-id="41df2-133">To limit the policy to subset of the target types, in the **Server restriction** box, select from limiting conditions or create a new condition.</span></span>  
  
     <span data-ttu-id="41df2-134">Pour plus d'informations sur les options disponibles de la boîte de dialogue **Créer une nouvelle stratégie** , consultez [Boîte de dialogue Créer une nouvelle stratégie ou Ouvrir une stratégie, page Général](../../integration-services/general-page-of-integration-services-designers-options.md) ou [Boîte de dialogue Créer une nouvelle stratégie ou Ouvrir une stratégie, page Description](create-new-policy-or-open-policy-dialog-box-description-page.md).</span><span class="sxs-lookup"><span data-stu-id="41df2-134">For more information on the available options in the **Create New Policy** dialog box, see [Create New Policy or Open Policy Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md) or [Create New Policy or Open Policy Dialog Box, Description Page](create-new-policy-or-open-policy-dialog-box-description-page.md).</span></span>  
  
12. <span data-ttu-id="41df2-135">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="41df2-135">When finished click **OK**.</span></span>  
  
  
