---
title: Évaluer une stratégie de gestion basée sur des stratégies à partir d’un objet | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: b9e9d646-4894-4dee-a02a-0c71a8dc020e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f0de02092c87a727b723a5940805f34a75052e5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611728"
---
# <a name="evaluate-a-policy-based-management-policy-from-an-object"></a><span data-ttu-id="71d92-102">Évaluer une stratégie de gestion basée sur des stratégies à partir d'un objet</span><span class="sxs-lookup"><span data-stu-id="71d92-102">Evaluate a Policy-Based Management Policy from an Object</span></span>
  <span data-ttu-id="71d92-103">Cette rubrique explique comment évaluer une stratégie d'une instance de serveur, d'une base de données ou d'un objet de base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71d92-103">This topic describes how to evaluate a policy from a server instance, database, or database object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="71d92-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="71d92-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="71d92-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="71d92-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="71d92-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="71d92-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="71d92-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="71d92-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="71d92-108">**Pour évaluer une stratégie à partir d'un objet à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="71d92-108">**To evaluate a policy from an object, using:**</span></span>  
  
     [<span data-ttu-id="71d92-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="71d92-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="71d92-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="71d92-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="71d92-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="71d92-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="71d92-112">Le mode d'exécution est défini dans le cadre de la stratégie et ne peut pas être modifié dans la boîte de dialogue **Évaluer les stratégies** .</span><span class="sxs-lookup"><span data-stu-id="71d92-112">The execution mode is defined as part of the policy and cannot be changed in the **Evaluate Policies** dialog box.</span></span>  
  
-   <span data-ttu-id="71d92-113">La boîte de dialogue **Évaluer les stratégies** affiche seulement les stratégies appropriées à l'objet de base de données.</span><span class="sxs-lookup"><span data-stu-id="71d92-113">The **Evaluate Policies** dialog box only shows policies appropriate for the database object.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="71d92-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="71d92-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="71d92-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="71d92-115">Permissions</span></span>  
 <span data-ttu-id="71d92-116">Nécessite l'appartenance au rôle PolicyAdministratorRole dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="71d92-116">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="71d92-117">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="71d92-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy-from-an-object"></a><span data-ttu-id="71d92-118">Pour évaluer une stratégie à partir d'un objet</span><span class="sxs-lookup"><span data-stu-id="71d92-118">To evaluate a policy from an object</span></span>  
  
1.  <span data-ttu-id="71d92-119">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur une instance de serveur, une base de données ou un objet de base de données, pointez sur **Stratégies**, puis sélectionnez **Évaluer**.</span><span class="sxs-lookup"><span data-stu-id="71d92-119">In Object Explorer, right-click a server instance, a database, or a database object, point to **Policies**, and select **Evaluate**.</span></span>  
  
2.  <span data-ttu-id="71d92-120">Dans la boîte de dialogue **Évaluer les stratégies** , sélectionnez une ou plusieurs stratégies, puis cliquez sur **Évaluer** pour exécuter la stratégie en mode d'évaluation.</span><span class="sxs-lookup"><span data-stu-id="71d92-120">In the **Evaluate Policies** dialog box, select one or more policies and click **Evaluate** to run the policy in evaluation mode.</span></span> <span data-ttu-id="71d92-121">Cela génère un rapport de conformité pour le jeu de cibles mais n'applique pas la conformité future et ne reconfigure pas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71d92-121">This generates a compliance report for the target set but does not reconfigure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or enforce future compliance.</span></span> <span data-ttu-id="71d92-122">Pour les cibles qui ne sont pas conformes aux stratégies sélectionnées et ont des propriétés qui peuvent être reconfigurées par la Gestion basée sur des stratégies, vous pouvez imposer la conformité aux stratégies en cliquant sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="71d92-122">For targets that do not comply with the selected policies and have properties that can be reconfigured by Policy-Based Management, you can enforce policy compliance by clicking **Apply**.</span></span> <span data-ttu-id="71d92-123">Pour plus d'informations sur les options disponibles de la boîte de dialogue **Évaluer les stratégies** , consultez [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md), [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md)et [Results Detailed View Dialog Box](results-detailed-view-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="71d92-123">For more information on the available options in the **Evaluate Policies** dialog box, see [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md), [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md), and [Results Detailed View Dialog Box](results-detailed-view-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="71d92-124">Lorsque vous avez terminé, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="71d92-124">When finished, click **Close**.</span></span>  
  
  
