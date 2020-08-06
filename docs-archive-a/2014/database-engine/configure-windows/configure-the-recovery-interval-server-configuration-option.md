---
title: Configurer l’option de configuration de serveur recovery interval | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- restoring recovery interval [SQL Server]
- checkpoints [SQL Server]
- recovery interval option [SQL Server]
- default recovery interval option
- time [SQL Server], recovery interval
- interval for recovery [SQL Server]
- maximum number of minutes per database recovery
- recovery [SQL Server], recovery interval option
ms.assetid: e4734b3b-8fbe-4b65-9c48-91b5a3dd18e1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 560d514ba8dd1503b59b3b59ecf404d876e24cd2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601687"
---
# <a name="configure-the-recovery-interval-server-configuration-option"></a><span data-ttu-id="90cc0-102">Configurer l'option de configuration de serveur recovery interval</span><span class="sxs-lookup"><span data-stu-id="90cc0-102">Configure the recovery interval Server Configuration Option</span></span>
  <span data-ttu-id="90cc0-103">Cette rubrique explique comment configurer l'option de configuration de serveur **recovery interval** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90cc0-103">This topic describes how to configure the **recovery interval** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="90cc0-104">L'option **recovery interval** définit une limite supérieure de durée de récupération pour une base de données.</span><span class="sxs-lookup"><span data-stu-id="90cc0-104">The **recovery interval** option defines an upper limit on the time recovering a database should take.</span></span> <span data-ttu-id="90cc0-105">[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] utilise la valeur spécifiée pour cette option afin de déterminer approximativement à quelle fréquence les [points de contrôle automatique](../../relational-databases/logs/database-checkpoints-sql-server.md) génèrent des points de contrôle automatique sur une base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="90cc0-105">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses the value specified for this option to determine approximately how often [automatic checkpoints](../../relational-databases/logs/database-checkpoints-sql-server.md) to issue automatic checkpoints on a given database.</span></span>  
  
 <span data-ttu-id="90cc0-106">La valeur par défaut pour l'intervalle de récupération est 0, ce qui permet au [!INCLUDE[ssDE](../../includes/ssde-md.md)] de configurer automatiquement l'intervalle de récupération.</span><span class="sxs-lookup"><span data-stu-id="90cc0-106">The default recovery-interval value is 0, which allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to automatically configure the recovery interval.</span></span> <span data-ttu-id="90cc0-107">En général, avec l'intervalle de récupération par défaut, les points de contrôle automatique sont générés environ une fois par minute pour les bases de données actives et la durée de récupération est inférieure à une minute.</span><span class="sxs-lookup"><span data-stu-id="90cc0-107">Typically, the default recovery interval results in automatic checkpoints occurring approximately once a minute for active databases and a recovery time of less than one minute.</span></span> <span data-ttu-id="90cc0-108">Des valeurs supérieures indiquent la durée de récupération maximale approximative, en minutes.</span><span class="sxs-lookup"><span data-stu-id="90cc0-108">Higher values indicate the approximate maximum recovery time, in minutes.</span></span> <span data-ttu-id="90cc0-109">Par exemple, si vous affectez à l'intervalle de récupération la valeur « 3 », cela indique que la durée de récupération maximale est d'environ trois minutes.</span><span class="sxs-lookup"><span data-stu-id="90cc0-109">For example, setting the recovery interval to 3 indicates a maximum recovery time of approximately three minutes.</span></span>  
  
 <span data-ttu-id="90cc0-110">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="90cc0-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="90cc0-111">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="90cc0-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="90cc0-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="90cc0-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="90cc0-113">Recommandations</span><span class="sxs-lookup"><span data-stu-id="90cc0-113">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="90cc0-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="90cc0-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="90cc0-115">**Pour configurer l'option de configuration de serveur recovery interval, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="90cc0-115">**To Configure the recovery interval Server Configuration Option, using:**</span></span>  
  
     [<span data-ttu-id="90cc0-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="90cc0-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="90cc0-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="90cc0-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="90cc0-118">**Suivi :**  [Après avoir configuré l’option recovery interval](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="90cc0-118">**Follow Up:**  [After you configure the recovery interval option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="90cc0-119">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="90cc0-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="90cc0-120">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="90cc0-120">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="90cc0-121">L'option intervalle de récupération affecte uniquement les bases de données qui utilisent le temps de récupération cible par défaut (0).</span><span class="sxs-lookup"><span data-stu-id="90cc0-121">The recovery interval affects only databases that use the default target recovery time (0).</span></span> <span data-ttu-id="90cc0-122">Pour remplacer l'intervalle de récupération de serveur sur une base de données, configurez un temps de récupération cible autre que celui par défaut sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="90cc0-122">To override the server recovery interval on a database, configure a non-default target recovery time on the database.</span></span> <span data-ttu-id="90cc0-123">Pour plus d’informations, consultez [Modifier la durée de récupération cible d’une base de données &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="90cc0-123">For more information, see [Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="90cc0-124">Recommandations</span><span class="sxs-lookup"><span data-stu-id="90cc0-124">Recommendations</span></span>  
  
-   <span data-ttu-id="90cc0-125">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="90cc0-125">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="90cc0-126">En général, il est recommandé de conserver la valeur 0 pour l'option intervalle de récupération, sauf si vous rencontrez des problèmes de performances.</span><span class="sxs-lookup"><span data-stu-id="90cc0-126">Typically, we recommend that you keep the recovery interval at 0, unless you experience performance problems.</span></span> <span data-ttu-id="90cc0-127">Si vous décidez d'augmenter la valeur de l'option intervalle de récupération, nous vous recommandons de l'augmenter progressivement par petits incréments et d'évaluer l'effet de chaque augmentation incrémentielle sur les performances de récupération.</span><span class="sxs-lookup"><span data-stu-id="90cc0-127">If you decide to increase the recovery-interval setting, we recommend increasing it gradually by small increments and evaluating the effect of each incremental increase on recovery performance.</span></span>  
  
-   <span data-ttu-id="90cc0-128">Si vous utilisez **sp_configure** pour attribuer à l’option **intervalle de récupération** une valeur supérieure à 60 (minutes), spécifiez RECONFIGURE WITH OVERRIDE.</span><span class="sxs-lookup"><span data-stu-id="90cc0-128">If you use **sp_configure** to change the value of the **recovery interval** option to more than 60 (minutes), specify RECONFIGURE WITH OVERRIDE.</span></span> <span data-ttu-id="90cc0-129">WITH OVERRIDE désactive le contrôle de la valeur de configuration (pour les valeurs non valides ou non recommandées).</span><span class="sxs-lookup"><span data-stu-id="90cc0-129">WITH OVERRIDE disables configuration value checking (for values that are not valid or are nonrecommended values).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="90cc0-130">Sécurité</span><span class="sxs-lookup"><span data-stu-id="90cc0-130">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="90cc0-131">Autorisations</span><span class="sxs-lookup"><span data-stu-id="90cc0-131">Permissions</span></span>  
 <span data-ttu-id="90cc0-132">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="90cc0-132">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="90cc0-133">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="90cc0-133">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="90cc0-134">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="90cc0-134">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="90cc0-135">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="90cc0-135">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="90cc0-136">**Pour définir l'intervalle de récupération**</span><span class="sxs-lookup"><span data-stu-id="90cc0-136">**To set the recovery interval**</span></span>  
  
1.  <span data-ttu-id="90cc0-137">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur une instance de serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="90cc0-137">In Object Explorer, right-click server instance and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="90cc0-138">Cliquez sur le nœud **Paramètres de base de données** .</span><span class="sxs-lookup"><span data-stu-id="90cc0-138">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="90cc0-139">Sous **Récupération**, dans la zone **Intervalle de récupération (minutes)** , tapez ou sélectionnez une valeur de 0 à 32767 pour définir la durée maximale en minutes que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut consacrer à la récupération de chaque base de données, au démarrage.</span><span class="sxs-lookup"><span data-stu-id="90cc0-139">Under **Recovery**, in the **Recovery interval (minutes)** box, type or select a value from 0 through 32767 to set the maximum amount of time, in minutes, that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should spend recovering each database at startup.</span></span> <span data-ttu-id="90cc0-140">La valeur par défaut est égale à 0, ce qui correspond à une configuration automatique par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90cc0-140">The default is 0, indicating automatic configuration by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="90cc0-141">Pour les bases de données actives, cela représente concrètement une durée de récupération inférieure à une minute et un point de contrôle chaque minute environ.</span><span class="sxs-lookup"><span data-stu-id="90cc0-141">In practice, this means a recovery time of less than one minute and a checkpoint approximately every one minute for active databases.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="90cc0-142">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="90cc0-142">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-recovery-interval"></a><span data-ttu-id="90cc0-143">Pour définir l'intervalle de récupération</span><span class="sxs-lookup"><span data-stu-id="90cc0-143">To set the recovery interval</span></span>  
  
1.  <span data-ttu-id="90cc0-144">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90cc0-144">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="90cc0-145">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="90cc0-145">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="90cc0-146">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="90cc0-146">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="90cc0-147">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `recovery interval` la valeur `3` minutes.</span><span class="sxs-lookup"><span data-stu-id="90cc0-147">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `recovery interval` option to `3` minutes.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'recovery interval', 3 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="90cc0-148">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="90cc0-148">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-recovery-internal-option"></a><a name="FollowUp"></a> <span data-ttu-id="90cc0-149">Suivi : Après avoir configuré l’option recovery interval</span><span class="sxs-lookup"><span data-stu-id="90cc0-149">Follow Up: After you configure the recovery internal option</span></span>  
 <span data-ttu-id="90cc0-150">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="90cc0-150">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90cc0-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90cc0-151">See Also</span></span>  
 <span data-ttu-id="90cc0-152">[Modifier la durée de récupération cible d’une base de données &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="90cc0-152">[Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md) </span></span>  
 <span data-ttu-id="90cc0-153">[Points de contrôle de base de données &#40;SQL Server&#41;](../../relational-databases/logs/database-checkpoints-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="90cc0-153">[Database Checkpoints &#40;SQL Server&#41;](../../relational-databases/logs/database-checkpoints-sql-server.md) </span></span>  
 <span data-ttu-id="90cc0-154">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="90cc0-154">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="90cc0-155">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="90cc0-155">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="90cc0-156">[show advanced options (option de configuration de serveur)](show-advanced-options-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="90cc0-156">[show advanced options Server Configuration Option](show-advanced-options-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="90cc0-157">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="90cc0-157">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
