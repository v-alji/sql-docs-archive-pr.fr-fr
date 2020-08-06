---
title: Supprimer une condition de gestion basée sur des stratégies | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, delete policy conditions
ms.assetid: e04148b8-f6dd-4c50-a5ef-c650b71dbf4d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f02a5294ecb53db4d8baa4f3dae0a232d9551a13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600842"
---
# <a name="delete-a-policy-based-management-condition"></a><span data-ttu-id="6357e-102">Supprimer une condition de gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="6357e-102">Delete a Policy-Based Management Condition</span></span>
  <span data-ttu-id="6357e-103">Cette rubrique explique comment supprimer une condition de gestion basée sur des stratégies dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6357e-103">This topic describes how to delete a Policy-based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="6357e-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="6357e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6357e-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="6357e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6357e-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="6357e-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6357e-107">**Pour supprimer une condition à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="6357e-107">**To delete a condition, using:**</span></span>  
  
     [<span data-ttu-id="6357e-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6357e-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6357e-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="6357e-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6357e-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="6357e-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6357e-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="6357e-111">Permissions</span></span>  
 <span data-ttu-id="6357e-112">Nécessite l'appartenance au rôle PolicyAdministratorRole dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="6357e-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6357e-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6357e-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-condition"></a><span data-ttu-id="6357e-114">Pour supprimer une condition</span><span class="sxs-lookup"><span data-stu-id="6357e-114">To delete a condition</span></span>  
  
1.  <span data-ttu-id="6357e-115">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur qui contient la condition que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="6357e-115">In **Object Explorer**, click the plus sign to expand the server that contains the condition that you want to delete.</span></span>  
  
2.  <span data-ttu-id="6357e-116">Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="6357e-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="6357e-117">Cliquez sur le signe plus (+) pour développer **Gestion de la stratégie**.</span><span class="sxs-lookup"><span data-stu-id="6357e-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="6357e-118">Cliquez sur le signe plus (+) pour développer le dossier **Conditions** .</span><span class="sxs-lookup"><span data-stu-id="6357e-118">Click the plus sign to expand the **Conditions** folder.</span></span>  
  
5.  <span data-ttu-id="6357e-119">Cliquez avec le bouton droit sur la condition à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="6357e-119">Right-click the condition that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="6357e-120">Dans la boîte de dialogue **Supprimer un objet** , assurez-vous que la condition correcte est sélectionnée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6357e-120">In the **Delete Object** dialog box, ensure that the correct condition is selected and then click **OK**.</span></span>  
  
  
