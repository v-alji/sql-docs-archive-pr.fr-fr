---
title: Désactiver ou réactiver une alerte | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], reactivating
- deleting alerts
- canceling alerts
- dropping alerts
- disabling alerts
- alerts [SQL Server], disabling
- reactivating alerts
- removing alerts
ms.assetid: 4cb37dc6-1134-405d-8590-58b44dcf63b2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3eec4ea7288f4847c0e9b861d80f23eb9c9ddba8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703755"
---
# <a name="disable-or-reactivate-an-alert"></a><span data-ttu-id="1a827-102">Disable or Reactivate an Alert</span><span class="sxs-lookup"><span data-stu-id="1a827-102">Disable or Reactivate an Alert</span></span>
  <span data-ttu-id="1a827-103">Cette rubrique explique comment désactiver ou réactiver une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerte de l’agent dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a827-103">This topic describes how to disable or reactivate a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="1a827-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="1a827-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1a827-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="1a827-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1a827-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="1a827-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1a827-107">**Pour désactiver ou réactiver une alerte, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="1a827-107">**To disable or reactivate an alert, using:**</span></span>  
  
     [<span data-ttu-id="1a827-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a827-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1a827-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1a827-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1a827-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="1a827-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1a827-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="1a827-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1a827-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="1a827-112">Permissions</span></span>  
 <span data-ttu-id="1a827-113">Par défaut, les membres du rôle serveur fixe **sysadmin** peuvent modifier les informations dans une alerte.</span><span class="sxs-lookup"><span data-stu-id="1a827-113">By default, members of the **sysadmin** fixed server role can edit information in an alert.</span></span> <span data-ttu-id="1a827-114">Les autres utilisateurs doivent disposer du rôle de base de données fixe **SQLAgentOperatorRole** dans la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="1a827-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1a827-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a827-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-reactivate-an-alert"></a><span data-ttu-id="1a827-116">Pour désactiver ou réactiver une alerte</span><span class="sxs-lookup"><span data-stu-id="1a827-116">To disable or reactivate an alert</span></span>  
  
1.  <span data-ttu-id="1a827-117">Dans **Explorateur d'objets**, cliquez sur le signe plus pour développer le serveur qui contient l'alerte que vous souhaitez désactiver ou réactiver.</span><span class="sxs-lookup"><span data-stu-id="1a827-117">In **Object Explorer**, click the plus sign to expand server that contains the alert you wish to disable or reactivate.</span></span>  
  
2.  <span data-ttu-id="1a827-118">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="1a827-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="1a827-119">Cliquez sur le signe plus (+) pour développer le dossier **Alertes** .</span><span class="sxs-lookup"><span data-stu-id="1a827-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="1a827-120">Cliquez avec le bouton droit sur l’alerte que vous souhaitez activer, puis sélectionnez **Activer** . Pour désactiver une alerte, cliquez avec le bouton droit sur l’alerte à désactiver, puis sélectionnez **Désactiver**.</span><span class="sxs-lookup"><span data-stu-id="1a827-120">Right-click the alert you wish to enable and select **Enable** To disable an alert, right-click the alert you want to disable and select **Disable**.</span></span>  
  
5.  <span data-ttu-id="1a827-121">La boîte de dialogue **Désactiver les alertes** ou **Activer les alertes** s'affiche en indiquant l'état du processus.</span><span class="sxs-lookup"><span data-stu-id="1a827-121">The **Disable Alert** or **Enable Alert** dialog box displays showing the status of the process.</span></span> <span data-ttu-id="1a827-122">Lorsque vous avez terminé, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="1a827-122">When finished, click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1a827-123">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1a827-123">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-reactivate-an-alert"></a><span data-ttu-id="1a827-124">Pour désactiver ou réactiver une alerte</span><span class="sxs-lookup"><span data-stu-id="1a827-124">To disable or reactivate an alert</span></span>  
  
1.  <span data-ttu-id="1a827-125">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a827-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1a827-126">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="1a827-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1a827-127">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="1a827-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled setting of Test Alert to 0  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_alert  
        @name = N'Test Alert',  
        @enabled = 0 ;  
    GO  
    ```  
  
 <span data-ttu-id="1a827-128">Pour plus d’informations, consultez [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1a827-128">For more information, see [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span></span>  
  
  
