---
title: Configurer l’option de configuration de serveur scan for startup procs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- scan for startup procs option
ms.assetid: 6bf9d252-e766-458d-9dcd-23d895f032a2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fbf46fc7476e6e879991cfe3f649fd5617f3275e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603617"
---
# <a name="configure-the-scan-for-startup-procs-server-configuration-option"></a><span data-ttu-id="edf2d-102">Configurer l'option de configuration de serveur scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="edf2d-102">Configure the scan for startup procs Server Configuration Option</span></span>
  <span data-ttu-id="edf2d-103">Cette rubrique explique comment configurer l'option de configuration de serveur **scan for startup procs** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edf2d-103">This topic describes how to configure the **scan for startup procs** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="edf2d-104">Utilisez l'option **scan for startup procs** pour rechercher les procédures stockées à exécution automatique au moment du démarrage de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="edf2d-104">Use the **scan for startup procs** option to scan for automatic execution of stored procedures at [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup time.</span></span> <span data-ttu-id="edf2d-105">Si cette option a la valeur 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recherche et exécute toutes les procédures stockées à exécution automatique définies sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="edf2d-105">If this option is set to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] scans for and runs all automatically run stored procedures that are defined on the server.</span></span> <span data-ttu-id="edf2d-106">La valeur par défaut de l’option **Recherche des procédures de démarrage** est égale à 0 (pas de recherche).</span><span class="sxs-lookup"><span data-stu-id="edf2d-106">The default value for **scan for startup procs** is 0 (do not scan).</span></span>  
  
 <span data-ttu-id="edf2d-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="edf2d-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="edf2d-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="edf2d-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="edf2d-109">Recommandations</span><span class="sxs-lookup"><span data-stu-id="edf2d-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="edf2d-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="edf2d-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="edf2d-111">**Pour configurer l'option scan for startup procs, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="edf2d-111">**To configure the scan for startup procs option, using:**</span></span>  
  
     [<span data-ttu-id="edf2d-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="edf2d-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="edf2d-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="edf2d-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="edf2d-114">**Suivi :**  [Après avoir configuré l’option scan for startup procs](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="edf2d-114">**Follow Up:**  [After you configure the scan for startup procs option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="edf2d-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="edf2d-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="edf2d-116">Recommandations</span><span class="sxs-lookup"><span data-stu-id="edf2d-116">Recommendations</span></span>  
  
-   <span data-ttu-id="edf2d-117">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="edf2d-117">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="edf2d-118">La valeur de cette option peut être définie à l’aide de **sp_configure**; cependant, elle est automatiquement définie si vous utilisez **sp_procoption**, qui permet de sélectionner ou non l’exécution automatique des procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="edf2d-118">The value for this option can be set by using **sp_configure**; however, it will be set automatically if you use **sp_procoption**, which is used to mark or unmark automatically run stored procedures.</span></span> <span data-ttu-id="edf2d-119">Quand vous utilisez **sp_procoption** pour signaler que la première procédure stockée est une procédure à exécution automatique, cette option prend automatiquement la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="edf2d-119">When **sp_procoption** is used to mark the first stored procedure as an autoproc, this option is set automatically to a value of 1.</span></span> <span data-ttu-id="edf2d-120">Lorsque vous utilisez **sp_procoption** pour désactiver l’exécution automatique, cette option prend automatiquement la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="edf2d-120">When **sp_procoption** is used to unmark the last stored procedure as an autoproc, this option is automatically set to a value of 0.</span></span> <span data-ttu-id="edf2d-121">Si vous utilisez **sp_procoption** pour activer ou désactiver l’exécution automatique des procédures et si vous supprimez systématiquement l’exécution automatique avant de supprimer les procédures correspondantes, il est inutile de définir manuellement cette option.</span><span class="sxs-lookup"><span data-stu-id="edf2d-121">If you use **sp_procoption** to mark and unmark autoprocs, and if you always unmark autoprocs before dropping them, there is no need to set this option manually.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="edf2d-122">Sécurité</span><span class="sxs-lookup"><span data-stu-id="edf2d-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="edf2d-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="edf2d-123">Permissions</span></span>  
 <span data-ttu-id="edf2d-124">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="edf2d-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="edf2d-125">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="edf2d-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="edf2d-126">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="edf2d-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="edf2d-127">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="edf2d-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-scan-for-startup-procs-option"></a><span data-ttu-id="edf2d-128">Pour configurer l'option scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="edf2d-128">To configure the scan for startup procs option</span></span>  
  
1.  <span data-ttu-id="edf2d-129">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="edf2d-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="edf2d-130">Cliquez sur le nœud **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="edf2d-130">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="edf2d-131">Sous **Divers**, attribuez à l’option **Recherche des procédures de démarrage** la valeur True ou False en sélectionnant la valeur de votre choix dans la zone de liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="edf2d-131">Under **Miscellaneous**, change the **Scan for Startup Procs** option to True or False by selecting the value you want from the drop-down list box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="edf2d-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="edf2d-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-scan-for-startup-procs-option"></a><span data-ttu-id="edf2d-133">Pour configurer l'option scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="edf2d-133">To configure the scan for startup procs option</span></span>  
  
1.  <span data-ttu-id="edf2d-134">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edf2d-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="edf2d-135">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="edf2d-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="edf2d-136">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="edf2d-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="edf2d-137">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `scan for startup procs` la valeur `1`.</span><span class="sxs-lookup"><span data-stu-id="edf2d-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `scan for startup procs` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'scan for startup procs', 1 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
##  <a name="follow-up-after-you-configure-the-scan-for-startup-procs-option"></a><a name="FollowUp"></a> <span data-ttu-id="edf2d-138">Suivi : Après avoir configuré l’option scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="edf2d-138">Follow Up: After you configure the scan for startup procs option</span></span>  
 <span data-ttu-id="edf2d-139">Le serveur doit être redémarré pour que le paramètre puisse être effet.</span><span class="sxs-lookup"><span data-stu-id="edf2d-139">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edf2d-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="edf2d-140">See Also</span></span>  
 <span data-ttu-id="edf2d-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="edf2d-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="edf2d-142">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="edf2d-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="edf2d-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="edf2d-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="edf2d-144">sp_procoption &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="edf2d-144">sp_procoption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql)  
  
  
