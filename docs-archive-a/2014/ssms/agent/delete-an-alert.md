---
title: Supprimer une alerte | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- alerts [SQL Server], deleting
- deleting alerts
- canceling alerts
- dropping alerts
- disabling alerts
- removing alerts
ms.assetid: c982b208-e2d1-4d34-8cee-940b9baf6586
author: stevestein
ms.author: sstein
ms.openlocfilehash: 15fdae19b150a5a06a32e91ec1947a0acfa5f900
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612063"
---
# <a name="delete-an-alert"></a><span data-ttu-id="a4798-102">Supprimer une alerte</span><span class="sxs-lookup"><span data-stu-id="a4798-102">Delete an Alert</span></span>
  <span data-ttu-id="a4798-103">Cette rubrique explique comment supprimer [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] des alertes de l’agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a4798-103">This topic describes how to delete [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a4798-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="a4798-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a4798-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="a4798-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a4798-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="a4798-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a4798-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a4798-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a4798-108">**Pour supprimer une alerte, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="a4798-108">**To delete an alert, using:**</span></span>  
  
     [<span data-ttu-id="a4798-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a4798-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a4798-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a4798-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a4798-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="a4798-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a4798-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="a4798-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a4798-113">En supprimant une alerte, vous supprimez également toute notification associée à celle-ci.</span><span class="sxs-lookup"><span data-stu-id="a4798-113">Removing an alert also removes any notifications associated with the alert.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a4798-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a4798-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a4798-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="a4798-115">Permissions</span></span>  
 <span data-ttu-id="a4798-116">Par défaut, seuls les membres du rôle serveur fixe **sysadmin** peuvent supprimer des alertes.</span><span class="sxs-lookup"><span data-stu-id="a4798-116">By default, only members of the **sysadmin** fixed server role can delete alerts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a4798-117">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a4798-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-alert"></a><span data-ttu-id="a4798-118">Pour supprimer une alerte</span><span class="sxs-lookup"><span data-stu-id="a4798-118">To delete an alert</span></span>  
  
1.  <span data-ttu-id="a4798-119">Dans l' **Explorateur d'objets** , cliquez sur le signe plus (+) pour développer le serveur qui contient l'alerte de SQL Server Agent que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="a4798-119">In **Object Explorer,** click the plus sign to expand the server that contains the SQL Server Agent alert that you want to delete.</span></span>  
  
2.  <span data-ttu-id="a4798-120">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a4798-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="a4798-121">Cliquez sur le signe plus (+) pour développer le dossier **Alertes** .</span><span class="sxs-lookup"><span data-stu-id="a4798-121">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="a4798-122">Cliquez avec le bouton droit sur l’alerte à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="a4798-122">Right-click the alert you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="a4798-123">Dans la boîte de dialogue **Supprimer un objet** , confirmez que l'alerte correcte est sélectionnée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4798-123">In the **Delete Object** dialog box, confirm that the correct alert is selected and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a4798-124">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a4798-124">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-alert"></a><span data-ttu-id="a4798-125">Pour supprimer une alerte</span><span class="sxs-lookup"><span data-stu-id="a4798-125">To delete an alert</span></span>  
  
1.  <span data-ttu-id="a4798-126">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4798-126">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a4798-127">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="a4798-127">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a4798-128">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a4798-128">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes the SQL Server Agent alert called 'Test Alert.'  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_alert  
       @name = N'Test Alert' ;  
    GO  
    ```  
  
 <span data-ttu-id="a4798-129">Pour plus d’informations, consultez s[sp_delete_alert &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-delete-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a4798-129">For more information, see s[sp_delete_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-alert-transact-sql).</span></span>  
  
  
