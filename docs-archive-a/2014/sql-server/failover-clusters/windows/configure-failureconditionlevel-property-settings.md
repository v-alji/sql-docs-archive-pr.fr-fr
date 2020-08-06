---
title: Configurer les paramètres de propriété FailureConditionLevel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 513dd179-9a46-46da-9fdd-7632cf6d0816
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8924b864d7cc8be078b370e3182713114f54ff6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605022"
---
# <a name="configure-failureconditionlevel-property-settings"></a><span data-ttu-id="4fc69-102">Configurer les paramètres de propriété FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="4fc69-102">Configure FailureConditionLevel Property Settings</span></span>
  <span data-ttu-id="4fc69-103">Utilisez la propriété FailureConditionLevel pour définir les conditions de basculement ou de redémarrage de l'instance de cluster de basculement (FCI) AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="4fc69-103">Use the FailureConditionLevel property to set the conditions for the AlwaysOn Failover Cluster Instance (FCI) to fail over or restart.</span></span> <span data-ttu-id="4fc69-104">Les modifications de cette propriété sont appliquées immédiatement sans nécessiter le redémarrage du service WSFC (cluster de basculement Windows Server) ou de la ressource FCI.</span><span class="sxs-lookup"><span data-stu-id="4fc69-104">Changes to this property are applied immediately without requiring a restart of the Windows Server Failover Cluster (WSFC) service or the FCI resource.</span></span>  
  
-   <span data-ttu-id="4fc69-105">**Avant de commencer :**  [Paramètres de propriété FailureConditionLevel](#Restrictions), [Sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="4fc69-105">**Before you begin:**  [FailureConditionLevel Property Settings](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="4fc69-106">**Pour configurer les paramètres de propriété FailureConditionLevel à l’aide de** [PowerShell](#PowerShellProcedure), [Gestionnaire du cluster de basculement](#WSFC), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="4fc69-106">**To configure the FailureConditionLevel property settings using,** [PowerShell](#PowerShellProcedure), [Failover Cluster Manager](#WSFC), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4fc69-107">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="4fc69-107">Before You Begin</span></span>  
  
###  <a name="failureconditionlevel-property-settings"></a><a name="Restrictions"></a> <span data-ttu-id="4fc69-108">Paramètres de propriété FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="4fc69-108">FailureConditionLevel Property Settings</span></span>  
 <span data-ttu-id="4fc69-109">Les conditions d'échec sont définies sur une échelle croissante.</span><span class="sxs-lookup"><span data-stu-id="4fc69-109">The failure conditions are set on an increasing scale.</span></span> <span data-ttu-id="4fc69-110">Pour les niveaux 1-5, chaque niveau inclut toutes les conditions des niveaux précédents en plus de ses propres conditions.</span><span class="sxs-lookup"><span data-stu-id="4fc69-110">For levels 1-5, each level includes all the conditions from the previous levels in addition to its own conditions.</span></span> <span data-ttu-id="4fc69-111">Cela signifie qu'à chaque niveau, la probabilité de basculement ou de redémarrage est plus importante.</span><span class="sxs-lookup"><span data-stu-id="4fc69-111">This means that with each level, there is an increased probability of a failover or restart.</span></span>  <span data-ttu-id="4fc69-112">Pour plus d'informations, consultez la section « Détermination des échecs » de la rubrique [Failover Policy for Failover Cluster Instances](failover-policy-for-failover-cluster-instances.md) .</span><span class="sxs-lookup"><span data-stu-id="4fc69-112">For more information, see the "Determining Failures" section of the [Failover Policy for Failover Cluster Instances](failover-policy-for-failover-cluster-instances.md) topic.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4fc69-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4fc69-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4fc69-114">Autorisations</span><span class="sxs-lookup"><span data-stu-id="4fc69-114">Permissions</span></span>  
 <span data-ttu-id="4fc69-115">Nécessite les autorisations ALTER SETTINGS et VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="4fc69-115">Requires ALTER SETTINGS and VIEW SERVER STATE permissions.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="4fc69-116">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fc69-116">Using PowerShell</span></span>  
  
### <a name="to-configure-failureconditionlevel-settings"></a><span data-ttu-id="4fc69-117">Pour configurer les paramètres FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="4fc69-117">To configure FailureConditionLevel settings</span></span>  
  
1.  <span data-ttu-id="4fc69-118">Démarrez Windows PowerShell avec élévation de privilèges via **Exécuter en tant qu'administrateur**.</span><span class="sxs-lookup"><span data-stu-id="4fc69-118">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="4fc69-119">Importez le module `FailoverClusters` pour activer les applets de commande de cluster.</span><span class="sxs-lookup"><span data-stu-id="4fc69-119">Import the `FailoverClusters` module to enable cluster cmdlets.</span></span>  
  
3.  <span data-ttu-id="4fc69-120">Utilisez l' `Get-ClusterResource` applet de commande pour rechercher la [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ressource, puis utilisez l' `Set-ClusterParameter` applet de commande pour définir la propriété **FailureConditionLevel** d’une instance de cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="4fc69-120">Use the `Get-ClusterResource` cmdlet to find the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource, then use `Set-ClusterParameter` cmdlet to set the **FailureConditionLevel** property for a Failover Cluster Instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="4fc69-121">Chaque fois que vous ouvrez une nouvelle fenêtre PowerShell, vous devez importer le module `FailoverClusters`.</span><span class="sxs-lookup"><span data-stu-id="4fc69-121">Every time you open a new PowerShell window, you need to import the `FailoverClusters` module.</span></span>  

 <span data-ttu-id="4fc69-122">L'exemple suivant modifie le paramètre FailureConditionLevel sur la ressource [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] «`SQL Server (INST1)`» par un basculement ou un redémarrage en cas d'erreurs de serveur critiques.</span><span class="sxs-lookup"><span data-stu-id="4fc69-122">The following example changes the FailureConditionLevel setting on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource "`SQL Server (INST1)`" to fail over or restart on critical server errors.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$fci = "SQL Server (INST1)"  
Get-ClusterResource $fci | Set-ClusterParameter FailureConditionLevel 3
```  
  
### <a name="related-content-powershell"></a><span data-ttu-id="4fc69-123">Contenu connexe (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="4fc69-123">Related Content (PowerShell)</span></span>  
  
-   <span data-ttu-id="4fc69-124">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Clustering et haute disponibilité) (Blog de l’équipe de clustering de basculement et d’équilibrage de la charge réseau)</span><span class="sxs-lookup"><span data-stu-id="4fc69-124">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Failover Clustering and Network Load Balancing Team Blog)</span></span>  
  
-   <span data-ttu-id="4fc69-125">[Mise en route de Windows PowerShell sur un cluster de basculement](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="4fc69-125">[Getting Started with Windows PowerShell on a Failover Cluster](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="4fc69-126">Commandes de ressource de cluster et applets de commande Windows PowerShell équivalentes</span><span class="sxs-lookup"><span data-stu-id="4fc69-126">Cluster resource commands and equivalent Windows PowerShell cmdlets</span></span>](https://msdn.microsoft.com/library/ee619744.aspx#BKMK_resource)  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="4fc69-127">Utilisation du composant logiciel enfichable Gestionnaire du cluster de basculement</span><span class="sxs-lookup"><span data-stu-id="4fc69-127">Using the Failover Cluster Manager Snap-in</span></span>  

### <a name="to-configure-failureconditionlevel-property-settings"></a><span data-ttu-id="4fc69-128">Pour configurer les paramètres de propriété FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="4fc69-128">To configure FailureConditionLevel property settings</span></span>
  
1.  <span data-ttu-id="4fc69-129">Ouvrez le composant logiciel enfichable Gestionnaire du cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="4fc69-129">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="4fc69-130">Développez **Services et applications** et sélectionnez l'instance FCI.</span><span class="sxs-lookup"><span data-stu-id="4fc69-130">Expand the **Services and Applications** and select the FCI.</span></span>  
  
3.  <span data-ttu-id="4fc69-131">Cliquez avec le bouton droit sur **Ressource SQL Server** sous **Autres ressources**puis, dans le menu, sélectionnez **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="4fc69-131">Right-click the **SQL Server resource** under **Other Resources**, and then select **Properties** from the menu.</span></span> <span data-ttu-id="4fc69-132">La boîte de dialogue **Propriétés** de la ressource SQL Server s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="4fc69-132">The SQL Server resource **Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="4fc69-133">Sélectionnez l'onglet **Propriétés** , entrez la valeur souhaitée pour la propriété **FaliureConditionLevel** , puis cliquez sur **OK** pour appliquer la modification.</span><span class="sxs-lookup"><span data-stu-id="4fc69-133">Select the **Properties** tab, enter the desired value for the **FaliureConditionLevel** property, and then click **OK** to apply the change.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4fc69-134">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4fc69-134">Using Transact-SQL</span></span>  

### <a name="to-configure-failureconditionlevel-property-settings"></a><span data-ttu-id="4fc69-135">Pour configurer les paramètres de propriété FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="4fc69-135">To configure FailureConditionLevel property settings</span></span>
  
 <span data-ttu-id="4fc69-136">À l’aide de l’instruction [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] , spécifiez la valeur de la propriété FailureConditionLevel.</span><span class="sxs-lookup"><span data-stu-id="4fc69-136">Using the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, you can specify the FailureConditionLevel property value.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="4fc69-137">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4fc69-137">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="4fc69-138">L'exemple suivant affecte à la propriété FailureConditionLevel la valeur 0, ce qui indique qu'aucun basculement ni redémarrage ne sera déclenché automatiquement sur n'importe quelle condition d'échec.</span><span class="sxs-lookup"><span data-stu-id="4fc69-138">The following example sets the FailureConditionLevel property to 0, indicating that failover or restart will not be triggered automatically on any failure conditions.</span></span>  
  
```sql
ALTER SERVER CONFIGURATION SET FAILOVER CLUSTER PROPERTY FailureConditionLevel = 0;  
```  
  
## <a name="see-also"></a><span data-ttu-id="4fc69-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4fc69-139">See Also</span></span>  
 <span data-ttu-id="4fc69-140">[sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4fc69-140">[sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) </span></span>  
 [<span data-ttu-id="4fc69-141">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="4fc69-141">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
