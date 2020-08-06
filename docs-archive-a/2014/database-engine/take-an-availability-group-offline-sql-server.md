---
title: Modifier le groupe de disponibilité hors connexion
description: Procédure de configuration de votre groupe de disponibilité Always On en mode hors connexion
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], take offline
ms.assetid: 50f5aad8-0dff-45ef-8350-f9596d3db898
author: rothja
ms.author: jroth
ms.openlocfilehash: db2f56befe6905b9c3de6bd1ab6a2e5a4a00b1b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610832"
---
# <a name="take-an-availability-group-offline-sql-server"></a><span data-ttu-id="caaff-103">Placer un groupe de disponibilité hors connexion (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="caaff-103">Take an Availability Group Offline (SQL Server)</span></span>
  <span data-ttu-id="caaff-104">Cette rubrique explique comment faire passer un groupe de disponibilité AlwaysOn de l'état ONLINE à l'état OFFLINE à l'aide de [!INCLUDE[tsql](../includes/tsql-md.md)] dans [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="caaff-104">This topic describes how to take an AlwaysOn availability group from the ONLINE state to the OFFLINE state by using [!INCLUDE[tsql](../includes/tsql-md.md)] in [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] and later versions.</span></span> <span data-ttu-id="caaff-105">Il n'y a aucune perte de données des bases de données de validation synchrone, car si aucun réplica avec validation synchrone n'est synchronisé, l'opération OFFLINE génère une erreur et conserve le groupe de disponibilité dans l'état ONLINE.</span><span class="sxs-lookup"><span data-stu-id="caaff-105">There is no data loss for synchronous-commit databases because if any synchronous-commit replica is not synchronized, the OFFLINE operation raises an error and leaves the availability group ONLINE.</span></span> <span data-ttu-id="caaff-106">Conserver le groupe de disponibilité en ligne protège les bases de données non synchronisées avec validation synchrone contre la perte de données.</span><span class="sxs-lookup"><span data-stu-id="caaff-106">Keeping the availability group online protects unsynchronized synchronous-commit databases from possible data loss.</span></span> <span data-ttu-id="caaff-107">Après qu'un groupe de disponibilité a été mis hors connexion, ses bases de données deviennent indisponibles pour les clients et vous ne pouvez pas remettre le groupe de disponibilité en ligne.</span><span class="sxs-lookup"><span data-stu-id="caaff-107">After an availability group goes offline, its databases become unavailable to clients and you cannot bring the availability group back online.</span></span> <span data-ttu-id="caaff-108">Par conséquent, mettez un groupe de disponibilité hors connexion uniquement pour migrer les ressources du groupe de disponibilité d'un cluster WSFC à un autre.</span><span class="sxs-lookup"><span data-stu-id="caaff-108">Therefore, take an availability group offline only to migrate the availability group resources from one WSFC cluster to another.</span></span>  
  
 <span data-ttu-id="caaff-109">Pendant une migration entre clusters de [!INCLUDE[ssHADR](../includes/sshadr-md.md)], si les applications se connectent directement au réplica principal d'un groupe de disponibilité, le groupe de disponibilité doit être mis hors connexion.</span><span class="sxs-lookup"><span data-stu-id="caaff-109">During a cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)], if any applications connect directly to the primary replica of an availability group, the availability group must be taken offline.</span></span> <span data-ttu-id="caaff-110">La migration entre clusters de [!INCLUDE[ssHADR](../includes/sshadr-md.md)] prend en charge la mise à niveau du système d'exploitation avec un temps mort minimal des groupes de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="caaff-110">Cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)] supports OS upgrade with minimal downtime of availability groups.</span></span> <span data-ttu-id="caaff-111">Le scénario classique consiste à utiliser la migration entre clusters de [!INCLUDE[ssHADR](../includes/sshadr-md.md)] pour la mise à niveau du système d'exploitation vers [!INCLUDE[win8](../includes/win8-md.md)] ou [!INCLUDE[win8srv](../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="caaff-111">The typical scenario is to use cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)] for OS upgrade to [!INCLUDE[win8](../includes/win8-md.md)] or [!INCLUDE[win8srv](../includes/win8srv-md.md)].</span></span> <span data-ttu-id="caaff-112">Pour plus d'informations, consultez [Migration entre clusters de groupes de disponibilité AlwaysOn pour la mise à niveau du système d'exploitation](https://msdn.microsoft.com/library/jj873730.aspx).</span><span class="sxs-lookup"><span data-stu-id="caaff-112">For more information, see [Cross-Cluster Migration of AlwaysOn Availability Groups for OS Upgrade](https://msdn.microsoft.com/library/jj873730.aspx).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="caaff-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="caaff-113">Before You Begin</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="caaff-114">Utilisez l'option OFFLINE uniquement pour une migration entre clusters des ressources du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="caaff-114">Use the OFFLINE option only for a cross-cluster migration of availability group resources.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="caaff-115">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="caaff-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="caaff-116">L'instance de serveur sur laquelle vous sélectionnez la commande OFFLINE doit exécuter [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] ou version ultérieure (édition Entreprise ou ultérieure).</span><span class="sxs-lookup"><span data-stu-id="caaff-116">The server instance on which you enter the OFFLINE command must be running [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] or above (Enterprise edition or above).</span></span>  
  
-   <span data-ttu-id="caaff-117">Le groupe de disponibilité doit être en ligne.</span><span class="sxs-lookup"><span data-stu-id="caaff-117">The availability group must currently be online.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="caaff-118">Recommandations</span><span class="sxs-lookup"><span data-stu-id="caaff-118">Recommendations</span></span>  
 <span data-ttu-id="caaff-119">Avant de mettre le groupe de disponibilité hors connexion, supprimez le ou les écouteurs du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="caaff-119">Before you take the availability group offline, delete the availability group listener or listeners.</span></span> <span data-ttu-id="caaff-120">Pour plus d’informations, consultez [Supprimer un écouteur de groupe de disponibilité &#40;SQL Server&#41;](availability-groups/windows/remove-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="caaff-120">For more information, see [Remove an Availability Group Listener &#40;SQL Server&#41;](availability-groups/windows/remove-an-availability-group-listener-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="caaff-121">Sécurité</span><span class="sxs-lookup"><span data-stu-id="caaff-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="caaff-122">Autorisations</span><span class="sxs-lookup"><span data-stu-id="caaff-122">Permissions</span></span>  
 <span data-ttu-id="caaff-123">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="caaff-123">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="caaff-124">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="caaff-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="caaff-125">**Pour placer le groupe de disponibilité hors connexion**</span><span class="sxs-lookup"><span data-stu-id="caaff-125">**To take an availability group offline**</span></span>  
  
1.  <span data-ttu-id="caaff-126">Connectez-vous à une instance de serveur qui héberge un réplica de disponibilité pour le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="caaff-126">Connect to a server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="caaff-127">Ce réplica peut être le réplica principal ou un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="caaff-127">This replica can be the primary replica or a secondary replica.</span></span>  
  
2.  <span data-ttu-id="caaff-128">Utilisez l'instruction [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , comme suit :</span><span class="sxs-lookup"><span data-stu-id="caaff-128">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="caaff-129">ALTER AVAILABILITY GROUP *nom_groupe* OFFLINE</span><span class="sxs-lookup"><span data-stu-id="caaff-129">ALTER AVAILABILITY GROUP *group_name* OFFLINE</span></span>  
  
     <span data-ttu-id="caaff-130">où *nom_groupe* correspond au nom du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="caaff-130">where *group_name* is the name of the availability group.</span></span>  
  
### <a name="example"></a><span data-ttu-id="caaff-131">Exemple</span><span class="sxs-lookup"><span data-stu-id="caaff-131">Example</span></span>  
 <span data-ttu-id="caaff-132">L'exemple suivant place le groupe de disponibilité `AccountsAG` hors connexion.</span><span class="sxs-lookup"><span data-stu-id="caaff-132">The following example takes the `AccountsAG` availability group offline.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP AccountsAG OFFLINE;  
```  
  
##  <a name="follow-up-after-the-availability-group-goes-offline"></a><a name="FollowUp"></a> <span data-ttu-id="caaff-133">Suivi : Après que le groupe de disponibilité a été mis hors connexion</span><span class="sxs-lookup"><span data-stu-id="caaff-133">Follow Up: After the Availability Group Goes Offline</span></span>  
  
-   <span data-ttu-id="caaff-134">**Enregistrement de l’opération OFFLINE :**  l’identité du nœud WSFC sur lequel l’opération OFFLINE a été initialisée est stockée dans le journal du cluster WSFC et dans le journal des erreurs SQL.</span><span class="sxs-lookup"><span data-stu-id="caaff-134">**Logging of OFFLINE operation:**  The identity of the WSFC node where the OFFLINE operation was initiated is stored in both the WSFC cluster log and the SQL ERRORLOG.</span></span>  
  
-   <span data-ttu-id="caaff-135">**Si vous n’avez pas supprimé l’écouteur de groupe de disponibilité avant de mettre le groupe hors connexion :**  Si vous migrez le groupe de disponibilité vers un autre cluster WSFC, supprimez le VNN et le VIP de l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="caaff-135">**If you did not delete the availability group listener before taking the group offline:**  If you are migrating the availability group to another WSFC cluster, delete the VNN and VIP of the listener.</span></span> <span data-ttu-id="caaff-136">Vous pouvez les supprimer à l’aide de la console de gestion du cluster de basculement, de l’applet de commande PowerShell [Remove-ClusterResource](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx) ou de [cluster.exe](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="caaff-136">You can delete them by using either the Failover Cluster Management console, the [Remove-ClusterResource](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx) PowerShell cmdlet, or [cluster.exe](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx).</span></span> <span data-ttu-id="caaff-137">Notez que cluster.exe est déconseillé sur Windows 8.</span><span class="sxs-lookup"><span data-stu-id="caaff-137">Note that cluster.exe is deprecated on Windows 8.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="caaff-138">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="caaff-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="caaff-139">Supprimer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="caaff-139">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](availability-groups/windows/remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="caaff-140">Changer le contexte de cluster HADR de l’instance de serveur &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="caaff-140">Change the HADR Cluster Context of Server Instance &#40;SQL Server&#41;</span></span>](availability-groups/windows/change-the-hadr-cluster-context-of-server-instance-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="caaff-141">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="caaff-141">Related Content</span></span>  
  
-   <span data-ttu-id="caaff-142">[Articles techniques SQL Server 2012](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="caaff-142">[SQL Server 2012 Technical Articles](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="caaff-143">Blog de l'équipe de SQL Server AlwaysOn : Blog officiel de l'équipe de SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="caaff-143">SQL Server AlwaysOn Team Blog: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
## <a name="see-also"></a><span data-ttu-id="caaff-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="caaff-144">See Also</span></span>  
 [<span data-ttu-id="caaff-145">Groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="caaff-145">AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](availability-groups/windows/always-on-availability-groups-sql-server.md)  
