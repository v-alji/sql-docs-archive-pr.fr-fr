---
title: Parcourir les chemins PowerShell SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: d68aca48-d161-45ed-9f4f-14122ed30218
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0a605479991c3e907cd9dcae254cc1bc04a49392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708459"
---
# <a name="navigate-sql-server-powershell-paths"></a><span data-ttu-id="324c3-102">Parcourir les chemins PowerShell SQL Server</span><span class="sxs-lookup"><span data-stu-id="324c3-102">Navigate SQL Server PowerShell Paths</span></span>
  <span data-ttu-id="324c3-103">Le fournisseur PowerShell du [!INCLUDE[ssDE](../includes/ssde-md.md)] expose le jeu d'objets dans une instance de SQL Server dans une structure similaire à un chemin d'accès de fichier.</span><span class="sxs-lookup"><span data-stu-id="324c3-103">The [!INCLUDE[ssDE](../includes/ssde-md.md)] PowerShell provider exposes the set of objects in an instance of SQL Server in a structure similar to a file path.</span></span> <span data-ttu-id="324c3-104">Vous pouvez utiliser des applets de commande Windows PowerShell pour naviguer jusqu'au chemin d'accès du fournisseur et créer des lecteurs personnalisés pour raccourcir le chemin d'accès que vous devez taper.</span><span class="sxs-lookup"><span data-stu-id="324c3-104">You can use Windows PowerShell cmdlets to navigate the provider path, and create custom drives to shorten the path you have to type.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="324c3-105">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="324c3-105">Before You Begin</span></span>  
 <span data-ttu-id="324c3-106">Windows PowerShell implémente des applets de commande pour parcourir la structure de chemin d'accès qui représentent la hiérarchie des objets pris en charge par un fournisseur PowerShell.</span><span class="sxs-lookup"><span data-stu-id="324c3-106">Windows PowerShell implements cmdlets to navigate the path structure that represent the hierarchy of objects supported by a PowerShell provider.</span></span> <span data-ttu-id="324c3-107">Une fois que vous avez accédé à un nœud dans le chemin d'accès, vous pouvez utiliser d'autres applets de commande pour exécuter des opérations de base sur l'objet actif.</span><span class="sxs-lookup"><span data-stu-id="324c3-107">When you have navigated to a node in the path, you can use other cmdlets to perform basic operations on the current object.</span></span> <span data-ttu-id="324c3-108">Étant donné que les applets de commande sont fréquemment utilisées, elles ont des alias canoniques courts.</span><span class="sxs-lookup"><span data-stu-id="324c3-108">Because the cmdlets are used frequently, they have short, canonical aliases.</span></span> <span data-ttu-id="324c3-109">Il existe également un ensemble d'alias qui mappent les applets de commande à des commandes semblables destinées à l'invite de commandes, et un autre ensemble pour les commandes de l'interpréteur de commandes UNIX.</span><span class="sxs-lookup"><span data-stu-id="324c3-109">There is also one set of aliases that maps the cmdlets to similar command prompt commands, and another set for UNIX shell commands.</span></span>  
  
 <span data-ttu-id="324c3-110">Le fournisseur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] implémente un sous-ensemble des applets de commande du fournisseur, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="324c3-110">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider implements a subset of the provider cmdlets, shown in the following table.</span></span>  
  
|<span data-ttu-id="324c3-111">Applet de commande</span><span class="sxs-lookup"><span data-stu-id="324c3-111">cmdlet</span></span>|<span data-ttu-id="324c3-112">Alias canonique</span><span class="sxs-lookup"><span data-stu-id="324c3-112">Canonical alias</span></span>|<span data-ttu-id="324c3-113">Alias d'applet de commande</span><span class="sxs-lookup"><span data-stu-id="324c3-113">cmd alias</span></span>|<span data-ttu-id="324c3-114">Alias de l'interpréteur de commandes UNIX</span><span class="sxs-lookup"><span data-stu-id="324c3-114">UNIX shell alias</span></span>|<span data-ttu-id="324c3-115">Description</span><span class="sxs-lookup"><span data-stu-id="324c3-115">Description</span></span>|  
|------------|---------------------|---------------|----------------------|-----------------|  
|<span data-ttu-id="324c3-116">**Get-Location**</span><span class="sxs-lookup"><span data-stu-id="324c3-116">**Get-Location**</span></span>|<span data-ttu-id="324c3-117">**gl**</span><span class="sxs-lookup"><span data-stu-id="324c3-117">**gl**</span></span>|<span data-ttu-id="324c3-118">**pwd**</span><span class="sxs-lookup"><span data-stu-id="324c3-118">**pwd**</span></span>|<span data-ttu-id="324c3-119">**pwd**</span><span class="sxs-lookup"><span data-stu-id="324c3-119">**pwd**</span></span>|<span data-ttu-id="324c3-120">Obtient le nœud actuel.</span><span class="sxs-lookup"><span data-stu-id="324c3-120">Gets the current node.</span></span>|  
|`Set-Location`|<span data-ttu-id="324c3-121">**SL**</span><span class="sxs-lookup"><span data-stu-id="324c3-121">**sl**</span></span>|<span data-ttu-id="324c3-122">**cd, chdir**</span><span class="sxs-lookup"><span data-stu-id="324c3-122">**cd, chdir**</span></span>|<span data-ttu-id="324c3-123">**cd, chdir**</span><span class="sxs-lookup"><span data-stu-id="324c3-123">**cd, chdir**</span></span>|<span data-ttu-id="324c3-124">Modifie le nœud actuel.</span><span class="sxs-lookup"><span data-stu-id="324c3-124">Changes the current node.</span></span>|  
|<span data-ttu-id="324c3-125">**Get-ChildItem**</span><span class="sxs-lookup"><span data-stu-id="324c3-125">**Get-ChildItem**</span></span>|<span data-ttu-id="324c3-126">**gci**</span><span class="sxs-lookup"><span data-stu-id="324c3-126">**gci**</span></span>|<span data-ttu-id="324c3-127">**dir**</span><span class="sxs-lookup"><span data-stu-id="324c3-127">**dir**</span></span>|<span data-ttu-id="324c3-128">**LS**</span><span class="sxs-lookup"><span data-stu-id="324c3-128">**ls**</span></span>|<span data-ttu-id="324c3-129">Répertorie les objets stockés sur le nœud actuel.</span><span class="sxs-lookup"><span data-stu-id="324c3-129">Lists the objects stored at the current node.</span></span>|  
|<span data-ttu-id="324c3-130">**Get-Item**</span><span class="sxs-lookup"><span data-stu-id="324c3-130">**Get-Item**</span></span>|<span data-ttu-id="324c3-131">**gi**</span><span class="sxs-lookup"><span data-stu-id="324c3-131">**gi**</span></span>|||<span data-ttu-id="324c3-132">Retourne les propriétés de l'élément actif.</span><span class="sxs-lookup"><span data-stu-id="324c3-132">Returns the properties of the current item.</span></span>|  
|<span data-ttu-id="324c3-133">**Rename-Item**</span><span class="sxs-lookup"><span data-stu-id="324c3-133">**Rename-Item**</span></span>|<span data-ttu-id="324c3-134">**rni**</span><span class="sxs-lookup"><span data-stu-id="324c3-134">**rni**</span></span>|<span data-ttu-id="324c3-135">**RN**</span><span class="sxs-lookup"><span data-stu-id="324c3-135">**rn**</span></span>|<span data-ttu-id="324c3-136">**ren**</span><span class="sxs-lookup"><span data-stu-id="324c3-136">**ren**</span></span>|<span data-ttu-id="324c3-137">Renomme un objet.</span><span class="sxs-lookup"><span data-stu-id="324c3-137">Renames an object.</span></span>|  
|<span data-ttu-id="324c3-138">**Remove-Item**</span><span class="sxs-lookup"><span data-stu-id="324c3-138">**Remove-Item**</span></span>|<span data-ttu-id="324c3-139">**instance réservée**</span><span class="sxs-lookup"><span data-stu-id="324c3-139">**ri**</span></span>|<span data-ttu-id="324c3-140">**del, rd**</span><span class="sxs-lookup"><span data-stu-id="324c3-140">**del, rd**</span></span>|<span data-ttu-id="324c3-141">**rm, rmdir**</span><span class="sxs-lookup"><span data-stu-id="324c3-141">**rm, rmdir**</span></span>|<span data-ttu-id="324c3-142">Supprime un objet.</span><span class="sxs-lookup"><span data-stu-id="324c3-142">Removes an object.</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="324c3-143">Certains identificateurs (noms d'objets) [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] contiennent des caractères que Windows PowerShell ne prend pas en charge dans les noms de chemins d'accès.</span><span class="sxs-lookup"><span data-stu-id="324c3-143">Some [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifiers (object names) contain characters that Windows PowerShell does not support in path names.</span></span> <span data-ttu-id="324c3-144">Pour plus d'informations sur l'utilisation de noms qui contiennent ces caractères, consultez [SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="324c3-144">For more information about how to use names that contain these characters, see [SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md).</span></span>  
  
### <a name="sql-server-information-returned-by-get-childitem"></a><span data-ttu-id="324c3-145">Informations de SQL Server retournées par Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="324c3-145">SQL Server Information Returned by Get-ChildItem</span></span>  
 <span data-ttu-id="324c3-146">Les informations retournées par **Get-ChildItem** (ou ses alias **dir** et **ls** ) dépendent de votre emplacement dans un chemin SQLSERVER:.</span><span class="sxs-lookup"><span data-stu-id="324c3-146">The information returned by **Get-ChildItem** (or its **dir** and **ls** aliases) depends on your location in a SQLSERVER: path.</span></span>  
  
|<span data-ttu-id="324c3-147">Emplacement de chemin d'accès</span><span class="sxs-lookup"><span data-stu-id="324c3-147">Path location</span></span>|<span data-ttu-id="324c3-148">Résultats de Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="324c3-148">Get-ChildItem results</span></span>|  
|-------------------|----------------------------|  
|<span data-ttu-id="324c3-149">SQLSERVER:\SQL</span><span class="sxs-lookup"><span data-stu-id="324c3-149">SQLSERVER:\SQL</span></span>|<span data-ttu-id="324c3-150">Retourne le nom de l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="324c3-150">Returns the name of the local computer.</span></span> <span data-ttu-id="324c3-151">Si vous avez utilisé SMO ou WMI pour vous connecter aux instances du [!INCLUDE[ssDE](../includes/ssde-md.md)] sur d'autres ordinateurs, ces ordinateurs sont également répertoriés.</span><span class="sxs-lookup"><span data-stu-id="324c3-151">If you have used the SMO or WMI to connect to instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] on other computers, those computers are also listed.</span></span>|  
|<span data-ttu-id="324c3-152">SQLSERVER:\SQL\\*nom_ordinateur*</span><span class="sxs-lookup"><span data-stu-id="324c3-152">SQLSERVER:\SQL\\*ComputerName*</span></span>|<span data-ttu-id="324c3-153">Liste des instances du [!INCLUDE[ssDE](../includes/ssde-md.md)] sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="324c3-153">The list of instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] on the computer.</span></span>|  
|<span data-ttu-id="324c3-154">SqlServer : \ SQL \\ *ComputerName* \\ *InstanceName*</span><span class="sxs-lookup"><span data-stu-id="324c3-154">SQLSERVER:\SQL\\*ComputerName*\\*InstanceName*</span></span>|<span data-ttu-id="324c3-155">Liste des types d'objets de niveau supérieur dans l'instance, tels que les points de terminaison, les certificats et les bases de données.</span><span class="sxs-lookup"><span data-stu-id="324c3-155">The list of top-level object types in the instance, such as Endpoints, Certificates, and Databases.</span></span>|  
|<span data-ttu-id="324c3-156">Nœud de classes d'objets, tels que Databases</span><span class="sxs-lookup"><span data-stu-id="324c3-156">Object class node, such as Databases</span></span>|<span data-ttu-id="324c3-157">Liste des objets de ce type, telle que la liste des bases de données : MASTER, Model, AdventureWorks20008R2.</span><span class="sxs-lookup"><span data-stu-id="324c3-157">The list of objects of that type, such as the list of databases: master, model, AdventureWorks20008R2.</span></span>|  
|<span data-ttu-id="324c3-158">Nœud de noms d’objets, comme AdventureWorks2012</span><span class="sxs-lookup"><span data-stu-id="324c3-158">Object name node, such as AdventureWorks2012</span></span>|<span data-ttu-id="324c3-159">Liste des types d'objets contenus dans l'objet.</span><span class="sxs-lookup"><span data-stu-id="324c3-159">The list of object types contained within the object.</span></span> <span data-ttu-id="324c3-160">Par exemple, une base de données répertorierait des types d'objets tels que les tables et les vues.</span><span class="sxs-lookup"><span data-stu-id="324c3-160">For example, a database would list object types such as tables and views.</span></span>|  
  
 <span data-ttu-id="324c3-161">Par défaut, **Get-ChildItem** ne répertorie pas d’objets système.</span><span class="sxs-lookup"><span data-stu-id="324c3-161">By default, **Get-ChildItem** does not list any system objects.</span></span> <span data-ttu-id="324c3-162">Utilisez le paramètre *Force* pour afficher les objets système, tels que les objets dans le schéma **sys** .</span><span class="sxs-lookup"><span data-stu-id="324c3-162">Use the *Force* parameter to see system objects, such as the objects in the **sys** schema.</span></span>  
  
### <a name="custom-drives"></a><span data-ttu-id="324c3-163">Lecteurs personnalisés</span><span class="sxs-lookup"><span data-stu-id="324c3-163">Custom Drives</span></span>  
 <span data-ttu-id="324c3-164">Windows PowerShell permet aux utilisateurs de définir des lecteurs virtuels appelés lecteurs PowerShell,</span><span class="sxs-lookup"><span data-stu-id="324c3-164">Windows PowerShell lets users define virtual drives, which are referred to as PowerShell drives.</span></span> <span data-ttu-id="324c3-165">qui sont mappés aux nœuds de démarrage d'une instruction de chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="324c3-165">These map over the starting nodes of a path statement.</span></span> <span data-ttu-id="324c3-166">Ils sont généralement utilisés pour raccourcir les chemins d'accès fréquemment tapés.</span><span class="sxs-lookup"><span data-stu-id="324c3-166">They are typically used to shorten paths that are typed frequently.</span></span> <span data-ttu-id="324c3-167">Les chemins d'accès SQLSERVER: peuvent devenir longs, occupant beaucoup de place dans la fenêtre Windows PowerShell et nécessitant beaucoup de saisie.</span><span class="sxs-lookup"><span data-stu-id="324c3-167">SQLSERVER: paths can get long, taking space in the Windows PowerShell window and requiring a lot of typing.</span></span> <span data-ttu-id="324c3-168">Si vous devez effectuer beaucoup de travail sur un nœud de chemin d'accès particulier, vous pouvez définir un lecteur Windows PowerShell personnalisé mappé à ce nœud.</span><span class="sxs-lookup"><span data-stu-id="324c3-168">If you are going to do a lot of work at a particular path node, you can define a custom Windows PowerShell drive that maps to that node.</span></span>  
  
## <a name="use-powershell-cmdlet-aliases"></a><span data-ttu-id="324c3-169">Utiliser des alias d'applets de commande PowerShell</span><span class="sxs-lookup"><span data-stu-id="324c3-169">Use PowerShell Cmdlet Aliases</span></span>  
 <span data-ttu-id="324c3-170">**Utiliser un alias d'applet de commande**</span><span class="sxs-lookup"><span data-stu-id="324c3-170">**Use a cmdlet alias**</span></span>  
  
-   <span data-ttu-id="324c3-171">Au lieu de taper un nom d'applet de commande complet, tapez un alias plus court ou un alias mappé à une commande d'invite de commandes familière.</span><span class="sxs-lookup"><span data-stu-id="324c3-171">Instead of typing a full cmdlet name, type a shorter alias, or one that maps to a familiar commend prompt command.</span></span>  
  
### <a name="alias-example-powershell"></a><span data-ttu-id="324c3-172">Exemple d'alias (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="324c3-172">Alias Example (PowerShell)</span></span>  
 <span data-ttu-id="324c3-173">Par exemple, vous pouvez utiliser l'un des jeux d'applets de commande ou ensembles d'alias suivants pour récupérer la liste des instances [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] disponibles si vous accédez au dossier SQLSERVER:\SQL et si vous demandez la liste des éléments enfants de ce dossier :</span><span class="sxs-lookup"><span data-stu-id="324c3-173">For example, you can use one of the following sets of cmdlets or aliases to retrieve a listing of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instances available to you by navigating to the SQLSERVER:\SQL folder and requesting the list of child items for the folder:</span></span>  
  
```powershell
## Shows using the full cmdet name.  
Set-Location SQLSERVER:\SQL  
Get-ChildItem  
  
## Shows using canonical aliases.  
sl SQLSERVER:\SQL  
gci  
  
## Shows using command prompt aliases.  
cd SQLSERVER:\SQL  
dir  
  
## Shows using Unix shell aliases.  
cd SQLSERVER:\SQL  
ls  
```  
  
## <a name="use-get-childitem"></a><span data-ttu-id="324c3-174">Utiliser Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="324c3-174">Use Get-ChildItem</span></span>  

### <a name="return-information-by-using-get-childitem"></a><span data-ttu-id="324c3-175">Renvoyer des informations à l'aide de Get-Childitem</span><span class="sxs-lookup"><span data-stu-id="324c3-175">Return information by using Get-Childitem</span></span>
  
1.  <span data-ttu-id="324c3-176">Accédez au nœud pour lequel vous souhaitez obtenir une liste de childrem</span><span class="sxs-lookup"><span data-stu-id="324c3-176">Navigate to the node for which you want a list of childrem</span></span>  
  
2.  <span data-ttu-id="324c3-177">Exécutez Get-Childitem pour obtenir la liste.</span><span class="sxs-lookup"><span data-stu-id="324c3-177">Run Get-Childitem to get the list.</span></span>  
  
### <a name="get-childitem-example-powershell"></a><span data-ttu-id="324c3-178">Exemple de Get-ChildItem (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="324c3-178">Get-ChildItem Example (PowerShell)</span></span>  
 <span data-ttu-id="324c3-179">Ces exemples illustrent les informations retournées par Get-Childitem pour différents nœuds dans un chemin d'accès de fournisseur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="324c3-179">These examples illustrate the information returned by Get-Childitem for different nodes in a SQL Server provider path.</span></span>  
  
```powershell
## Return the current computer and any computer  
## to which you have made a SQL or WMI connection.  
Set-Location SQLSERVER:\SQL  
Get-ChildItem  
  
## List the instances of the Database Engine on the local computer.  
Set-Location SQLSERVER:\SQL\localhost  
Get-ChildItem  
  
## Lists the categories of objects available in the  
## default instance on the local computer.  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT  
Get-ChildItem  
  
## Lists the databases from the local default instance.  
## The force parameter is used to include the system databases.  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
Get-ChildItem -force  
```  
  
## <a name="create-a-custom-drive"></a><span data-ttu-id="324c3-180">Créer un lecteur personnalisé</span><span class="sxs-lookup"><span data-stu-id="324c3-180">Create a Custom Drive</span></span>  

### <a name="create-and-use-a-custom-drive"></a><span data-ttu-id="324c3-181">Créer et utiliser un lecteur personnalisé</span><span class="sxs-lookup"><span data-stu-id="324c3-181">Create and use a custom drive</span></span>
  
1.  <span data-ttu-id="324c3-182">Utilisez `New-PSDrive` pour définir un lecteur personnalisé.</span><span class="sxs-lookup"><span data-stu-id="324c3-182">Use `New-PSDrive` to define a custom drive.</span></span> <span data-ttu-id="324c3-183">Utilisez le paramètre `Root` pour spécifier le chemin d'accès représenté par le nom du lecteur personnalisé.</span><span class="sxs-lookup"><span data-stu-id="324c3-183">Use the `Root` parameter to specify the path that is represented by the custom drive name.</span></span>  
  
2.  <span data-ttu-id="324c3-184">Faites référence au nom du lecteur personnalisé dans les applets de commande de navigation de chemin d'accès telles que `Set-Location`.</span><span class="sxs-lookup"><span data-stu-id="324c3-184">Reference the custom drive name in path navigation cmdlets such as `Set-Location`.</span></span>  
  
### <a name="custom-drive-example-powershell"></a><span data-ttu-id="324c3-185">Exemple de lecteur personnalisé (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="324c3-185">Custom Drive Example (PowerShell)</span></span>  
 <span data-ttu-id="324c3-186">Cet exemple crée un lecteur virtuel nommé AWDB qui mappe au nœud pour une copie déployée de l’exemple de base de données AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="324c3-186">This example creates a virtual drive named AWDB that maps to the node for a deployed copy of the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="324c3-187">Le lecteur virtuel est ensuite utilisé pour naviguer jusqu'à une table dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="324c3-187">The virtual drive is then used to navigate to a table in the database.</span></span>  
  
```powershell
## Create a new virtual drive.  
New-PSDrive -Name AWDB -Root SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012  
  
## Use AWDB: to navigate to a specific table.  
Set-Location AWDB:\Tables\Purchasing.Vendor  
```  
  
## <a name="see-also"></a><span data-ttu-id="324c3-188">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="324c3-188">See Also</span></span>  
 <span data-ttu-id="324c3-189">[Fournisseur SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="324c3-189">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="324c3-190">[Utiliser des chemins d’accès SQL Server PowerShell](work-with-sql-server-powershell-paths.md) </span><span class="sxs-lookup"><span data-stu-id="324c3-190">[Work With SQL Server PowerShell Paths](work-with-sql-server-powershell-paths.md) </span></span>  
 <span data-ttu-id="324c3-191">[Convertir des URN en chemins d’accès de fournisseur SQL Server](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span><span class="sxs-lookup"><span data-stu-id="324c3-191">[Convert URNs to SQL Server Provider Paths](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span></span>  
 [<span data-ttu-id="324c3-192">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="324c3-192">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
