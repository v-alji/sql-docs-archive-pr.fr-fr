---
title: Obtenir de l’aide sur SQL Server PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Help [PowerShell]
- Help [SQL Server], PowerShell
- PowerShell [SQL Server], help
ms.assetid: 968c316d-db83-4c24-8ea6-9f18736842f7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f1d97a3b694eebb924f9e1ff228d4d38da4f45ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701585"
---
# <a name="get-help-sql-server-powershell"></a><span data-ttu-id="d6338-102">Obtenir de l'aide sur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6338-102">Get Help SQL Server PowerShell</span></span>
  <span data-ttu-id="d6338-103">Il existe plusieurs sources d'informations sur l'utilisation du fournisseur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour Windows PowerShell et des applets de commande.</span><span class="sxs-lookup"><span data-stu-id="d6338-103">There are several sources of information about using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider for Windows PowerShell and cmdlets.</span></span> <span data-ttu-id="d6338-104">Cela inclut l'aide qui est disponible dans l'environnement Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6338-104">This includes the help that is available in the Windows PowerShell environment.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="d6338-105">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d6338-105">Before You Begin</span></span>  
 <span data-ttu-id="d6338-106">Pour en savoir plus sur Windows PowerShell, consultez le [Guide Mise en route de Windows PowerShell](https://technet.microsoft.com/library/hh857337.aspx).</span><span class="sxs-lookup"><span data-stu-id="d6338-106">To learn about Windows PowerShell, see [Windows PowerShell Getting Started Guide](https://technet.microsoft.com/library/hh857337.aspx).</span></span>  
  
 <span data-ttu-id="d6338-107">Pour obtenir une vue d’ensemble des applets de commande et du fournisseur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , consultez [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="d6338-107">For an overview of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets and provider, see [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="help-in-the-windows-powershell-environment"></a><span data-ttu-id="d6338-108">Aide dans l'environnement Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6338-108">Help in the Windows PowerShell Environment</span></span>  
 <span data-ttu-id="d6338-109">Utilisez l’applet de commande **Get-Help** pour obtenir de l’aide dans l’environnement Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6338-109">Use the **Get-Help** cmdlet to get help in the Windows PowerShell environment.</span></span> <span data-ttu-id="d6338-110">**Get-Help** fournit l’aide de base pour le langage Windows PowerShell, ainsi que pour les différentes applets de commande et les divers fournisseurs disponibles dans Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6338-110">**Get-Help** provides basic help for the Windows PowerShell language and the various cmdlets and providers available in Windows PowerShell.</span></span>  
  
 <span data-ttu-id="d6338-111">Pour plus d’informations sur les moyens d’utiliser **Get-Help**, consultez [Obtention d’aide : Get-Help](https://go.microsoft.com/fwlink/?LinkId=102136).</span><span class="sxs-lookup"><span data-stu-id="d6338-111">For more information on the ways you can use **Get-Help**, see [Get-Help: Getting Help](https://go.microsoft.com/fwlink/?LinkId=102136).</span></span>  
  
### <a name="sql-server-powershell-provider-help"></a><span data-ttu-id="d6338-112">Aide du fournisseur PowerShell SQL Server</span><span class="sxs-lookup"><span data-stu-id="d6338-112">SQL Server PowerShell Provider Help</span></span>  
 <span data-ttu-id="d6338-113">Le fournisseur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell implémente plusieurs dossiers sur un lecteur virtuel SQLSERVER, tels que les dossiers SQLSERVER:\SQL et SQLSERVER:\DAC.</span><span class="sxs-lookup"><span data-stu-id="d6338-113">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider implements several folders on a SQLSERVER virtual drive, such as the SQLSERVER:\SQL and SQLSERVER:\DAC folders.</span></span> <span data-ttu-id="d6338-114">Chaque dossier est associé à l'un des modèles d'objet de gestion SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d6338-114">Each folder is associated with one of the SQL Server manageability object models.</span></span> <span data-ttu-id="d6338-115">Vous pouvez répertorier les méthodes et les propriétés associées à chaque nœud dans un chemin d'accès SQL Server, mais vous ne pouvez pas obtenir de l'aide sur celles-ci dans l'environnement PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6338-115">While you can list the methods and properties associated with each node in a SQL Server path, you cannot get help for them in the PowerShell environment.</span></span> <span data-ttu-id="d6338-116">Pour obtenir un tableau des dossiers avec des liens à la référence de programmation associée, consultez [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="d6338-116">For a table of the folders with links to the associated programming reference, see [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span></span>  
  
### <a name="invoke-sqlcmd-help"></a><span data-ttu-id="d6338-117">Aide d'Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="d6338-117">Invoke-Sqlcmd Help</span></span>  
 <span data-ttu-id="d6338-118">L’applet de commande **Invoke-Sqlcmd** utilise comme entrée une requête ou un fichier de script exécutable par l’utilitaire **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="d6338-118">The **Invoke-Sqlcmd** cmdlet takes as input any query or script file that can be run by the **sqlcmd** utility.</span></span> <span data-ttu-id="d6338-119">Vous pouvez utiliser **Get-Help** pour obtenir des informations concernant **Invoke-Sqlcmd** et ses paramètres, mais **Get-Help** ne couvre pas les requêtes **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="d6338-119">You can use **Get-Help** to get information about **Invoke-Sqlcmd** and its parameters, but there is no **Get-Help** coverage for the **sqlcmd** queries.</span></span>  
  
 <span data-ttu-id="d6338-120">L’entrée *-Query* ou *-QueryFromFile* peut contenir :</span><span class="sxs-lookup"><span data-stu-id="d6338-120">The *-Query* or *-QueryFromFile* input can contain:</span></span>  
  
-   <span data-ttu-id="d6338-121">Variables et commandes**sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="d6338-121">**sqlcmd** variables and commands.</span></span> <span data-ttu-id="d6338-122">Pour plus d'informations sur ces variables et commandes, consultez la section Notes de [sqlcmd Utility](../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="d6338-122">For information about these variables and commands, see the Remarks section of [sqlcmd Utility](../tools/sqlcmd-utility.md).</span></span>  
  
-   <span data-ttu-id="d6338-123">Instructions[!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6338-123">[!INCLUDE[tsql](../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="d6338-124">Pour plus d’informations sur le langage [!INCLUDE[tsql](../includes/tsql-md.md)], consultez [Référence Transact-SQL &#40;moteur de base de données&#41;](/sql/t-sql/language-reference).</span><span class="sxs-lookup"><span data-stu-id="d6338-124">For more information about the [!INCLUDE[tsql](../includes/tsql-md.md)] language, see [Transact-SQL Reference &#40;Database Engine&#41;](/sql/t-sql/language-reference).</span></span>  
  
-   <span data-ttu-id="d6338-125">Instructions XQuery.</span><span class="sxs-lookup"><span data-stu-id="d6338-125">XQuery statements.</span></span> <span data-ttu-id="d6338-126">Pour plus d’informations sur le langage XQuery pris en charge par [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], consultez [Références relatives au langage Xquery &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server).</span><span class="sxs-lookup"><span data-stu-id="d6338-126">For more information about the XQuery language supported by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [XQuery Language Reference &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server).</span></span>  
  
## <a name="get-help-for-a-sql-server-cmdlet"></a><span data-ttu-id="d6338-127">Obtenir de l'aide pour une applet de commande SQL Server</span><span class="sxs-lookup"><span data-stu-id="d6338-127">Get Help for a SQL Server cmdlet</span></span>  
 <span data-ttu-id="d6338-128">**Pour obtenir de l’aide pour une applet de commande**</span><span class="sxs-lookup"><span data-stu-id="d6338-128">**To get help for a cmdlet**</span></span>  
  
-   <span data-ttu-id="d6338-129">Exécutez Get-Help en spécifiant le nom de l'applet de commande et le niveau de l'aide à retourner.</span><span class="sxs-lookup"><span data-stu-id="d6338-129">Run Get-Help specifying the name of the cmdlet and the level of help to be returned.</span></span>  
  
### <a name="example-cmdlet-get-help"></a><span data-ttu-id="d6338-130">Exemple : applet de commande Get-Help</span><span class="sxs-lookup"><span data-stu-id="d6338-130">Example: cmdlet Get-Help</span></span>  
 <span data-ttu-id="d6338-131">Les exemples ci-après renvoient différents niveaux d’aide pour **Invoke-Sqlcmd**:</span><span class="sxs-lookup"><span data-stu-id="d6338-131">The following examples return various levels of help for **Invoke-Sqlcmd**:</span></span>  
  
```powershell
## Get the basic help.  
Get-Help Invoke-Sqlcmd  
  
## Get the full help.  
Get-Help Invoke-Sqlcmd -Full  
  
## Get the parameter descriptions.  
Get-Help Invoke-Sqlcmd -Parameter *  
  
## Get the code examples.  
Get-Help Invoke-Sqlcmd -Examples  
  
## Get the syntax diagram.  
Get-Help Invoke-Sqlcmd -Syntax  
```  
  
## <a name="get-a-list-of-providers"></a><span data-ttu-id="d6338-132">Obtenir une liste de fournisseurs</span><span class="sxs-lookup"><span data-stu-id="d6338-132">Get a List of Providers</span></span>  

### <a name="to-get-a-list-of-active-providers"></a><span data-ttu-id="d6338-133">Pour obtenir une liste des fournisseurs actifs</span><span class="sxs-lookup"><span data-stu-id="d6338-133">To get a list of active providers</span></span>
  
1.  <span data-ttu-id="d6338-134">Exécutez Get-Help en spécifiant la catégorie de fournisseur.</span><span class="sxs-lookup"><span data-stu-id="d6338-134">Run Get-Help specifying the provider category.</span></span>  
  
 <span data-ttu-id="d6338-135">Pour plus d'informations sur l'obtention d'aide sur les fournisseurs dans Windows PowerShell, consultez [Drives and Providers](https://go.microsoft.com/fwlink/?LinkId=102137)(en anglais).</span><span class="sxs-lookup"><span data-stu-id="d6338-135">For more information about getting provider help in Windows PowerShell, see [Drives and Providers](https://go.microsoft.com/fwlink/?LinkId=102137).</span></span>  
  
### <a name="example-get-a-list-of-providers"></a><span data-ttu-id="d6338-136">Exemple : obtenir une liste de fournisseurs</span><span class="sxs-lookup"><span data-stu-id="d6338-136">Example: Get a List of Providers</span></span>  
 <span data-ttu-id="d6338-137">Le code suivant retourne la liste des fournisseurs actuellement activés dans votre session Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="d6338-137">This code returns a list of the providers currently enabled in your Windows PowerShell session:</span></span>  
  
```powershell
Get-Help -Category provider  
```  
  
## <a name="get-help-about-the-sql-server-provider"></a><span data-ttu-id="d6338-138">Obtenir de l'aide sur le fournisseur SQL Server</span><span class="sxs-lookup"><span data-stu-id="d6338-138">Get Help About the SQL Server Provider</span></span>  
 <span data-ttu-id="d6338-139">**Pour obtenir de l'aide sur le fournisseur**</span><span class="sxs-lookup"><span data-stu-id="d6338-139">**To get help about the provider**</span></span>  
  
1.  <span data-ttu-id="d6338-140">Exécuter Get-Help en spécifiant le nom SQLServer</span><span class="sxs-lookup"><span data-stu-id="d6338-140">Run Get-Help specifying the name SQLServer</span></span>  
  
### <a name="example-get-sql-server-provider-help"></a><span data-ttu-id="d6338-141">Exemple : obtenir de l'aide sur le fournisseur SQL Server</span><span class="sxs-lookup"><span data-stu-id="d6338-141">Example: Get SQL Server Provider Help</span></span>  
 <span data-ttu-id="d6338-142">Cet exemple retourne des informations de base sur le fournisseur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="d6338-142">This example returns basic information about the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider:</span></span>  
  
```powershell
Get-Help SQLServer  
```  
  
## <a name="list-methods-and-properties"></a><span data-ttu-id="d6338-143">Répertorier les méthodes et les propriétés</span><span class="sxs-lookup"><span data-stu-id="d6338-143">List Methods and Properties</span></span>  
 <span data-ttu-id="d6338-144">**Pour répertorier les méthodes et les propriétés pour un nœud dans un chemin d'accès du fournisseur SQL Server**</span><span class="sxs-lookup"><span data-stu-id="d6338-144">**To list the methods and properties for a node in a SQL Server provider path**</span></span>  
  
1.  <span data-ttu-id="d6338-145">Utilisez la commande CD pour passer à un nœud dans le chemin d'accès de SQL Server ou créez une variable ayant pour valeur cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="d6338-145">Either CD to a node in the SQL Server path, or create a variable set to that location.</span></span>  
  
2.  <span data-ttu-id="d6338-146">Exécutez l’applet de commande **obten-Member** avec le paramètre-type défini sur les méthodes ou les propriétés</span><span class="sxs-lookup"><span data-stu-id="d6338-146">Run the **Get-Member** cmdlet with the -Type parameter set to either Methods or Properties</span></span>  
  
### <a name="examples-listing-methods-and-properties"></a><span data-ttu-id="d6338-147">Exemples : affichage de la liste des méthodes et des propriétés</span><span class="sxs-lookup"><span data-stu-id="d6338-147">Examples: Listing Methods and Properties</span></span>  
 <span data-ttu-id="d6338-148">L'exemple suivant répertorie les méthodes prises en charge pour le nœud Bases de données :</span><span class="sxs-lookup"><span data-stu-id="d6338-148">This example lists the methods supported for the Databases node:</span></span>  
  
```powershell
Set-Location SQL:\MyComputer\DEFAULT\Databases  
Get-Item . | Get-Member -Type Methods  
```  
  
 <span data-ttu-id="d6338-149">Cet exemple répertorie les propriétés pour une variable dont la valeur est un objet SMO Table :</span><span class="sxs-lookup"><span data-stu-id="d6338-149">This example lists the properties for a variable that has been set to an SMO Table object:</span></span>  
  
```powershell
$MyVar = New-Object Microsoft.SqlServer.Management.SMO.Table  
$MyVar | Get-Member -Type Properties  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6338-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d6338-150">See Also</span></span>  
 <span data-ttu-id="d6338-151">[Fournisseur SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="d6338-151">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="d6338-152">Utiliser les applets de commande du Moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="d6338-152">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
