---
title: Utiliser des chemins PowerShell SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: f31d8e2c-8d59-4fee-ac2a-324668e54262
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d2647251eb1c8843d4ab7a95d2c439e47f5bb6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699846"
---
# <a name="work-with-sql-server-powershell-paths"></a><span data-ttu-id="7b32b-102">Utiliser des chemins d'accès PowerShell SQL Server</span><span class="sxs-lookup"><span data-stu-id="7b32b-102">Work With SQL Server PowerShell Paths</span></span>
  <span data-ttu-id="7b32b-103">Après avoir accédé à un nœud dans un chemin d'accès de fournisseur du [!INCLUDE[ssDE](../includes/ssde-md.md)] , vous pouvez effectuer des opérations ou récupérer des informations à l'aide des méthodes et propriétés de l'objet de gestion du [!INCLUDE[ssDE](../includes/ssde-md.md)] associé au nœud.</span><span class="sxs-lookup"><span data-stu-id="7b32b-103">After you have navigated to a node in a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can perform work or retrieve information by using the methods and properties from the [!INCLUDE[ssDE](../includes/ssde-md.md)] management object associated with the node.</span></span>  
  
1.  [<span data-ttu-id="7b32b-104">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="7b32b-104">Before You Begin</span></span>](#BeforeYouBegin)  
  
2.  <span data-ttu-id="7b32b-105">**Pour travailler sur un nœud de chemin d'accès :**  [Affichage de la liste des méthodes et des propriétés](#ListPropMeth), [Utilisation des méthodes et des propriétés](#UsePropMeth)</span><span class="sxs-lookup"><span data-stu-id="7b32b-105">**To work on a path node:**  [Listing Methods and Properties](#ListPropMeth), [Using Methods and Properties](#UsePropMeth)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7b32b-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="7b32b-106">Before You Begin</span></span>  
 <span data-ttu-id="7b32b-107">Après avoir accédé à un nœud dans un chemin d'accès de fournisseur du [!INCLUDE[ssDE](../includes/ssde-md.md)] , vous pouvez effectuer deux types d'actions :</span><span class="sxs-lookup"><span data-stu-id="7b32b-107">After you have navigated to a node in a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can perform two types of actions:</span></span>  
  
-   <span data-ttu-id="7b32b-108">Vous pouvez exécuter des applets de commande Windows PowerShell qui s’appliquent à des nœuds, telles que **Rename-Item**.</span><span class="sxs-lookup"><span data-stu-id="7b32b-108">You can run Windows PowerShell cmdlets that operate on nodes, such as **Rename-Item**.</span></span>  
  
-   <span data-ttu-id="7b32b-109">Vous pouvez appeler les méthodes du modèle objet SMO ( [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Objects) associé, tel que SMO.</span><span class="sxs-lookup"><span data-stu-id="7b32b-109">You can call the methods from the associated [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] management object model, such as SMO.</span></span> <span data-ttu-id="7b32b-110">Par exemple, si vous accédez au nœud Databases dans un chemin d’accès, vous pouvez utiliser les méthodes et propriétés de la classe <xref:Microsoft.SqlServer.Management.Smo.Database> .</span><span class="sxs-lookup"><span data-stu-id="7b32b-110">For example, if you navigate to the Databases node in a path, you can use the methods and properties of the <xref:Microsoft.SqlServer.Management.Smo.Database> class.</span></span>  
  
 <span data-ttu-id="7b32b-111">Le fournisseur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] est utilisé pour gérer les objets dans une instance du [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b32b-111">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider is used to manage the objects in an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="7b32b-112">Il n'est pas utilisé pour travailler avec les données de bases de données.</span><span class="sxs-lookup"><span data-stu-id="7b32b-112">It is not used to work with the data in databases.</span></span> <span data-ttu-id="7b32b-113">Si vous avez accédé à une table ou une vue, vous ne pouvez pas utiliser le fournisseur pour sélectionner, insérer, mettre à jour ou supprimer des données.</span><span class="sxs-lookup"><span data-stu-id="7b32b-113">If you have navigated to a table or view, you cannot use the provider to select, insert, update, or delete data.</span></span> <span data-ttu-id="7b32b-114">Utilisez l’applet de commande **Invoke-Sqlcmd** pour interroger ou modifier des données dans des tables et des vues à partir de l’environnement Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b32b-114">Use the **Invoke-Sqlcmd** cmdlet to query or change data in tables and views from the Windows PowerShell environment.</span></span> <span data-ttu-id="7b32b-115">Pour plus d’informations, consultez [Invoke-Sqlcmd (applet de commande)](../database-engine/invoke-sqlcmd-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="7b32b-115">For more information, see [Invoke-Sqlcmd cmdlet](../database-engine/invoke-sqlcmd-cmdlet.md).</span></span>  
  
##  <a name="listing-methods-and-properties"></a><a name="ListPropMeth"></a> <span data-ttu-id="7b32b-116">Affichage de la liste des méthodes et des propriétés</span><span class="sxs-lookup"><span data-stu-id="7b32b-116">Listing Methods and Properties</span></span>
  
 <span data-ttu-id="7b32b-117">Pour afficher les méthodes et propriétés disponibles pour des objets ou classes d’objets spécifiques, utilisez l’applet de commande **Get-Member** .</span><span class="sxs-lookup"><span data-stu-id="7b32b-117">To view the methods and properties available for specific objects or object classes, use the **Get-Member** cmdlet.</span></span>  
  
### <a name="examples-listing-methods-and-properties"></a><span data-ttu-id="7b32b-118">Exemples : affichage de la liste des méthodes et des propriétés</span><span class="sxs-lookup"><span data-stu-id="7b32b-118">Examples: Listing Methods and Properties</span></span>  
 <span data-ttu-id="7b32b-119">Cet exemple affecte à une variable Windows PowerShell la classe <xref:Microsoft.SqlServer.Management.Smo.Database> SMO et répertorie les méthodes et les propriétés :</span><span class="sxs-lookup"><span data-stu-id="7b32b-119">This example sets a Windows PowerShell variable to the SMO <xref:Microsoft.SqlServer.Management.Smo.Database> class and lists the methods and properties:</span></span>  
  
```powershell
$MyDBVar = New-Object Microsoft.SqlServer.Management.SMO.Database  
$MyDBVar | Get-Member -Type Methods  
$MyDBVar | Get-Member -Type Properties  
```  
  
 <span data-ttu-id="7b32b-120">Vous pouvez également utiliser **Get-Member** pour répertorier les méthodes et les propriétés associées au nœud de fin d’un chemin d’accès Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b32b-120">You can also use **Get-Member** to list the methods and properties that are associated with the end node of a Windows PowerShell path.</span></span>  
  
 <span data-ttu-id="7b32b-121">L'exemple suivant accède au nœud Databases d'un chemin d'accès SQLSERVER: et répertorie les propriétés de collection :</span><span class="sxs-lookup"><span data-stu-id="7b32b-121">This example navigates to the Databases node in a SQLSERVER: path and lists the collection properties:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
Get-Item . | Get-Member -Type Properties  
```  
  
 <span data-ttu-id="7b32b-122">Cet exemple accède au nœud AdventureWorks2012 d'un chemin d'accès SQLSERVER: et répertorie les propriétés d'objet :</span><span class="sxs-lookup"><span data-stu-id="7b32b-122">This example navigates to the AdventureWorks2012 node in a SQLSERVER: path and lists the object properties:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012  
Get-Item . | Get-Member -Type Properties  
```  
  
##  <a name="using-smo-methods-and-properties"></a><a name="UsePropMeth"></a><span data-ttu-id="7b32b-123">Utilisation des méthodes et des propriétés SMO</span><span class="sxs-lookup"><span data-stu-id="7b32b-123">Using SMO Methods and Properties</span></span>  
  
 <span data-ttu-id="7b32b-124">Pour effectuer un travail sur les objets d'un chemin d'accès de fournisseur du [!INCLUDE[ssDE](../includes/ssde-md.md)] , vous pouvez utiliser les méthodes et les propriétés SMO.</span><span class="sxs-lookup"><span data-stu-id="7b32b-124">To perform work on objects from a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can use SMO methods and properties.</span></span>  
  
### <a name="examples-using-methods-and-properties"></a><span data-ttu-id="7b32b-125">Exemples : utilisation de méthodes et propriétés</span><span class="sxs-lookup"><span data-stu-id="7b32b-125">Examples: Using Methods and Properties</span></span>  
 <span data-ttu-id="7b32b-126">L’exemple suivant utilise la propriété SMO **Schema** pour obtenir la liste des tables du schéma Sales dans AdventureWorks2012 :</span><span class="sxs-lookup"><span data-stu-id="7b32b-126">This example uses the SMO **Schema** property to get a list of the tables from the Sales schema in AdventureWorks2012:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012\Tables  
Get-ChildItem | Where {$_.Schema -eq "Sales"}  
```  
  
 <span data-ttu-id="7b32b-127">Cet exemple utilise la méthode SMO **script** pour générer un script qui contient les `CREATE VIEW` instructions que vous devez avoir pour recréer les vues dans AdventureWorks2012 :</span><span class="sxs-lookup"><span data-stu-id="7b32b-127">This example uses the SMO **Script** method to generate a script that contains the `CREATE VIEW` statements you must have to re-create the views in AdventureWorks2012:</span></span>  
  
```powershell
Remove-Item C:\PowerShell\CreateViews.sql  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012\Views  
foreach ($Item in Get-ChildItem) { $Item.Script() | Out-File -Filepath C:\PowerShell\CreateViews.sql -append }  
```  
  
 <span data-ttu-id="7b32b-128">L'exemple suivant utilise la méthode SMO **Create** pour créer une base de données, puis la propriété **State** pour indiquer si la base de données existe :</span><span class="sxs-lookup"><span data-stu-id="7b32b-128">This example uses the SMO **Create** method to create a database, and then uses the **State** property to show whether the database exists:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
$MyDBVar = New-Object Microsoft.SqlServer.Management.SMO.Database  
$MyDBVar.Parent = (Get-Item ..)  
$MyDBVar.Name = "NewDB"  
$MyDBVar.Create()  
$MyDBVar.State  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b32b-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7b32b-129">See Also</span></span>  
 <span data-ttu-id="7b32b-130">[Fournisseur SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="7b32b-130">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="7b32b-131">[Parcourir les chemins d’accès SQL Server PowerShell](navigate-sql-server-powershell-paths.md) </span><span class="sxs-lookup"><span data-stu-id="7b32b-131">[Navigate SQL Server PowerShell Paths](navigate-sql-server-powershell-paths.md) </span></span>  
 <span data-ttu-id="7b32b-132">[Convertir des URN en chemins d’accès de fournisseur SQL Server](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span><span class="sxs-lookup"><span data-stu-id="7b32b-132">[Convert URNs to SQL Server Provider Paths](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span></span>  
 [<span data-ttu-id="7b32b-133">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b32b-133">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
