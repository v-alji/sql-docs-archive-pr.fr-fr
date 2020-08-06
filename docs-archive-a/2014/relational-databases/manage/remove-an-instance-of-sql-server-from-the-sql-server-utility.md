---
title: Supprimer une instance de SQL Server de l’utilitaire SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.utility.remove.f1
ms.assetid: ae1d126a-46d2-47bf-b339-17c743df6491
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c09897fcd3ac6d82308288391cf54176eef49d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614590"
---
# <a name="remove-an-instance-of-sql-server-from-the-sql-server-utility"></a><span data-ttu-id="52bf1-102">Supprimer une instance de SQL Server de l'utilitaire SQL Server</span><span class="sxs-lookup"><span data-stu-id="52bf1-102">Remove an Instance of SQL Server from the SQL Server Utility</span></span>
  <span data-ttu-id="52bf1-103">Suivez la procédure suivante pour supprimer une instance gérée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de l’utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52bf1-103">Use the following steps to remove a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="52bf1-104">Cette procédure supprime l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] du mode Liste de l’UCP et interrompt la collecte de données de l’utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52bf1-104">This procedure removes the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the UCP list view and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility data collection stops.</span></span> <span data-ttu-id="52bf1-105">L'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'est pas désinstallée.</span><span class="sxs-lookup"><span data-stu-id="52bf1-105">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not uninstalled.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="52bf1-106">Avant d'utiliser cette procédure pour supprimer une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de l'utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , assurez-vous que les services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et Agent SQL Server s'exécutent sur l'instance à supprimer.</span><span class="sxs-lookup"><span data-stu-id="52bf1-106">Before you use this procedure to remove an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, make sure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and SQL Server Agent services are running on the instance to remove.</span></span>  
  
1.  <span data-ttu-id="52bf1-107">Depuis l’Explorateur de l’utilitaire dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], cliquez sur **Instances gérées**.</span><span class="sxs-lookup"><span data-stu-id="52bf1-107">From the Utility Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click on **Managed Instances**.</span></span> <span data-ttu-id="52bf1-108">Observez le mode Liste des instances gérées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans le volet de contenu de l’Explorateur de l’utilitaire.</span><span class="sxs-lookup"><span data-stu-id="52bf1-108">Observe the list view of managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the Utility Explorer content pane.</span></span>  
  
2.  <span data-ttu-id="52bf1-109">Dans la colonne **Nom de l’instance SQL Server** du mode Liste, sélectionnez l’instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à supprimer de l’utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52bf1-109">In the **SQL Server Instance Name** column of the list view, select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to remove from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="52bf1-110">Cliquez avec le bouton droit sur l’instance à supprimer et sélectionnez **Supprimer une instance gérée…** .</span><span class="sxs-lookup"><span data-stu-id="52bf1-110">Right-click on the instance to remove, and select **Remove Managed Instance...**.</span></span>  
  
3.  <span data-ttu-id="52bf1-111">Spécifiez les informations d’identification avec des privilèges d’administrateur pour l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] : Cliquez sur **Se connecter...** , vérifiez les informations dans la boîte de dialogue **Se connecter au serveur**, puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="52bf1-111">Specify credentials with administrator privileges for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: Click **Connect...**, verify the information in the **Connect to Server** dialog box, then click **Connect**.</span></span> <span data-ttu-id="52bf1-112">Les informations de connexion s’affichent sur le dialogue **Supprimer une instance gérée** .</span><span class="sxs-lookup"><span data-stu-id="52bf1-112">You will see the login information on the **Remove Managed Instance** dialog.</span></span>  
  
4.  <span data-ttu-id="52bf1-113">Cliquez sur **OK**pour confirmer l’opération.</span><span class="sxs-lookup"><span data-stu-id="52bf1-113">To confirm the operation, click **OK**.</span></span> <span data-ttu-id="52bf1-114">Pour quitter l’installation, cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="52bf1-114">To quit the operation, click **Cancel**.</span></span>  
  
## <a name="manually-remove-a-managed-instance-of-sql-server-from-a-sql-server-utility"></a><span data-ttu-id="52bf1-115">Supprimer manuellement une instance gérée de SQL Server d'un utilitaire SQL Server</span><span class="sxs-lookup"><span data-stu-id="52bf1-115">Manually Remove a Managed Instance of SQL Server from a SQL Server Utility</span></span>  
 <span data-ttu-id="52bf1-116">Cette procédure supprime l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] du mode Liste de l’UCP et interrompt la collecte de données de l’utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52bf1-116">This procedure removes the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the UCP list view and stops [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility data collection.</span></span> <span data-ttu-id="52bf1-117">L'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'est pas désinstallée.</span><span class="sxs-lookup"><span data-stu-id="52bf1-117">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not uninstalled.</span></span>  
  
 <span data-ttu-id="52bf1-118">Pour utiliser PowerShell pour supprimer une instance gérée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de l’utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52bf1-118">To use PowerShell to remove a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="52bf1-119">Ce script effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="52bf1-119">This script performs the following operations:</span></span>  
  
-   <span data-ttu-id="52bf1-120">obtient l'UCP par le nom de l'instance du serveur ;</span><span class="sxs-lookup"><span data-stu-id="52bf1-120">Gets the UCP by server instance name.</span></span>  
  
-   <span data-ttu-id="52bf1-121">supprime l’instance gérée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de l’utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52bf1-121">Removes the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
```powershell
# Get Ucp connection  
$UcpServerInstanceName = "ComputerName\InstanceName";  
$UtilityInstance = new-object -Type Microsoft.SqlServer.Management.Smo.Server $UcpServerInstanceName;  
$UcpConnection = new-object -Type Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection $UtilityInstance.ConnectionContext.SqlConnectionObject;  
$Utility = [Microsoft.SqlServer.Management.Utility.Utility]::Connect($UcpConnection);  
  
# Now remove the ManagedInstance from the SQL Server Utility  
$ServerInstanceName = "ComputerName\InstanceName";  
$Instance = new-object -Type Microsoft.SqlServer.Management.Smo.Server $ServerInstanceName;  
$InstanceConnection = new-object -Type Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection $Instance.ConnectionContext.SqlConnectionObject;  
$ManagedInstance = $Utility.ManagedInstances[$ServerInstanceName];  
$ManagedInstance.Remove($InstanceConnection);  
```  
  
<span data-ttu-id="52bf1-122">Il est important de faire référence au [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nom de l’instance exactement tel qu’il est stocké dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52bf1-122">It's important to refer to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name exactly as it is stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="52bf1-123">Sur une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui respecte la casse, vous devez spécifier le nom de l’instance en respectant la casse exacte, telle qu’elle est retournée par @@SERVERNAME.</span><span class="sxs-lookup"><span data-stu-id="52bf1-123">On a case-sensitive instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must specify the instance name using the exact casing as returned by @@SERVERNAME.</span></span> 

<span data-ttu-id="52bf1-124">Pour obtenir le nom de l'instance pour l'instance gérée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], exécutez la requête suivante sur l'instance gérée :</span><span class="sxs-lookup"><span data-stu-id="52bf1-124">To get the instance name for the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run this query on the managed instance:</span></span>  
  
```sql
select @@SERVERNAME AS instance_name  
```  
  
 <span data-ttu-id="52bf1-125">À ce stade, l’instance gérée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est complètement supprimée de l’UCP.</span><span class="sxs-lookup"><span data-stu-id="52bf1-125">At this point, the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is fully removed from the UCP.</span></span> <span data-ttu-id="52bf1-126">Elle disparaît du mode Liste lorsque vous actualisez les données de l'utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52bf1-126">It disappears from the list view the next time you refresh data for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="52bf1-127">Le résultat est identique à celui qu'obtient un utilisateur qui effectue avec succès l'opération de suppression d'instance gérée dans l'interface utilisateur SSMS.</span><span class="sxs-lookup"><span data-stu-id="52bf1-127">This state is identical to a user successfully going through the remove managed instance operation in the SSMS user interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52bf1-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="52bf1-128">See Also</span></span>  
 <span data-ttu-id="52bf1-129">[Utiliser l'Explorateur de l'utilitaire pour gérer l'Utilitaire SQL Server](use-utility-explorer-to-manage-the-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="52bf1-129">[Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="52bf1-130">Résolution des problèmes liés à l’utilitaire SQL Server</span><span class="sxs-lookup"><span data-stu-id="52bf1-130">Troubleshoot the SQL Server Utility</span></span>](../../database-engine/troubleshoot-the-sql-server-utility.md)  
