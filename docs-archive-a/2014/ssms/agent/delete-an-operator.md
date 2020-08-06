---
title: Supprimer un opérateur | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- canceling operators
- removing operators
- deleting operators
- dropping operators
- jobs [SQL Server Agent], operators
- operators (users) [Database Engine], deleting with Management Studio
ms.assetid: 2b7b8627-082d-4189-8584-abd3a9b604cf
author: stevestein
ms.author: sstein
ms.openlocfilehash: 75bea1c5c5fabff7ce55fe07a5181baa8f99e0fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601263"
---
# <a name="delete-an-operator"></a><span data-ttu-id="ed2cb-102">Delete an Operator</span><span class="sxs-lookup"><span data-stu-id="ed2cb-102">Delete an Operator</span></span>
  <span data-ttu-id="ed2cb-103">Cette rubrique explique comment supprimer un opérateur afin qu’il ne reçoive plus [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de notifications d’alerte de l’agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed2cb-103">This topic describes how to remove an operator so they no longer receive [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ed2cb-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="ed2cb-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ed2cb-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="ed2cb-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ed2cb-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="ed2cb-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ed2cb-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ed2cb-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ed2cb-108">**Pour supprimer un opérateur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="ed2cb-108">**To delete an operator, using:**</span></span>  
  
     [<span data-ttu-id="ed2cb-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ed2cb-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ed2cb-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ed2cb-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ed2cb-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ed2cb-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ed2cb-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="ed2cb-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="ed2cb-113">Si vous supprimez un opérateur, toutes les notifications qui lui sont associées le sont également.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-113">When an operator is removed, all the notifications associated with the operator are also removed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ed2cb-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ed2cb-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ed2cb-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="ed2cb-115">Permissions</span></span>  
 <span data-ttu-id="ed2cb-116">Les membres du rôle serveur fixe **sysadmin** peuvent supprimer des opérateurs.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-116">Members of the **sysadmin** fixed server role can delete operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ed2cb-117">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ed2cb-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-operator"></a><span data-ttu-id="ed2cb-118">Pour supprimer un opérateur</span><span class="sxs-lookup"><span data-stu-id="ed2cb-118">To delete an operator</span></span>  
  
1.  <span data-ttu-id="ed2cb-119">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur qui contient l'opérateur que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-119">In **Object Explorer**, click the plus sign to expand the server that contains the operator you want to delete.</span></span>  
  
2.  <span data-ttu-id="ed2cb-120">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="ed2cb-121">Cliquez sur le signe plus (+) pour développer le dossier **Opérateurs** .</span><span class="sxs-lookup"><span data-stu-id="ed2cb-121">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="ed2cb-122">Cliquez avec le bouton droit sur l’opérateur à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-122">Right-click the operator that you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="ed2cb-123">Dans la boîte de dialogue **Supprimer un objet** , assurez-vous que l'opérateur correct est sélectionné, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-123">In the **Delete Object** dialog box, make sure that the correct operator is selected, and then click **OK**.</span></span> <span data-ttu-id="ed2cb-124">Si vous voulez qu'un autre opérateur reçoive les alertes et les travaux envoyés à l'opérateur supprimé, activez l'option **Réaffecter à** et sélectionnez un opérateur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-124">If you want another operator to receive the alerts and jobs sent to the deleted operator, check **Reassign to** and select an operator in the list.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ed2cb-125">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ed2cb-125">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-operator"></a><span data-ttu-id="ed2cb-126">Pour supprimer un opérateur</span><span class="sxs-lookup"><span data-stu-id="ed2cb-126">To delete an operator</span></span>  
  
1.  <span data-ttu-id="ed2cb-127">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed2cb-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ed2cb-128">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ed2cb-129">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ed2cb-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- deletes operator 'Test Operator' and reassigns all alerts and jobs sent to that operator to 'Fran??ois Ajenstat'  
    USE msdb ;  
    GO  
  
    EXEC sp_delete_operator @name = 'Test Operator',  
        @reassign_to_operator = 'Fran??ois Ajenstat';  
    GO  
    ```  
  
 <span data-ttu-id="ed2cb-130">Pour plus d’informations, consultez [sp_delete_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ed2cb-130">For more information, see [sp_delete_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-operator-transact-sql).</span></span>  
  
  
