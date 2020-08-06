---
title: Configurer l’option de configuration de serveur nested triggers | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- nested triggers option
ms.assetid: 29d7372b-d406-4a5b-80c6-a2d231d25211
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7b27e185b0833f2e51be16393ff4d59a81046970
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611299"
---
# <a name="configure-the-nested-triggers-server-configuration-option"></a><span data-ttu-id="fec2a-102">Configurer l'option de configuration de serveur nested triggers</span><span class="sxs-lookup"><span data-stu-id="fec2a-102">Configure the nested triggers Server Configuration Option</span></span>
  <span data-ttu-id="fec2a-103">Cette rubrique explique comment configurer l'option de configuration de serveur **nested triggers** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fec2a-103">This topic describes how to configure the **nested triggers** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="fec2a-104">L'option **Déclencheurs imbriqués** contrôle si un déclencheur AFTER peut s'exécuter en cascade,</span><span class="sxs-lookup"><span data-stu-id="fec2a-104">The **nested triggers** option controls whether an AFTER trigger can cascade.</span></span> <span data-ttu-id="fec2a-105">autrement dit, effectuer une action qui active un autre déclencheur, qui active un autre déclencheur, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="fec2a-105">That is, perform an action that initiates another trigger, which initiates another trigger, and so on.</span></span> <span data-ttu-id="fec2a-106">Lorsque l'option **nested triggers** a la valeur 0, les déclencheurs AFTER ne peuvent pas s'exécuter en cascade.</span><span class="sxs-lookup"><span data-stu-id="fec2a-106">When **nested triggers** is set to 0, AFTER triggers cannot cascade.</span></span> <span data-ttu-id="fec2a-107">Quand l’option **nested triggers** a la valeur 1 (valeur par défaut), les déclencheurs AFTER peuvent s’exécuter en cascade sur un maximum de 32 niveaux.</span><span class="sxs-lookup"><span data-stu-id="fec2a-107">When **nested triggers** is set to 1 (the default), AFTER triggers can cascade to as many as 32 levels.</span></span> <span data-ttu-id="fec2a-108">Les déclencheurs INSTEAD OF peuvent être imbriqués quel que soit le paramétrage de cette option.</span><span class="sxs-lookup"><span data-stu-id="fec2a-108">INSTEAD OF triggers can be nested regardless of the setting of this option.</span></span>  
  
 <span data-ttu-id="fec2a-109">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="fec2a-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fec2a-110">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="fec2a-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fec2a-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="fec2a-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fec2a-112">**Pour configurer l'option nested triggers, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="fec2a-112">**To configure the nested triggers option, using:**</span></span>  
  
     [<span data-ttu-id="fec2a-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fec2a-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fec2a-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fec2a-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="fec2a-115">**Suivi :**  [Après avoir configuré l’option nested triggers](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="fec2a-115">**Follow Up:**  [After you configure the nested triggers option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fec2a-116">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="fec2a-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fec2a-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="fec2a-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fec2a-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="fec2a-118">Permissions</span></span>  
 <span data-ttu-id="fec2a-119">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fec2a-119">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="fec2a-120">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="fec2a-120">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="fec2a-121">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="fec2a-121">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fec2a-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fec2a-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-nested-triggers-option"></a><span data-ttu-id="fec2a-123">Pour configurer l’option nested triggers</span><span class="sxs-lookup"><span data-stu-id="fec2a-123">To configure the nested triggers option</span></span>  
  
1.  <span data-ttu-id="fec2a-124">Dans **l’Explorateur d’objets**, cliquez avec le bouton droit sur un serveur, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="fec2a-124">In **Object Explorer**, right-click a server, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="fec2a-125">Dans la page **Avancées** , attribuez à l’option **Autoriser les déclencheurs à activer d’autres déclencheurs** la valeur **True** (valeur par défaut) ou **False**.</span><span class="sxs-lookup"><span data-stu-id="fec2a-125">On the **Advanced** page, set the **Allow Triggers to Fire Others** option to **True** (the default) or **False**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fec2a-126">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fec2a-126">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-nested-triggers-option"></a><span data-ttu-id="fec2a-127">Pour configurer l’option nested triggers</span><span class="sxs-lookup"><span data-stu-id="fec2a-127">To configure the nested triggers option</span></span>  
  
1.  <span data-ttu-id="fec2a-128">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fec2a-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fec2a-129">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="fec2a-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fec2a-130">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="fec2a-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="fec2a-131">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `nested triggers` la valeur `0`.</span><span class="sxs-lookup"><span data-stu-id="fec2a-131">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `nested triggers` option to `0`.</span></span>  
  
```wmimof  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'nested triggers', 0 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="fec2a-132">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fec2a-132">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-nested-triggers-option"></a><a name="FollowUp"></a> <span data-ttu-id="fec2a-133">Suivi : Après avoir configuré l’option nested triggers</span><span class="sxs-lookup"><span data-stu-id="fec2a-133">Follow Up: After you configure the nested triggers option</span></span>  
 <span data-ttu-id="fec2a-134">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="fec2a-134">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fec2a-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fec2a-135">See Also</span></span>  
 <span data-ttu-id="fec2a-136">[Créer des déclencheurs imbriqués](../../relational-databases/triggers/create-nested-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="fec2a-136">[Create Nested Triggers](../../relational-databases/triggers/create-nested-triggers.md) </span></span>  
 <span data-ttu-id="fec2a-137">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fec2a-137">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="fec2a-138">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fec2a-138">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="fec2a-139">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fec2a-139">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
