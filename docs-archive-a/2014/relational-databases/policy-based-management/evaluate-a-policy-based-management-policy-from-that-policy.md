---
title: Évaluer une stratégie de gestion basée sur des stratégies à partir de cette stratégie | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: 0b3214bd-d0ab-45ab-9281-3d95507abe54
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 207c86f1465c49238fc9b50ee75489b43d956caf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611730"
---
# <a name="evaluate-a-policy-based-management-policy-from-that-policy"></a><span data-ttu-id="c7326-102">Évaluer une stratégie de gestion basée sur des stratégies pour cette stratégie</span><span class="sxs-lookup"><span data-stu-id="c7326-102">Evaluate a Policy-Based Management Policy from That Policy</span></span>
  <span data-ttu-id="c7326-103">Cette rubrique explique comment évaluer une stratégie à l'aide de cette stratégie dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7326-103">This topic describes how to evaluate a policy using that policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="c7326-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="c7326-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c7326-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="c7326-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c7326-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c7326-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c7326-107">**Pour évaluer une stratégie à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="c7326-107">**To evaluate a policy, using:**</span></span>  
  
     [<span data-ttu-id="c7326-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c7326-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c7326-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c7326-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c7326-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c7326-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c7326-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c7326-111">Permissions</span></span>  
 <span data-ttu-id="c7326-112">Nécessite l'appartenance au rôle PolicyAdministratorRole dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="c7326-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c7326-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c7326-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy"></a><span data-ttu-id="c7326-114">Pour évaluer une stratégie</span><span class="sxs-lookup"><span data-stu-id="c7326-114">To evaluate a policy</span></span>  
  
1.  <span data-ttu-id="c7326-115">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur qui contient la stratégie que vous souhaitez évaluer.</span><span class="sxs-lookup"><span data-stu-id="c7326-115">In **Object Explorer**, click the plus sign to expand the server that contains the policy that you want to evaluate.</span></span>  
  
2.  <span data-ttu-id="c7326-116">Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="c7326-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="c7326-117">Cliquez sur le signe plus (+) pour développer **Gestion de la stratégie**.</span><span class="sxs-lookup"><span data-stu-id="c7326-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="c7326-118">Cliquez sur le signe plus (+) pour développer le dossier **Stratégies** .</span><span class="sxs-lookup"><span data-stu-id="c7326-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="c7326-119">Cliquez avec le bouton droit sur la stratégie à évaluer, puis sélectionnez **Évaluer**.</span><span class="sxs-lookup"><span data-stu-id="c7326-119">Right-click the policy that you want to evaluate and select **Evaluate**.</span></span>  
  
6.  <span data-ttu-id="c7326-120">La boîte de dialogue **Résultats d'évaluation**  indique les résultats de l'évaluation de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="c7326-120">In the **Evaluate Results**  dialog box, you see the results of the policy evaluation.</span></span> <span data-ttu-id="c7326-121">Pour les cibles qui ne sont pas conformes à la stratégie et ont des propriétés qui peuvent être reconfigurées par la Gestion basée sur des stratégies, vous pouvez imposer la conformité en cliquant sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="c7326-121">For targets that do not comply with the policy and have properties that can be reconfigured by Policy-Based Management, you can enforce compliance by clicking **Apply**.</span></span> <span data-ttu-id="c7326-122">Pour plus d'informations sur les options disponibles de la boîte de dialogue **Évaluer les stratégies** , consultez [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md) et [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md).</span><span class="sxs-lookup"><span data-stu-id="c7326-122">For more information on the available options in the **Evaluate Policies** dialog box, see [Evaluate Policies Dialog Box, Policy Selection Page](evaluate-policies-dialog-box-policy-selection-page.md) and [Evaluate Policies Dialog Box, Evaluation Results Page](evaluate-policies-dialog-box-evaluation-results-page.md).</span></span>  
  
7.  <span data-ttu-id="c7326-123">Lorsque vous avez terminé, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="c7326-123">When finished, click **Close**.</span></span>  
  
  
