---
title: Configurer l’accès en lecture seule sur un réplica de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- connection access to availability replicas
- Availability Groups [SQL Server], readable secondary replicas
- active secondary replicas [SQL Server], read-only access to
- Availability Groups [SQL Server], read-only routing
- Availability Groups [SQL Server], client connectivity
ms.assetid: 22387419-22c4-43fa-851c-5fecec4b049b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab13081396aff46d193c1b0449d6b93042ee60d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697192"
---
# <a name="configure-read-only-access-on-an-availability-replica-sql-server"></a><span data-ttu-id="3e395-102">Configurer l'accès en lecture seule sur un réplica de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3e395-102">Configure Read-Only Access on an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="3e395-103">Par défaut l'accès en lecture/écriture et l'intention de lecture sont autorisés sur le réplica principal et aucune connexion directe n'est autorisée sur les réplicas secondaires d'un groupe de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="3e395-103">By default both read-write and read-intent access are allowed to the primary replica and no connections are allowed to secondary replicas of an AlwaysOn availability group.</span></span> <span data-ttu-id="3e395-104">Cette rubrique explique comment configurer l'accès à la connexion sur un réplica de disponibilité d'un groupe de disponibilité AlwaysOn dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e395-104">This topic describes how to configure connection access on an availability replica of an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
 <span data-ttu-id="3e395-105">Pour plus d’informations sur les conséquences de l’activation de l’accès en lecture seule pour un réplica secondaire et pour obtenir une présentation de l’accès à la connexion, consultez [À propos de l’accès de la connexion client aux réplicas de disponibilité &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) et [Secondaires actifs : réplicas secondaires lisibles &#40;groupes de disponibilité AlwaysOn&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="3e395-105">For information about the implications of enabling read-only access for a secondary replica and for an introduction to connection access, see [About Client Connection Access to Availability Replicas &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) and [Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3e395-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="3e395-106">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="3e395-107">Conditions préalables requises et restrictions</span><span class="sxs-lookup"><span data-stu-id="3e395-107">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="3e395-108">Pour configurer un autre accès à la connexion, vous devez être connecté à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="3e395-108">To configure different connection access, you must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3e395-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="3e395-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3e395-110">Autorisations</span><span class="sxs-lookup"><span data-stu-id="3e395-110">Permissions</span></span>  
  
|<span data-ttu-id="3e395-111">Tâche</span><span class="sxs-lookup"><span data-stu-id="3e395-111">Task</span></span>|<span data-ttu-id="3e395-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="3e395-112">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="3e395-113">Pour configurer des réplicas lors de la création d'un groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="3e395-113">To configure replicas when creating an availability group</span></span>|<span data-ttu-id="3e395-114">Requiert l’appartenance au rôle serveur fixe **sysadmin** et l’autorisation de serveur CREATE AVAILABILITY GROUP, l’autorisation ALTER ANY AVAILABILITY GROUP ou l’autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="3e395-114">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
|<span data-ttu-id="3e395-115">Pour modifier un réplica de disponibilité :</span><span class="sxs-lookup"><span data-stu-id="3e395-115">To modify an availability replica</span></span>|<span data-ttu-id="3e395-116">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="3e395-116">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3e395-117">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e395-117">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="3e395-118">**Pour configurer l'accès sur un réplica de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="3e395-118">**To configure access on an availability replica**</span></span>  
  
1.  <span data-ttu-id="3e395-119">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge le réplica principal et développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="3e395-119">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="3e395-120">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="3e395-120">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="3e395-121">Cliquez sur le groupe de disponibilité dont vous souhaitez modifier le réplica.</span><span class="sxs-lookup"><span data-stu-id="3e395-121">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="3e395-122">Cliquez avec le bouton droit sur le réplica de disponibilité, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="3e395-122">Right-click the availability replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="3e395-123">Dans la boîte de dialogue **Propriétés du réplica de disponibilité** , vous pouvez modifier l'accès à la connexion pour le rôle principal et le rôle secondaire, comme suit :</span><span class="sxs-lookup"><span data-stu-id="3e395-123">In the **Availability Replica Properties** dialog box, you can change the connection access for the primary role and for the secondary role, as follows:</span></span>  
  
    -   <span data-ttu-id="3e395-124">Pour le rôle secondaire, sélectionnez une nouvelle valeur dans la liste déroulante **Rôle secondaire accessible en lecture** , comme suit :</span><span class="sxs-lookup"><span data-stu-id="3e395-124">For the secondary role, select a new value from the **Readable secondary** drop list, as follows:</span></span>  
  
         <span data-ttu-id="3e395-125">**Non**</span><span class="sxs-lookup"><span data-stu-id="3e395-125">**No**</span></span>  
         <span data-ttu-id="3e395-126">Aucune connexion utilisateur n'est autorisée aux bases de données secondaires de ce réplica.</span><span class="sxs-lookup"><span data-stu-id="3e395-126">No user connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="3e395-127">Elles ne sont pas disponibles pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="3e395-127">They are not available for read access.</span></span> <span data-ttu-id="3e395-128">Il s'agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="3e395-128">This is the default setting.</span></span>  
  
         <span data-ttu-id="3e395-129">**Tentative de lecture uniquement**</span><span class="sxs-lookup"><span data-stu-id="3e395-129">**Read-intent only**</span></span>  
         <span data-ttu-id="3e395-130">Seules les connexions en lecture seule sont autorisées aux bases de données secondaires de ce réplica.</span><span class="sxs-lookup"><span data-stu-id="3e395-130">Only read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="3e395-131">La ou les bases de données secondaires sont toutes disponibles pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="3e395-131">The secondary database(s) are all available for read access.</span></span>  
  
         <span data-ttu-id="3e395-132">**Oui**</span><span class="sxs-lookup"><span data-stu-id="3e395-132">**Yes**</span></span>  
         <span data-ttu-id="3e395-133">Toutes les connexions sont autorisées aux bases de données secondaires de ce réplica, mais uniquement pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="3e395-133">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="3e395-134">La ou les bases de données secondaires sont toutes disponibles pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="3e395-134">The secondary database(s) are all available for read access.</span></span>  
  
    -   <span data-ttu-id="3e395-135">Pour le rôle principal, sélectionnez une nouvelle valeur dans la liste déroulante **Connexions en rôle principal** , comme suit :</span><span class="sxs-lookup"><span data-stu-id="3e395-135">For the primary role, select a new value from the **Connections in primary role** drop list, as follows:</span></span>  
  
         <span data-ttu-id="3e395-136">**Autoriser toutes les connexions**</span><span class="sxs-lookup"><span data-stu-id="3e395-136">**Allow all connections**</span></span>  
         <span data-ttu-id="3e395-137">Toutes les connexions aux bases de données sont autorisées dans le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="3e395-137">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="3e395-138">Il s'agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="3e395-138">This is the default setting.</span></span>  
  
         <span data-ttu-id="3e395-139">**Autoriser les connexions en lecture/écriture**</span><span class="sxs-lookup"><span data-stu-id="3e395-139">**Allow read/write connections**</span></span>  
         <span data-ttu-id="3e395-140">Lorsque la propriété d'intention de l'application a la valeur **ReadWrite** ou si cette propriété n'est pas définie, la connexion est autorisée.</span><span class="sxs-lookup"><span data-stu-id="3e395-140">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="3e395-141">Les connexions où la propriété de connexion d'intention de l'application a la valeur **ReadOnly** ne sont pas autorisées.</span><span class="sxs-lookup"><span data-stu-id="3e395-141">Connections where the Application Intent connection property is set to **ReadOnly** are not allowed.</span></span> <span data-ttu-id="3e395-142">Cela peut permettre d'éviter aux clients de se connecter à une charge de travail de tentative de lecture au réplica primaire par erreur.</span><span class="sxs-lookup"><span data-stu-id="3e395-142">This can help prevent customers from connecting a read-intent work load to the primary replica by mistake.</span></span> <span data-ttu-id="3e395-143">Pour plus d'informations sur la propriété de connexion d'intention de l'application, consultez [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="3e395-143">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3e395-144">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3e395-144">Using Transact-SQL</span></span>  
 <span data-ttu-id="3e395-145">**Pour configurer l'accès sur un réplica de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="3e395-145">**To configure access on an availability replica**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e395-146">Pour obtenir un exemple de cette procédure, consultez [Exemple (Transact-SQL)](#TsqlExample)plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="3e395-146">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="3e395-147">Connectez-vous à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="3e395-147">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="3e395-148">Si vous spécifiez un réplica pour un nouveau groupe de disponibilité, utilisez l'instruction [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e395-148">If you are specifying a replica for a new availability group, use the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="3e395-149">Si vous ajoutez ou modifiez un réplica d’un groupe de disponibilité existant, utilisez l’instruction [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e395-149">If you are adding or modifying a replica of an existing availability group, use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
    -   <span data-ttu-id="3e395-150">Pour configurer l'accès à la connexion pour le rôle secondaire, dans la clause ADD REPLICA ou MODIFY REPLICA WITH, spécifiez l'option SECONDARY_ROLE, comme suit :</span><span class="sxs-lookup"><span data-stu-id="3e395-150">To configure connection access for the secondary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the SECONDARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="3e395-151">SECONDARY_ROLE **(** ALLOW_CONNECTIONS **=** { NO | READ_ONLY | ALL } **)**</span><span class="sxs-lookup"><span data-stu-id="3e395-151">SECONDARY_ROLE **(** ALLOW_CONNECTIONS **=** { NO | READ_ONLY | ALL } **)**</span></span>  
  
         <span data-ttu-id="3e395-152">où :</span><span class="sxs-lookup"><span data-stu-id="3e395-152">where,</span></span>  
  
         <span data-ttu-id="3e395-153">Non</span><span class="sxs-lookup"><span data-stu-id="3e395-153">NO</span></span>  
         <span data-ttu-id="3e395-154">Aucune connexion directe n'est autorisée aux bases de données secondaires de ce réplica.</span><span class="sxs-lookup"><span data-stu-id="3e395-154">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="3e395-155">Elles ne sont pas disponibles pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="3e395-155">They are not available for read access.</span></span> <span data-ttu-id="3e395-156">Il s'agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="3e395-156">This is the default setting.</span></span>  
  
         <span data-ttu-id="3e395-157">READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="3e395-157">READ_ONLY</span></span>  
         <span data-ttu-id="3e395-158">Seules les connexions en lecture seule sont autorisées aux bases de données secondaires de ce réplica.</span><span class="sxs-lookup"><span data-stu-id="3e395-158">Only read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="3e395-159">La ou les bases de données secondaires sont toutes disponibles pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="3e395-159">The secondary database(s) are all available for read access.</span></span>  
  
         <span data-ttu-id="3e395-160">ALL</span><span class="sxs-lookup"><span data-stu-id="3e395-160">ALL</span></span>  
         <span data-ttu-id="3e395-161">Toutes les connexions sont autorisées aux bases de données secondaires de ce réplica, mais uniquement pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="3e395-161">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="3e395-162">La ou les bases de données secondaires sont toutes disponibles pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="3e395-162">The secondary database(s) are all available for read access.</span></span>  
  
3.  <span data-ttu-id="3e395-163">Pour configurer l'accès à la connexion pour le rôle principal, dans la clause ADD REPLICA ou MODIFY REPLICA WITH, spécifiez l'option PRIMARY_ROLE, comme suit :</span><span class="sxs-lookup"><span data-stu-id="3e395-163">To configure connection access for the primary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the PRIMARY_ROLE option, as follows:</span></span>  
  
     <span data-ttu-id="3e395-164">PRIMARY_ROLE **(** ALLOW_CONNECTIONS **=** { READ_WRITE | ALL } **)**</span><span class="sxs-lookup"><span data-stu-id="3e395-164">PRIMARY_ROLE **(** ALLOW_CONNECTIONS **=** { READ_WRITE | ALL } **)**</span></span>  
  
     <span data-ttu-id="3e395-165">où :</span><span class="sxs-lookup"><span data-stu-id="3e395-165">where,</span></span>  
  
     <span data-ttu-id="3e395-166">READ_WRITE</span><span class="sxs-lookup"><span data-stu-id="3e395-166">READ_WRITE</span></span>  
     <span data-ttu-id="3e395-167">Les connexions où la propriété de connexion d’intention de l’application a la valeur **ReadOnly** ne sont pas autorisées.</span><span class="sxs-lookup"><span data-stu-id="3e395-167">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span>  <span data-ttu-id="3e395-168">Lorsque la propriété d'intention de l'application a la valeur **ReadWrite** ou si cette propriété n'est pas définie, la connexion est autorisée.</span><span class="sxs-lookup"><span data-stu-id="3e395-168">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="3e395-169">Pour plus d'informations sur la propriété de connexion d'intention de l'application, consultez [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="3e395-169">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
     <span data-ttu-id="3e395-170">ALL</span><span class="sxs-lookup"><span data-stu-id="3e395-170">ALL</span></span>  
     <span data-ttu-id="3e395-171">Toutes les connexions aux bases de données sont autorisées dans le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="3e395-171">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="3e395-172">Il s'agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="3e395-172">This is the default setting.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="3e395-173">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3e395-173">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="3e395-174">L'exemple suivant ajoute un réplica secondaire à un groupe de disponibilité nommé *AG2*.</span><span class="sxs-lookup"><span data-stu-id="3e395-174">The following example adds a secondary replica to an availability group named *AG2*.</span></span> <span data-ttu-id="3e395-175">Une instance de serveur autonome, *COMPUTER03\HADR_INSTANCE*, est spécifiée pour héberger le nouveau réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="3e395-175">A stand-alone server instance, *COMPUTER03\HADR_INSTANCE*, is specified to host the new availability replica.</span></span> <span data-ttu-id="3e395-176">Ce réplica est configuré pour autoriser uniquement les connexions en lecture/écriture pour le rôle principal et pour autoriser uniquement les connexions de tentative de lecture pour le rôle secondaire.</span><span class="sxs-lookup"><span data-stu-id="3e395-176">This replica configured to allow only read-write connections for the primary role and to allow only read-intent connections for secondary role.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP AG2   
   ADD REPLICA ON   
      'COMPUTER03\HADR_INSTANCE' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER03:7022',  
         PRIMARY_ROLE ( ALLOW_CONNECTIONS = READ_WRITE ),  
         SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY )  
         );   
GO  
```  
  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="3e395-177">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e395-177">Using PowerShell</span></span>  

### <a name="to-configure-access-on-an-availability-replica"></a><span data-ttu-id="3e395-178">Pour configurer l'accès sur un réplica de disponibilité</span><span class="sxs-lookup"><span data-stu-id="3e395-178">To configure access on an availability replica</span></span>
  
> [!NOTE]  
>  <span data-ttu-id="3e395-179">Pour obtenir un exemple de code, consultez les exemples PowerShell plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="3e395-179">For a code example, see the PowerShell examples later in this section.</span></span>  
  
1.  <span data-ttu-id="3e395-180">Accédez au répertoire (`cd`) de l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="3e395-180">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="3e395-181">Lorsque vous ajoutez un réplica de disponibilité à un groupe de disponibilité, utilisez l'applet de commande `New-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="3e395-181">When adding an availability replica to an availability group, use the `New-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="3e395-182">Lorsque vous modifiez un réplica de disponibilité existant, utilisez l'applet de commande `Set-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="3e395-182">When modifying an existing availability replica, use the `Set-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="3e395-183">Les paramètres pertinents sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="3e395-183">The relevant parameters are as follows:</span></span>  
  
    -   <span data-ttu-id="3e395-184">Pour configurer l’accès à la connexion pour le rôle secondaire, spécifiez le `ConnectionModeInSecondaryRole` paramètre *secondary_role_keyword* , où *secondary_role_keyword* correspond à l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e395-184">To configure connection access for the secondary role, specify the `ConnectionModeInSecondaryRole`*secondary_role_keyword* parameter, where *secondary_role_keyword* equals one of the following values:</span></span>  
  
         `AllowNoConnections`  
         <span data-ttu-id="3e395-185">Aucune connexion directe n'est autorisée aux bases de données dans le réplica secondaire et les bases de données ne sont pas disponibles pour un accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="3e395-185">No direct connections are allowed to the databases in the secondary replica and the databases are not available for read access.</span></span> <span data-ttu-id="3e395-186">Il s'agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="3e395-186">This is the default setting.</span></span>  
  
         `AllowReadIntentConnectionsOnly`  
         <span data-ttu-id="3e395-187">Seules sont autorisées les connexions aux bases de données dans le réplica secondaire où la propriété d’intention de l’application est définie sur **ReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="3e395-187">Connections are allowed only to the databases in the secondary replica where the Application Intent property is set to **ReadOnly**.</span></span> <span data-ttu-id="3e395-188">Pour plus d'informations sur cette propriété, consultez [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="3e395-188">For more information about this property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
         `AllowAllConnections`  
         <span data-ttu-id="3e395-189">Toutes les connexions sont autorisées aux bases de données dans le réplica secondaire pour un accès en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="3e395-189">All connections are allowed to the databases in the secondary replica for read-only access.</span></span>  
  
    -   <span data-ttu-id="3e395-190">Pour configurer l’accès à la connexion pour le rôle principal, spécifiez `ConnectionModeInPrimaryRole` *primary_role_keyword*, où *primary_role_keyword* est égal à l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e395-190">To configure connection access for the primary role, specify `ConnectionModeInPrimaryRole`*primary_role_keyword*, where *primary_role_keyword* equals one of the following values:</span></span>  
  
         `AllowReadWriteConnections`  
         <span data-ttu-id="3e395-191">Les connexions où la propriété de connexion d'intention de l'application a la valeur ReadOnly ne sont pas autorisées.</span><span class="sxs-lookup"><span data-stu-id="3e395-191">Connections where the Application Intent connection property is set to ReadOnly are disallowed.</span></span> <span data-ttu-id="3e395-192">Lorsque la propriété d'intention de l'application a la valeur ReadWrite ou si cette propriété n'est pas définie, la connexion est autorisée.</span><span class="sxs-lookup"><span data-stu-id="3e395-192">When the Application Intent property is set to ReadWrite or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="3e395-193">Pour plus d'informations sur la propriété de connexion d'intention de l'application, consultez [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="3e395-193">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
         `AllowAllConnections`  
         <span data-ttu-id="3e395-194">Toutes les connexions aux bases de données sont autorisées dans le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="3e395-194">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="3e395-195">Il s'agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="3e395-195">This is the default setting.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3e395-196">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e395-196">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="3e395-197">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="3e395-197">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="3e395-198">Pour configurer et utiliser le fournisseur de SQL Server PowerShell, consultez [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="3e395-198">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
<span data-ttu-id="3e395-199">L'exemple suivant définit les paramètres `ConnectionModeInSecondaryRole` et `ConnectionModeInPrimaryRole` sur `AllowAllConnections`.</span><span class="sxs-lookup"><span data-stu-id="3e395-199">The following example, sets the both the `ConnectionModeInSecondaryRole` and `ConnectionModeInPrimaryRole` parameters to `AllowAllConnections`.</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\PrimaryServer\default\AvailabilityGroups\MyAg  
$primaryReplica = Get-Item "AvailabilityReplicas\PrimaryServer"  

Set-SqlAvailabilityReplica -ConnectionModeInSecondaryRole "AllowAllConnections" `
 -InputObject $primaryReplica  
Set-SqlAvailabilityReplica -ConnectionModeInPrimaryRole "AllowAllConnections" `
-InputObject $primaryReplica
```  

##  <a name="follow-up-after-configuring-read-only-access-for-an-availability-replica"></a><a name="FollowUp"></a> <span data-ttu-id="3e395-200">Suivi : Après avoir configuré l’accès en lecture seule pour un réplica de disponibilité</span><span class="sxs-lookup"><span data-stu-id="3e395-200">Follow Up: After Configuring Read-Only Access for an Availability Replica</span></span>  
 <span data-ttu-id="3e395-201">**Accès en lecture seule aux réplicas secondaires accessibles en lecture.**</span><span class="sxs-lookup"><span data-stu-id="3e395-201">**Read-only access to a readable secondary replica**</span></span>  
  
-   <span data-ttu-id="3e395-202">Lorsque vous utilisez l' [utilitaire bcp](../../../tools/bcp-utility.md) ou l' [utilitaire sqlcmd](../../../tools/sqlcmd-utility.md), vous pouvez spécifier l’accès en lecture seule à n’importe quel réplica secondaire qui est activé pour l’accès en lecture seule en spécifiant le `-K ReadOnly` commutateur.</span><span class="sxs-lookup"><span data-stu-id="3e395-202">When using the [bcp Utility](../../../tools/bcp-utility.md) or [sqlcmd Utility](../../../tools/sqlcmd-utility.md), you can specify read-only access to any secondary replica that is enabled for read-only access by specifying the `-K ReadOnly` switch.</span></span>  
  
-   <span data-ttu-id="3e395-203">Pour permettre aux applications clientes de se connecter aux réplicas secondaires accessibles en lecture :</span><span class="sxs-lookup"><span data-stu-id="3e395-203">To enable client applications to connect to readable secondary replicas:</span></span>  
  
    ||<span data-ttu-id="3e395-204">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="3e395-204">Prerequisite</span></span>|<span data-ttu-id="3e395-205">Lien</span><span class="sxs-lookup"><span data-stu-id="3e395-205">Link</span></span>|  
    |-|------------------|----------|  
    |<span data-ttu-id="3e395-206">![Case à cocher](../../media/checkboxemptycenterxtraspacetopandright.gif "Case à cocher")</span><span class="sxs-lookup"><span data-stu-id="3e395-206">![Checkbox](../../media/checkboxemptycenterxtraspacetopandright.gif "Checkbox")</span></span>|<span data-ttu-id="3e395-207">Assurez-vous que le groupe de disponibilité possède un écouteur.</span><span class="sxs-lookup"><span data-stu-id="3e395-207">Ensure that the availability group has a listener.</span></span>|[<span data-ttu-id="3e395-208">Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3e395-208">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)|  
    |<span data-ttu-id="3e395-209">![Case à cocher](../../media/checkboxemptycenterxtraspacetopandright.gif "Case à cocher")</span><span class="sxs-lookup"><span data-stu-id="3e395-209">![Checkbox](../../media/checkboxemptycenterxtraspacetopandright.gif "Checkbox")</span></span>|<span data-ttu-id="3e395-210">Configurez le routage en lecture seule pour le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="3e395-210">Configure read-only routing for the availability group.</span></span>|[<span data-ttu-id="3e395-211">Configurer le routage en lecture seule pour un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3e395-211">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)|  
  
 <span data-ttu-id="3e395-212">**Facteurs qui peuvent affecter les déclencheurs et les travaux à la suite d'un basculement**</span><span class="sxs-lookup"><span data-stu-id="3e395-212">**Factors that might affect triggers and jobs after a failover**</span></span>  
  
 <span data-ttu-id="3e395-213">Si vous avez des déclencheurs et des travaux qui vont échouer lors de l'exécution sur une base de données secondaire inaccessible en lecture ou sur une base de données secondaire accessible en lecture, vous devez générer un script pour les déclencheurs et travaux à vérifier sur un réplica donné afin de déterminer si la base de données est une base de données principale ou une base de données secondaire accessible en lecture.</span><span class="sxs-lookup"><span data-stu-id="3e395-213">If you have triggers and jobs that will fail when running on a non-readable secondary database or on a readable secondary database, you need to script the triggers and jobs to check on a given replica to determine whether the database is a primary database or is a readable secondary database.</span></span> <span data-ttu-id="3e395-214">Pour obtenir ces informations, utilisez la fonction [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) pour retourner la propriété **Updatability** de la base de données.</span><span class="sxs-lookup"><span data-stu-id="3e395-214">To obtain this information, use the [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **Updatability** property of the database.</span></span> <span data-ttu-id="3e395-215">Pour identifier une base de données en lecture seule, spécifiez la valeur READ_ONLY, comme suit :</span><span class="sxs-lookup"><span data-stu-id="3e395-215">To identify a read-only database, specify READ_ONLY as the value, as follows:</span></span>  
  
```  
DATABASEPROPERTYEX([db name],'Updatability') = N'READ_ONLY'  
```  
  
 <span data-ttu-id="3e395-216">Pour identifier une base de données en lecture-écriture, spécifiez la valeur READ_WRITE.</span><span class="sxs-lookup"><span data-stu-id="3e395-216">To identify a read-write database, specify READ_WRITE as the value.</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="3e395-217">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="3e395-217">Related Tasks</span></span>  
  
-   [<span data-ttu-id="3e395-218">Configurer le routage en lecture seule pour un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3e395-218">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="3e395-219">Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3e395-219">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="3e395-220">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="3e395-220">Related Content</span></span>  
  
-   [<span data-ttu-id="3e395-221">Always On : Proposition de valeur du réplica secondaire accessible en lecture</span><span class="sxs-lookup"><span data-stu-id="3e395-221">Always On: Value Proposition of Readable Secondary</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-value-proposition-of-readable-secondary)  
  
-   [<span data-ttu-id="3e395-222">Always On : Pourquoi existe-t-il deux options pour activer un réplica secondaire pour la charge de travail en lecture ?</span><span class="sxs-lookup"><span data-stu-id="3e395-222">Always On: Why there are two options to enable a secondary replica for read workload?</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-why-there-are-two-options-to-enable-a-secondary-replica-for-read-workload)  
  
-   [<span data-ttu-id="3e395-223">Always On : Configuration d’un réplica secondaire accessible en lecture</span><span class="sxs-lookup"><span data-stu-id="3e395-223">Always On: Setting up Readable Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-setting-up-readable-seconary-replica)  
  
-   [<span data-ttu-id="3e395-224">Always On : J’ai activé un réplica secondaire accessible en lecture, mais ma requête est bloquée</span><span class="sxs-lookup"><span data-stu-id="3e395-224">Always On: I just enabled Readable Secondary but my query is blocked?</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-i-just-enabled-readable-secondary-but-my-query-is-blocked)  
  
-   [<span data-ttu-id="3e395-225">Always On : Mise à disposition des dernières statistiques disponibles sur le réplica secondaire accessible en lecture, la base de données en lecture seule et l’instantané de base de données</span><span class="sxs-lookup"><span data-stu-id="3e395-225">Always On: Making latest statistics available on Readable Secondary, Read-Only database and Database Snapshot</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-making-latest-statistics-available-on-readable-secondary-read-only-database-and-database-snapshot)  
  
-   [<span data-ttu-id="3e395-226">Always On : Problèmes avec des statistiques sur la base de données en lecture seule, l’instantané de base de données et le réplica secondaire</span><span class="sxs-lookup"><span data-stu-id="3e395-226">Always On: Challenges with statistics on ReadOnly database, Database Snapshot and Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-challenges-with-statistics-on-readonly-database-database-snapshot-and-secondary-replica)  
  
-   [<span data-ttu-id="3e395-227">Always On : Impact sur la charge de travail principale lorsque vous exécutez la charge de travail de création de rapports sur le réplica secondaire</span><span class="sxs-lookup"><span data-stu-id="3e395-227">Always On: Impact on the primary workload when you run reporting workload on the secondary replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-impact-on-the-primary-workload-when-you-run-reporting-workload-on-the-secondary-replica)  
  
-   [<span data-ttu-id="3e395-228">Always On : Impact du mappage entre la charge de travail de création de rapports sur le réplica secondaire accessible en lecture et l’isolement d’instantané</span><span class="sxs-lookup"><span data-stu-id="3e395-228">Always On: Impact of mapping reporting workload on Readable Secondary to Snapshot Isolation</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-impact-of-mapping-reporting-workload-on-readable-secondary-to-snapshot-isolation)  
  
-   [<span data-ttu-id="3e395-229">Always On : Réduction des blocages de thread REDO lors de l’exécution d’une charge de travail de création de rapports sur le réplica secondaire</span><span class="sxs-lookup"><span data-stu-id="3e395-229">Always On: Minimizing blocking of REDO thread when running reporting workload on Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-minimizing-blocking-of-redo-thread-when-running-reporting-workload-on-secondary-replica)  
  
-   [<span data-ttu-id="3e395-230">Always On : Réplica secondaire accessible en lecture et latence des données</span><span class="sxs-lookup"><span data-stu-id="3e395-230">Always On: Readable Secondary and data latency</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-readable-secondary-and-data-latency)  
  
## <a name="see-also"></a><span data-ttu-id="3e395-231">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e395-231">See Also</span></span>  
 <span data-ttu-id="3e395-232">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3e395-232">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="3e395-233">Secondaires actifs : réplicas secondaires accessibles en lecture &#40;groupes de disponibilité AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="3e395-233">Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;</span></span>](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)  
 [<span data-ttu-id="3e395-234">À propos de l’accès de la connexion client aux réplicas de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3e395-234">About Client Connection Access to Availability Replicas &#40;SQL Server&#41;</span></span>](about-client-connection-access-to-availability-replicas-sql-server.md)  
