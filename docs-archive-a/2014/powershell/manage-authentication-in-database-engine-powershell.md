---
title: Gérer l’authentification dans le moteur de base de données PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: ab9212a6-6628-4f08-a38c-d3156e05ddea
author: stevestein
ms.author: sstein
ms.openlocfilehash: 018a2698a43148af971622f54c8418bf23c2c781
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696907"
---
# <a name="manage-authentication-in-database-engine-powershell"></a><span data-ttu-id="4f9fb-102">Gérer l'authentification dans le moteur de base de données PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f9fb-102">Manage Authentication in Database Engine PowerShell</span></span>
  <span data-ttu-id="4f9fb-103">Par défaut, les composants de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell utilisent l'authentification Windows lors de la connexion à une instance du [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f9fb-103">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell components use Windows Authentication when connecting to an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="4f9fb-104">Vous pouvez utiliser l'authentification SQL Server en définissant un lecteur virtuel PowerShell ou en spécifiant les paramètres `-Username` et `-Password` pour `Invoke-Sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="4f9fb-104">You can use SQL Server Authentication by either defining a PowerShell virtual drive, or by specifying the `-Username` and `-Password` parameters for `Invoke-Sqlcmd`.</span></span>  
  
1.  <span data-ttu-id="4f9fb-105">**Avant de commencer :**  [Autorisations](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="4f9fb-105">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
2.  <span data-ttu-id="4f9fb-106">**Pour définir l’authentification en utilisant :**  [Un lecteur virtuel](#SQLAuthVirtDrv), [Invoke-Sqlcmd](#SQLAuthInvSqlCmd)</span><span class="sxs-lookup"><span data-stu-id="4f9fb-106">**To set authentication, using:**  [A Virtual Drive](#SQLAuthVirtDrv), [Invoke-Sqlcmd](#SQLAuthInvSqlCmd)</span></span>  
  
##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4f9fb-107">Autorisations</span><span class="sxs-lookup"><span data-stu-id="4f9fb-107">Permissions</span></span>  
 <span data-ttu-id="4f9fb-108">Toutes les actions que vous pouvez effectuer dans une instance du [!INCLUDE[ssDE](../includes/ssde-md.md)] sont contrôlées par les autorisations accordées aux informations d'identification utilisées pour la connexion à l'instance.</span><span class="sxs-lookup"><span data-stu-id="4f9fb-108">All actions you can perform in an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] are controlled by the permissions granted to the authentication credentials used to connect to the instance.</span></span> <span data-ttu-id="4f9fb-109">Par défaut, le fournisseur et les applets de commande [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilisent le compte Windows sous lequel ils s'exécutent pour établir une connexion via l'authentification Windows au [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f9fb-109">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider and cmdlets use the Windows account under which it is running to make a Windows Authentication connection to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="4f9fb-110">Pour établir une connexion via l'authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vous devez fournir un ID de connexion et un mot de passe d'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f9fb-110">To make a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication connection you must supply a SQL Server Authentication login ID and password.</span></span> <span data-ttu-id="4f9fb-111">Lorsque vous utilisez le [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] fournisseur, vous devez associer les [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] informations d’identification de connexion à un lecteur virtuel, puis utiliser la commande de changement de répertoire ( `cd` ) pour vous connecter à ce lecteur.</span><span class="sxs-lookup"><span data-stu-id="4f9fb-111">When using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider, you must associate the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login credentials with a virtual drive, and then use the change directory command (`cd`) to connect to that drive.</span></span> <span data-ttu-id="4f9fb-112">Dans Windows PowerShell, les informations d'identification de sécurité peuvent être associées uniquement à des lecteurs virtuels.</span><span class="sxs-lookup"><span data-stu-id="4f9fb-112">In Windows PowerShell, security credentials can only be associated with virtual drives.</span></span>  
  
##  <a name="sql-server-authentication-using-a-virtual-drive"></a><a name="SQLAuthVirtDrv"></a> <span data-ttu-id="4f9fb-113">Authentification SQL Server avec un lecteur virtuel</span><span class="sxs-lookup"><span data-stu-id="4f9fb-113">SQL Server Authentication Using a Virtual Drive</span></span>  
 <span data-ttu-id="4f9fb-114">**Pour créer un lecteur virtuel associé à une connexion via l'authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4f9fb-114">**To create a virtual drive associated with a SQL Server Authentication login**</span></span>  
  
1.  <span data-ttu-id="4f9fb-115">Créez une fonction qui :</span><span class="sxs-lookup"><span data-stu-id="4f9fb-115">Create a function that:</span></span>  
  
    1.  <span data-ttu-id="4f9fb-116">Possède des paramètres pour le nom indiquant le lecteur virtuel, l'ID de connexion et le chemin d'accès du fournisseur à associer au lecteur virtuel.</span><span class="sxs-lookup"><span data-stu-id="4f9fb-116">Has parameters for the name to give the virtual drive, the login ID, and the provider path to associate with the virtual drive.</span></span>  
  
    2.  <span data-ttu-id="4f9fb-117">Utilise `read-host` pour inviter l'utilisateur à fournir le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="4f9fb-117">Uses `read-host` to prompt the user for the password.</span></span>  
  
    3.  <span data-ttu-id="4f9fb-118">Utilise `new-object` pour créer un objet d'informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="4f9fb-118">Uses `new-object` to create a credentials object.</span></span>  
  
    4.  <span data-ttu-id="4f9fb-119">Utilise `new-psdrive` pour créer un lecteur virtuel avec les informations d'identification fournies.</span><span class="sxs-lookup"><span data-stu-id="4f9fb-119">Uses `new-psdrive` to create a virtual drive with the supplied credentials.</span></span>  
  
2.  <span data-ttu-id="4f9fb-120">Appelez la fonction pour créer un lecteur virtuel avec les informations d'identification fournies.</span><span class="sxs-lookup"><span data-stu-id="4f9fb-120">Invoke the function to create a virtual drive with the supplied credentials.</span></span>  
  
### <a name="example-virtual-drive"></a><span data-ttu-id="4f9fb-121">Exemple (lecteur virtuel)</span><span class="sxs-lookup"><span data-stu-id="4f9fb-121">Example (Virtual Drive)</span></span>  
 <span data-ttu-id="4f9fb-122">Cet exemple crée une fonction nommée **sqldrive** que vous pouvez utiliser pour créer un lecteur virtuel associé à la connexion via l'authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] et à l'instance spécifiées.</span><span class="sxs-lookup"><span data-stu-id="4f9fb-122">This example creates a function named **sqldrive** that you can use to create a virtual drive that is associated with the specified [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication login and instance.</span></span>  
  
 <span data-ttu-id="4f9fb-123">La fonction **sqldrive** vous invite à entrer le mot de passe de votre connexion, en masquant celui-ci à mesure que vous le tapez.</span><span class="sxs-lookup"><span data-stu-id="4f9fb-123">The **sqldrive** function prompts you to enter the password for your login, masking the password as you type it in.</span></span> <span data-ttu-id="4f9fb-124">Ensuite, chaque fois que vous utilisez la commande de changement de répertoire ( `cd` ) pour vous connecter à un chemin d’accès à l’aide du nom de lecteur virtuel, toutes les opérations sont effectuées à l’aide des [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] informations d’identification de connexion d’authentification que vous avez fournies lors de la création du lecteur.</span><span class="sxs-lookup"><span data-stu-id="4f9fb-124">Then, whenever you use the change directory command (`cd`) to connect to a path by using the virtual drive name, all operations are performed by using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication login credentials that you supplied when you created the drive.</span></span>  
  
```powershell
## Create a function that specifies the login and prompts for the password.  
  
function sqldrive  
{  
    param( [string]$name, [string]$login = "MyLogin", [string]$root = "SQLSERVER:\SQL\MyComputer\MyInstance" )  
    $pwd = Read-Host -AsSecureString -Prompt "Password"  
    $cred = New-Object System.Management.Automation.PSCredential -argumentlist $login, $pwd  
    New-PSDrive $name -PSProvider SqlServer -Root $root -Credential $cred -Scope 1  
}  
  
## Use the sqldrive function to create a SQLAuth virtual drive.  
sqldrive SQLAuth  
  
## CD to the virtual drive, which invokes the supplied authentication credentials.  
cd SQLAuth  
```  
  
##  <a name="sql-server-authentication-using-invoke-sqlcmd"></a><a name="SQLAuthInvSqlCmd"></a> <span data-ttu-id="4f9fb-125">Authentification SQL Server avec Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="4f9fb-125">SQL Server Authentication Using Invoke-Sqlcmd</span></span>  
 <span data-ttu-id="4f9fb-126">**Pour utiliser Invoke-Sqlcmd avec l'authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4f9fb-126">**To use Invoke-Sqlcmd with SQL Server Authentication**</span></span>  
  
1.  <span data-ttu-id="4f9fb-127">Utilisez le paramètre de `-Username` pour spécifier un ID de connexion, et le paramètre de `-Password` pour spécifier le mot de passe associé.</span><span class="sxs-lookup"><span data-stu-id="4f9fb-127">Use the `-Username` parameter to specify a login ID, and the `-Password` parameter to specify the associated password.</span></span>  
  
### <a name="example-invoke-sqlcmd"></a><span data-ttu-id="4f9fb-128">Exemple (Invoke-Sqlcmd)</span><span class="sxs-lookup"><span data-stu-id="4f9fb-128">Example (Invoke-Sqlcmd)</span></span>  
 <span data-ttu-id="4f9fb-129">Cet exemple utilise l'applet de commande read-host pour inviter l'utilisateur à entrer un mot de passe, puis se connecte via l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f9fb-129">This example uses the read-host cmdlet to prompt the user for a password, and then connects using SQL Server Authentication.</span></span>  
  
```powershell
## Prompt the user for their password.  
$pwd = Read-Host -AsSecureString -Prompt "Password"  
  
Invoke-Sqlcmd -Query "SELECT GETDATE() AS TimeOfQuery;" -ServerInstance "MyComputer\MyInstance" -Username "MyLogin" -Password $pwd  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f9fb-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f9fb-130">See Also</span></span>  
 <span data-ttu-id="4f9fb-131">[SQL Server PowerShell](sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="4f9fb-131">[SQL Server PowerShell](sql-server-powershell.md) </span></span>  
 <span data-ttu-id="4f9fb-132">[Fournisseur SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="4f9fb-132">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="4f9fb-133">Invoke-Sqlcmd (applet de commande)</span><span class="sxs-lookup"><span data-stu-id="4f9fb-133">Invoke-Sqlcmd cmdlet</span></span>](../database-engine/invoke-sqlcmd-cmdlet.md)  
