---
title: Configurer l’option de configuration de serveur max text repl size | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- max text repl size option
ms.assetid: 3056cf64-621d-4996-9162-3913f6bc6d5b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2af0cf426583ee328f0a484de1c3539836c0d8af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611297"
---
# <a name="configure-the-max-text-repl-size-server-configuration-option"></a><span data-ttu-id="37599-102">Configurer l'option de configuration de serveur max text repl size</span><span class="sxs-lookup"><span data-stu-id="37599-102">Configure the max text repl size Server Configuration Option</span></span>
  <span data-ttu-id="37599-103">Cette rubrique explique comment configurer l'option de configuration de serveur **max text repl size** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37599-103">This topic describes how to configure the **max text repl size** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="37599-104">L’option **max text repl size** spécifie la taille maximale (en octets) `text` des `ntext` données,,,,, et pouvant `varchar(max)` `nvarchar(max)` `varbinary(max)` `xml` `image` être ajoutées à une colonne répliquée ou capturée dans une seule instruction INSERT, Update, WRITETEXT ou UPDATETEXT.</span><span class="sxs-lookup"><span data-stu-id="37599-104">The **max text repl size** option specifies the maximum size (in bytes) of `text`, `ntext`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, `xml`, and `image` data that can be added to a replicated column or captured column in a single INSERT, UPDATE, WRITETEXT, or UPDATETEXT statement.</span></span> <span data-ttu-id="37599-105">La valeur par défaut est 65536 octets.</span><span class="sxs-lookup"><span data-stu-id="37599-105">The default value is 65536 bytes.</span></span> <span data-ttu-id="37599-106">La valeur -1 indique l'absence de limite autre que celle imposée par le type de données.</span><span class="sxs-lookup"><span data-stu-id="37599-106">A value of -1 indicates that there is no size limit, other than the limit imposed by the data type.</span></span>  
  
 <span data-ttu-id="37599-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="37599-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="37599-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="37599-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="37599-109">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="37599-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="37599-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="37599-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="37599-111">**Pour configurer l'option max text repl size, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="37599-111">**To configure the max text repl size option, using:**</span></span>  
  
     [<span data-ttu-id="37599-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37599-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="37599-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="37599-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="37599-114">**Suivi :**  [Après avoir configuré l’option max text repl size](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="37599-114">**Follow Up:**  [After you configure the max text repl size option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="37599-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="37599-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="37599-116">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="37599-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="37599-117">Cette option s'applique à la réplication transactionnelle et à la capture des données modifiées.</span><span class="sxs-lookup"><span data-stu-id="37599-117">This option applies to transactional replication and Change Data Capture.</span></span> <span data-ttu-id="37599-118">Lorsqu'un serveur est configuré pour la réplication transactionnelle et la capture des données modifiées, la valeur spécifiée s'applique aux deux fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="37599-118">When a server is configured for both transactional replication and Change Data Capture, the specified value applies to both features.</span></span> <span data-ttu-id="37599-119">Elle est ignorée dans le cas d'une réplication d'instantané et de fusion.</span><span class="sxs-lookup"><span data-stu-id="37599-119">This option is ignored by snapshot replication and merge replication.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="37599-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="37599-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="37599-121">Autorisations</span><span class="sxs-lookup"><span data-stu-id="37599-121">Permissions</span></span>  
 <span data-ttu-id="37599-122">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="37599-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="37599-123">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="37599-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="37599-124">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="37599-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="37599-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37599-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-text-repl-size-option"></a><span data-ttu-id="37599-126">Pour configurer l'option Taille de réplication de texte maximum</span><span class="sxs-lookup"><span data-stu-id="37599-126">To configure the max text repl size option</span></span>  
  
1.  <span data-ttu-id="37599-127">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="37599-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="37599-128">Cliquez sur le nœud **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="37599-128">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="37599-129">Sous **Divers**, modifiez l'option **Taille de réplication de texte maximum** pour lui attribuer la valeur souhaitée.</span><span class="sxs-lookup"><span data-stu-id="37599-129">Under **Miscellaneous**, change the **Max Text Replication Size** option to the desired value.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="37599-130">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="37599-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-text-repl-size-option"></a><span data-ttu-id="37599-131">Pour configurer l'option Taille de réplication de texte maximum</span><span class="sxs-lookup"><span data-stu-id="37599-131">To configure the max text repl size option</span></span>  
  
1.  <span data-ttu-id="37599-132">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37599-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="37599-133">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="37599-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="37599-134">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="37599-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="37599-135">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `max text repl size` la valeur `-1`.</span><span class="sxs-lookup"><span data-stu-id="37599-135">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max text repl size` option to `-1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;   
RECONFIGURE ;   
GO  
EXEC sp_configure 'max text repl size', -1 ;   
GO  
RECONFIGURE;   
GO  
  
```  
  
 <span data-ttu-id="37599-136">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="37599-136">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-text-repl-size-option"></a><a name="FollowUp"></a> <span data-ttu-id="37599-137">Suivi : Après avoir configuré l’option max text repl size</span><span class="sxs-lookup"><span data-stu-id="37599-137">Follow Up: After you configure the max text repl size option</span></span>  
 <span data-ttu-id="37599-138">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="37599-138">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37599-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="37599-139">See Also</span></span>  
 <span data-ttu-id="37599-140">[Réplication SQL Server](../../relational-databases/replication/sql-server-replication.md) </span><span class="sxs-lookup"><span data-stu-id="37599-140">[SQL Server Replication](../../relational-databases/replication/sql-server-replication.md) </span></span>  
 <span data-ttu-id="37599-141">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="37599-141">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="37599-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="37599-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="37599-143">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="37599-143">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="37599-144">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="37599-144">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="37599-145">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="37599-145">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span></span>  
 <span data-ttu-id="37599-146">[UPDATETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/updatetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="37599-146">[UPDATETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/updatetext-transact-sql) </span></span>  
 [<span data-ttu-id="37599-147">WRITETEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="37599-147">WRITETEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/writetext-transact-sql)  
  
  
