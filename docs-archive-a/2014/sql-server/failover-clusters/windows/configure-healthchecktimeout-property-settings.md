---
title: Configurer les paramètres de propriété HealthCheckTimeout | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 3bbeb979-e6fc-4184-ad6e-cca62108de74
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a38cd6e9e4718a2f1c136e5412cde340e92f14c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605020"
---
# <a name="configure-healthchecktimeout-property-settings"></a><span data-ttu-id="40ff9-102">Configurer les paramètres de propriété HealthCheckTimeout</span><span class="sxs-lookup"><span data-stu-id="40ff9-102">Configure HealthCheckTimeout Property Settings</span></span>
  <span data-ttu-id="40ff9-103">Le paramètre HealthCheckTimeout est utilisé pour spécifier le temps, en millisecondes, pendant lequel la DLL de ressource SQL Server doit attendre les informations retournées par la procédure stockée [sp_server_diagnostics](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) avant de déclarer l'instance de cluster de basculement (FCI) AlwaysOn comme sans réponse.</span><span class="sxs-lookup"><span data-stu-id="40ff9-103">The HealthCheckTimeout setting is used to specify the length of time, in milliseconds, that the SQL Server resource DLL should wait for information returned by the [sp_server_diagnostics](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) stored procedure before reporting the AlwaysOn Failover Cluster Instance (FCI) as unresponsive.</span></span> <span data-ttu-id="40ff9-104">Les modifications apportées aux paramètres de délai d'attente entrent immédiatement en vigueur et ne requièrent pas de redémarrage de la ressource SQL Server.</span><span class="sxs-lookup"><span data-stu-id="40ff9-104">Changes that are made to the timeout settings are effective immediately and do not require a restart of the SQL Server resource.</span></span>  
  
-   <span data-ttu-id="40ff9-105">**Avant de commencer :**  [Limitations et restrictions](#Limits), [sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="40ff9-105">**Before you begin:**  [Limitations and Restrictions](#Limits), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="40ff9-106">**Pour configurer le paramètre HeathCheckTimeout, utilisez :**  [PowerShell](#PowerShellProcedure), [Gestionnaire du cluster de basculement](#WSFC), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="40ff9-106">**To Configure the HeathCheckTimeout setting, using:**  [PowerShell](#PowerShellProcedure), [Failover Cluster Manager](#WSFC), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="40ff9-107">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="40ff9-107">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limits"></a> <span data-ttu-id="40ff9-108">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="40ff9-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="40ff9-109">La valeur par défaut pour cette propriété est 60 000 millisecondes (60 secondes).</span><span class="sxs-lookup"><span data-stu-id="40ff9-109">The default value for this property is 60,000 milliseconds (60 seconds).</span></span> <span data-ttu-id="40ff9-110">La valeur minimale est 15 000 millisecondes (15 secondes).</span><span class="sxs-lookup"><span data-stu-id="40ff9-110">The minimum value is 15,000 milliseconds (15 seconds).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="40ff9-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="40ff9-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="40ff9-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="40ff9-112">Permissions</span></span>  
 <span data-ttu-id="40ff9-113">Nécessite les autorisations ALTER SETTINGS et VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="40ff9-113">Requires ALTER SETTINGS and VIEW SERVER STATE permissions.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="40ff9-114">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="40ff9-114">Using PowerShell</span></span>  
  
### <a name="to-configure-healthchecktimeout-settings"></a><span data-ttu-id="40ff9-115">Pour configurer les paramètres HealthCheckTimeout</span><span class="sxs-lookup"><span data-stu-id="40ff9-115">To configure HealthCheckTimeout settings</span></span>  
  
1.  <span data-ttu-id="40ff9-116">Démarrez Windows PowerShell avec élévation de privilèges via **Exécuter en tant qu'administrateur**.</span><span class="sxs-lookup"><span data-stu-id="40ff9-116">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="40ff9-117">Importez le module `FailoverClusters` pour activer les applets de commande de cluster.</span><span class="sxs-lookup"><span data-stu-id="40ff9-117">Import the `FailoverClusters` module to enable cluster cmdlets.</span></span>  
  
3.  <span data-ttu-id="40ff9-118">Utilisez l' `Get-ClusterResource` applet de commande pour rechercher la [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ressource, puis utilisez l' `Set-ClusterParameter` applet de commande pour définir la propriété **HealthCheckTimeout** de l’instance de cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="40ff9-118">Use the `Get-ClusterResource` cmdlet to find the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource, then use `Set-ClusterParameter` cmdlet to set the **HealthCheckTimeout** property for the failover cluster instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="40ff9-119">Chaque fois que vous ouvrez une nouvelle fenêtre PowerShell, vous devez importer le module `FailoverClusters`.</span><span class="sxs-lookup"><span data-stu-id="40ff9-119">Every time you open a new PowerShell window, you need to import the `FailoverClusters` module.</span></span>  

 <span data-ttu-id="40ff9-120">L'exemple suivant modifie le paramètre HealthCheckTimeout sur la ressource [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] «`SQL Server (INST1)`» afin qu'il indique 60 000 millisecondes.</span><span class="sxs-lookup"><span data-stu-id="40ff9-120">The following example changes the HealthCheckTimeout setting on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource "`SQL Server (INST1)`" to 60000 milliseconds.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$fci = "SQL Server (INST1)"  
Get-ClusterResource $fci | Set-ClusterParameter HealthCheckTimeout 60000  
```  
  
### <a name="related-content-powershell"></a><span data-ttu-id="40ff9-121">Contenu connexe (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="40ff9-121">Related Content (PowerShell)</span></span>  
  
-   <span data-ttu-id="40ff9-122">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Clustering et haute disponibilité) (Blog de l’équipe de clustering de basculement et d’équilibrage de la charge réseau)</span><span class="sxs-lookup"><span data-stu-id="40ff9-122">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Failover Clustering and Network Load Balancing Team Blog)</span></span>  
  
-   <span data-ttu-id="40ff9-123">[Mise en route de Windows PowerShell sur un cluster de basculement](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="40ff9-123">[Getting Started with Windows PowerShell on a Failover Cluster](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="40ff9-124">Commandes de ressource de cluster et applets de commande Windows PowerShell équivalentes</span><span class="sxs-lookup"><span data-stu-id="40ff9-124">Cluster resource commands and equivalent Windows PowerShell cmdlets</span></span>](https://msdn.microsoft.com/library/ee619744.aspx#BKMK_resource)  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="40ff9-125">Utilisation du composant logiciel enfichable Gestionnaire du cluster de basculement</span><span class="sxs-lookup"><span data-stu-id="40ff9-125">Using the Failover Cluster Manager Snap-in</span></span>  
 <span data-ttu-id="40ff9-126">**Pour configurer le paramètre HeathCheckTimeout**</span><span class="sxs-lookup"><span data-stu-id="40ff9-126">**To configure HealthCheckTimeout setting**</span></span>  
  
1.  <span data-ttu-id="40ff9-127">Ouvrez le composant logiciel enfichable Gestionnaire du cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="40ff9-127">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="40ff9-128">Développez **Services et applications** et sélectionnez l'instance FCI.</span><span class="sxs-lookup"><span data-stu-id="40ff9-128">Expand **Services and Applications** and select the FCI.</span></span>  
  
3.  <span data-ttu-id="40ff9-129">Cliquez avec le bouton droit sur **Ressource SQL Server** sous **Autres ressources** , puis sélectionnez **Propriétés** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="40ff9-129">Right-click the **SQL Server resource** under **Other Resources** and select **Properties** from the right-click menu.</span></span> <span data-ttu-id="40ff9-130">La boîte de dialogue **Propriétés** de la ressource SQL Server s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="40ff9-130">The SQL Server resource **Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="40ff9-131">Sélectionnez l'onglet **Propriétés** , entrez la valeur souhaitée pour la propriété **HealthCheckTimeout** , puis cliquez sur **OK** pour appliquer la modification.</span><span class="sxs-lookup"><span data-stu-id="40ff9-131">Select the **Properties** tab, enter the desired value for the **HealthCheckTimeout** property, and then click **OK** to apply the change.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="40ff9-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="40ff9-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="40ff9-133">À l’aide de l’instruction [ALTER Server Configuration](/sql/t-sql/statements/alter-server-configuration-transact-sql) [!INCLUDE[tsql](../../../includes/tsql-md.md)] , vous pouvez spécifier la valeur de la propriété HealthCheckTimeOut.</span><span class="sxs-lookup"><span data-stu-id="40ff9-133">Using the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, you can specify the HealthCheckTimeOut property value.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="40ff9-134">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="40ff9-134">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="40ff9-135">L'exemple suivant définit l'option HealthCheckTimeout sur 15 000 millisecondes (15 secondes).</span><span class="sxs-lookup"><span data-stu-id="40ff9-135">The following example sets the HealthCheckTimeout option to 15,000 milliseconds (15 seconds).</span></span>  
  
```sql
ALTER SERVER CONFIGURATION   
SET FAILOVER CLUSTER PROPERTY HealthCheckTimeout = 15000;  
```  
  
## <a name="see-also"></a><span data-ttu-id="40ff9-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="40ff9-136">See Also</span></span>  
 [<span data-ttu-id="40ff9-137">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="40ff9-137">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
