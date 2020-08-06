---
title: Utiliser les applets de commande du Moteur de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Cmdlets [SQL Server], Encode-Sqlname
- Encode-Sqlname cmdlet
- PowerShell [SQL Server], Encode-Sqlname
- Convert-UrnToPath cmdlet
- PowerShell [SQL Server], cmdlets
- Cmdlets [SQL Server]
- PowerShell [SQL Server], Convert-UrnToPath
- Cmdlets [SQL Server], Convert-UrnToPath
- Decode-Sqlname cmdlet
- PowerShell [SQL Server], Decode-Sqlname
- Cmdlets [SQL Server], Decode-Sqlname
ms.assetid: 720aa982-09ae-41a3-b603-a91004cfbe3e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 015500c7c985f9f1a1d190954406844f3b184932
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601043"
---
# <a name="use-the-database-engine-cmdlets"></a><span data-ttu-id="4eae7-102">Utiliser les applets de commande du Moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="4eae7-102">Use the Database Engine cmdlets</span></span>
  <span data-ttu-id="4eae7-103">Les applets de commande Windows PowerShell sont des commandes à fonction unique qui utilisent généralement une convention d’affectation des noms de type « verbe-nom », par exemple **Get-Help** ou **Set-MachineName**.</span><span class="sxs-lookup"><span data-stu-id="4eae7-103">Windows PowerShell cmdlets are single-function commands that typically have a verb-noun naming convention, such as **Get-Help** or **Set-MachineName**.</span></span> <span data-ttu-id="4eae7-104">Le fournisseur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour Windows PowerShell fournit des applets de commande spécifiques à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4eae7-104">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider for Windows PowerShell supplies cmdlets specific to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="database-engine-cmdlets"></a><span data-ttu-id="4eae7-105">Applets de commande du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="4eae7-105">Database Engine cmdlets</span></span>  
 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="4eae7-106">implémente un petit nombre d'applets de commande pour le [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4eae7-106">implements a small number of cmdlets for the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="4eae7-107">Ces applets de commande sont principalement utilisées pour exécuter des scripts Transact-SQL existants à partir de nouveaux scripts PowerShell, pour évaluer les stratégies de gestion basée sur des stratégies et pour aider à spécifier des identificateurs SQL Server dans les chemins d'accès de fournisseur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4eae7-107">These cmdlets are primarily used to run existing Transact-SQL scripts from new PowerShell scripts, evaluate policy-based management policies, and aid in specifying SQL Server identifiers in SQL Server Provider paths.</span></span>  
  
 <span data-ttu-id="4eae7-108">La plupart des scripts Windows PowerShell travaillent avec le [!INCLUDE[ssDE](../includes/ssde-md.md)] en utilisant le fournisseur PowerShell SQL Server et les modèles d'objet de gestion SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4eae7-108">Most Windows PowerShell scripts work with the [!INCLUDE[ssDE](../includes/ssde-md.md)] by using the SQL Server PowerShell provider and the SQL Server manageability object models.</span></span> <span data-ttu-id="4eae7-109">Pour plus d’informations, consultez [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4eae7-109">For more information, see [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="get-cmdlet-help"></a><span data-ttu-id="4eae7-110">Obtenir de l'aide sur les applets de commande</span><span class="sxs-lookup"><span data-stu-id="4eae7-110">Get Cmdlet Help</span></span>  
 <span data-ttu-id="4eae7-111">Dans l’environnement Windows PowerShell, l’applet de commande **Get-Help** fournit des informations d’aide sur chaque applet de commande.</span><span class="sxs-lookup"><span data-stu-id="4eae7-111">In the Windows PowerShell environment, the **Get-Help** cmdlet provides help information for each cmdlet.</span></span> <span data-ttu-id="4eae7-112">L’applet**Get-Help** renvoie des informations telles que la syntaxe, les définitions de paramètres, les types d’entrée et de sortie et une description de l’action réalisée par l’applet de commande.</span><span class="sxs-lookup"><span data-stu-id="4eae7-112">**Get-Help** returns information such as the syntax, parameter definitions, input and output types, and a description of the action performed by the cmdlet.</span></span> <span data-ttu-id="4eae7-113">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../2014/database-engine/get-help-sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4eae7-113">For more information, see [Get Help SQL Server PowerShell](../../2014/database-engine/get-help-sql-server-powershell.md).</span></span>  
  
### <a name="partial-parameter-names"></a><span data-ttu-id="4eae7-114">Noms de paramètres partiels</span><span class="sxs-lookup"><span data-stu-id="4eae7-114">Partial Parameter Names</span></span>  
 <span data-ttu-id="4eae7-115">Il n'est pas nécessaire de spécifier le nom entier d'un paramètre d'applet de commande.</span><span class="sxs-lookup"><span data-stu-id="4eae7-115">You do not have to specify the entire name of a cmdlet parameter.</span></span> <span data-ttu-id="4eae7-116">Il vous suffit de spécifier une partie suffisante du nom pour le distinguer des autres paramètres pris en charge par l'applet de commande.</span><span class="sxs-lookup"><span data-stu-id="4eae7-116">You only have to specify enough of the name to uniquely separate it from the other parameters that are supported by the cmdlet.</span></span> <span data-ttu-id="4eae7-117">Ces exemples montrent trois façons différentes de spécifier le paramètre **Invoke-Sqlcmd -QueryTimeout** :</span><span class="sxs-lookup"><span data-stu-id="4eae7-117">For example, these examples show three ways of specifying the **Invoke-Sqlcmd -QueryTimeout** parameter:</span></span>  
  
```powershell
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryTimeout 3  
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryTime 3  
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryT 3  
```  
  
## <a name="database-engine-cmdlet-tasks"></a><span data-ttu-id="4eae7-118">Tâches d'applet de commande du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="4eae7-118">Database Engine cmdlet Tasks</span></span>  
  
|<span data-ttu-id="4eae7-119">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="4eae7-119">Task Description</span></span>|<span data-ttu-id="4eae7-120">Rubrique</span><span class="sxs-lookup"><span data-stu-id="4eae7-120">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="4eae7-121">Décrit l’utilisation de l’applet de commande **Invoke-Sqlcmd** pour exécuter des scripts **sqlcmd** ou des commandes qui contiennent des instructions XQuery ou [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4eae7-121">Describes using **Invoke-Sqlcmd** to run **sqlcmd** scripts or commands that contain [!INCLUDE[tsql](../includes/tsql-md.md)] or XQuery statements.</span></span> <span data-ttu-id="4eae7-122">Elle peut accepter l’entrée **sqlcmd** sous la forme d’un paramètre d’entrée de chaîne de caractères ou sous la forme du nom d’un fichier de script à ouvrir.</span><span class="sxs-lookup"><span data-stu-id="4eae7-122">It can accept the **sqlcmd** input as either a character string input parameter, or as the name of a script file to open.</span></span>|[<span data-ttu-id="4eae7-123">Invoke-Sqlcmd (applet de commande)</span><span class="sxs-lookup"><span data-stu-id="4eae7-123">Invoke-Sqlcmd cmdlet</span></span>](../../2014/database-engine/invoke-sqlcmd-cmdlet.md)|  
|<span data-ttu-id="4eae7-124">Décrit l’utilisation de l’applet de commande **Invoke-PolicyEvaluation** pour indiquer si un ensemble d’objets [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cible est conforme ou non aux conditions définies dans les stratégies de gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="4eae7-124">Describes using **Invoke-PolicyEvaluation** to report whether a target set of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects comply with the conditions that are defined in policy-based management policies.</span></span> <span data-ttu-id="4eae7-125">Vous pouvez éventuellement utiliser cette applet de commande pour reconfigurer toutes les options définissables dans les objets cibles qui ne sont pas conformes aux conditions des stratégies.</span><span class="sxs-lookup"><span data-stu-id="4eae7-125">Optionally, the cmdlet can be used to reconfigure any settable options in the target objects that do not comply with the policy conditions.</span></span>|[<span data-ttu-id="4eae7-126">Invoke-PolicyEvaluation (applet de commande)</span><span class="sxs-lookup"><span data-stu-id="4eae7-126">Invoke-PolicyEvaluation cmdlet</span></span>](../../2014/database-engine/invoke-policyevaluation-cmdlet.md)|  
|<span data-ttu-id="4eae7-127">Décrit l'utilisation des applets de commande `Encode-Sqlname` et `Decode-Sqlname` pour gérer les identificateurs SQL Server qui contiennent des caractères non pris en charge dans les chemins d'accès Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4eae7-127">Describes using `Encode-Sqlname` and `Decode-Sqlname` to handle SQL Server identifiers that contain characters not supported in Windows PowerShell paths.</span></span>|[<span data-ttu-id="4eae7-128">Encoder et décoder des identificateurs SQL Server</span><span class="sxs-lookup"><span data-stu-id="4eae7-128">Encode and Decode SQL Server Identifiers</span></span>](../powershell/encode-and-decode-sql-server-identifiers.md)|  
|<span data-ttu-id="4eae7-129">Décrit l'utilisation de l'applet de commande `Convert-UrnToPath` pour convertir l'URN (Uniform Resource Locator) d'un objet de gestion de SQL Server dans son équivalent de chemin d'accès au fournisseur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4eae7-129">Describes using `Convert-UrnToPath` to convert a SQL Server Manageability Object Uniform Resource Name (URN) to the equivalent SQL Server Provider path.</span></span>|[<span data-ttu-id="4eae7-130">Convertir des URN en chemins de fournisseur SQL Server</span><span class="sxs-lookup"><span data-stu-id="4eae7-130">Convert URNs to SQL Server Provider Paths</span></span>](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md)|  
  
## <a name="see-also"></a><span data-ttu-id="4eae7-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4eae7-131">See Also</span></span>  
 <span data-ttu-id="4eae7-132">[Fournisseur SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="4eae7-132">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="4eae7-133">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="4eae7-133">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span></span>  
 [<span data-ttu-id="4eae7-134">Vue d’ensemble des applets de commande PowerShell pour groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4eae7-134">Overview of PowerShell Cmdlets for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](availability-groups/windows/overview-of-powershell-cmdlets-for-always-on-availability-groups-sql-server.md)  
  
  
