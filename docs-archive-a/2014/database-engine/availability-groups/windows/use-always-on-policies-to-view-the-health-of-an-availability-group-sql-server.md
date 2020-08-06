---
title: Utiliser des stratégies AlwaysOn pour afficher l’intégrité d’un groupe de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 6f1bcbc3-1220-4071-8e53-4b957f5d3089
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c4444afc2348b2407dc19c1c12761ef0251631e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708623"
---
# <a name="use-alwayson-policies-to-view-the-health-of-an-availability-group-sql-server"></a><span data-ttu-id="ebe82-102">Utiliser les stratégies AlwaysOn pour afficher l'intégrité d'un groupe de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ebe82-102">Use AlwaysOn Policies to View the Health of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="ebe82-103">Cette rubrique explique comment déterminer l'état opérationnel d'un groupe de disponibilité AlwaysOn à l'aide d'une stratégie AlwaysOn dans [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou PowerShell dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ebe82-103">This topic describes how to determine the operational health of an AlwaysOn availability group by using an AlwaysOn policy in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="ebe82-104">Pour plus d’informations sur la gestion basée sur des stratégies AlwaysOn, consultez [stratégies AlwaysOn pour les problèmes opérationnels avec groupes de disponibilité AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="ebe82-104">For information about AlwaysOn Policy Based Management, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ebe82-105">Pour les stratégies AlwaysOn, les noms de catégorie sont utilisés comme identificateurs.</span><span class="sxs-lookup"><span data-stu-id="ebe82-105">For AlwaysOn policies, the category names are used as IDs.</span></span> <span data-ttu-id="ebe82-106">Modifier le nom d'une catégorie AlwaysOn compromettrait sa fonctionnalité d'évaluation de l'intégrité.</span><span class="sxs-lookup"><span data-stu-id="ebe82-106">Changing the name of an AlwaysOn category would break its health-evaluation functionality.</span></span> <span data-ttu-id="ebe82-107">Par conséquent, les noms de catégorie AlwaysOn ne doivent jamais être modifiés.</span><span class="sxs-lookup"><span data-stu-id="ebe82-107">Therefore, the names of AlwaysOn category should never be modified.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ebe82-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ebe82-108">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ebe82-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ebe82-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ebe82-110">Autorisations</span><span class="sxs-lookup"><span data-stu-id="ebe82-110">Permissions</span></span>  
 <span data-ttu-id="ebe82-111">Requiert les autorisations CONNECT, VIEW SERVER STATE et VIEW ANY DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="ebe82-111">Requires CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions.</span></span>  
  
##  <a name="using-the-alwayson-dashboard"></a><a name="SSMSProcedure"></a><span data-ttu-id="ebe82-112">Utilisation du tableau de bord AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="ebe82-112">Using the AlwaysOn Dashboard</span></span>  
 <span data-ttu-id="ebe82-113">**Pour ouvrir le tableau de bord AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="ebe82-113">**To open the AlwaysOn Dashboard**</span></span>  
  
1.  <span data-ttu-id="ebe82-114">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge l'un des réplicas de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="ebe82-114">In Object Explorer, connect to the server instance that hosts one of the availability replicas.</span></span> <span data-ttu-id="ebe82-115">Pour afficher des informations sur tous les réplicas de disponibilité d'un groupe de disponibilité, utilisez l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="ebe82-115">To view information about all of the availability replicas in an availability group, use to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="ebe82-116">Cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="ebe82-116">Click the server name to expand the server tree.</span></span>  
  
3.  <span data-ttu-id="ebe82-117">Développez le nœud **Haute disponibilité AlwaysOn** .</span><span class="sxs-lookup"><span data-stu-id="ebe82-117">Expand the **AlwaysOn High Availability** node.</span></span>  
  
     <span data-ttu-id="ebe82-118">Cliquez avec le bouton droit sur le nœud **Groupes de disponibilité** ou développez ce nœud et cliquez avec le bouton droit sur un groupe de disponibilité spécifique.</span><span class="sxs-lookup"><span data-stu-id="ebe82-118">Either right-click the **Availability Groups** node or expand this node and right-click a specific availability group.</span></span>  
  
4.  <span data-ttu-id="ebe82-119">Sélectionnez la commande **Afficher le tableau de bord** .</span><span class="sxs-lookup"><span data-stu-id="ebe82-119">Select the **Show Dashboard** command.</span></span>  
  
 <span data-ttu-id="ebe82-120">Pour plus d’informations sur l’utilisation du tableau de bord AlwaysOn, consultez [Utiliser le tableau de bord AlwaysOn &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="ebe82-120">For information about how to use the AlwaysOn Dashboard, see [Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="ebe82-121">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebe82-121">Using PowerShell</span></span>  
 <span data-ttu-id="ebe82-122">**Utiliser des stratégies AlwaysOn pour afficher l’intégrité d’un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="ebe82-122">**Use AlwaysOn policies to view the health of an availability group**</span></span>  
  
1.  <span data-ttu-id="ebe82-123">Définissez la valeur par défaut (`cd`) sur une instance de serveur qui héberge l'un des réplicas de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="ebe82-123">Set default (`cd`) to a server instance that hosts one of the availability replicas.</span></span> <span data-ttu-id="ebe82-124">Pour afficher des informations sur tous les réplicas de disponibilité d'un groupe de disponibilité, utilisez l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="ebe82-124">To view information about all of the availability replicas in an availability group, use to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="ebe82-125">Utilisez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="ebe82-125">Use the following cmdlets:</span></span>  
  
     `Test-SqlAvailabilityGroup`  
     <span data-ttu-id="ebe82-126">Évalue l'intégrité d'un groupe de disponibilité lors de l'évaluation des stratégies de gestion basées sur des stratégies SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ebe82-126">Assesses the health of an availability group by evaluating SQL Server policy based management (PBM) policies.</span></span> <span data-ttu-id="ebe82-127">Vous devez disposer des autorisations CONNECT, VIEW SERVER STATE et VIEW ANY DEFINITION pour exécuter cette applet de commande.</span><span class="sxs-lookup"><span data-stu-id="ebe82-127">You must have CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions to execute this cmdlet.</span></span>  
  
     <span data-ttu-id="ebe82-128">Par exemple, la commande suivante affiche tous les groupes de disponibilité avec l’état d’intégrité « Erreur » sur l’instance de serveur `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="ebe82-128">For example, the following command shows all availability groups with a health state of "Error" on the server instance `Computer\Instance`.</span></span>  
  
    ```powershell
    Get-ChildItem SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups |
        Test-SqlAvailabilityGroup |
        Where-Object { $_.HealthState -eq "Error" }  
    ```  
  
     `Test-SqlAvailabilityReplica`  
     <span data-ttu-id="ebe82-129">Évalue l'intégrité des réplicas de disponibilité lors de l'évaluation des stratégies de gestion basées sur des stratégies SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ebe82-129">Assesses the health of availability replicas by evaluating SQL Server policy based management (PBM) policies.</span></span> <span data-ttu-id="ebe82-130">Vous devez disposer des autorisations CONNECT, VIEW SERVER STATE et VIEW ANY DEFINITION pour exécuter cette applet de commande.</span><span class="sxs-lookup"><span data-stu-id="ebe82-130">You must have CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions to execute this cmdlet.</span></span>  
  
     <span data-ttu-id="ebe82-131">Par exemple, la commande suivante évalue l'intégrité du réplica de disponibilité nommé `MyReplica` dans le groupe de disponibilité `MyAg` et génère un bref résumé.</span><span class="sxs-lookup"><span data-stu-id="ebe82-131">For example, the following command evaluates the health of the availability replica named `MyReplica` in the availability group `MyAg` and outputs a brief summary.</span></span>  
  
    ```powershell
    Test-SqlAvailabilityReplica -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
     `Test-SqlDatabaseReplicaState`  
     <span data-ttu-id="ebe82-132">Évalue l'intégrité d'une base de données de disponibilité sur tous les réplicas de disponibilité joints par l'évaluation des stratégies de gestion basées sur des stratégies SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ebe82-132">Assesses the health of an availability database on all joined availability replicas by evaluating SQL Server policy based management (PBM) policies.</span></span>  
  
     <span data-ttu-id="ebe82-133">Par exemple, la commande suivante évalue l'intégrité de toutes les bases de données de disponibilité du groupe de disponibilité `MyAg` et génère un bref résumé pour chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="ebe82-133">For example, the following command evaluates the health of all availability databases in the availability group `MyAg` and outputs a brief summary for each database.</span></span>  
  
    ```powershell
    Get-ChildItem SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\DatabaseReplicaStates |
        Test-SqlDatabaseReplicaState  
    ```  
  
     <span data-ttu-id="ebe82-134">Ces applets de commande acceptent les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="ebe82-134">These cmdlets accept the following options:</span></span>  
  
    |<span data-ttu-id="ebe82-135">Option</span><span class="sxs-lookup"><span data-stu-id="ebe82-135">Option</span></span>|<span data-ttu-id="ebe82-136">Description</span><span class="sxs-lookup"><span data-stu-id="ebe82-136">Description</span></span>|  
    |------------|-----------------|  
    |`AllowUserPolicies`|<span data-ttu-id="ebe82-137">Exécute des stratégies d'utilisateur présentes dans les catégories de stratégie AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="ebe82-137">Runs user policies found in the AlwaysOn policy categories.</span></span>|  
    |`InputObject`|<span data-ttu-id="ebe82-138">Collection d'objets qui représentent des groupes de disponibilité, des réplicas de disponibilité ou des états de base de données de disponibilité (selon les applets de commande que vous utilisez).</span><span class="sxs-lookup"><span data-stu-id="ebe82-138">A collection of objects that, represent availability groups, availability replicas, or availability database states (depending on which cmdlet you are using).</span></span> <span data-ttu-id="ebe82-139">L'applet de commande calcule l'intégrité des objets spécifiés.</span><span class="sxs-lookup"><span data-stu-id="ebe82-139">The cmdlet will compute the health of the specified objects.</span></span>|  
    |`NoRefresh`|<span data-ttu-id="ebe82-140">Lorsque ce paramètre est défini, l'applet de commande n'actualise pas manuellement les objets spécifiés par le paramètre `-Path` ou `-InputObject`.</span><span class="sxs-lookup"><span data-stu-id="ebe82-140">When this parameter is set, the cmdlet will not manually refresh the objects specified by the `-Path` or `-InputObject` parameter.</span></span>|  
    |`Path`|<span data-ttu-id="ebe82-141">Chemin d'accès au groupe de disponibilité, à un ou plusieurs réplicas de disponibilité ou à l'état de cluster de réplica de la base de données de disponibilité (selon les applets de commande que vous utilisez).</span><span class="sxs-lookup"><span data-stu-id="ebe82-141">The path to the availability group, one or more availability replicas, or database replica cluster state of the availability database (depending on which cmdlet you are using).</span></span> <span data-ttu-id="ebe82-142">Il s'agit d'un paramètre facultatif.</span><span class="sxs-lookup"><span data-stu-id="ebe82-142">This is an optional parameter.</span></span> <span data-ttu-id="ebe82-143">Si elle n'est pas spécifiée, la valeur de ce paramètre est définie par défaut à l'emplacement de travail actuel.</span><span class="sxs-lookup"><span data-stu-id="ebe82-143">If not specified, the value of this parameter defaults to the current working location.</span></span>|  
    |`ShowPolicyDetails`|<span data-ttu-id="ebe82-144">Indique le résultat de chaque évaluation de la stratégie exécutée par cette applet de commande.</span><span class="sxs-lookup"><span data-stu-id="ebe82-144">Shows the result of each policy evaluation performed by this cmdlet.</span></span> <span data-ttu-id="ebe82-145">L'applet de commande génère un objet par évaluation de stratégie, et cet objet comporte des champs décrivant les résultats de l'évaluation (que la stratégie ait réussi ou non, le nom de la stratégie et la catégorie, etc.).</span><span class="sxs-lookup"><span data-stu-id="ebe82-145">The cmdlet outputs one object per policy evaluation, and this object has fields describing the results of evaluation (whether the policy passed or not, the policy name and category, and so forth).</span></span>|  
  
     <span data-ttu-id="ebe82-146">Par exemple, la commande `Test-SqlAvailabilityGroup` suivante spécifie le paramètre `-ShowPolicyDetails` pour afficher le résultat de chaque évaluation de stratégie exécutée par cette applet de commande pour chaque stratégie de gestion basée sur des stratégies (PBM) exécutée sur le groupe de disponibilité nommé `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="ebe82-146">For example, the following `Test-SqlAvailabilityGroup` command specifies the `-ShowPolicyDetails` parameter to show the result of each policy evaluation performed by this cmdlet for each policy-based management (PBM) policy that was executed on the availability group named `MyAg`.</span></span>  
  
    ```powershell
    Test-SqlAvailabilityGroup -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\AgName -ShowPolicyDetails  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="ebe82-147">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ebe82-147">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="ebe82-148">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ebe82-148">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="ebe82-149">**Pour configurer et utiliser le fournisseur SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ebe82-149">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="ebe82-150">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebe82-150">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="ebe82-151">Obtenir de l'aide sur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebe82-151">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="ebe82-152">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="ebe82-152">Related Content</span></span>  
 <span data-ttu-id="ebe82-153">**Blogs de l’équipe SQL Server AlwaysOn-surveillance de l’intégrité AlwaysOn avec PowerShell :**</span><span class="sxs-lookup"><span data-stu-id="ebe82-153">**SQL Server AlwaysOn Team Blogs-Monitoring AlwaysOn Health with PowerShell:**</span></span>  
  
-   [<span data-ttu-id="ebe82-154">Partie 1 : Vue d'ensemble de l'applet de commande</span><span class="sxs-lookup"><span data-stu-id="ebe82-154">Part 1: Basic Cmdlet Overview</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-1-basic-cmdlet-overview)  
  
-   [<span data-ttu-id="ebe82-155">Partie 2 : Utilisation avancée de l'applet de commande</span><span class="sxs-lookup"><span data-stu-id="ebe82-155">Part 2: Advanced Cmdlet Usage</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/the-alwayson-health-model-part-2-extending-the-health-model)  
  
-   [<span data-ttu-id="ebe82-156">Partie 3 : Application de surveillance simple</span><span class="sxs-lookup"><span data-stu-id="ebe82-156">Part 3: A Simple Monitoring Application</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-3-a-simple-monitoring-application)  
  
-   [<span data-ttu-id="ebe82-157">Partie 4 : Intégration à l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="ebe82-157">Part 4: Integration with SQL Server Agent</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-4-integration-with-sql-server-agent)  
  
## <a name="see-also"></a><span data-ttu-id="ebe82-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ebe82-158">See Also</span></span>  
 <span data-ttu-id="ebe82-159">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ebe82-159">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="ebe82-160">[Administration d’un groupe de disponibilité &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ebe82-160">[Administration of an Availability Group &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="ebe82-161">[Surveillance des groupes de disponibilité &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ebe82-161">[Monitoring of Availability Groups &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="ebe82-162">Stratégies AlwaysOn pour les problèmes opérationnels avec des groupes de disponibilité AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ebe82-162">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)</span></span>](always-on-policies-for-operational-issues-always-on-availability.md) 
