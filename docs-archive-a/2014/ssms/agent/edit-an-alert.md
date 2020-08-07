---
title: Modifier une alerte | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], modifying
- modifying alerts
ms.assetid: f518e528-cc8f-446a-b37d-98505b86e430
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1eae606b3c2ca4c18d088e650e774986d4e31387
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610950"
---
# <a name="edit-an-alert"></a><span data-ttu-id="b5d62-102">Modifier une alerte</span><span class="sxs-lookup"><span data-stu-id="b5d62-102">Edit an Alert</span></span>
  <span data-ttu-id="b5d62-103">Cette rubrique explique comment modifier une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerte de l’agent dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b5d62-103">This topic describes how to edit a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b5d62-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="b5d62-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b5d62-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="b5d62-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b5d62-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b5d62-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b5d62-107">**Pour modifier une alerte, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="b5d62-107">**To edit an alert, using:**</span></span>  
  
     [<span data-ttu-id="b5d62-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b5d62-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b5d62-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b5d62-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b5d62-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b5d62-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b5d62-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b5d62-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b5d62-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b5d62-112">Permissions</span></span>  
 <span data-ttu-id="b5d62-113">Par défaut, les membres du rôle serveur fixe **sysadmin** peuvent modifier les informations dans une alerte.</span><span class="sxs-lookup"><span data-stu-id="b5d62-113">By default, members of the **sysadmin** fixed server role can edit information in an alert.</span></span> <span data-ttu-id="b5d62-114">Les autres utilisateurs doivent disposer du rôle de base de données fixe **SQLAgentOperatorRole** dans la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="b5d62-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b5d62-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b5d62-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-edit-an-alert"></a><span data-ttu-id="b5d62-116">Pour modifier une alerte</span><span class="sxs-lookup"><span data-stu-id="b5d62-116">To edit an alert</span></span>  
  
1.  <span data-ttu-id="b5d62-117">Dans l' **Explorateur d'objets** , cliquez sur le signe plus (+) pour développer le serveur contenant l'alerte que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="b5d62-117">In **Object Explorer,** click the plus sign to expand the server containing the alert you want to edit.</span></span>  
  
2.  <span data-ttu-id="b5d62-118">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="b5d62-119">Cliquez sur le signe plus (+) pour développer le dossier **Alertes** .</span><span class="sxs-lookup"><span data-stu-id="b5d62-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="b5d62-120">Cliquez avec le bouton droit sur l’alerte à modifier, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-120">Right-click the alert you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="b5d62-121">Mettez à jour les propriétés de l'alerte dans les pages **Général**, **Réponse**et **Options** .</span><span class="sxs-lookup"><span data-stu-id="b5d62-121">Update the alert properties on the **General**, **Response**, and **Options** pages.</span></span>  
  
6.  <span data-ttu-id="b5d62-122">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-122">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b5d62-123">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b5d62-123">Using Transact-SQL</span></span>  
  
#### <a name="to-edit-an-alert"></a><span data-ttu-id="b5d62-124">Pour modifier une alerte</span><span class="sxs-lookup"><span data-stu-id="b5d62-124">To edit an alert</span></span>  
  
1.  <span data-ttu-id="b5d62-125">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5d62-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b5d62-126">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b5d62-127">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="b5d62-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled setting of Test Alert to 0  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_alert  
        @name = N'Test Alert',  
        @enabled = 0 ;  
    GO  
    ```  
  
 <span data-ttu-id="b5d62-128">Pour plus d’informations, consultez [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b5d62-128">For more information, see [sp_update_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql).</span></span>  
  
  
