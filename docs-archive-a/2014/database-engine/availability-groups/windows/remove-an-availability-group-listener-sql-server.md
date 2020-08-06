---
title: Supprimer un écouteur de groupe de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removeaglistener.default.f1
helpviewer_keywords:
- Availability Groups [SQL Server], listeners
ms.assetid: fd9bba9a-d29f-4c23-8ecd-aaa049ed5f1b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 057b9c137cb4d8bbbdd03be61df600f7e59b264c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603054"
---
# <a name="remove-an-availability-group-listener-sql-server"></a><span data-ttu-id="ba701-102">Supprimer un écouteur de groupe de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ba701-102">Remove an Availability Group Listener (SQL Server)</span></span>
  <span data-ttu-id="ba701-103">Cette rubrique explique comment supprimer un écouteur de groupe de disponibilité d'un groupe de disponibilité AlwaysOn à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou PowerShell dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba701-103">This topic describes how to remove an availability group listener from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="ba701-104">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="ba701-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ba701-105">Composants requis</span><span class="sxs-lookup"><span data-stu-id="ba701-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="ba701-106">Recommandations</span><span class="sxs-lookup"><span data-stu-id="ba701-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="ba701-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ba701-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ba701-108">**Pour supprimer un écouteur à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="ba701-108">**To remove a listener, using:**</span></span>  
  
     [<span data-ttu-id="ba701-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ba701-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ba701-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ba701-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="ba701-111">PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba701-111">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ba701-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ba701-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="ba701-113">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="ba701-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="ba701-114">Vous devez être connecté à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="ba701-114">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="ba701-115">Recommandations</span><span class="sxs-lookup"><span data-stu-id="ba701-115">Recommendations</span></span>  
 <span data-ttu-id="ba701-116">Avant de supprimer un écouteur de groupe de disponibilité, nous vous recommandons de vérifier qu'aucune application ne l'utilise.</span><span class="sxs-lookup"><span data-stu-id="ba701-116">Before you delete an availability group listener, we recommend that you ensure that no applications are using it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ba701-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ba701-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ba701-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="ba701-118">Permissions</span></span>  
 <span data-ttu-id="ba701-119">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="ba701-119">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ba701-120">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ba701-120">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="ba701-121">**Pour supprimer un écouteur de groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="ba701-121">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="ba701-122">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge le réplica principal, cliquez sur le nom du serveur pour développer l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="ba701-122">In Object Explorer, connect to the server instance that hosts the primary replica, and click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="ba701-123">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="ba701-123">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="ba701-124">Développez le nœud du groupe de disponibilité, puis développez le nœud **Écouteurs de groupe de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="ba701-124">Expand the node of the availability group, and expand the **Availability Groups Listeners** node.</span></span>  
  
4.  <span data-ttu-id="ba701-125">Cliquez avec le bouton droit sur l’écouteur à supprimer et sélectionnez la commande **Supprimer** .</span><span class="sxs-lookup"><span data-stu-id="ba701-125">Right-click the listener to be removed, and select the **Delete** command.</span></span>  
  
5.  <span data-ttu-id="ba701-126">Cela ouvre la boîte de dialogue **Supprimer l'écouteur du groupe de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="ba701-126">This opens the **Remove Listener from Availability Group** dialog box.</span></span> <span data-ttu-id="ba701-127">Pour plus d'informations, consultez [Supprimer l'écouteur du groupe de disponibilité](#AgListenerPropertiesDialog), plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="ba701-127">For more information, see [Remove Listener from Availability Group](#AgListenerPropertiesDialog), later in this topic.</span></span>  
  
###  <a name="remove-listener-from-availability-group-dialog-box"></a><a name="AgListenerPropertiesDialog"></a><span data-ttu-id="ba701-128">Supprimer l’écouteur du groupe de disponibilité (boîte de dialogue)</span><span class="sxs-lookup"><span data-stu-id="ba701-128">Remove Listener from Availability Group (Dialog Box)</span></span>  
 <span data-ttu-id="ba701-129">**Nom**</span><span class="sxs-lookup"><span data-stu-id="ba701-129">**Name**</span></span>  
 <span data-ttu-id="ba701-130">Nom de l'écouteur à supprimer.</span><span class="sxs-lookup"><span data-stu-id="ba701-130">The name of the listener to be removed.</span></span>  
  
 <span data-ttu-id="ba701-131">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="ba701-131">**Result**</span></span>  
 <span data-ttu-id="ba701-132">Affiche un lien, **Opération réussie** ou **Erreur**, sur lequel vous pouvez cliquer pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="ba701-132">Displays a link, either **Success** or **Error**, which you can click for more information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ba701-133">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ba701-133">Using Transact-SQL</span></span>  
 <span data-ttu-id="ba701-134">**Pour supprimer un écouteur de groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="ba701-134">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="ba701-135">Connectez-vous à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="ba701-135">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="ba701-136">Utilisez l'instruction [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , comme suit :</span><span class="sxs-lookup"><span data-stu-id="ba701-136">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="ba701-137">ALTER AVAILABILITY GROUP *group_name* supprimer l’écouteur **' *`dns_name`* '**</span><span class="sxs-lookup"><span data-stu-id="ba701-137">ALTER AVAILABILITY GROUP *group_name* REMOVE LISTENER **'*`dns_name`*'**</span></span>  
  
     <span data-ttu-id="ba701-138">où *nom_groupe* est le nom du groupe de disponibilité et *nom_dns* est le nom DNS de l’écouteur du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="ba701-138">where *group_name* is the name of the availability group and *dns_name* is the DNS name of the availability group listener.</span></span>  
  
     <span data-ttu-id="ba701-139">L'exemple suivant supprime l'écouteur du groupe de disponibilité `AccountsAG` .</span><span class="sxs-lookup"><span data-stu-id="ba701-139">The following example deletes the listener of the `AccountsAG` availability group.</span></span> <span data-ttu-id="ba701-140">Le nom DNS est AccountsAG_Listener.</span><span class="sxs-lookup"><span data-stu-id="ba701-140">The DNS name is AccountsAG_Listener.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP AccountsAG REMOVE LISTENER 'AccountsAG_Listener';  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="ba701-141">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba701-141">Using PowerShell</span></span>  
 <span data-ttu-id="ba701-142">**Pour supprimer un écouteur de groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="ba701-142">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="ba701-143">Définissez la valeur par défaut (`cd`) sur l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="ba701-143">Set default (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="ba701-144">Utilisez l'applet de commande `Remove-Item` intégrée pour supprimer un écouteur.</span><span class="sxs-lookup"><span data-stu-id="ba701-144">Use the built in `Remove-Item` cmdlet to remove a listener.</span></span> <span data-ttu-id="ba701-145">Par exemple, la commande suivante supprime un écouteur nommé `MyListener` d'un groupe de disponibilité nommé `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="ba701-145">For example, the following command removes a listener named `MyListener` from an availability group named `MyAg`.</span></span>  
  
    ```powershell
    Remove-Item SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AGListeners\MyListener  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="ba701-146">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba701-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="ba701-147">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ba701-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ba701-148">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ba701-148">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ba701-149">Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ba701-149">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="ba701-150">Afficher les propriétés d’écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ba701-150">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ba701-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba701-151">See Also</span></span>  
 <span data-ttu-id="ba701-152">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ba701-152">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="ba701-153">Écouteurs de groupe de disponibilité, connectivité client et basculement d’application &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ba701-153">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)  
