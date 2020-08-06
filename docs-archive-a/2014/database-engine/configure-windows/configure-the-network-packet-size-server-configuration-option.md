---
title: Configurer l’option de configuration de serveur network packet size | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default packet size
- size [SQL Server], packets
- packets [SQL Server], size
- network packet size option
ms.assetid: 236985bf-fc4a-4a57-98f7-a71ef977fd7b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69e5963675349bceff6a0ee022f6dc28da03db59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700211"
---
# <a name="configure-the-network-packet-size-server-configuration-option"></a><span data-ttu-id="34122-102">Configurer l'option de configuration de serveur network packet size</span><span class="sxs-lookup"><span data-stu-id="34122-102">Configure the network packet size Server Configuration Option</span></span>
  <span data-ttu-id="34122-103">Cette rubrique explique comment configurer l' `network packet size` option de configuration de serveur dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34122-103">This topic describes how to configure the `network packet size` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="34122-104">L' `network packet size` option définit la taille du paquet (en octets) utilisée sur l’ensemble du réseau.</span><span class="sxs-lookup"><span data-stu-id="34122-104">The `network packet size` option sets the packet size (in bytes) that is used across the whole network.</span></span> <span data-ttu-id="34122-105">Les paquets constituent les morceaux de taille définie de données qui transfèrent les requêtes et les résultats entre les clients et les serveurs.</span><span class="sxs-lookup"><span data-stu-id="34122-105">Packets are the fixed-size chunks of data that transfer requests and results between clients and servers.</span></span> <span data-ttu-id="34122-106">La taille des paquets par défaut est 4 096 octets.</span><span class="sxs-lookup"><span data-stu-id="34122-106">The default packet size is 4,096 bytes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34122-107">Ne modifiez pas la taille des paquets, sauf si vous êtes certain que cela permettra d'accroître les performances.</span><span class="sxs-lookup"><span data-stu-id="34122-107">Do not change the packet size unless you are certain that it will improve performance.</span></span> <span data-ttu-id="34122-108">Pour la plupart des applications, la taille de paquet par défaut représente la meilleure solution.</span><span class="sxs-lookup"><span data-stu-id="34122-108">For most applications, the default packet size is best.</span></span>  
  
 <span data-ttu-id="34122-109">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="34122-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="34122-110">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="34122-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="34122-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="34122-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="34122-112">Recommandations</span><span class="sxs-lookup"><span data-stu-id="34122-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="34122-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="34122-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="34122-114">**Pour configurer l'option network packet size, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="34122-114">**To configure the network packet size option, using:**</span></span>  
  
     [<span data-ttu-id="34122-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="34122-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="34122-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="34122-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="34122-117">**Suivi :**  [Après avoir configuré l’option network packet size](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="34122-117">**Follow Up:**  [After you configure the network packet size option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="34122-118">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="34122-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="34122-119">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="34122-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="34122-120">La taille de paquet réseau maximale pour les connexions chiffrées est 16 383 octets.</span><span class="sxs-lookup"><span data-stu-id="34122-120">The maximum network packet size for encrypted connections is 16,383 bytes.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="34122-121">Recommandations</span><span class="sxs-lookup"><span data-stu-id="34122-121">Recommendations</span></span>  
  
-   <span data-ttu-id="34122-122">Cette option avancée ne doit être modifiée que par un administrateur de base de données qualifié ou un technicien agréé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34122-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="34122-123">Si une application effectue des opérations de copie en bloc, ou envoie ou reçoit de grandes quantités de données de type texte ou image, l'utilisation d'une taille de paquet supérieure à la taille par défaut peut améliorer les performances car elle permet de réduire les opérations de lecture et d'écriture sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="34122-123">If an application does bulk copy operations or sends or receives large amounts of text or image data, a packet size larger than the default might improve efficiency because it results in fewer network read-and-write operations.</span></span> <span data-ttu-id="34122-124">Si une application envoie et reçoit de petites quantités d'informations, la taille de paquets peut être définie à 512 octets, ce qui est suffisant pour la plupart des transferts de données.</span><span class="sxs-lookup"><span data-stu-id="34122-124">If an application sends and receives small amounts of information, the packet size can be set to 512 bytes, which is sufficient for most data transfers.</span></span>  
  
-   <span data-ttu-id="34122-125">Pour des systèmes utilisant différents protocoles réseau, attribuez à l’option network packet size la taille adaptée au protocole le plus utilisé.</span><span class="sxs-lookup"><span data-stu-id="34122-125">On systems that are using different network protocols, set network packet size to the size for the most common protocol used.</span></span> <span data-ttu-id="34122-126">L'option network packet size permet d'accroître les performances lorsque les protocoles réseau prennent en charge les paquets de grande taille.</span><span class="sxs-lookup"><span data-stu-id="34122-126">The network packet size option improves network performance when network protocols support larger packets.</span></span> <span data-ttu-id="34122-127">Les applications clientes peuvent remplacer cette valeur.</span><span class="sxs-lookup"><span data-stu-id="34122-127">Client applications can override this value.</span></span>  
  
-   <span data-ttu-id="34122-128">Vous pouvez également appeler les fonctions OLE DB, ODBC (Open Database Connectivity ) et DB-Library pour demander une modification de la taille des paquets.</span><span class="sxs-lookup"><span data-stu-id="34122-128">You can also call OLE DB, Open Database Connectivity (ODBC), and DB-Library functions request a change the packet size.</span></span> <span data-ttu-id="34122-129">Si le serveur ne peut pas prendre en charge la taille des paquets demandée, le [!INCLUDE[ssDE](../../includes/ssde-md.md)] envoie un message d’avertissement au client.</span><span class="sxs-lookup"><span data-stu-id="34122-129">If the server cannot support the requested packet size, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will send a warning message to the client.</span></span> <span data-ttu-id="34122-130">Dans certains cas, la modification de la taille des paquets peut entraîner un échec de la liaison de communication, tel que :</span><span class="sxs-lookup"><span data-stu-id="34122-130">In some circumstances, changing the packet size might lead to a communication link failure, such as the following:</span></span>  
  
     `Native Error: 233, no process is on the other end of the pipe.`  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="34122-131">Sécurité</span><span class="sxs-lookup"><span data-stu-id="34122-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="34122-132">Autorisations</span><span class="sxs-lookup"><span data-stu-id="34122-132">Permissions</span></span>  
 <span data-ttu-id="34122-133">Les autorisations d’exécution de **sp_configure** , sans paramètre ou avec le premier paramètre uniquement, sont accordées par défaut à tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="34122-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="34122-134">Pour exécuter **sp_configure** avec les deux paramètres afin de modifier une option de configuration ou d’exécuter l’instruction RECONFIGURE, un utilisateur doit disposer de l’autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="34122-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="34122-135">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="34122-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="34122-136">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="34122-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-network-packet-size-option"></a><span data-ttu-id="34122-137">Pour configurer l'option network packet size</span><span class="sxs-lookup"><span data-stu-id="34122-137">To configure the network packet size option</span></span>  
  
1.  <span data-ttu-id="34122-138">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="34122-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="34122-139">Cliquez sur le nœud **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="34122-139">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="34122-140">Sous **Réseau**, sélectionnez une valeur pour la zone **Taille du paquet réseau** .</span><span class="sxs-lookup"><span data-stu-id="34122-140">Under **Network**, select a value for the **Network Packet Size** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="34122-141">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="34122-141">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-network-packet-size-option"></a><span data-ttu-id="34122-142">Pour configurer l'option network packet size</span><span class="sxs-lookup"><span data-stu-id="34122-142">To configure the network packet size option</span></span>  
  
1.  <span data-ttu-id="34122-143">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34122-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="34122-144">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="34122-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="34122-145">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="34122-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="34122-146">Cet exemple montre comment utiliser [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) pour attribuer à l’option `network packet size` la valeur `6500` octets.</span><span class="sxs-lookup"><span data-stu-id="34122-146">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `network packet size` option to `6500` bytes.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'network packet size', 6500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="34122-147">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="34122-147">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-network-packet-size-option"></a><a name="FollowUp"></a> <span data-ttu-id="34122-148">Suivi : Après avoir configuré l’option network packet size</span><span class="sxs-lookup"><span data-stu-id="34122-148">Follow Up: After you configure the network packet size option</span></span>  
 <span data-ttu-id="34122-149">Le paramètre prend effet immédiatement sans redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="34122-149">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34122-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="34122-150">See Also</span></span>  
 <span data-ttu-id="34122-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34122-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="34122-152">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34122-152">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="34122-153">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="34122-153">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
