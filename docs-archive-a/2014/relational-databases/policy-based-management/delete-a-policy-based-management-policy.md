---
title: Supprimer une stratégie de gestion basée sur des stratégies | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, delete policies
ms.assetid: 488f0305-190c-4223-aa5c-e9bd43b520eb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c43bc3cdf4a7a5b5d9268bbd7e68506616d1f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695571"
---
# <a name="delete-a-policy-based-management-policy"></a><span data-ttu-id="2a857-102">Supprimer une stratégie de gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="2a857-102">Delete a Policy-Based Management Policy</span></span>
  <span data-ttu-id="2a857-103">Cette rubrique explique comment supprimer une stratégie de gestion basée sur des stratégies dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a857-103">This topic describes how to delete a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2a857-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="2a857-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2a857-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="2a857-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2a857-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2a857-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2a857-107">**Pour supprimer une stratégie à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="2a857-107">**To delete a policy, using:**</span></span>  
  
     [<span data-ttu-id="2a857-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2a857-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2a857-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2a857-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2a857-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2a857-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2a857-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2a857-111">Permissions</span></span>  
 <span data-ttu-id="2a857-112">Nécessite l'appartenance au rôle PolicyAdministratorRole dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="2a857-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2a857-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2a857-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-policy"></a><span data-ttu-id="2a857-114">Pour supprimer une stratégie</span><span class="sxs-lookup"><span data-stu-id="2a857-114">To delete a policy</span></span>  
  
1.  <span data-ttu-id="2a857-115">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer la stratégie de gestion basée sur des stratégies que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="2a857-115">In Object Explorer, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to delete.</span></span>  
  
2.  <span data-ttu-id="2a857-116">Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="2a857-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="2a857-117">Cliquez sur le signe plus (+) pour développer **Gestion de la stratégie**.</span><span class="sxs-lookup"><span data-stu-id="2a857-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="2a857-118">Cliquez sur le signe plus (+) pour développer le dossier **Stratégies** .</span><span class="sxs-lookup"><span data-stu-id="2a857-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="2a857-119">Cliquez avec le bouton droit sur la stratégie à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="2a857-119">Right-click the policy that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="2a857-120">Dans la boîte de dialogue **Supprimer un objet** , assurez-vous que la condition correcte est sélectionnée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a857-120">In the **Delete Object** dialog box, ensure that the correct condition is selected and then click **OK**.</span></span>  
  
  
