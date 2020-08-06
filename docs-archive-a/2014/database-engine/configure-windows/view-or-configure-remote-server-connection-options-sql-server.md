---
title: Afficher ou configurer des options de connexion au serveur distant (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote servers [SQL Server], connection options
- servers [SQL Server], remote
- connections [SQL Server], remote servers
ms.assetid: 356d3e6b-8514-4bd2-a683-9de147949b2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 73fe5e484d62cde025d1a560937e8cbcf5ec361d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697147"
---
# <a name="view-or-configure-remote-server-connection-options-sql-server"></a><span data-ttu-id="d8533-102">Afficher ou configurer des options de connexion au serveur distant (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d8533-102">View or Configure Remote Server Connection Options (SQL Server)</span></span>
  <span data-ttu-id="d8533-103">Cette rubrique explique comment afficher ou configurer des options de connexion au serveur distant au niveau du serveur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8533-103">This topic describes how to view or configure remote server connection options at the server level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d8533-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="d8533-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d8533-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="d8533-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d8533-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d8533-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d8533-107">**Pour afficher ou configurer des options de connexion au serveur distant, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="d8533-107">**To view or configure remote server connection options, using:**</span></span>  
  
     [<span data-ttu-id="d8533-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8533-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d8533-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d8533-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="d8533-110">**Suivi :**  [Après avoir configuré des options de connexion au serveur distant](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="d8533-110">**Follow Up:**  [After you configure remote server connection options](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d8533-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d8533-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d8533-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d8533-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d8533-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="d8533-113">Permissions</span></span>  
 <span data-ttu-id="d8533-114">L’exécution de **sp_serveroption** nécessite l’autorisation ALTER ANY LINKED SERVER sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="d8533-114">Executing **sp_serveroption** requires ALTER ANY LINKED SERVER permission on the server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d8533-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8533-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-configure-remote-server-connection-options"></a><span data-ttu-id="d8533-116">Pour afficher ou configurer des options de connexion au serveur distant</span><span class="sxs-lookup"><span data-stu-id="d8533-116">To view or configure remote server connection options</span></span>  
  
1.  <span data-ttu-id="d8533-117">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d8533-117">In Object Explorer, right-click a server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="d8533-118">Dans la boîte de dialogue **Propriétés de SQL Server - \<***server_name***>** , cliquez sur **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="d8533-118">In the **SQL Server Properties - \<***server_name***>** dialog box, click **Connections**.</span></span>  
  
3.  <span data-ttu-id="d8533-119">Sur la page **Connexions** , vérifiez les paramètres **Connexions au serveur distant** et au besoin modifiez-les.</span><span class="sxs-lookup"><span data-stu-id="d8533-119">On the **Connections** page, review the **Remote server connections** settings, and modify them if necessary.</span></span>  
  
4.  <span data-ttu-id="d8533-120">Répétez les étapes 1 à 3 sur l'autre serveur de la paire de serveurs distants.</span><span class="sxs-lookup"><span data-stu-id="d8533-120">Repeat steps 1 through 3 on the other server of the remote server pair.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d8533-121">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d8533-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-remote-server-connection-options"></a><span data-ttu-id="d8533-122">Pour afficher les options de connexion au serveur distant</span><span class="sxs-lookup"><span data-stu-id="d8533-122">To view remote server connection options</span></span>  
  
1.  <span data-ttu-id="d8533-123">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8533-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d8533-124">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="d8533-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d8533-125">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d8533-125">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d8533-126">Cet exemple utilise [sp_helpserver](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) pour retourner des informations sur tous les serveurs distants.</span><span class="sxs-lookup"><span data-stu-id="d8533-126">This example uses [sp_helpserver](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) to return information about all remote servers.</span></span>  
  
```sql  
USE master;  
GO  
EXEC sp_helpserver ;  
```  
  
#### <a name="to-configure-remote-server-connection-options"></a><span data-ttu-id="d8533-127">Pour configurer des options de connexion au serveur distant</span><span class="sxs-lookup"><span data-stu-id="d8533-127">To configure remote server connection options</span></span>  
  
1.  <span data-ttu-id="d8533-128">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8533-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d8533-129">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="d8533-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d8533-130">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d8533-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d8533-131">Cet exemple montre comment utiliser [sp_serveroption](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql) pour configurer un serveur distant.</span><span class="sxs-lookup"><span data-stu-id="d8533-131">This example shows how to use [sp_serveroption](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql) to configure a remote server.</span></span> <span data-ttu-id="d8533-132">Cet exemple configure un serveur distant correspondant à une autre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `SEATTLE3`, de façon à ce qu'il soit compatible avec le classement de l'instance locale de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8533-132">The example configures a remote server corresponding to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `SEATTLE3`, to be collation compatible with the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
```sql  
USE master;  
EXEC sp_serveroption 'SEATTLE3', 'collation compatible', 'true';  
```  
  
##  <a name="follow-up-after-you-configure-remote-server-connection-options"></a><a name="FollowUp"></a> <span data-ttu-id="d8533-133">Suivi : Après avoir configuré des options de connexion au serveur distant</span><span class="sxs-lookup"><span data-stu-id="d8533-133">Follow Up: After you configure remote server connection options</span></span>  
 <span data-ttu-id="d8533-134">Le serveur distant doit être arrêté et redémarré pour que le paramètre puisse prendre effet.</span><span class="sxs-lookup"><span data-stu-id="d8533-134">The remote server must be stopped and restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8533-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8533-135">See Also</span></span>  
 <span data-ttu-id="d8533-136">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d8533-136">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="d8533-137">[Serveurs distants](remote-servers.md) </span><span class="sxs-lookup"><span data-stu-id="d8533-137">[Remote Servers](remote-servers.md) </span></span>  
 <span data-ttu-id="d8533-138">[Serveurs liés &#40;moteur de base de données&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="d8533-138">[Linked Servers &#40;Database Engine&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span></span>  
 <span data-ttu-id="d8533-139">[sp_linkedservers &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-linkedservers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d8533-139">[sp_linkedservers &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-linkedservers-transact-sql) </span></span>  
 <span data-ttu-id="d8533-140">[sp_helpserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d8533-140">[sp_helpserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) </span></span>  
 [<span data-ttu-id="d8533-141">sp_serveroption &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8533-141">sp_serveroption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql)  
  
  
