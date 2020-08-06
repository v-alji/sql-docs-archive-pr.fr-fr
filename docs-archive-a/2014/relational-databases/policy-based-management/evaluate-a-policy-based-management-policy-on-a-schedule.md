---
title: Évaluer une stratégie de gestion basée sur des stratégies sur une planification | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: bea09522-ff47-4037-ab55-a98ea7c10099
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f1c6b1a7d13d14c02f4b4e537c2dbdb2df39d02c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699461"
---
# <a name="evaluate-a-policy-based-management-policy-on-a-schedule"></a><span data-ttu-id="b8963-102">Évaluer une stratégie de gestion basée sur des stratégies sur une planification</span><span class="sxs-lookup"><span data-stu-id="b8963-102">Evaluate a Policy-Based Management Policy on a Schedule</span></span>
  <span data-ttu-id="b8963-103">Cette rubrique explique comment évaluer une stratégie de gestion basée sur des stratégies sur une planification dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8963-103">This topic describes how to evaluate a Policy-Based Management policy on a schedule in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="b8963-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="b8963-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b8963-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="b8963-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b8963-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b8963-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b8963-107">**Pour évaluer une stratégie sur une planification à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="b8963-107">**To evaluate a policy on a schedule, using:**</span></span>  
  
     [<span data-ttu-id="b8963-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b8963-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b8963-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b8963-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b8963-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b8963-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b8963-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b8963-111">Permissions</span></span>  
 <span data-ttu-id="b8963-112">Nécessite l'appartenance au rôle PolicyAdministratorRole dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="b8963-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b8963-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b8963-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-evaluate-a-policy-on-a-schedule"></a><span data-ttu-id="b8963-114">Pour évaluer une stratégie sur une planification</span><span class="sxs-lookup"><span data-stu-id="b8963-114">To evaluate a policy on a schedule</span></span>  
  
1.  <span data-ttu-id="b8963-115">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur qui contient la planification que vous souhaitez évaluer.</span><span class="sxs-lookup"><span data-stu-id="b8963-115">In **Object Explorer**, click the plus sign to expand the server that contains the policy schedule that you want to evaluate.</span></span>  
  
2.  <span data-ttu-id="b8963-116">Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="b8963-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="b8963-117">Cliquez sur le signe plus (+) pour développer **Gestion de la stratégie**.</span><span class="sxs-lookup"><span data-stu-id="b8963-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="b8963-118">Cliquez sur le signe plus (+) pour développer le dossier **Stratégies** .</span><span class="sxs-lookup"><span data-stu-id="b8963-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="b8963-119">Cliquez avec le bouton droit sur la stratégie dont vous voulez évaluer une planification, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b8963-119">Right-click the policy whose schedule you what to evaluate and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="b8963-120">Dans la boîte de dialogue **Ouvrir une stratégie -** _nom_stratégie_, dans la liste **Mode d’évaluation**, sélectionnez **Selon la planification**.</span><span class="sxs-lookup"><span data-stu-id="b8963-120">On the **Open Policy -**_policy_name_ dialog box, in the **Evaluation Mode** list, select **On schedule**.</span></span>  
  
7.  <span data-ttu-id="b8963-121">Sous **Planification**, cliquez sur **Choisir** pour spécifier une planification existante ou sur **Nouveau** pour créer une planification.</span><span class="sxs-lookup"><span data-stu-id="b8963-121">Under **Schedule**, click either **Pick** to specify an existing schedule or **New** to create a new schedule.</span></span>  
  
8.  <span data-ttu-id="b8963-122">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b8963-122">When finished, click **OK**.</span></span>  
  
  
