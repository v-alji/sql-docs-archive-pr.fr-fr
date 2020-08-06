---
title: Configurer l’option de configuration de serveur priority boost | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- priority boost option
ms.assetid: 765f1e83-dd52-44fb-b0c8-1078f213607b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f42d7d2022e07dcac3039557295dc70e4500583d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603621"
---
# <a name="configure-the-priority-boost-server-configuration-option"></a><span data-ttu-id="03a30-102">Configurer l'option de configuration de serveur priority boost</span><span class="sxs-lookup"><span data-stu-id="03a30-102">Configure the priority boost Server Configuration Option</span></span>
  <span data-ttu-id="03a30-103">Cette rubrique explique comment configurer l'option de configuration **priority boost** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03a30-103">This topic describes how to configure the **priority boost** configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="03a30-104">Utilisez l’option **priority boost** pour spécifier si [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit être exécuté avec un degré plus élevé de priorité de planification [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2008 ou Windows 2008 R2 que pour d’autres processus exécutés sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="03a30-104">Use the **priority boost** option to specify whether [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should run at a higher [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2008 or Windows 2008 R2 scheduling priority than other processes on the same computer.</span></span> <span data-ttu-id="03a30-105">Si la valeur de cette option est égale à 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bénéficie d'une base de priorité de 13 dans le planificateur de Windows 2008 ou Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="03a30-105">If you set this option to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs at a priority base of 13 in the Windows 2008 or Windows Server 2008 R2 scheduler.</span></span> <span data-ttu-id="03a30-106">La valeur par défaut est 0, ce qui représente une base de priorité de 7.</span><span class="sxs-lookup"><span data-stu-id="03a30-106">The default is 0, which is a priority base of 7.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="03a30-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="03a30-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="03a30-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="03a30-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="03a30-109">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="03a30-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="03a30-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="03a30-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="03a30-111">**Pour configurer l'option priority boost, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="03a30-111">**To configure the priority boost option, using:**</span></span>  
  
     [<span data-ttu-id="03a30-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03a30-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="03a30-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03a30-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="03a30-114">**Suivi :**  [Après avoir configuré l’option priority boost](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="03a30-114">**Follow Up:**  [After you configure the priority boost option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="03a30-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="03a30-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="03a30-116">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="03a30-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="03a30-117">Si vous attribuez une valeur trop élevée à la priorité, vous risquez d'épuiser les ressources affectées aux fonctions réseau et aux fonctions du système d'exploitation, ce qui peut entraîner des problèmes lors de l'arrêt de SQL Server ou de l'utilisation d'autres tâches du système d'exploitation sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="03a30-117">Raising the priority too high may drain resources from essential operating system and network functions, resulting in problems shutting down SQL Server or using other operating system tasks on the server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="03a30-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="03a30-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="03a30-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="03a30-119">Permissions</span></span>  
 <span data-ttu-id="03a30-120">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="03a30-120">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="03a30-121">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="03a30-121">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="03a30-122">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="03a30-122">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="03a30-123">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03a30-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-priority-boost-option"></a><span data-ttu-id="03a30-124">Pour configurer l'option priority boost</span><span class="sxs-lookup"><span data-stu-id="03a30-124">To configure the priority boost option</span></span>  
  
1.  <span data-ttu-id="03a30-125">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="03a30-125">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="03a30-126">Cliquez sur le nœud **Processeurs** .</span><span class="sxs-lookup"><span data-stu-id="03a30-126">Click the **Processors** node.</span></span>  
  
3.  <span data-ttu-id="03a30-127">Sous **Threads**, activez la case à cocher **Renforcer la priorité SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="03a30-127">Under **Threads**, select the **Boost SQL Server priority** check box.</span></span>  
  
4.  <span data-ttu-id="03a30-128">Arrêtez puis redémarrez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03a30-128">Stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="03a30-129">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03a30-129">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-priority-boost-option"></a><span data-ttu-id="03a30-130">Pour configurer l'option priority boost</span><span class="sxs-lookup"><span data-stu-id="03a30-130">To configure the priority boost option</span></span>  
  
1.  <span data-ttu-id="03a30-131">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03a30-131">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="03a30-132">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="03a30-132">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="03a30-133">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="03a30-133">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="03a30-134">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `priority boost` la valeur `1`.</span><span class="sxs-lookup"><span data-stu-id="03a30-134">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `priority boost` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'priority boost', 1 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="03a30-135">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="03a30-135">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-priority-boost-option"></a><a name="FollowUp"></a> <span data-ttu-id="03a30-136">Suivi : Après avoir configuré l’option priority boost</span><span class="sxs-lookup"><span data-stu-id="03a30-136">Follow Up: After you configure the priority boost option</span></span>  
 <span data-ttu-id="03a30-137">Le serveur doit être redémarré pour que le paramètre puisse être effet.</span><span class="sxs-lookup"><span data-stu-id="03a30-137">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03a30-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="03a30-138">See Also</span></span>  
 <span data-ttu-id="03a30-139">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="03a30-139">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="03a30-140">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="03a30-140">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="03a30-141">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="03a30-141">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
