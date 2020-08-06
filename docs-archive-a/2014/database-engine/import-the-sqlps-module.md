---
title: Importer le module SQLPS | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a972c56e-b2af-4fe6-abbd-817406e2c93a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 37e66db05615ce8a285a80e5ac26b0cae411abeb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703276"
---
# <a name="import-the-sqlps-module"></a><span data-ttu-id="2b6a3-102">Importer le module SQLPS</span><span class="sxs-lookup"><span data-stu-id="2b6a3-102">Import the SQLPS Module</span></span>
  <span data-ttu-id="2b6a3-103">La méthode recommandée pour gérer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à partir de PowerShell consiste à importer le module `sqlps` dans un environnement Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="2b6a3-103">The recommended way to manage [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] from PowerShell is to import the `sqlps` module into a Windows PowerShell 2.0 environment.</span></span> <span data-ttu-id="2b6a3-104">Le module charge et inscrit les assemblys de facilité de gestion et les composants logiciels enfichables [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b6a3-104">The module loads and registers the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] snap-ins and manageability assemblies.</span></span>  
  
1.  <span data-ttu-id="2b6a3-105">**Avant de commencer :**  [sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="2b6a3-105">**Before You Begin:**  [Security](#Security)</span></span>  
  
2.  <span data-ttu-id="2b6a3-106">**Pour charger le module :**  [Charger le module sqlps](#LoadSqlps)</span><span class="sxs-lookup"><span data-stu-id="2b6a3-106">**To load the module:**  [Load the sqlps Module](#LoadSqlps)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="2b6a3-107">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2b6a3-107">Before You Begin</span></span>  
 <span data-ttu-id="2b6a3-108">Après avoir importé le module `sqlps` dans Windows PowerShell, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="2b6a3-108">After importing the `sqlps` module into Windows PowerShell, you can then:</span></span>  
  
-   <span data-ttu-id="2b6a3-109">exécuter des commandes Windows PowerShell de façon interactive ;</span><span class="sxs-lookup"><span data-stu-id="2b6a3-109">Interactively run Windows PowerShell commands.</span></span>  
  
-   <span data-ttu-id="2b6a3-110">exécuter des fichiers de script Windows PowerShell ;</span><span class="sxs-lookup"><span data-stu-id="2b6a3-110">Run Windows PowerShell script files.</span></span>  
  
-   <span data-ttu-id="2b6a3-111">exécuter des applets de commande [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="2b6a3-111">Run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets.</span></span>  
  
-   <span data-ttu-id="2b6a3-112">utiliser les chemins d'accès du fournisseur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour naviguer dans la hiérarchie des objets [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="2b6a3-112">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider paths to navigate through the hierarchy of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
-   <span data-ttu-id="2b6a3-113">utiliser les modèles objets de la facilité de gestion [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (tels que Microsoft.SqlServer.Management.Smo) pour gérer des objets [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b6a3-113">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] manageability object models (such as Microsoft.SqlServer.Management.Smo) to manage [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b6a3-114">Les verbes utilisés dans les noms de deux applets de commande SQL Server (`Encode-Sqlname` et `Decode-Sqlname`) ne correspondent pas aux verbes approuvés pour Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="2b6a3-114">The verbs used in the names of two SQL Server cmdlets (`Encode-Sqlname` and `Decode-Sqlname`) do not match the approved verbs for Windows PowerShell 2.0.</span></span> <span data-ttu-id="2b6a3-115">Cela n'a aucun effet sur leur opération, mais Windows PowerShell déclenche un avertissement lorsque le module `sqlps` est importé dans une session.</span><span class="sxs-lookup"><span data-stu-id="2b6a3-115">This has no effect on their operation, but Windows PowerShell raises a warning when the `sqlps` module is imported to a session.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2b6a3-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2b6a3-116">Security</span></span>  
 <span data-ttu-id="2b6a3-117">Par défaut, Windows PowerShell s’exécute avec le niveau **Restreint**de la stratégie d’exécution de scripts, ce qui empêche l’exécution de tout script Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b6a3-117">By default, Windows PowerShell runs with the scripting execution policy set to **Restricted**, which prevents running any Windows PowerShell scripts.</span></span> <span data-ttu-id="2b6a3-118">Pour charger le module `sqlps`, vous pouvez utiliser l'applet de commande `Set-ExecutionPolicy` pour activer l'exécution de scripts signés uniquement ou de tous les scripts.</span><span class="sxs-lookup"><span data-stu-id="2b6a3-118">To load the `sqlps` module, you can use the `Set-ExecutionPolicy` cmdlet to enable running signed scripts, or any scripts.</span></span> <span data-ttu-id="2b6a3-119">Exécutez uniquement des scripts provenant de sources fiables et sécurisez tous les fichiers d'entrée et de sortie en utilisant les autorisations NTFS appropriées.</span><span class="sxs-lookup"><span data-stu-id="2b6a3-119">Only run scripts from trusted sources, and secure all input and output files using the appropriate NTFS permissions.</span></span> <span data-ttu-id="2b6a3-120">Pour plus d'informations sur l'activation de scripts Windows PowerShell, consultez [Exécution de scripts Windows PowerShell](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell?view=powershell-6#how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows).</span><span class="sxs-lookup"><span data-stu-id="2b6a3-120">For more information about enabling Windows PowerShell scripts, see [Running Windows PowerShell Scripts](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell?view=powershell-6#how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows).</span></span>  
  
##  <a name="load-the-sqlps-module"></a><a name="LoadSqlps"></a> <span data-ttu-id="2b6a3-121">Charger le module sqlps</span><span class="sxs-lookup"><span data-stu-id="2b6a3-121">Load the sqlps Module</span></span>  

### <a name="to-load-the-sqlps-module-in-windows-powershell"></a><span data-ttu-id="2b6a3-122">Pour charger le module sqlps dans Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b6a3-122">To load the sqlps module in Windows PowerShell</span></span>
  
1.  <span data-ttu-id="2b6a3-123">Utilisez l'applet de commande `Set-ExecutionPolicy` pour définir la stratégie d'exécution de scripts appropriée.</span><span class="sxs-lookup"><span data-stu-id="2b6a3-123">Use the `Set-ExecutionPolicy` cmdlet to set the appropriate script execution policy.</span></span>  
  
2.  <span data-ttu-id="2b6a3-124">Utilisez l'applet de commande `Import-Module` pour importer le module sqlps.</span><span class="sxs-lookup"><span data-stu-id="2b6a3-124">Use the `Import-Module` cmdlet to import the sqlps module.</span></span> <span data-ttu-id="2b6a3-125">Spécifiez le paramètre `DisableNameChecking` si vous souhaitez supprimer l'avertissement sur `Encode-Sqlname` et `Decode-Sqlname`.</span><span class="sxs-lookup"><span data-stu-id="2b6a3-125">Specify the `DisableNameChecking` parameter if you want to suppress the warning about `Encode-Sqlname` and `Decode-Sqlname`.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="2b6a3-126">Exemple (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="2b6a3-126">Example (PowerShell)</span></span>  
 <span data-ttu-id="2b6a3-127">Cet exemple charge le module `sqlps` avec la fonction de vérification des noms désactivée.</span><span class="sxs-lookup"><span data-stu-id="2b6a3-127">This example loads the `sqlps` module with name checking turned off.</span></span>  
  
```powershell
## Import the SQL Server Module.  
  
Import-Module "sqlps" -DisableNameChecking  
```  

## <a name="see-also"></a><span data-ttu-id="2b6a3-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2b6a3-128">See Also</span></span>  
 <span data-ttu-id="2b6a3-129">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="2b6a3-129">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span></span>  
 <span data-ttu-id="2b6a3-130">[Fournisseur SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="2b6a3-130">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="2b6a3-131">Utiliser les applets de commande du Moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="2b6a3-131">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
