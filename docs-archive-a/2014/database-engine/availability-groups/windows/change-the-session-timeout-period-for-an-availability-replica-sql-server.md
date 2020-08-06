---
title: Changer le délai d’expiration de session pour un réplica de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], session timeout
- session timeout [SQL Server]
ms.assetid: e23c6e06-1cd1-4d4a-9bc2-e3e06ab2933d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 302ba4a2b0b72a70b05e563eb4085913074469eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708672"
---
# <a name="change-the-session-timeout-period-for-an-availability-replica-sql-server"></a><span data-ttu-id="dbed1-102">Modifier le délai d'expiration de session pour un réplica de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="dbed1-102">Change the Session-Timeout Period for an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="dbed1-103">Cette rubrique explique comment configurer la période d'expiration de session d'un réplica de disponibilité AlwaysOn à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou de PowerShell dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbed1-103">This topic describes how to configure the session-timeout period of an AlwaysOn availability replica by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="dbed1-104">La période d'expiration de session est une propriété de réplica qui contrôle le nombre de secondes (en secondes) pendant lequel un réplica de disponibilité attend une réponse ping d'un réplica connecté avant de considérer que la connexion a échoué.</span><span class="sxs-lookup"><span data-stu-id="dbed1-104">The session-timeout period is a replica property that controls how many seconds (in seconds) that an availability replica waits for a ping response from a connected replica before considering the connection to have failed.</span></span> <span data-ttu-id="dbed1-105">Par défaut, un réplica attend une réponse ping pendant 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="dbed1-105">By default, a replica waits 10 seconds for a ping response.</span></span> <span data-ttu-id="dbed1-106">Cette propriété de réplica applique uniquement la connexion entre un réplica secondaire donné et le réplica principal du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="dbed1-106">This replica property applies only the connection between a given secondary replica and the primary replica of the availability group.</span></span> <span data-ttu-id="dbed1-107">Pour plus d’informations sur le délai d’expiration de session, consultez [Vue d’ensemble des groupes de disponibilité Always On &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dbed1-107">For more information about the session-timeout period, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="dbed1-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="dbed1-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dbed1-109">Composants requis</span><span class="sxs-lookup"><span data-stu-id="dbed1-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="dbed1-110">Recommandations</span><span class="sxs-lookup"><span data-stu-id="dbed1-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="dbed1-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="dbed1-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dbed1-112">**Pour modifier la période d'expiration de session, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="dbed1-112">**To change the session-timeout period, using:**</span></span>  
  
     [<span data-ttu-id="dbed1-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dbed1-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="dbed1-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dbed1-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="dbed1-115">PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbed1-115">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dbed1-116">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="dbed1-116">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="dbed1-117">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="dbed1-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="dbed1-118">Vous devez être connecté à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="dbed1-118">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="dbed1-119">Recommandations</span><span class="sxs-lookup"><span data-stu-id="dbed1-119">Recommendations</span></span>  
 <span data-ttu-id="dbed1-120">Le temps d'attente recommandé est de 10 secondes minimum.</span><span class="sxs-lookup"><span data-stu-id="dbed1-120">We recommend that you keep the time-out period at 10 seconds or greater.</span></span> <span data-ttu-id="dbed1-121">En définissant une valeur inférieure à 10 secondes, vous créez la possibilité qu'un système surchargé soit à court de PING et qu'il déclare à tort une défaillance.</span><span class="sxs-lookup"><span data-stu-id="dbed1-121">Setting the value to less than 10 seconds creates the possibility of a heavily loaded system missing PINGs and declaring a false failure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dbed1-122">Sécurité</span><span class="sxs-lookup"><span data-stu-id="dbed1-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dbed1-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="dbed1-123">Permissions</span></span>  
 <span data-ttu-id="dbed1-124">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="dbed1-124">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dbed1-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dbed1-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="dbed1-126">**Pour modifier la période d'expiration de session pour un réplica de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="dbed1-126">**To change the session-timeout period for an availability replica**</span></span>  
  
1.  <span data-ttu-id="dbed1-127">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge le réplica principal et développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="dbed1-127">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="dbed1-128">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="dbed1-128">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="dbed1-129">Cliquez sur le groupe de disponibilité dont vous souhaitez configurer le réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="dbed1-129">Click the availability group whose availability replica you want to configure.</span></span>  
  
4.  <span data-ttu-id="dbed1-130">Cliquez avec le bouton droit sur le réplica à configurer, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="dbed1-130">Right-click the replica to be configured, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="dbed1-131">Dans la boîte de dialogue **Propriétés du réplica de disponibilité** , utilisez le champ **Délai d’expiration de session (secondes)** pour modifier le nombre de secondes pour la période d’expiration de session sur ce réplica.</span><span class="sxs-lookup"><span data-stu-id="dbed1-131">In the **Availability Replica Properties** dialog box, use the **Session timeout (seconds)** field to change the number of seconds for the session-timeout period on this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dbed1-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dbed1-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="dbed1-133">**Pour modifier la période d'expiration de session pour un réplica de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="dbed1-133">**To change the session-timeout period for an availability replica**</span></span>  
  
1.  <span data-ttu-id="dbed1-134">Connectez-vous à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="dbed1-134">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="dbed1-135">Utilisez l'instruction [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , comme suit :</span><span class="sxs-lookup"><span data-stu-id="dbed1-135">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="dbed1-136">ALTER AVAILABILITY GROUP *nom_groupe*</span><span class="sxs-lookup"><span data-stu-id="dbed1-136">ALTER AVAILABILITY GROUP *group_name*</span></span>  
  
     <span data-ttu-id="dbed1-137">MODIFY REPLICA ON «*nom_instance*» WITH ( SESSION_TIMEOUT =*secondes* )</span><span class="sxs-lookup"><span data-stu-id="dbed1-137">MODIFY REPLICA ON '*instance_name*' WITH ( SESSION_TIMEOUT =*seconds* )</span></span>  
  
     <span data-ttu-id="dbed1-138">où *nom_groupe* est le nom du groupe de disponibilité, *nom_instance* est le nom de l’instance de serveur qui héberge le réplica de disponibilité à modifier, et *secondes* spécifie le nombre minimal de secondes pendant lesquelles le réplica doit attendre avant d’appliquer un journal aux bases de données lorsqu’il joue le rôle de réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="dbed1-138">where *group_name* is the name of the availability group, *instance_name* is the name of the server instance that hosts the availability replica to be modified, and *seconds* specifies the minimum number of seconds that the replica must wait before applying log to databases when acting as a secondary replica.</span></span> <span data-ttu-id="dbed1-139">La valeur par défaut est de 0 seconde, ce qui indique qu'il n'existe pas de délai d'application.</span><span class="sxs-lookup"><span data-stu-id="dbed1-139">The default is 0 seconds, which indicates that there is no apply delay.</span></span>  
  
     <span data-ttu-id="dbed1-140">L'exemple suivant, écrit sur le réplica principal du groupe de disponibilité `AccountsAG` modifie la valeur d'expiration de session sur `15` secondes pour le réplica situé sur l'instance de serveur `INSTANCE09` .</span><span class="sxs-lookup"><span data-stu-id="dbed1-140">The following example, entered on the primary replica of the `AccountsAG` availability group, changes the session-timeout value to `15` seconds for the replica located on the `INSTANCE09` server instance.</span></span>  
  
    ```  
    ALTER AVAILABILITY GROUP AccountsAG   
       MODIFY REPLICA ON 'INSTANCE09' WITH (SESSION_TIMEOUT = 15);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="dbed1-141">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbed1-141">Using PowerShell</span></span>  

### <a name="to-change-the-session-timeout-period-for-an-availability-replica"></a><span data-ttu-id="dbed1-142">Pour modifier la période d'expiration de session pour un réplica de disponibilité</span><span class="sxs-lookup"><span data-stu-id="dbed1-142">To change the session-timeout period for an availability replica</span></span>
  
1.  <span data-ttu-id="dbed1-143">Accédez au répertoire (`cd`) de l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="dbed1-143">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="dbed1-144">Utilisez l'applet de commande `Set-SqlAvailabilityReplica` avec le paramètre `SessionTimeout` pour modifier le nombre de secondes pour la période d'expiration de session sur un réplica de disponibilité spécifié.</span><span class="sxs-lookup"><span data-stu-id="dbed1-144">Use the `Set-SqlAvailabilityReplica` cmdlet with the `SessionTimeout` parameter to change the number of seconds for the session-timeout period on a specified availability replica.</span></span>  
  
     <span data-ttu-id="dbed1-145">Par exemple, la commande suivante définit le délai d'expiration de session sur 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="dbed1-145">For example, the following command sets the session-timeout period to 15 seconds.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -SessionTimeout 15 -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="dbed1-146">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dbed1-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="dbed1-147">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="dbed1-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="dbed1-148">Pour configurer et utiliser le fournisseur de SQL Server PowerShell, consultez [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="dbed1-148">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dbed1-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dbed1-149">See Also</span></span>  
 [<span data-ttu-id="dbed1-150">Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dbed1-150">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
