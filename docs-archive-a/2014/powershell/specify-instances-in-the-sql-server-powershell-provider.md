---
title: Spécifier des instances dans le fournisseur SQL Server PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 9373de68-fd43-45f2-b9a6-149c96610aeb
author: stevestein
ms.author: sstein
ms.openlocfilehash: cc04bacc1ff36b0b5ce526a377fcdb750ad134a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604592"
---
# <a name="specify-instances-in-the-sql-server-powershell-provider"></a><span data-ttu-id="2cbef-102">Spécifier des instances dans le fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cbef-102">Specify Instances in the SQL Server PowerShell Provider</span></span>
  <span data-ttu-id="2cbef-103">Les chemins d'accès spécifiés pour le fournisseur PowerShell SQL Server doivent identifier l'instance du [!INCLUDE[ssDE](../includes/ssde-md.md)] et de l'ordinateur sur lequel elle s'exécute.</span><span class="sxs-lookup"><span data-stu-id="2cbef-103">The paths specified for the SQL Server PowerShell provider must identify the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] and the computer it is running on.</span></span> <span data-ttu-id="2cbef-104">La syntaxe pour spécifier l'ordinateur et l'instance doit être conforme aux règles relatives aux identificateurs SQL Server et aux chemins d'accès Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cbef-104">The syntax for specifying the computer and the instance must comply with both the rules for SQL Server identifiers and Windows PowerShell paths.</span></span>  
  
1.  <span data-ttu-id="2cbef-105">**Avant de commencer :**  [Limitations et restrictions](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="2cbef-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="2cbef-106">**Pour spécifier une instance :**  [Exemples](#Examples)</span><span class="sxs-lookup"><span data-stu-id="2cbef-106">**To specify an instance:**  [Examples](#Examples)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="2cbef-107">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2cbef-107">Before You Begin</span></span>  
 <span data-ttu-id="2cbef-108">Le premier nœud venant après SQLSERVER:\SQL dans un chemin d'accès de fournisseur SQL Server est le nom de l'ordinateur qui exécute l'instance du [!INCLUDE[ssDE](../includes/ssde-md.md)]; par exemple :</span><span class="sxs-lookup"><span data-stu-id="2cbef-108">The first node following the SQLSERVER:\SQL in a SQL Server provider path is the name of the computer that is running the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)]; for example:</span></span>  
  
```  
SQLSERVER:\SQL\MyComputer  
```  
  
 <span data-ttu-id="2cbef-109">Si vous exécutez Windows PowerShell sur le même ordinateur que l'instance du [!INCLUDE[ssDE](../includes/ssde-md.md)], vous pouvez utiliser localhost ou (local) à la place du nom de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2cbef-109">If you are running Windows PowerShell on the same computer as the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], you can use either localhost or (local) instead of the name of the computer.</span></span> <span data-ttu-id="2cbef-110">Les scripts utilisant localhost ou (local) peuvent être exécutés sur n'importe quel ordinateur, sans qu'il soit nécessaire de les modifier pour refléter différents noms d'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2cbef-110">Scripts that use localhost or (local) can be run on any computer without having to be changed to reflect the different computer names.</span></span>  
  
 <span data-ttu-id="2cbef-111">Vous pouvez exécuter plusieurs instances du programme exécutable du [!INCLUDE[ssDE](../includes/ssde-md.md)] sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2cbef-111">You can run multiple instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] executable program on the same computer.</span></span> <span data-ttu-id="2cbef-112">Le nœud venant après le nom de l'ordinateur dans un chemin d'accès de fournisseur SQL Server identifie l'instance ; par exemple :</span><span class="sxs-lookup"><span data-stu-id="2cbef-112">The node following the computer name in a SQL Server provider path identifies the instance; for example:</span></span>  
  
```  
SQLSERVER:\SQL\MyComputer\MyInstance  
```  
  
 <span data-ttu-id="2cbef-113">Chaque ordinateur peut avoir une instance par défaut du [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cbef-113">Each computer can have one default instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="2cbef-114">Vous ne spécifiez pas de nom pour l'instance par défaut lorsque vous l'installez.</span><span class="sxs-lookup"><span data-stu-id="2cbef-114">You do not specify a name for the default instance when you install it.</span></span> <span data-ttu-id="2cbef-115">Si vous spécifiez seulement un nom d'ordinateur dans une chaîne de connexion, vous êtes connecté à l'instance par défaut sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2cbef-115">If you specify only a computer name in a connection string, you are connected to the default instance on that computer.</span></span> <span data-ttu-id="2cbef-116">Toutes les autres instances sur l'ordinateur doivent être des instances nommées.</span><span class="sxs-lookup"><span data-stu-id="2cbef-116">All other instances on the computer must be named instances.</span></span> <span data-ttu-id="2cbef-117">Vous spécifiez le nom de l'instance pendant l'installation, et les chaînes de connexion doivent spécifier à la fois le nom d'ordinateur et le nom de l'instance.</span><span class="sxs-lookup"><span data-stu-id="2cbef-117">You specify the instance name during setup, and connection strings must specify both the computer name and the instance name.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="2cbef-118">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2cbef-118">Limitations and Restrictions</span></span>  
 <span data-ttu-id="2cbef-119">Vous ne pouvez pas utiliser de point (.) pour spécifier l'ordinateur local dans les scripts PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cbef-119">You cannot use a period (.) to specify the local computer in PowerShell scripts.</span></span> <span data-ttu-id="2cbef-120">Le point n'est pas pris en charge car PowerShell l'interprète comme une commande.</span><span class="sxs-lookup"><span data-stu-id="2cbef-120">The period is not supported because the period is interpreted as a command by PowerShell.</span></span>  
  
 <span data-ttu-id="2cbef-121">Les parenthèses contenues dans (local) sont normalement traitées comme des commandes par Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cbef-121">The parenthesis characters in (local) are normally treated as commands by Windows PowerShell.</span></span> <span data-ttu-id="2cbef-122">Vous devez les encoder ou les placer dans une séquence d'échappement pour une utilisation dans un chemin d'accès, ou mettre le chemin d'accès entre guillemets doubles.</span><span class="sxs-lookup"><span data-stu-id="2cbef-122">You must either encode them or escape them for use in a path, or enclose the path in double-quotation marks.</span></span> <span data-ttu-id="2cbef-123">Pour plus d'informations, consultez Encoder et décoder des identificateurs SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2cbef-123">For more information, see Encode and Decode SQL Server Identifiers.</span></span>  
  
 <span data-ttu-id="2cbef-124">Le fournisseur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requiert que vous spécifiiez toujours un nom d'instance.</span><span class="sxs-lookup"><span data-stu-id="2cbef-124">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider requires that you always specify an instance name.</span></span> <span data-ttu-id="2cbef-125">Pour les instances par défaut, vous devez spécifier le nom de l'instance DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="2cbef-125">For default instances, you must specify an instance name of DEFAULT.</span></span>  
  
##  <a name="examples-computer-and-instance-names"></a><a name="Examples"></a> <span data-ttu-id="2cbef-126">Exemples : noms d'ordinateur et d'instance</span><span class="sxs-lookup"><span data-stu-id="2cbef-126">Examples; Computer and Instance Names</span></span>  
 <span data-ttu-id="2cbef-127">Cet exemple utilise localhost et DEFAULT pour spécifier l'instance par défaut sur l'ordinateur local :</span><span class="sxs-lookup"><span data-stu-id="2cbef-127">This example uses localhost and DEFAULT to specify the default instance on the local computer:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT
```  
  
 <span data-ttu-id="2cbef-128">Les parenthèses contenues dans (local) sont normalement traitées comme des commandes par Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cbef-128">The parenthesis characters in (local) are normally treated as commands by Windows PowerShell.</span></span> <span data-ttu-id="2cbef-129">Vous devez effectuer l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2cbef-129">You must either:</span></span>  
  
-   <span data-ttu-id="2cbef-130">Mettre la chaîne de chemin d'accès entre guillemets :</span><span class="sxs-lookup"><span data-stu-id="2cbef-130">Enclose the path string in quotes:</span></span>  
  
    ```powershell
    Set-Location "SQLSERVER:\SQL\(local)\DEFAULT"  
    ```  
  
-   <span data-ttu-id="2cbef-131">Placer la parenthèse dans une séquence d'échappement à l'aide du caractère « \` » (backtick) :</span><span class="sxs-lookup"><span data-stu-id="2cbef-131">Escape the parenthesis using the back tick character (\`):</span></span>  
  
    ```powershell
    Set-Location SQLSERVER:\SQL\`(local`)\DEFAULT  
    ```  
  
-   <span data-ttu-id="2cbef-132">Encoder la parenthèse à l'aide de sa représentation hexadécimale :</span><span class="sxs-lookup"><span data-stu-id="2cbef-132">Encode the parenthesis using their hexadecimal representation:</span></span>  
  
    ```powershell
    Set-Location SQLSERVER:\SQL\%28local%29\DEFAULT  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2cbef-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2cbef-133">See Also</span></span>  
 <span data-ttu-id="2cbef-134">[Identificateurs de SQL Server dans PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="2cbef-134">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="2cbef-135">[Fournisseur SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="2cbef-135">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="2cbef-136">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cbef-136">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
